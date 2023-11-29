---
title: Versionsinformation | Uppgraderingsinstruktioner och åtgärdade fel i Adobe Experience Manager Guides, december 2023-versionen
description: Lär dig mer om felkorrigeringarna och hur du uppgraderar till december 2023-utgåvan av Adobe Experience Manager Guides as a Cloud Service.
source-git-commit: 9fcc8faec4631d710dbdfd7e4f8567069d0ba120
workflow-type: tm+mt
source-wordcount: '1290'
ht-degree: 2%

---

# December 2023-utgåvan av Adobe Experience Manager Guides as a Cloud Service

Den här versionsinformationen innehåller uppgraderingsinstruktioner, kompatibilitetsmatris och problem som åtgärdats i version december 2023 av Adobe Experience Manager Guides as a Cloud Service (kallas senare *as a Cloud Service stödlinjer för Experience Manager*).

Mer information om de nya funktionerna och förbättringarna finns i [Nyheter i december 2023-utgåvan av as a Cloud Service Experience Manager Guides](whats-new-2023.12.0.md).

## Uppgradera till december 2023-versionen

Uppgradera din nuvarande konfiguration av Experience Manager Guides as a Cloud Service genom att utföra följande steg:

1. Ta en titt på Cloud Servicens Git-kod och växla till den gren som är konfigurerad i Cloud Servicens pipeline för den miljö som du vill uppgradera.
2. Uppdatera `<dox.version>` egenskap i `/dox/dox.installer/pom.xml` fil med dina Cloud Service Git-kod till 2023.12.0.15.
3. Genomför ändringarna och kör Cloud Servicens pipeline för att uppgradera till december 2023-utgåvan av Experience Manager Guides as a Cloud Service.

## Steg för att aktivera utlösaren för ett skript via en serverlet

(Endast om du använder en version som är tidigare än versionen från juni 2023 av Experience Manager Guides as a Cloud Service)

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

I det tidigare svaret på JSON, nyckeln `lockNodePath` innehåller sökvägen till den nod som skapas i databasen som pekar på det skickade jobbet. Den tas automatiskt bort när jobbet är klart, så du kan referera till den här noden för jobbstatus.

Vänta tills jobbet är klart innan du fortsätter till nästa steg.

>[!NOTE]
>
> Du bör kontrollera om noden fortfarande finns och jobbens status.

```
GET
http://<aem_domain>/var/dxml/executor-locks/translation-map-upgrade/1683190032886.json
```

## Steg för att bokföra det befintliga innehållet så att det använder den brutna länkrapporten

(Endast om du använder en version som är tidigare än versionen från juni 2023 av Experience Manager Guides as a Cloud Service)

Utför följande steg för att efterbearbeta befintligt innehåll och använda den nya brutna länkrapporten:

1. (Valfritt) Om det finns fler än 100 000 DITA-filer i systemet uppdaterar du `queryLimitReads` och `queryLimitInMemory` under `org.apache.jackrabbit.oak.query.QueryEngineSettingsService` till ett större värde (vilket värde som helst som är större än antalet resurser, till exempel 200 000) och sedan distribuera om.

   - Använd instruktionerna i *Konfigurationsåsidosättningar* i Installera och konfigurera Adobe Experience Manager Guides as a Cloud Service för att skapa konfigurationsfilen.
   - Ange följande (egenskap) information i konfigurationsfilen för att konfigurera `queryLimitReads` och `queryLimitInMemory` alternativ:

     | PID | Egenskapsnyckel | Egenskapsvärde |
     |---|---|---|
     | org.apache.jackrabbit.oak.query.QueryEngineSettingsService | queryLimitReads | Värde: 200000 Standardvärde: 100000 |
     | org.apache.jackrabbit.oak.query.QueryEngineSettingsService | queryLimitInMemory | Värde: 200000 Standardvärde: 100000 |

1. Kör en POST-begäran till servern (med korrekt autentisering) - `http://<server>//bin/guides/reports/upgrade`.

1. API:t returnerar ett jobId. Om du vill kontrollera jobbets status kan du skicka en GET-förfrågan med jobb-ID till samma slutpunkt - `http://<server>/bin/guides/reports/upgrade?jobId= {jobId}`
(Till exempel: `http://localhost:8080/bin/guides/reports/upgrade?jobId=2022/9/15/7/27/7dfa1271-981e-4617-b5a4-c18379f11c42_678`)

1. När jobbet är klart svarar den tidigare GETEN med framgång. Om jobbet misslyckas av någon anledning kan felet ses i serverloggarna.

1. Återgå till standardvärdet eller det tidigare befintliga värdet för `queryLimitReads` om du har ändrat den i steg 1.

## Steg för att indexera befintligt innehåll så att det använder den nya sök- och ersätt-listan och ämneslistan på fliken Rapporter:

(Endast om du använder en version som är tidigare än versionen från juni 2023 av Experience Manager Guides as a Cloud Service)

Utför följande steg för att indexera det befintliga innehållet och använd den nya sök- och ersätt-texten på mappnivå och ämneslista på fliken Rapporter:

1. Kör en POST-begäran till servern (med korrekt autentisering) - `http://<server:port>/bin/guides/map-find/indexing`. (Valfritt: Du kan skicka specifika sökvägar för kartorna för att indexera dem. Som standard indexeras alla kartor|| Till exempel: `https://<Server:port>/bin/guides/map-find/indexing?paths=<map_path_in_repository>`)

1. Du kan också skicka en rotmapp för att indexera DITA-mappningarna för en viss mapp (och dess undermappar). Till exempel, `http://<server:port>/bin/guides/map-find/indexing?root=/content/dam/test`. Observera, att om både sökvägsparametern och rotparametern skickas, beaktas bara sökvägsparametern.

1. API:t returnerar ett jobId. Om du vill kontrollera jobbets status kan du skicka en GET-förfrågan med jobb-ID till samma slutpunkt - `http://<server:port>/bin/guides/map-find/indexing?jobId={jobId}`(Till exempel: `http://localhost:8080/bin/guides/map-find/indexing?jobId=2022/9/15/7/27/7dfa1271-981e-4617-b5a4-c18379f11c42_678`)


1. När jobbet är klart svarar den tidigare GETEN med framgång och anger om några kartor misslyckades. De korrekt indexerade mappningarna kan bekräftas från serverloggarna.

## Steg som ska hantera `'fmdita rewriter'` konflikt

Experience Manager Guides har en [**egen sling-omskrivare**](../cs-install-guide/conf-output-generation.md#custom-rewriter) för hantering av länkar som genereras vid korsmappningar (länkar mellan ämnen i två olika kartor).

Om du har en annan anpassad Sing Rewriter i kodbasen använder du en `'order'` värdet är större än 50, eftersom Experience Manager Guides sling rewriter använder `'order'` 50.  Om du vill åsidosätta detta måste du ange ett värde > 50. Mer information finns i [Omskrivningsförlopp för utdata](https://sling.apache.org/documentation/bundles/output-rewriting-pipelines-org-apache-sling-rewriter.html).

Under uppgraderingen har `'order'` värdet ändras från 1 000 till 50, du måste sammanfoga den befintliga anpassade omskrivaren, om det finns någon, med `'fmdita-rewriter'`.


## Kompatibilitetsmatris

I det här avsnittet visas kompatibilitetsmatrisen för de program som stöds av Experience Manager Guides as a Cloud Service December 2023.

### FrameMaker och FrameMaker Publishing Server

| Experience Manager Guides as a Cloud Release | FMPS | FrameMaker |
| --- | --- | --- |
| 2023.12.0 | Inte kompatibel | 2022 eller senare |
| | | |


### Syrgasanslutning

| Experience Manager Guides as a Cloud Release | Syrgasanslutningsfönster | Syrgasanslutning Mac | Redigera i syrgasfönster | Redigera i Syrgas Mac |
| --- | --- | --- | --- | --- |
| 2023.12.0 | 3.3-uuid.5 | 3.3-uuid.5 | 2.3 | 2.3 |
|  |  |  |  |


### Kunskapsbasmallens version

| Komponentpaketets namn | Komponentversion | Mallversion |
|---|---|---|
| Innehållspaket för komponenter i Experience Manager-stödlinjer för Cloud Service | dxml-components.all-1.2.2 | aem-site-template-dxml.all-1.0.15 |

## Åtgärdade problem

De buggar som har åtgärdats i olika områden listas nedan:



### Redigering

- The **Titel** på webbredigeringsfliken trunkeras efter en punkt (.) tecken. (14372)
- Felmeddelanden för duplicerade mappningsnamn i resursgränssnittet uppdateras inte. (14320)
- Ett fel inträffar i logiken för att skapa versioner när resurser dras och släpps. (14291)
- Återanvändbart innehåll hoppar över element-ID:n. (14213)
- Inställningskontrollen som ska döljas **Språkvariabler** panel under **Utdata** -fliken saknas. (14194)
- Webbredigeraren genererar programfel när en ny referens eller ett nytt ämne läggs till med ett specialiserat schema i layoutvyn. (14094)
- En ankarlänk till `<dlentry>` eller `<dt>` länktexten visas inte. (13543)
- The **Favoriter** det går inte att läsa in samlingen i Web Editor. (13495)
- Citat visar länkar som inte går att klicka på när de skapas med ett unikt ID med blanksteg. (13447)
- I **Layout** vy för en bokkarta, använda **Flytta åt höger** om du vill göra ett markerat kapitel till ett delelement fungerar inte. (12567)
- XML Editors förhandsgranskningsfönster är trunkerat i Google Chrome- och Microsoft Edge-webbläsare. (10755)
- Webbredigeraren saknar möjlighet att kapsla in ett element inuti de överordnade elementen. (8791)

### Publicering

- Fmdita-komponenter har en hårdkodad sökväg med `delegator.jsp`, som förhindrar övertäckning av AEM Sites-komponenter. (13993)
- Den taggade vyn av PDF-reaktorn i Native PDF fungerar inte som förväntat. (13622)
- Vid publicering av AEM påträffas ett problem vid implementering i datalagret för stora kartor med scope-peer-länkar. (13531)
- Det går inte att aktivera en webbplats med kontrollpanelen Experience Manager Guides Bulk Publication. (13439)
- Elementetiketternas lokalisering fungerar inte korrekt i AEM Sites-utdata. (12144)
- Saknas **diaval** i förinställningar för utdata på mappprofilnivå som har skapats via webbredigerarens användargränssnitt. (11903)

### Förvaltning

- AEM molnmiljöer stöter på ett MongoWrite-undantag på grund av stora noder. (13509)

### Översättning

- The **Acceptera/avvisa** visas felaktigt för automatiskt godkänd mänsklig översättning. (14318)
- Internationaliseringsproblem (i18n) inträffar under omvandlingen av icke-engelska DITA-filer till AEM sidor. (14286)
- Översatt innehåll kan inte synkroniseras från temporära översättningsprojekt, och översättningsguiden för DITA XML-redigeraren visar felaktigt **Pågår** status för godkända jobb. (9938)

### Tillgänglighet

- Det går inte att navigera i arbetsytans användargränssnitt eftersom fokus blir svällt i ämnesredigeraren. (13517)

## Känt fel

Adobe har identifierat följande kända fel i december 2023-utgåvan:
- &quot;Hämtning av ett ogiltigt DTD-fel&quot; inträffar då och då vid uppgradering till december 2023-utgåvan.