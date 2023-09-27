---
title: Versionsinformation | Uppgraderingsinstruktioner och åtgärdade fel i Adobe Experience Manager Guides, oktober 2023-versionen
description: Läs om felkorrigeringarna och hur du uppgraderar till oktober 2023-versionen av Adobe Experience Manager Guides as a Cloud Service
source-git-commit: 4ce9024579aeaa97e6e35ac777ee3c14f0061aa6
workflow-type: tm+mt
source-wordcount: '999'
ht-degree: 2%

---

# Oktober 2023-versionen av Adobe Experience Manager Guides as a Cloud Service

Den här versionsinformationen innehåller uppgraderingsinstruktioner, kompatibilitetsmatris och problem som åtgärdats i version oktober 2023 av Adobe Experience Manager-handboken (senare kallad *AEM stödlinjer as a Cloud Service*).

Mer information om de nya funktionerna och förbättringarna finns i [Nyheter i oktober 2023-versionen av AEM Guides as a Cloud Service](whats-new-2023.10.0.md).

## Uppgradera till oktober 2023-versionen

Uppgradera din nuvarande AEM Guides as a Cloud Service genom att utföra följande steg:

1. Ta en titt på Cloud Servicens Git-kod och växla till den gren som är konfigurerad i Cloud Servicens pipeline för den miljö som du vill uppgradera.
2. Uppdatera `<dox.version>` egenskap i `/dox/dox.installer/pom.xml` fil med dina Cloud Service Git-kod till 2023.10.0.373.
3. Genomför ändringarna och kör Cloud Servicens pipeline för att uppgradera till oktober 2023-versionen av AEM Guides as a Cloud Service.

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

1. (Valfritt) Om det finns fler än 100 000 DITA-filer i systemet uppdaterar du `queryLimitReads` under `org.apache.jackrabbit.oak.query.QueryEngineSettingsService` till ett större värde (vilket värde som helst som är större än antalet resurser, till exempel 200 000) och sedan distribuera om.

   - Använd instruktionerna i *Konfigurationsåsidosättningar* i Installera och konfigurera Adobe Experience Manager Guides as a Cloud Service för att skapa konfigurationsfilen.
   - Ange följande (egenskap) information i konfigurationsfilen för att konfigurera alternativet queryLimitReads:

     | PID | Egenskapsnyckel | Egenskapsvärde |
     |---|---|---|
     | org.apache.jackrabbit.oak.query.QueryEngineSettingsService | queryLimitReads | Värde: 200000 Standardvärde: 100000 |

1. Kör en POST-begäran till servern (med korrekt autentisering) - `http://<server:port>//bin/guides/reports/upgrade`.

1. API:t returnerar ett jobId. Om du vill kontrollera jobbets status kan du skicka en GET-förfrågan med jobb-ID till samma slutpunkt - `http://<server:port>/bin/guides/reports/upgrade?jobId= {jobId}`
(Till exempel: `http://localhost:8080/bin/guides/map-find/indexing?jobId=2022/9/15/7/27/7dfa1271-981e-4617-b5a4-c18379f11c42_678`)

1. När jobbet är klart svarar den tidigare GETEN med framgång. Om jobbet misslyckas av någon anledning kan felet ses i serverloggarna.

1. Återgå till standardvärdet eller det tidigare befintliga värdet för `queryLimitReads` om du har ändrat den i steg 1.

## Steg för att indexera befintligt innehåll så att det använder den nya sök- och ersätt-listan och ämneslistan på fliken Rapporter:

(Endast om du använder en version som är tidigare än versionen från juni 2023 av AEM Guides as a Cloud Service)

Utför följande steg för att indexera det befintliga innehållet och använd den nya sök- och ersätt-texten på mappnivå och ämneslista på fliken Rapporter:

1. Kör en POST till servern \(med korrekt autentisering\) - `http://<server:port\>/bin/guides/map-find/indexing`. (Valfritt: Du kan skicka specifika banor för mappningarna för att indexera dem. Som standard indexeras alla mappningar \|\| Exempel: `https://<Server:port\>/bin/guides/map-find/indexing?paths=<map\_path\_in\_repository\>`)

1. Du kan också skicka en rotmapp för att indexera DITA-mappningarna för en viss mapp (och dess undermappar). Till exempel, `http://<server:port\>/bin/guides/map-find/indexing?root=/content/dam/test`. Observera, att om både sökvägsparametern och rotparametern skickas, beaktas bara sökvägsparametern.

1. API:t returnerar ett jobId. Om du vill kontrollera jobbets status kan du skicka en GET-förfrågan med jobb-ID till samma slutpunkt - `http://<server:port\>/bin/guides/map-find/indexing?jobId=\{jobId\}`\(Exempel: `http://localhost:8080/bin/guides/map-find/indexing?jobId=2022/9/15/7/27/7dfa1271-981e-4617-b5a4-c18379f11c42`\)


1. När jobbet är klart svarar den tidigare GETEN med framgång och anger om några kartor misslyckades. De korrekt indexerade mappningarna kan bekräftas från serverloggarna.

## Kompatibilitetsmatris

I det här avsnittet visas kompatibilitetsmatrisen för de program som stöds av AEM Guides as a Cloud Service från oktober 2023.

### FrameMaker och FrameMaker Publishing Server

| AEM stödlinjer som en Cloud-release | FMPS | FrameMaker |
| --- | --- | --- |
| 2023.10.0 | Inte kompatibel | 2022 eller senare |
| | | |


### Syrgasanslutning

| AEM stödlinjer som en Cloud-release | Syrgasanslutningsfönster | Syrgasanslutning Mac | Redigera i syrgasfönster | Redigera i Syrgas Mac |
| --- | --- | --- | --- | --- |
| 2023.10.0 | 3.2-uuid 5 | 3.2-uuid 5 | 2.3 | 2.3 |
|  |  |  |  |


### Kunskapsbasmallens version

| Komponentpaketets namn | Komponentversion | Mallversion |
|---|---|---|
| AEM Guides Components Content Package for Cloud Service | dxml-components.all-1.2.2 | aem-site-template-dxml.all-1.0.15 |

## Åtgärdade problem

De buggar som har åtgärdats i olika områden listas nedan:

### Redigering

- Eftermiddagstid anges inte i **Datum** för att skapa baslinjer. (12712)
- Det går inte att klistra in JSON-koden i `<codeblock>` i Web Editor. (12326)
- Versionsändringar som inte har sparats och indikatorerna för dem visas inte för stora filer. (11784)
- När du redigerar på koreanska ändras det första tecknet till standardvärdet. (10049)


### Publicering

- PDF | Ordningen på ämnena är inte fast när utdata från PDF skapas. (13157)
- Inbyggd PDF| Det finns ingen standardformattagg för `<p>`-element. (12559)
- PDF | Infogade format som används i innehållsområdet används inte för ämnen som skrivs framför och under. (13510)
- The `DeliveryTarget` attribut sprids inte när AEM genereras.  (13132)
- The **Publicera** arbetsflödet fastnar när AEM genereras för innehåll med vissa fel. (12000)

### Förvaltning

- Versionshistorik visas inte även om `dc:format` egenskapen finns inte för en resurs. (10463)


### Granska

- Granskningen av ett ämne visar felaktiga kommentarer. (13453)



### Översättning

- Baslinjen exporterad från **Översättning** Kontrollpanelen misslyckas och öppnas inte på målspråket. (13466)

- Nya översättningsprojekt skapas i stället för att nya jobb läggs till i de valda befintliga översättningsprojekten.  (10214)






