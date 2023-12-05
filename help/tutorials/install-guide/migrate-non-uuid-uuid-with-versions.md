---
title: Konvertera icke-UID-innehåll med versioner till UUID-innehåll
description: Lär dig hur du migrerar icke-UID-innehåll med versioner.
source-git-commit: 880cd344ceb65ea339be699ebcad41c0d62e168a
workflow-type: tm+mt
source-wordcount: '1287'
ht-degree: 0%

---

# Migrera icke-UID-innehåll med versioner

Utför dessa steg för att migrera icke-UID-innehåll med versioner till UUID-innehåll.

## Kompatibilitetsmatris

| Aktuell version AEM stödlinjer (ej UUID) | Version som krävs för att migrera till UUID | Uppgraderingssökväg som stöds |
|---|---|---|
| 3.8.5 | 4.0 ej UUID | Installera 4.1 (UUID) och kör migreringen |
| 4.0, 4.0.x, 4.1 eller 4.1.x | Samma som aktuellt icke-UUID | Installera 4.1 (UUID) och kör migreringen |
| 4.2 eller högre | NA | Stöds inte ännu |

## Obligatoriska paket

1. **Rensa version**: `com.adobe.guides.version-purge-1.0.11.zip` (valfritt)
1. **Före migrering**: `com.adobe.guides.pre-uuid-migration-1.0.7.zip`
1. **Migrering**: `com.adobe.guides.uuid-upgrade-1.0.17`
1. **Efter migrering**: `com.adobe.guides.post-uuid-migration-1.0.2.zip`


## Före migrering

1. (Valfritt) Rensa innehållet i version för att ta bort onödiga versioner och snabba upp migreringsprocessen. Installera paketet om du vill rensa version på version 4.1 (stöds INTE på 4.0) `com.adobe.guides.version-purge-1.0.11.zip`och gå till användargränssnittet med denna URL `http://<server-name> /libs/fmdita/clientlibs/xmleditor_version_purge/page.html`.

   >[!NOTE]
   >
   >Verktyget tar inte bort versioner som används i baslinjer eller granskningar och har inga etiketter.
1. Installera paketet före migrering (`com.adobe.guides.pre-uuid-migration-1.0.7.zip`).

1. Kör följande fråga nedan för att få en rapport med en beräknad tid (ETA) för hur lång migreringen kommer att ta och den rapporterar om det finns filer med innehållsproblem som inte skulle migreras.

>[!NOTE]
>
>Du måste ha administratörsbehörighet för att kunna utföra migreringen.


| URL för slutpunkt | Typ av begäran | Frågeparameter | Förväntade resultat |
|---|---|---|---|
| `/bin/guides/pre_uuid_upgrade` <br> <br>**Till exempel**: http://localhost:4502/bin/guides/pre_uuid_upgrade?root=/content/dam | GET | **root**: Rotmapp<br> **Värde**: `/content/dam` för hela databasen. | En rapport före migreringen (.csv) skapas med en lista över antalet filer, totalt antal versioner och felen. <br><br> **Exempelutdata**:<br>RootFolder: /content/dam <br>Totalt antal filer: 2697 <br>Totalt antal versioner: 10380 <br>Antal filer med fel: 28 <br>En detaljerad rapport kommer AEM CRX på `/content/uuid-pgrade/UuidMigrationReport_1688400131039.csv` |

Det här steget kan misslyckas om det finns många DITA-filer i systemet. Du kan åtgärda detta genom att öka gränsen för antalet filer som gås igenom i frågan genom att öka värdet för *Minnets läsgräns (queryLimitReads)* i inställningstjänsten för Apache Jackrabbit Query Engine från 100000 ett tal som är större än det totala antalet DITA-resurser som finns i systemet.

## Migrering

### Steg 1: Uppdatera konfigurationen

1. Se till att det lediga utrymmet är minst 10 gånger så stort som det utrymme som AEM (crx-quickstart directory) tar under migreringen. När du är klar med migreringen kan du återvinna det mesta av diskutrymmet genom att köra en komprimering (se [Revision Cleanup](https://experienceleague.adobe.com/docs/experience-manager-65/deploying/deploying/revision-cleanup.html?lang=en)).

1. Aktivera *Aktivera startprogram för arbetsflöde efter bearbetning* in `com.adobe.fmdita.config.ConfigManager` och *Aktivera efterbearbetning av version* in `com.adobe.fmdita.postprocess.version.PostProcessVersionObservation.`

1. Installera UUID-versionen av den version som stöds över den version som inte är UUID. Om du till exempel använder en 4.0-version som inte är UUID eller en 4.1-version som inte är UID måste du installera UUID version 4.1.

1. Installera det nya paketet för uuid-migrering (`com.adobe.guides.uuid-upgrade-1.0.17`).

1. Inaktivera följande arbetsflöden och andra arbetsflöden som körs på `/content/dam` använda starter i `http://localhost:4502/libs/cq/workflow/content/console.html`.

   * Arbetsflöde för DAM-uppdatering
   * Arbetsflöde för DAM-metadataåterställning

1. Inaktivera *Aktivera startprogram för arbetsflöde efter bearbetning* in `com.adobe.fmdita.config.ConfigManager` och inaktivera *Aktivera efterbearbetning av version* in `com.adobe.fmdita.postprocess.version.PostProcessVersionObservation`.

1. Inaktivera egenskapen Aktivera validering (`validation.enabled`) in Day CQ Tagging Service.

1. Se till att `uuid.regex` egenskapsmappen är korrekt inställd i `com.adobe.fmdita.config.ConfigManager`. Om det är tomt anger du standardvärdet - `^GUID-(?<id>.*)`.
1. Lägg till en separat loggare för `com.adobe.fmdita.uuid.upgrade.UuidUpgrade` Webbläsarsvaret finns också på `/content/uuid-upgrade/logs`.

### Steg 2: Kör skriptet och validera

Kör den angivna frågan på en mapp med mindre data innan den körs `/content/dam`.

>[!TIP]
>
>Du kan kontrollera om alla filer i mappen är korrekt uppgraderade och om alla funktioner bara fungerar för den mappen.

| URL för slutpunkt | Typ av begäran | Frågeparameter | Förväntade resultat |
|---|---|---|---|
| `/bin/guides/uuid_upgrade`<br><br> **Till exempel**: `http://localhost:4502/bin/guides/uuid_upgrade?root=/content/dam/test` | GET | **root**: Rotmapp <br>**Värde**: /content/dam för hela databasen.<br><br>**ignoreImageVersions**<br> **Värde**: true/false (ignorerar bearbetning av bildversioner. Standardvärdet är false) | Migreringsrapporten med listan över filer har migrerats, det gick inte att uppgradera, uppgraderats med fel och den totala tiden har tagits. <br><br> **Exempelutdata**: <br> [INFORMATION] Lista över filer som misslyckades:0 <br>[INFORMATION] Nej. av filer som uppgraderats: 2241 <br>[INFORMATION] Nej. av filer som uppgraderats med fel: 28 <br>[INFORMATION] Nej. av filerna kunde inte uppgraderas: 0 <br> [INFORMATION] Total tid tagen: 0:37:03.131 |

>[!NOTE]
>
> Innehållsmigreringen kan köras på mappnivå eller på hela `/content/dam` eller i samma mapp (kör migreringen igen).

Dessutom är det viktigt att se till att innehållsmigreringen också görs för alla medieresurser, till exempel bilder och grafik som du har använt i DITA-innehållet.

#### Migrering av baslinje

Kör frågan på mappen som du redan har migrerat för att migrera baslinjerna på den.

| URL för slutpunkt | Typ av begäran | Frågeparameter | Förväntade resultat |
|---|---|---|---|
| `/bin/guides/baseline_uuid_upgrade`<br><br> **Till exempel**: ` http://localhost:4502/bin/guides/baseline_uuid_upgrade?root=/content/dam/test` | GET | **root**: Rotmapp <br> **Värde**: /content/dam för hela databasen. <br><br> **ignoreImageVersions**<br> **Värde**: true/false <br>(Ignorerar bearbetning av bildversioner. Standardvärdet är false) <br><br> **doReviews** <br> **Värde**: true/false <br> (Om granskningarna måste uppgraderas eller inte. Standardvärdet är false.) Migreringsrapporten med listan över filer har migrerats, det gick inte att uppgradera, uppgraderats med fel och den totala tiden har tagits. <br> <br> **Exempelutdata**:<br>[INFORMATION] Lista över filer misslyckades <br> [INFORMATION] Nej. av filer som uppgraderats 2241<br> [INFORMATION] Nej. av filer som uppgraderats med fel 28<br>[INFORMATION] Nej. av filerna kunde inte uppgradera 0<br>[INFORMATION] Total tid tagen: 0:37:03.131 |


### Steg 3: Återställ konfigurationen

När servern har migrerats kan du aktivera efterbearbetning, taggning och följande arbetsflöden (inklusive alla andra arbetsflöden som inaktiveras från början under migreringen) för att fortsätta arbeta på servern.

* Arbetsflöde för DAM-uppdatering
* Arbetsflöde för DAM-metadata

>[!NOTE]
>
>Om vissa filer inte bearbetas eller är skadade före migreringen kommer de att skadas före migreringen och förbli skadade även efter migreringen.

## Migreringsvalidering

1. Installera migreringspaketet efter uid (`com.adobe.guides.post-uuid-migration-1.0.2.zip`).

1. Kör följande fråga för att verifiera att det inte uppstod några fel under migreringen som gjorde att länkar bryts. Skriptet identifierar om det finns länkar som inte har brutits tidigare men som har brutits av någon anledning.

   | URL för slutpunkt | Typ av begäran | Frågeparameter | Förväntade resultat |
   |---|---|---|---|
   | `/bin/guides/get_broken_links` <br> <br> **Till exempel**:<br>`http://localhost:4502/bin/guides/get_broken_links` | GET | NA | Migreringsrapport med det totala antalet filer med trasiga UID:n och deras respektive filsökvägar. <br> <br> **Exempelutdata**:<br>[FELSÖKNING] Kontrollerar om alla dessa GUID används i innehållet.<br>[FELSÖKNING] Totalt antal filer som kan ha trasiga UUID:n: 0 <br>[FELSÖKNING] Banor som eventuellt har trasiga UUID:0 |

1. När migreringen är klar kan större delen av diskutrymmet återvinnas genom att köra en komprimering (se `https://experienceleague.adobe.com/docs/experience-manager-65/deploying/deploying/revision-cleanup.html?lang=en`).

## Migrera Delta innehåll

1. Om du vill migrera deltainnehållet från den aktiva servern (icke-UID) till den aktuella UUID-servern installerar du förmigreringsskriptet på den icke-UID-servern.

1. Kör följande fråga på hela datauppsättningen (eller undermappen) för att identifiera och exportera alla filer som ändrats efter den angivna tidsstämpeln: Tidsstämpeln använder ISO8601-formatet för datum och tider ( YYYY-MM-DDTHH:mm:ss.SSSZ) och tillåter även partiella representationer, som YYYY-MM-DD.

   | URL för slutpunkt | Typ av begäran | Frågeparameter | Förväntade resultat |
   |---|---|---|---|
   | `/bin/guides/data_export`<br><br>**Till exempel**: <br> `http://localhost:4502/bin/guides/data_export?timestamp=2023-07-11&root=/content/dam` | GET | **tidsstämpel** <br> **Värde**: ÅÅÅ-MM-DD<br><br> **root**: Rotmapp <br> **Värde**: `/content/dam` för hela databasen. | En ZIP-fil med delta-innehåll skapas på /var/dxml/exporting. <br> <br>**Exempel**: dataexport_1689761491218.zip (filen skapas) |

1. Ladda ned zip-filen som exporteras av skriptet. Den sista raden i svaret bör ge sökvägen till den genererade zip-filen (som lagras i /var/dxml/exporting in the system).

1. Ladda upp zip-filen till uid-servern på önskad sökväg i Assets UI.

1. Kontrollera att paketet efter migreringen är installerat på uuid-servern.

1. Kör följande fråga för att importera deltainnehållet från den överförda ZIP-filen till systemet. Frågan bör innehålla sökvägen till den överförda ZIP-filen för att kunna identifiera och bearbeta data.

   | URL för slutpunkt | Typ av begäran | Frågeparameter | Förväntade resultat |
   |---|---|---|---|
   | `/bin/guides/data_import`<br> **Till exempel**:`http://localhost:4502/bin/guides/data_import?path=/content/dam/dataexport_1689344927551.zip&createVersion=true` | POST | **bana**<br> **Värde**: `/content/dam/filename.zip`(Plats för överförd fil) **createVersion** <br> **Värde**: true/false<br>(Standardvärdet för createVersion är false). | Filen överförs till den önskade innehållssökvägen.<br><br>**Exempel**: `dataexport_1689761491218.zip`<br><br> (Samma fil som exporterades i föregående steg överförs till den önskade sökvägen i `/content/dam`). |

1. Skriptet skapar en ny fil om den inte finns eller åsidosätter den befintliga filen om den ändrats.

>[!NOTE]
>
> Versionshistoriken och andra ändringar som görs på servern (som arbetsflöden och granskningar) måste uppdateras manuellt.
