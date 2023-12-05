---
title: Versionsinformation | Uppgraderingsinstruktioner och åtgärdade fel i Adobe Experience Manager Guides, versionen från september 2023
description: Läs om felkorrigeringarna och hur du uppgraderar till september 2023-utgåvan av Adobe Experience Manager Guides as a Cloud Service
source-git-commit: 880cd344ceb65ea339be699ebcad41c0d62e168a
workflow-type: tm+mt
source-wordcount: '1486'
ht-degree: 0%

---

# Septemberversionen 2023 av Adobe Experience Manager Guides as a Cloud Service

Den här versionsinformationen innehåller uppgraderingsinstruktioner, kompatibilitetsmatris och problem som åtgärdats i Adobe Experience Manager-handbokens version från september 2023 (kallas senare *AEM stödlinjer as a Cloud Service*).

Mer information om de nya funktionerna och förbättringarna finns i [Nyheter i september 2023-utgåvan av AEM Guides as a Cloud Service](whats-new-2023.9.0.md).

## Uppgradera till versionen från september 2023

Uppgradera din nuvarande AEM Guides as a Cloud Service genom att utföra följande steg:

1. Ta en titt på Cloud Servicens Git-kod och växla till den gren som är konfigurerad i Cloud Servicens pipeline för den miljö som du vill uppgradera.
2. Uppdatera `<dox.version>` egenskap i `/dox/dox.installer/pom.xml` fil med dina Cloud Service Git-kod till 2023.9.0.359.
3. Genomför ändringarna och kör Cloud Servicen för att uppgradera till september 2023-utgåvan av AEM Guides as a Cloud Service.

## Steg för att aktivera utlösaren för ett skript via en serverlet

(Endast om du använder en version som är tidigare än versionen från juni 2023 av AEM Guides as a Cloud Service)

När du har slutfört installationen kan du välja att HIT-aktivera utlösaren för att starta översättningsjobbet:

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

I det tidigare svaret på JSON, nyckeln `lockNodePath` innehåller sökvägen till den nod som skapas i databasen som pekar på det skickade jobbet. Den tas automatiskt bort när jobbet är klart, tills dess kan du referera till den här noden för aktuell status för jobbet.

Vänta tills jobbet är klart innan du fortsätter till nästa steg.

>[!NOTE]
>
> Du bör kontrollera om noden fortfarande finns och jobbens status.

```
GET
http://<aem_domain>/var/dxml/executor-locks/translation-map-upgrade/1683190032886.json
```

## Steg för att bokföra det befintliga innehållet så att det använder den brutna länkrapporten

(Endast om du använder en version som är tidigare än versionen från juni 2023 av AEM Guides as a Cloud Service)

Utför följande steg för att efterbearbeta befintligt innehåll och använda den nya brutna länkrapporten:

1. (Valfritt) Om det finns fler än 100 000 dita-filer i systemet uppdaterar du `queryLimitReads` under `org.apache.jackrabbit.oak.query.QueryEngineSettingsService` till ett större värde (vilket värde som helst som är större än antalet resurser, till exempel 200 000) och sedan distribuera om.

   - Använd instruktionerna i *Konfigurationsåsidosättningar* i Installera och konfigurera Adobe Experience Manager Guides as a Cloud Service för att skapa konfigurationsfilen.
   - Ange följande (egenskap) information i konfigurationsfilen för att konfigurera alternativet queryLimitReads:

     | PID | Egenskapsnyckel | Egenskapsvärde |
     |---|---|---|
     | org.apache.jackrabbit.oak.query.QueryEngineSettingsService | queryLimitReads | Värde: 200000 Standardvärde: 100000 |

1. Kör en POST-begäran till servern (med korrekt autentisering) - `http://<server:port>//bin/guides/reports/upgrade`.

1. API:t returnerar ett jobId. Om du vill kontrollera jobbets status kan du skicka en GET-förfrågan med jobb-ID till samma slutpunkt - `http://<server:port>/bin/guides/reports/upgrade?jobId= {jobId}`
(Till exempel: `http://localhost:8080/bin/guides/map-find/indexing?jobId=2022/9/15/7/27/7dfa1271-981e-4617-b5a4-c18379f11c42_678`)

1. När jobbet är klart svarar den tidigare GETEN med framgång. Om jobbet misslyckas av någon anledning kan fel ses från serverloggarna.

1. Återgå till standardvärdet eller det tidigare befintliga värdet för `queryLimitReads` om du har ändrat den i steg 1.

## Steg för att indexera befintligt innehåll så att det använder den nya sök- och ersätt-listan och ämneslistan på fliken Rapporter:

(Endast om du använder en version som är tidigare än versionen från juni 2023 av AEM Guides as a Cloud Service)

Utför följande steg för att indexera det befintliga innehållet och använd den nya sök- och ersätt-texten på mappnivå och ämneslista på fliken Rapporter:

1. Kör en POST till servern \(med korrekt autentisering\) - `http://<server:port\>/bin/guides/map-find/indexing`. (Valfritt: Du kan skicka specifika banor för mappningarna för att indexera dem. Som standard indexeras alla mappningar \|\| Exempel: `https://<Server:port\>/bin/guides/map-find/indexing?paths=<map\_path\_in\_repository\>`)

1. Du kan också skicka en rotmapp för att indexera DITA-mappningarna för en viss mapp (och dess undermappar). Till exempel: `http://<server:port\>/bin/guides/map-find/indexing?root=/content/dam/test`. Observera, att om både sökvägsparametern och rotparametern skickas, beaktas bara sökvägsparametern.

1. API:t returnerar ett jobId. Om du vill kontrollera jobbets status kan du skicka en GET-förfrågan med jobb-ID till samma slutpunkt - `http://<server:port\>/bin/guides/map-find/indexing?jobId=\{jobId\}`\(Exempel: `http://localhost:8080/bin/guides/map-find/indexing?jobId=2022/9/15/7/27/7dfa1271-981e-4617-b5a4-c18379f11c42`\)


1. När jobbet är klart svarar den tidigare GETEN och anger om några kartor misslyckades. De korrekt indexerade mappningarna kan bekräftas från serverloggarna.

## Kompatibilitetsmatris

I det här avsnittet visas kompatibilitetsmatrisen för de program som stöds av AEM Guides as a Cloud Service från september 2023.

### FrameMaker och FrameMaker Publishing Server

| AEM stödlinjer som en Cloud-release | FMPS | FrameMaker |
| --- | --- | --- |
| 2023.09.0 | Inte kompatibel | 2022 eller senare |
| | | |


### Syrgasanslutning

| AEM stödlinjer som en Cloud-release | Syrgasanslutningsfönster | Syrgasanslutning Mac | Redigera i syrgasfönster | Redigera i Syrgas Mac |
| --- | --- | --- | --- | --- |
| 2023.09.0 | 3.1-uuid 17 | 3.1-uuid 17 | 2,3 | 2,3 |
|  |  |  |  |


### Kunskapsbasmallens version

| Komponentpaketets namn | Komponentversion | Mallversion |
|---|---|---|
| AEM Guides Components Content Package for Cloud Service | dxml-components.all-1.2.2 | aem-site-template-dxml.all-1.0.15 |

## Åtgärdade problem

De buggar som har åtgärdats i olika områden listas nedan:

### Redigering

- Ämnesfilen är inte olåst i Web Editor, även om alternativet Lås upp fil och alternativet Spara inte är markerat. (12558)
- Det går inte att checka ut en fil i webbredigeraren, trots att du har valt alternativet NEJ för att ignorera ändringarna före incheckning. 12557
- Verktygstipsen för filikonerna Lås och lås upp i huvudverktygsfältet i Web Editor är inte konsekventa med de ikoner som visas i databasvyn.(12555)
- Alternativet Avbryt utcheckning och Lås upp visas för en fil i Web Editor som ännu inte är utcheckad i Kartvyn. (12556)
- Det går inte att markera PDF-resurserna i de befintliga topicref-länkarna. (12477)
- I databasvyn kan du inte dra ämnen eller bilder efter att du har använt funktionerna Sök/Filter. 12396)
- Sökresultaten inaktiveras på panelen Sök och ersätt när du har öppnat en sökad fil. (12142)
- Siffertangenten&quot;8&quot; på sidotangentbordet fungerar inte i redigeraren AEM stödlinjer. (12106)

- Prefixet dupliceras i förhandsgranskningsläget i Web Editor. 13133
- `Choicetable` rader visas inte eller kan inte markeras. 12616
- Webbredigeraren genererar valideringsfel i specifika scenarier när du skapar ett ämne med ett anpassat schema. 12576
- Mallreferenser för dynamiska ämnen skapar inte någon kopia i innehållsmappen när en karta från mappningsmallen skapas. (12150)
- Sökrutan i DITA-kartor har ingen stängningsknapp. (11867)
- När du sparar långa filer i Web Editor `DirtyChecker` genererar ett undantag med en lång stackspårning och fyller i loggfilerna. (11860)
- För att skapa DITA-avsnitt krävs behörigheten Ta bort på motsvarande mappnod, men kartan kan skapas med skrivbehörighet. 11706
- I webbredigeraren visas en felaktig titel när det finns ett snedstreck. (10949)


### Förvaltning

- Fältet &quot;title&quot; i DITA-mappningens metadataegenskaper skrivs över av `<title>` kartelementet. (10702)
- Innehållsreferens är bruten kopiering och inklistring av DITA-filer när ämnets ID inte är detsamma som GUID. 12614
- I dynamiska baslinjer hämtas inte listan med etiketter från de direkta referenserna för arbetskopian av en DITA-karta. (11917)

### Publicering

- Publiceringen misslyckas när namnet på en förinställning för inbyggda PDF ändras. (12564)
- När du duplicerar en inbyggd PDF-mall dupliceras den till standardmallplatsen i stället för den angivna anpassade mallplatsen. 12563

- PDF | Om du tar med flera xrefs, utvidgas texten utanför kolumnbredden. 13004
- PDF | När ämnet och titeln har samma ID leder det till en felaktig generering av PDF-utdata. 12644
- PDF | Lägga till en utdataklass till en överordnad `<topicref>` -elementet i en DITA-karta och använder en anpassad stil på klassen Output. Formateringen används på element i ämnesbrödtexten, inklusive avsnittsrubriker.(12166)
- Inkrementell publicering fungerar inte om en DITA-karta har flera diavalrefs. (12117)
- AEM | När du skapar en karta med nyckelord som pekar på ett ämne som en variabel och lägger till processing-role=resource-only skapas en del oväntade sidor. (12099)
- Om resurser från AEM DAM används i andra utdata än den AEM platsen, återspeglar inte metadata&quot;jcr:createdBy&quot; utgivarens namn eller namnet på den användare som senast ändrade DITA-kartan eller -avsnittet. (12090)
- AEM Sites | DITA-kartan med topichad i navigeringsrubriken (med tecken som inte stöds) leder till felaktiga sidadresser. (11978)
- PDF | Problem inträffar med stöd för topichead/topicmeta/navtitle i Frontmatter och Backmatter. (11969)
- PDF | Det tar tid att generera PDF för stora dokument. (11955)
- PDF | Om du byter namn på en förinställning genereras ett NullPointerException-fel när du genererar utdata i PDF. 11889
- The `<conref>` -innehåll visas inte i utdata från PDF. (11131)
- Ett extra blanksteg läggs till i `<div>` element vid växling mellan redigeringsvyn för författare och källa i sidlayoutredigeraren. 10750)
- Innehållet som replikeras i AEM Cloud Manager visas inte i Publish-instansen. 9564

### Översättning

- Processen att exportera en namnändrad baslinje för en översättning misslyckas. (12993)
- Den översatta filens namn visas i stället för källfilens namn. (11630)
