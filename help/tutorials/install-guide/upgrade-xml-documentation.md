---
title: Uppgradera Adobe Experience Manager-guider
description: Lär dig hur du uppgraderar Adobe Experience Manager-guider
exl-id: fdc395cf-a54f-4eca-b69f-52ef08d84a6e
source-git-commit: a00484a6e0a900a568ae1f651e96dca31add1bd8
workflow-type: tm+mt
source-wordcount: '2750'
ht-degree: 0%

---

# Uppgradera Adobe Experience Manager-guider {#id224MBE0M0XA}

>[!NOTE]
>
> Följ uppgraderingsinstruktionerna som är specifika för den licensierade versionen av din produkt.

Du kan uppgradera din nuvarande version av AEM Guides till version 4.2.1
- Om du använder version 4.1, 4.1.x eller 4.2 kan du uppgradera direkt till version 4.2.1.
- Om du använder version 4.0 måste du uppgradera till version 4.2 innan du uppgraderar till version 4.2.1.
- Om du använder version 3.8.5 måste du uppgradera till version 4.0 innan du uppgraderar till version 4.2.
- Om du har en version som är äldre än 3.8.5, se avsnittet om AEM i den produktspecifika installationshandboken.

>[!NOTE]
>
> Du måste installera AEM Service Pack innan du uppgraderar AEM Guides version.

Mer information finns i följande procedurer:

- [Uppgradera från 3.8.5 till version 4.0](#id2256DK003E1)
- [Uppgradera till version 4.2](#id22A3F500SXA)
- [Uppgradera till version 4.2.1](#upgrade-version-4-2-1)


>[!IMPORTANT]
>
> Innan du börjar uppgradera bör du göra en fullständig säkerhetskopiering av systemet för att undvika dataförluster.

## Uppgradera från version 3.8.5 till version 4.0 {#id2256DK003E1}

Om du använder AEM Guides version 3.8.5 kan du uppgradera till version 4.0 av AEM Guides. Med uppgraderingsfunktionen behöver du inte avinstallera den tidigare versionen av AEM.

Innan du kör processen måste du slutföra vissa uppgifter. I följande delavsnitt får du hjälp att igenom förutsättningarna, skapa rapporter och migreringsprocessen. När du har installerat AEM Guides version 4.0 kan du anpassa olika konfigurationer enligt kundinställningarna.

>[!NOTE]
>
> Denna uppgraderingsprocess gäller endast från version 3.8.5 till version 4.0. För processen att uppgradera från version 3.4 eller senare till 3.8.5, se *AEM* i den produktspecifika installationsguiden som finns i [Hjälparkivsida](https://helpx.adobe.com/xml-documentation-for-experience-manager/archive.html).

****Förutsättningar****

Innan du startar uppgraderingen av AEM Guides bör du kontrollera att du har:

1. Granskningskommentarerna i ämnen som är öppna för granskning har importerats.
1. Alla aktiva granskningar stängdes.
1. Alla översättningsuppgifter stängdes.
1. Avinstallera eventuella snabbkorrigeringar AEM Guides som installerats högst upp i den tidigare versionen \(huvud- eller patch-version\) av AEM Guides.

**Innan du installerar version 4.0**

Utför följande steg innan du installerar version 4.0:

1. Se till att AEM är i version 3.8.5.
1. Hämta uppgraderingsskriptpaketet. Om du vill göra det söker du efter&quot;XML Documentation solution 4.0 Upgrade Package&quot; på [Adobe Software Distribution Portal](https://experience.adobe.com/#/downloads/content/software-distribution/en/aem.html) som laddar ned en zip-fil.
1. Överför det här paketet till AEM via Package Manager och installera det här paketet.
1. När uppgraderingspaketet har installerats kör du skripten nedan i samma ordning och följer instruktionerna:

**Kontrollera API för uppgraderingskompatibilitet**

Detta API är utformat för att utvärdera den aktuella systemstatusen och rapportera om uppgraderingen är möjlig eller inte. Om du vill köra det här skriptet utlöser du slutpunkten nedan:

| Slutpunkt | /bin/dxml/upgrade/3xto4x/report |
| --- | --- |
| Typ av begäran | **GET** Du kan använda en webbläsare, där du är inloggad som administratör för AEM. |
| Förväntat svar | - Om alla nödvändiga noder kan flyttas får du en kontroll som du godkänt. <br>- Om det finns en nod på målplatsen får du ett relevant fel. Rensa databasen \(delete node /var/dxml\) och installera om uppgraderingspaketet och utlösa sedan den här slutpunkten igen. <br>**Obs!** Detta är inget vanligt fel eftersom målplatsen inte används tidigare av 3.x AEM Guides. <br> - Om det här manuset inte lyckas ska du inte fortsätta och rapportera till ditt kundframgångsteam. |

**API för systemdatamigrering**

Detta API är utformat för att migrera systemdata enligt anvisningarna i **Migreringsmappning** -avsnitt.

1. Kör inte det här skriptet om API:t för Kontrollera uppgraderingskompatibilitet misslyckas \(fortsätt inte\).
1. När API:t för kontroll av uppgraderingskompatibilitet returneras kan du köra uppgraderingsskriptet.

| Slutpunkt | /bin/dxml/upgrade/3xto4x |
| --- | --- |
| Typ av begäran | **POST** Skriptet är en begäran om POST och ska därför köras via agenter som Postman. |
| Förväntat svar | - När migreringen är klar kan du installera XML Documentation-lösning version 4.0.<br>- Om fel uppstår återställer du till den senaste kontrollpunkten och delar felloggarna med API-utdata till kundens framgångsgrupp. |

**Migreringsmappning**: API:t ovan migrerar alla data under källplatsen till målplatsen.

| Källa | Mål |
|------|------|
| /content/fmdita | /var/dxml |
| /content/dxml | /var/dxml |
| /etc/fmdita | /libs/fmdita |

## Installera version 4.0 {#id23598G006XA}

1. Installera endast version 4.0 om uppgraderingsstegen lyckades.
1. Ladda ned 4.0-versionspaket från [Adobe Software Distribution Portal](https://experience.adobe.com/#/downloads/content/software-distribution/en/aem.html):

   - Om du använder en UUID-version av programvara söker du efter&quot;4.0 UID Release for XML Documentation solution for AEM 6.5&quot;.
   - Om du använder en icke-UID-version av programvara söker du efter&quot;4.0 Non-UUID Release for XML Documentation solution for AEM 6.5&quot;.
Överför paketet till den befintliga AEM med CRX Package Manager och installera det.

   >[!NOTE]
   >
   > Vänta tills alla systemkomponenter har startats.

1. Rensa webbläsarcachen när paketet har installerats.
1. Utför följande steg om en dispatcher har konfigurerats på AEM Author-instansen:
   - Kontrollera att följande hanteras i dispatcherregler:
   - URL-mönstret /home/users/\*/preferences är vitlistat.
   - URL-mönstret /libs/cq/security/userinfo.json är inte cachelagrat.
1. Rensa dispatchercache \(för att rensa alla `clientlibs` cache-lagrad\).

## Uppgradera till version 4.2 {#id22A3F500SXA}

Uppgradering till version 4.2 beror på den aktuella versionen av AEM.

Om du använder version 4.0, 4.1 eller 4.1.x kan du uppgradera direkt till version 4.2.

****Förutsättningar****

Innan du startar uppgraderingsprocessen för AEM Guides 4.2 måste du se till att du har:

1. Uppgraderat till AEM Guides version 4.0, 4.1 eller 4.1.x.
1. Alla översättningsuppgifter stängdes.
1. Loggnivån har ändrats till **INFORMATION** for `com.adobe.fmdita.translationservices.TranslationMapUpgradeScript` och lägga till loggarna i en ny loggfil, till exempel `logs/translation_upgrade.log.`

>[!NOTE]
>
> Du bör stänga alla aktiva granskningar. Om granskningsuppgifterna inte stängs när du uppgraderar till 4.2 fortsätter de äldre pågående granskningsuppgifterna att ta användare på de äldre granskningssidorna, och de granskningsuppgifter som skapas efter uppgraderingen visar de senaste uppdateringarna i funktionen.

## Installera version 4.2 {#id2245IK0E0EV}

1. Ladda ned versionspaket 4.2 från [Adobe Software Distribution Portal](https://experience.adobe.com/#/downloads/content/software-distribution/en/aem.html).
1. Installera paket för version 4.2.
1. När du har slutfört paketinstallationen väntar du på följande meddelanden i loggarna:

   `Completed the post deployment setup script`

   Ovanstående meddelande anger att alla installationssteg är slutförda.

   Om du råkar ut för något av följande felkorrigeringar ska du rapportera dem till ditt kundteam:

   - Fel i installationsskript efter distribution
   - Undantag vid portering av översättnings-MAP
   - Det går inte att portera översättningskarta från v1 till v2 för egenskap
1. Uppgradera plugin-programmet för syreanslutning som släppts med version 4.2 \(vid behov\).
1. Rensa webbläsarcachen när paketet har installerats.
1. Fortsätt uppgradera anpassningarna enligt anvisningarna i nästa avsnitt.

## När du har installerat version 4.2 {#id2326F02004K}

>[!IMPORTANT]
>
> Hi-tech-mallar visas inte på uppgraderad server. Om du vill inkludera hi-tech-mallen på servern kan du kopiera den: Källa: /libs/fmdita/pdf/Hi-Tech Destination: /content/dam/dita-templates/pdf

När du har installerat AEM Guides kan du sammanfoga de olika konfigurationer som är tillämpliga från den nyinstallerade versionen till din installation.

>[!NOTE]
>
> Modellen för dam-update-asset kan anpassas. Om några anpassningar har gjorts måste vi synkronisera anpassningarna och AEM i arbetskopian av modellen.

1. **DAM Update Asset workflow \(Efterbehandlingsändringar\):**

1. Öppna URL:

   ```http
   http://localhost:4502/libs/cq/workflow/admin/console/content/models.html
   ```

1. Välj **Arbetsflöde för DAM-uppdatering**.
1. Klicka på **Redigera**.
1. Om **DXML Post Process Initiator** kontrollerar du att anpassningarna är synkroniserade.
1. Om **DXML Post Process Initiator** om komponenten inte finns utför du följande steg för att infoga den:

1. Klicka **Infoga komponent** \(Ansvarig för AEM Guides-efterbearbetning är det sista steget i processen\).
1. Konfigurera **Processsteg** med information nedan:

   **Fliken Allmänt**

   **Titel:** DXML Post Process Initiator

   **Beskrivning**: Initieringssteg för DXML-efterbearbetning av den ändrade/skapade resursen som kommer att utlösa ett snedjobb för DXML-efterbearbetning

   **Fliken Process**

   - Välj **DXML Post Process Initiator** från **Process** nedrullningsbar listruta

   - Välj **Avancerad hanterare**

   - Välj **Klar**

1. Klicka **Synkronisera** överst till höger när du är klar med ändringarna. Du får ett meddelande om att åtgärden lyckades.

   >[!NOTE]
   >
   > Uppdatera och verifiera att anpassade ändringar och AEM guidas efterbearbetningssteg finns i den slutliga arbetsflödesmodellen.

1. En gång **Arbetsflöde för DAM-uppdatering** valideras, kontrollera motsvarande startkonfigurationer. Gå till AEM Workflow interface och öppna startkartor.

   ```http
   http://localhost:4502/libs/cq/workflow/content/console.html
   ```

   Sök efter och ändra \(om det behövs\) till följande två startprogram \(som ska vara aktiva\) som motsvarar **Arbetsflöde för DAM-uppdatering**:

1. Startprogram för &quot;*Noden har skapats*&quot; for **Arbetsflöde för DAM-uppdatering**- för villkor `"jcr:content/jcr:mimeType!=video"`ska värdet Globbing vara:

   ```json
   /content/dam(/((?!/subassets|/translation_output).)*/)renditions/original
   ```

   - excludeList ska ha `"event-user-data:changedByWorkflowProcess"`.
   - Startprogram för &quot;*Noden ändrad*&quot; for **Arbetsflöde för DAM-uppdatering -** for condition &quot;`jcr:content/jcr:mimeType!=video`&quot;,
   - Globbing-värdet ska vara:

   ```json
   /content/dam(/((?!/subassets|/translation_output).)*/)renditions/original
   ```

   - excludeList ska ha `"event-user-data:changedByWorkflowProcess"`.
1. När uppgraderingen är klar kontrollerar du att alla anpassningar/övertäckningar har validerats och uppdaterats så att de matchar den nya programkoden. Nedan ges några exempel:
   - Alla komponenter som överlappas av/libs/fmditor/libsska jämföras med den nya produktkoden och uppdateringar ska göras i överlagrade filer under/i appar.
   - Alla kategorier av klientlib som används från produkten bör granskas för ändringar. Alla åsidosatta konfigurationer \(exempel nedan\) bör jämföras med de senaste för att få de senaste funktionerna:
   - elementmapping.xml
   - ui\_config.json\(kan ha angetts i mappprofiler\)
   - ändrad `com.adobe.fmdita.config.ConfigManager`
   - Kontrollera om någon av de anpassade koderna använder några gamla sökvägar \(som anges i [Migreringsmappning](#id2244LE040XA) ) - ska uppdateras till de nya sökvägarna så att anpassningarna också fungerar som förväntat.
1. Läs om nya konfigurationer i den aktuella versionen \(kontrollera [Versionsinformation](../release-info/release-notes-4.2.md)\) och se om någon funktion påverkas genom att vidta lämpliga åtgärder. Ett exempel kan vara att använda&quot;Förbättrad fil- och versionshantering&quot; som introducerades i version 4.0, som du måste aktivera en konfiguration för.

## Steg för att indexera befintligt innehåll så att det använder den nya funktionen för att söka och ersätta:

Utför följande steg för att indexera det befintliga innehållet och använd den nya sök- och ersätt-texten på mappningsnivå:

- Kör en POST till servern \(med korrekt autentisering\) - `http://<server:port\>/bin/guides/map-find/indexing`. \(Valfritt: Du kan skicka specifika sökvägar för kartorna för indexering, som standard indexeras alla kartor \|\| Exempel: `https://<Server:port\>/bin/guides/map-find/indexing?paths=<map\_path\_in\_repository\>`\)

- API:t returnerar ett jobId. Om du vill kontrollera jobbets status kan du skicka en GET-förfrågan med jobb-ID till samma slutpunkt - `http://<server:port\>/bin/guides/map-find/indexing?jobId=\{jobId\}`\(Exempel: `http://localhost:8080/bin/guides/map-find/indexing?jobId=2022/9/15/7/27/7dfa1271-981e-4617-b5a4-c18379f11c42`\)

- När jobbet är klart kommer ovanstående GET-förfrågan att svara och ange om några kartor misslyckades. De korrekt indexerade mappningarna kan bekräftas från serverloggarna.

## Uppgradera till version 4.2.1 {#upgrade-version-4-2-1}

Uppgradering till version 4.2.1 beror på den aktuella versionen av AEM.

Om du använder version 4.1, 4.1.x eller 4.2 kan du uppgradera direkt till version 4.2.1.

>[!NOTE]
>
>Efterbearbetning och indexering kan ta några timmar. Vi rekommenderar att du startar uppgraderingsprocessen under lågtider.

****Förutsättningar****

Innan du startar uppgraderingsprocessen för AEM Guides 4.2.1 måste du se till att du har:

1. Uppgraderat till AEM Guides version 4.1, 4.1.x eller 4.2.
1. Alla översättningsuppgifter stängdes.
1. Loggnivån har ändrats till **INFORMATION** for `com.adobe.fmdita.translationservices.TranslationMapUpgradeScript` och lägga till loggarna i en ny loggfil, till exempel `logs/translation_upgrade.log.`

>[!NOTE]
>
> Du bör stänga alla aktiva granskningar. Om granskningsuppgifterna inte stängs när du uppgraderar till 4.2 fortsätter de äldre pågående granskningsuppgifterna att ta användare på de äldre granskningssidorna, och de granskningsuppgifter som skapas efter uppgraderingen visar de senaste uppdateringarna i funktionen.

## Installera version 4.2.1

1. Hämta versionspaket 4.2.1 från [Adobe Software Distribution Portal](https://experience.adobe.com/#/downloads/content/software-distribution/en/aem.html).
1. Installera paket för version 4.2.1.
1. Du kan välja att HIT-aktivera utlösaren för att starta uppgraderingsjobbet för översättningskartan. Mer information finns i [Aktivera utlösare för skript via en serverenhet](#enable-trigger-serverlet).


1. När du har slutfört paketinstallationen väntar du på följande meddelanden i loggarna:

   `Completed the post deployment setup script`

   Ovanstående meddelande anger att alla installationssteg är slutförda.

   Om du råkar ut för något av följande felkorrigeringar ska du rapportera dem till ditt kundteam:

   - Fel i installationsskript efter distribution
   - Undantag vid portering av översättnings-MAP
   - Det går inte att portera översättningskarta från v1 till v2 för egenskap
1. Uppgradera plugin-programmet för syreanslutning som släppts med version 4.2 \(vid behov\).
1. Rensa webbläsarcachen när paketet har installerats.
1. Fortsätt uppgradera anpassningarna enligt anvisningarna i nästa avsnitt.

### Aktivera utlösare för skript via en serverenhet{#enable-trigger-serverlet}

POST:

```
http://localhost:4503/bin/guides/script/start?jobType=translation-map-upgrade
```

Svar:

```
{
"msg": "Job is successfully submitted and lock node is created for future reference",
"lockNodePath": "/var/dxml/executor-locks/translation-map-upgrade/1683190032886",
"status": "SCHEDULED"
}
```

I svaret ovan, JSON, är nyckeln `lockNodePath` innehåller sökvägen till den nod som skapas i databasen som pekar på det skickade jobbet. Den tas automatiskt bort när jobbet är klart, tills dess kan du referera till den här noden för aktuell status för jobbet.

Exempellogg: Här följer ett exempel på loggar som visas i loggfilen när du har utlöst skriptet.

```
04.05.2023 14:17:12.876 *INFO* [[0:0:0:0:0:0:0:1] [1683190032736] POST /bin/guides/script/start HTTP/1.1] com.adobe.dxml.common.executor.RunnableSynchronizedOTS Acquiring lock for job : translation-map-upgrade
04.05.2023 14:17:12.897 *INFO* [pool-59-thread-1] com.adobe.fmdita.xmltranslation.ots.TranslationMapUpgradeOTS Starting the thread to upgrade translation map from V1 to V2
04.05.2023 14:17:12.899 *INFO* [pool-59-thread-1] com.adobe.dxml.common.executor.RunnableSynchronizedOTS Initiating lock for node : /var/dxml/executor-locks/translation-map-upgrade/1683190032886
04.05.2023 14:17:12.901 *INFO* [pool-59-thread-1] com.adobe.fmdita.translationservices.TranslationMapUpgradeScript Starting porting of translation map from V1 to V2
04.05.2023 14:17:12.904 *INFO* [pool-59-thread-1] com.adobe.fmdita.translationservices.TranslationMapUpgradeScript Memory increase is of : 764 kB
04.05.2023 14:17:12.906 *INFO* [pool-59-thread-1] com.adobe.fmdita.translationservices.TranslationMapUpgradeScript Completed porting of translation map from V1 to V2
04.05.2023 14:17:12.907 *INFO* [pool-59-thread-1] com.adobe.dxml.common.executor.RunnableSynchronizedOTS Releasing lock for node : /var/dxml/executor-locks/translation-map-upgrade/1683190032886
04.05.2023 14:17:12.909 *INFO* [pool-59-thread-1] com.adobe.fmdita.xmltranslation.ots.TranslationMapUpgradeOTS Completed the thread to upgrade translation map from V1 to V2
```

Sök efter `com.adobe.fmdita.translationservices.TranslationMapUpgradeScript Completed porting of translation map from V1 to V2` och `com.adobe.fmdita.xmltranslation.ots.TranslationMapUpgradeOTS Completed the thread to upgrade translation map from V1 to V2` innan du fortsätter till nästa steg.



## När du har installerat version 4.2.1

>[!IMPORTANT]
>
> Hi-tech-mallar visas inte på uppgraderad server. Om du vill inkludera hi-tech-mallen på servern kan du kopiera den: Källa: /libs/fmdita/pdf/Hi-Tech Destination: /content/dam/dita-templates/pdf

När du har installerat AEM Guides kan du sammanfoga de olika konfigurationer som är tillämpliga från den nyinstallerade versionen till din installation.

>[!NOTE]
>
> Modellen för dam-update-asset kan anpassas. Om några anpassningar har gjorts måste vi synkronisera anpassningarna och AEM i arbetskopian av modellen.

1. **DAM Update Asset workflow \(Efterbehandlingsändringar\):**

1. Öppna URL:

   ```http
   http://localhost:4502/libs/cq/workflow/admin/console/content/models.html
   ```

1. Välj **Arbetsflöde för DAM-uppdatering**.
1. Klicka på **Redigera**.
1. Om **DXML Post Process Initiator** kontrollerar du att anpassningarna är synkroniserade.
1. Om **DXML Post Process Initiator** om komponenten inte finns utför du följande steg för att infoga den:

1. Klicka **Infoga komponent** \(Ansvarig för AEM Guides-efterbearbetning är det sista steget i processen\).
1. Konfigurera **Processsteg** med information nedan:

   **Fliken Allmänt**

   **Titel:** DXML Post Process Initiator

   **Beskrivning**: Initieringssteg för DXML-efterbearbetning av den ändrade/skapade resursen som kommer att utlösa ett snedjobb för DXML-efterbearbetning

   **Fliken Process**

   - Välj **DXML Post Process Initiator** från **Process** nedrullningsbar listruta

   - Välj **Avancerad hanterare**

   - Välj **Klar**

1. Klicka **Synkronisera** överst till höger när du är klar med ändringarna. Du får ett meddelande om att åtgärden lyckades.

   >[!NOTE]
   >
   > Uppdatera och verifiera att anpassade ändringar och AEM guidas efterbearbetningssteg finns i den slutliga arbetsflödesmodellen.

1. En gång **Arbetsflöde för DAM-uppdatering** valideras, kontrollera motsvarande startkonfigurationer. Gå till AEM Workflow interface och öppna startkartor.

   ```http
   http://localhost:4502/libs/cq/workflow/content/console.html
   ```

   Sök efter och ändra \(om det behövs\) till följande två startprogram \(som ska vara aktiva\) som motsvarar **Arbetsflöde för DAM-uppdatering**:

1. Startprogram för &quot;*Noden har skapats*&quot; for **Arbetsflöde för DAM-uppdatering**- för villkor `"jcr:content/jcr:mimeType!=video"`ska värdet Globbing vara:

   ```json
   /content/dam(/((?!/subassets|/translation_output).)*/)renditions/original
   ```

   - excludeList ska ha `"event-user-data:changedByWorkflowProcess"`.
   - Startprogram för &quot;*Noden ändrad*&quot; for **Arbetsflöde för DAM-uppdatering -** for condition &quot;`jcr:content/jcr:mimeType!=video`&quot;, ska värdet Globbing vara:

   ```json
   /content/dam(/((?!/subassets|/translation_output).)*/)renditions/original
   ```

   - `excludeList` borde ha `"event-user-data:changedByWorkflowProcess"`.

1. När uppgraderingen är klar kontrollerar du att alla anpassningar/övertäckningar har validerats och uppdaterats så att de matchar den nya programkoden. Nedan ges några exempel:
   - Alla komponenter som överlappas av/libs/fmditor/libsska jämföras med den nya produktkoden och uppdateringar ska göras i överlagrade filer under/i appar.
   - Alla kategorier av klientlib som används från produkten bör granskas för ändringar. Alla åsidosatta konfigurationer \(exempel nedan\) bör jämföras med de senaste för att få de senaste funktionerna:
   - elementmapping.xml
   - ui\_config.json\(kan ha angetts i mappprofiler\)
   - ändrad `com.adobe.fmdita.config.ConfigManager`
   - Kontrollera om någon av de anpassade koderna använder några gamla sökvägar \(som anges i [Migreringsmappning](#id2244LE040XA) ) - ska uppdateras till de nya sökvägarna så att anpassningarna också fungerar som förväntat.
1. Läs om nya konfigurationer i den aktuella versionen \(kontrollera [Versionsinformation](../release-info/release-notes-4.2.1.md)\) och se om någon funktion påverkas genom att vidta lämpliga åtgärder. Ett exempel kan vara att använda&quot;Förbättrad fil- och versionshantering&quot; som introducerades i version 4.0, som du måste aktivera en konfiguration för.

## Steg för att indexera befintligt innehåll så att det använder den nya funktionen för att söka och ersätta:

Utför följande steg för att indexera det befintliga innehållet och använd den nya sök- och ersätt-texten på mappningsnivå:

- Se till att `damAssetLucene` indexeringen har slutförts. Det kan ta upp till några timmar, beroende på mängden data som finns på servern. Du kan bekräfta att omindexeringen har slutförts genom att kontrollera att fältet för omindexering har värdet false i
  `http://<server:port>/oak:index/damAssetLucene`.  Om du har lagt till anpassningar i `damAssetLucene`måste du kanske använda dem igen.

- Kör en POST till servern \(med korrekt autentisering\) - `http://<server:port\>/bin/guides/map-find/indexing`. (Valfritt: Du kan skicka specifika sökvägar för kartorna för indexering, som standard indexeras alla kartor \|\| Exempel: `https://<Server:port\>/bin/guides/map-find/indexing?paths=<map\_path\_in\_repository\>`)

- Du kan också skicka en rotmapp för att indexera DITA-mappningarna för en viss mapp (och dess undermappar). Till exempel, `http://<server:port\>/bin/guides/map-find/indexing?root=/content/dam/test`. Observera, att om både sökvägsparametern och rotparametern skickas, beaktas bara sökvägsparametern.

- API:t returnerar ett jobId. Om du vill kontrollera jobbets status kan du skicka en GET-förfrågan med jobb-ID till samma slutpunkt - `http://<server:port\>/bin/guides/map-find/indexing?jobId=\{jobId\}`\(Exempel: `http://localhost:8080/bin/guides/map-find/indexing?jobId=2022/9/15/7/27/7dfa1271-981e-4617-b5a4-c18379f11c42`\)


- När jobbet är klart kommer ovanstående GET-förfrågan att svara och ange om några kartor misslyckades. De korrekt indexerade mappningarna kan bekräftas från serverloggarna.

**Överordnat ämne:**[ Hämta och installera](download-install.md)
