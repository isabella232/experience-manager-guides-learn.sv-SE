---
title: Versionsinformation | Uppgraderingsinstruktioner och åtgärdade problem i Adobe Experience Manager Guides, november 2023-versionen
description: Lär dig mer om felkorrigeringarna och hur du uppgraderar till november 2023-utgåvan av Adobe Experience Manager Guides as a Cloud Service
source-git-commit: 1d8f00a82e92e1648615c409d4652b6ce3da7a1f
workflow-type: tm+mt
source-wordcount: '1640'
ht-degree: 2%

---

# Novemberversionen 2023 av Adobe Experience Manager Guides as a Cloud Service

Den här versionsinformationen innehåller uppgraderingsinstruktioner, kompatibilitetsmatris och problem som åtgärdats i version november 2023 av Adobe Experience Manager Guides as a Cloud Service (kallas senare *as a Cloud Service stödlinjer för Experience Manager*).

Mer information om de nya funktionerna och förbättringarna finns i [Nyheter i november 2023-utgåvan av as a Cloud Service Experience Manager Guides](whats-new-2023.11.0.md).

## Uppgradera till november 2023-versionen

Uppgradera din nuvarande konfiguration av Experience Manager Guides as a Cloud Service genom att utföra följande steg:

1. Ta en titt på Cloud Servicens Git-kod och växla till den gren som är konfigurerad i Cloud Servicens pipeline för den miljö som du vill uppgradera.
2. Uppdatera `<dox.version>` egenskap i `/dox/dox.installer/pom.xml` fil med dina Cloud Service Git-kod till 2023.11.0.406.
3. Genomför ändringarna och kör Cloud Servicens pipeline för att uppgradera till november 2023-utgåvan av Experience Manager Guides as a Cloud Service.

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

I det tidigare svaret på JSON, nyckeln `lockNodePath` innehåller sökvägen till den nod som skapas i databasen som pekar på det skickade jobbet. Den tas automatiskt bort när jobbet är klart. Sedan kan du referera till den här noden för jobbstatus.

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

1. Kör en POST-begäran till servern (med korrekt autentisering) - `http://<server:port>//bin/guides/reports/upgrade`.

1. API:t returnerar ett jobId. Om du vill kontrollera jobbets status kan du skicka en GET-förfrågan med jobb-ID till samma slutpunkt - `http://<server:port>/bin/guides/reports/upgrade?jobId= {jobId}`
(Till exempel: `http://localhost:8080/bin/guides/map-find/indexing?jobId=2022/9/15/7/27/7dfa1271-981e-4617-b5a4-c18379f11c42_678`)

1. När jobbet är klart svarar den tidigare GETEN med framgång. Om jobbet misslyckas av någon anledning kan felet ses i serverloggarna.

1. Återgå till standardvärdet eller det tidigare befintliga värdet för `queryLimitReads` om du har ändrat den i steg 1.

## Steg för att indexera befintligt innehåll så att det använder den nya sök- och ersätt-listan och ämneslistan på fliken Rapporter:

(Endast om du använder en version som är tidigare än versionen från juni 2023 av Experience Manager Guides as a Cloud Service)

Utför följande steg för att indexera det befintliga innehållet och använd den nya sök- och ersätt-texten på mappnivå och ämneslista på fliken Rapporter:

1. Kör en POST till servern \(med korrekt autentisering\) - `http://<server:port\>/bin/guides/map-find/indexing`. (Valfritt: Du kan skicka specifika banor för mappningarna för att indexera dem. Som standard indexeras alla mappningar \|\| Exempel: `https://<Server:port\>/bin/guides/map-find/indexing?paths=<map\_path\_in\_repository\>`)

1. Du kan också skicka en rotmapp för att indexera DITA-mappningarna för en viss mapp (och dess undermappar). Till exempel, `http://<server:port\>/bin/guides/map-find/indexing?root=/content/dam/test`. Observera, att om både sökvägsparametern och rotparametern skickas, beaktas bara sökvägsparametern.

1. API:t returnerar ett jobId. Om du vill kontrollera jobbets status kan du skicka en GET-förfrågan med jobb-ID till samma slutpunkt - `http://<server:port\>/bin/guides/map-find/indexing?jobId=\{jobId\}`\(Exempel: `http://localhost:8080/bin/guides/map-find/indexing?jobId=2022/9/15/7/27/7dfa1271-981e-4617-b5a4-c18379f11c42`\)


1. När jobbet är klart svarar den tidigare GETEN med framgång och anger om några kartor misslyckades. De korrekt indexerade mappningarna kan bekräftas från serverloggarna.

## Steg som ska hantera `'fmdita rewriter'` konflikt

Experience Manager Guides har en [**egen sling-omskrivare**](../cs-install-guide/conf-output-generation.md#custom-rewriter) för hantering av länkar som genereras vid korsmappningar (länkar mellan ämnen i två olika kartor).

Om du har en annan anpassad Sing Rewriter i kodbasen använder du en `'order'` värdet är större än 50, eftersom Experience Manager Guides sling rewriter använder `'order'` 50.  Om du vill åsidosätta detta måste du ange ett värde > 50. Mer information finns i [Omskrivningsförlopp för utdata](https://sling.apache.org/documentation/bundles/output-rewriting-pipelines-org-apache-sling-rewriter.html).

Under uppgraderingen har `'order'` värdet ändras från 1 000 till 50, du måste sammanfoga den befintliga anpassade omskrivaren, om det finns någon, med `'fmdita-rewriter'`.


## Kompatibilitetsmatris

I det här avsnittet visas kompatibilitetsmatrisen för de program som stöds av Experience Manager Guides as a Cloud Service från november 2023.

### FrameMaker och FrameMaker Publishing Server

| Stödlinjer för Experience Manager som en molnrelease | FMPS | FrameMaker |
| --- | --- | --- |
| 2023.11.0 | Inte kompatibel | 2022 eller senare |
| | | |


### Syrgasanslutning

| Experience Manager Guides as a Cloud Release | Syrgasanslutningsfönster | Syrgasanslutning Mac | Redigera i syrgasfönster | Redigera i Syrgas Mac |
| --- | --- | --- | --- | --- |
| 2023.11.0 | 3.2-uuid 5 | 3.2-uuid 5 | 2.3 | 2.3 |
|  |  |  |  |


### Kunskapsbasmallens version

| Komponentpaketets namn | Komponentversion | Mallversion |
|---|---|---|
| Innehållspaket för komponenter i Experience Manager-stödlinjer för Cloud Service | dxml-components.all-1.2.2 | aem-site-template-dxml.all-1.0.15 |

## Åtgärdade problem

De buggar som har åtgärdats i olika områden listas nedan:



### Redigering

- Avstånd efter konref `<ph>` -elementet försvinner när avsnittet sparas. (13642)
- Programfel inträffar när DITA-filer sparas innan efterbearbetningen är klar. (13571)
- Om titeln på ett ämne innehåller ett snedstreck `/`visas bara de bokstäver som kommer efter. (13455)
- Förhandsvisningen av bilden försvinner inte när du har visat förhandsvisningen i redigeraren. (13454)
- Popup-fönstret Infoga nyckelord visas inte när rotmappsdefinierade nycklar används i andra ämnen. (12950)
- Stängningsikoner visas inte när mycket stora bilder förhandsvisas på panelen Versionshistorik. (12867)
- Det går inte att ändra tidszonen för **Version skapad den** kolumnen för baslinjer. (12711)
- The **Tidigare versioner** i resursgränssnittet visas en felaktig tidsstämpel för **Aktuell** fält. (12624)
- Om du skapar en DITA-fil från en mall med ett filnamn som börjar med numeriska tecken resulterar det i ett namnutrymmesfel. (12188)
- I webbredigeraren **Nyckelreferenser** öppnas när du infogar `varname` -tagg. (10940)
- Zip-filer känns inte igen i Web Editor och du kan inte dra och släppa dem. (12709)
- Innehållet med vissa attribut som används på det markeras inte i redigerings- eller förhandsgranskningsläge. (11063)
- När du stänger ett ämne efter att du har redigerat det omdirigeras du till AEM hemsida i stället för att gå tillbaka till mappvyn. (13306)
- Efterbearbetningen av filer som har kopierats och klistrats in i molntjänsterna fördröjs. (12457)
- Rotmappsinställningen finns kvar i Web Editor även om användaren inte uttryckligen har angett den i användarinställningarna. (11551)


### Publicering

- Publicera som innehållsfragmentfunktion fungerar inte för filer som listas i sökresultaten. (14090)
- Vid ursprunglig PDF-publicering kräver bakgrundsfärgen i mallayouten en sidomladdning när du återgår till `None`. (13621)
- Problem vid implementering av datastore för en stor DITA-karta med scope-peer-länkar AEM Site publishing. (13530)
- I Native PDF-publicering äventyras tillgängligheten eftersom bilder i sidhuvud och sidfot inte visar alternativ text. (12829)
- Det går inte att duplicera sidlayout i PDF utan att lägga till något tillägg automatiskt. (12534)
- När du genererar utdata från PDF med Native PDF-publicering kommer filnamnet att trunkeras efter en viss period. (13620)
- Felaktiga ikoner och verktygstips visas för  **Redigera innehåll** i verktygsfältet Sidlayouter i mallarna som används för publicering i Native PDF. (13492)
- Anpassade metadata är inte tillgängliga i det slutliga resultatet. (12116)
- fmdita rewriter står i konflikt med användarens omskrivarkonfiguration och leder till att långa URL-adresser visas i stället för länkarna. (12076)
- I AEM platsförinställning kan du välja att **Generera olika PDF för varje ämne** inte fungerar. (11555)
- Inbyggd PDF-publicering saknar stöd för CMYK-färgmodellskonvertering. (10754)
- Dynamiska baslinjeanrop använder namnet i stället för titeln, vilket leder till att det inte går att exportera DITA-mappnings-API. (14268)

### Förvaltning

- Innehållsreferensen bryts vid kopiering och inklistring av DITA-filer med självreferenslänkar utan GUID. (13540)
- Baslinjen i Web Editor visar titeln för den föregående versionen i stället för den valda versionen av DITA-filen. (13444)
- The **Rapporter** i webbredigerarens användargränssnitt kan inte visa ämneslistan för gamla DITA-kartor som skapats före Juli 2023-uppgraderingen av Experience Manager Guides as a Cloud Service. (11852)
- Villkorsförinställningar för stora DITA-kartor skapas inte. (10936)
- En självreferenslänk visas under listan med brutna länkar i rapporter. (13539)

### Granska

- Granskningspanelerna sida vid sida i den tidigare och den aktuella versionen i webbredigeraren är inte korrekta i oktober 2023-versionen av as a Cloud Service för Experience Manager-stödlinjer. (14156)
- Anpassning av e-postmallar för **Granska** arbetsflödet fungerar inte med att täcka över noderna. (13954)
- The **Stäng** på sidan Granska i Experience Manager-guiderna tar användarna till AEM hemsida. (13535)
- Brutna tecken visas när fragment skapas på koreanska. (13489)
- Det går inte att klicka på koreanska bilagor på Experience Manager Guides Review-skärmen. (13436)
- Karttitel klipps av på skärmen för granskning och samarbete, utan möjlighet att visa hela titeln. (13012)

### Översättning

- Godkänn automatiskt fungerar inte ibland, och undantag uppstår om ett felaktigt värde är aktiverat **Översättningsstatus**. (13607)
- Baslinjen som exporteras från översättningsinstrumentpanelen misslyckas och öppnas inte på målspråket. (12993)

## Känt fel

Adobe har identifierat följande kända fel i novemberversionen 2023.

- Selektiv omgenerering av ämnen för AEM webbplatsutdata misslyckas.