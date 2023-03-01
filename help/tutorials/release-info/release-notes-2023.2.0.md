---
title: Versionsinformation | Adobe Experience Manager Guides as a Cloud Service, februari 2023-versionen
description: Den senaste versionen av Adobe Experience Manager Guides as a Cloud Service
source-git-commit: d56855bf9078482ec1676b0eeb7a13df05475d5c
workflow-type: tm+mt
source-wordcount: '2178'
ht-degree: 1%

---

# Den senaste versionen av Adobe Experience Manager Guides as a Cloud Service

## Uppgradera till den senaste versionen

Uppgradera din nuvarande Adobe Experience Manager Guides as a Cloud Service (kallas senare *AEM stödlinjer as a Cloud Service*) genom att utföra följande steg:
1. Ta en titt på Cloud Servicens Git-kod och växla till den gren som är konfigurerad i Cloud Servicens pipeline för den miljö som du vill uppgradera.
2. Uppdatera `<dox.version>` egenskap i `/dox/dox.installer/pom.xml` fil med dina Cloud Services Git-kod till 2023.2.235.
3. Genomför ändringarna och kör Cloud Servicens pipeline för att uppgradera till den senaste versionen av AEM Guides as a Cloud Service.

## Steg för att indexera det befintliga innehållet (endast om du använder en version som är tidigare än september-versionen av AEM stödlinjer as a Cloud Service)

Utför följande steg för att indexera det befintliga innehållet och använd den nya sök- och ersätt-texten på mappningsnivå:

* Kör en serverbegäran (med korrekt autentisering) - `http://<server:port>/bin/guides/map-find/indexing`.
(Valfritt: Du kan skicka specifika sökvägar för mappningarna för att indexera dem. Som standard indexeras alla mappningar || Exempel: `https://<Server:port>/bin/guides/map-find/indexing?paths=<map_path_in_repository>`)

* API:t returnerar ett jobId. Om du vill kontrollera jobbets status kan du skicka en GET-förfrågan med jobb-ID till samma slutpunkt - `http://<server:port>/bin/guides/map-find/indexing?jobId={jobId}`
(Exempel: http://&lt;
_localhost:8080_>/bin/guides/map-find/indexing?jobId=2022/9/15/7/27/7dfa1271-981e-4617-b5a4-c18379f11c42_678)

* När jobbet är klart kommer ovanstående GET-förfrågan att svara och ange om några kartor misslyckades. De korrekt indexerade mappningarna kan bekräftas från serverloggarna.

## Kompatibilitetsmatris

I det här avsnittet visas kompatibilitetsmatrisen för de program som stöds av AEM Guide as a Cloud Service från februari 2023.

### FrameMaker och FrameMaker Publishing Server

| AEM stödlinjer som en Cloud-release | FMPS | FrameMaker |
| --- | --- | --- |
| 2023.02.0 | Inte kompatibel | 2022 eller senare |
|  |  |  |

*Originalplan och villkor skapade i AEM stöds i FMPS-versioner från och med 2020.2.

### Syrgasanslutning

| AEM stödlinjer som en Cloud-release | Syrgasanslutningsfönster | Syrgasanslutning Mac | Redigera i syrgasfönster | Redigera i Syrgas Mac |
| --- | --- | --- | --- | --- |
| 2023.02.0 | 2.8-uuid-8 | 2.8-uuid-8 | 2.3 | 2.3 |
|  |  |  |  |


## Nya funktioner och förbättringar

AEM Guides as a Cloud Service innehåller förbättringar och nya funktioner i den senaste versionen:

### Generera rapporter från Web Editor

AEM Guides innehåller en funktion i Web Editor som gör att du kan kontrollera att dina tekniska dokument är fullständiga och generera rapporter för dem.
Du kan visa ämneslistan, hantera metadata och se multimedia som används i alla referenser för den aktuella kartan från
**Rapporter** i Web Editor.

**Generera ämneslistvyn**

Du kan generera ämneslistan med detaljerad information om ämnen, som referenstyp, dokumenttillstånd och författare. Du kan också generera CSV-filen för att hämta den aktuella ögonblicksbilden av ämnena i DITA-kartan.

**Hantera metadata och ändra dokumentstatus**

Du kan lägga till taggar i ett enskilt ämne eller använda funktionen för grupptaggning för att lägga till flera taggar i flera ämnen, en DITA-karta eller en delkarta. Du kan också ändra dokumentläget för alla markerade ämnen till nästa möjliga gemensamma dokumentläge.

<img src="assets/web-editor-metadata-panel.png" alt="hantera metadata" width="600">

**Generera multimedierapport**

Du kan generera multimedierapporten som innehåller detaljerad information om multimedia som används i referenserna på den aktuella kartan. Du kan filtrera och sortera multimediefilerna som visas i rapporten.
Du kan också generera CSV-filen för att hämta den aktuella ögonblicksbilden av multimedia som används i DITA-kartan.

<img src="assets/web-editor-reports-multimedia.png" alt="multimedierapport" width="600">

### Förbättrat användargränssnitt för granskningsfunktioner

Nu har AEM ett förbättrat användargränssnitt som hjälper dig att granska de ämnen som delas ut för granskning. I den senaste versionen har granskningsfunktionen följande förbättringar:

* Uppdaterat användargränssnitt
* Med villkorspanelen kan du markera innehållet enligt de tillgängliga villkoren i avsnittet
* Varje kommentar på kommentarspanelen är länkad till motsvarande text i det aktuella ämnet. Den hjälper dig att identifiera kommenterad text.
* Kommentarerna visas i den ordning som de kommenteras i dokumentet.
* Namnet på granskningsaktiviteten visas i granskningsarbetsflödet.
* Välj en rotmapp för granskningsaktiviteten som används för att matcha alla nyckelreferenser och ordlistor som används i granskningsinnehållet.
* Sammanhangsberoende verktygsfält som hjälper dig att snabbt markera eller genomstryka text
* Alternativ-menyn för att redigera eller ta bort egna kommentarer
* För inaktuella kommentarer har du tillgång till sida vid sida-vy som hjälper dig att jämföra den tidigare versionen av ämnet med den aktuella granskningsversionen.
* När du använder filtren filtreras kommentarerna på den högra panelen efter markeringen, och antalet kommentarer på den vänstra panelen uppdateras därefter.


   <img alt="granskningsuppgift" src="assets/comment-pop-up-panel.png" width="600">



### Översättningsförbättringar

Nu finns det användarvänliga förbättringar på kontrollpanelen Översättning som gör det enklare att översätta dokument från webbredigeraren.

**Skicka versionsetiketten till målversionen**

AEM kan du skicka källfilens etikett till målfilen. Det gör det enklare att identifiera källversionen för den översatta filen.

<img alt="översättningsetiketter" src="assets/translation-pass-source-label.png" width="600">

Om du t.ex. har källfiler med versionsetiketten Version 1.0 tillämpad kan du även skicka källetiketten (version 1.0) till den översatta filen.

**Tvinga synkronisering av osynkroniserade resurser**

Om du gör ändringar i vissa resurser markeras de som inte synkroniserade av AEM stödlinjer. Du kan antingen översätta de ändrade resurserna på nytt eller välja att inte längre synkronisera. Om du till exempel har gjort några mindre ändringar som verkligen inte behöver en översättning, kan du markera deras status som Synkroniserad.

<img src="assets/translation-version-diff.png" alt="översättningskort" width="600">

**Visa pågående översättningsprojekt för ett ämne eller en karta**

Vissa referenser på översättningsinstrumentpanelen kanske pågår. Nu finns det en funktion i AEM Guides som du kan använda för att visa listan över alla pågående översättningsprojekt (tillsammans med målspråket) som innehåller den valda referensen.


### Generera utdata i olika format från Web Editor

Nu kan du enkelt generera utdata för dina ämnen eller DITA-kartor från Web Editor. Du kan konfigurera olika utdataförinställningar som AEM Site, PDF, HTML5, JSON (ett headless output-format) och anpassade utdata. Du kan sedan använda dessa för att generera respektive utdata.

Du kan definiera attribut i dina DITA-avsnitt och sedan använda villkorsförinställningen för att tillämpa ett villkor när du publicerar utdata. Du kan också använda publiceringsfunktionen för baslinje för att selektivt publicera en specifik version av DITA-kartan eller ditt DITA-avsnitt.


### Söka efter och ersätta text på mappningsnivå

Med AEM stödlinjer kan du söka efter filer på en karta som innehåller viss text. Den sökta texten markeras i filerna. Nu kan du även ersätta det sökda ordet eller frasen med ett annat ord eller en annan fras i alla filer. Du kan välja **Ersätt alla** ikonen till höger överst i listan om du vill ersätta alla förekomster av den sökta termen i alla filer.

<img src="assets/map-find-replace.png" alt="sök efter ersättning" width="600">

### Ta bort och duplicera filer från databaspanelen

Nu kan du enkelt skapa en dubblett eller en kopia av en fil från **Alternativ** den markerade filens meny på databaspanelen. Som standard skapas filen med ett suffix (som `filename_1.extension`).

<img src="assets/options-menu-repo-view-file-level.png" alt="menyn för filalternativ " width="500">


### Andra förbättringar i Web Editor

* I AEM stödlinjer kan du utföra några vanliga åtgärder för bilder och mediefiler med hjälp av snabbmenyn. Nu kan du även hitta den valda bilden eller mediet i databasen eller förhandsgranska filen i resursgränssnittet.

* Namnet på den aktuella mappprofilen visas som etikett för ikonen för användarinställningar i huvudverktygsfältet. Detta hjälper dig att identifiera den mappprofil som du arbetar med.

* När du öppnar en karta i kartvyn visas den aktuella kartans titel i mitten av huvudverktygsfältet. Detta är praktiskt om du vill att användarna ska veta vilken karta som är öppen.


### Visa titeln i stället för UUID i syreredigeraren

Nu kan du välja AEM stödlinjer **Använd titel i redigeraren och karthanteraren** i Inställningar. Om du väljer det här alternativet visas filens titel på filens flik när den öppnas i redigeraren eller i DITA Maps Manager. Om du inte väljer det här alternativet visas filens UUID på filens flik.

### Microservice-baserad publicering för AEM Guides as a Cloud Service

Med den nya publiceringsmikrotjänsten kan du köra stora publiceringsarbetsbelastningar samtidigt AEM Guides as a Cloud Service och utnyttja den branschledande Adobe I/O Runtime serverlösa plattform.

För varje publiceringsbegäran AEM Guides as a Cloud Service körs en separat behållare som skalas vågrätt efter användarens önskemål. På så sätt kan du köra flera publiceringsbegäranden och få bättre prestanda.

Mer information finns i [Konfigurera ny mikrotjänstbaserad publicering för AEM Guides as a Cloud Service](https://experienceleague.adobe.com/docs/experience-manager-guides-learn/tutorials/knowledge-base/publishing/configure-microservices.md).

### PDF | Lägg till ett eget bokmärke i utdata från PDF

Nu kan du lägga till ett eget bokmärke för ett visst innehåll i det slutliga PDF-resultatet för enkel navigering. Detta läggs till i innehållsförteckningen som skapas från avsnittet eller avsnittsrubrikerna på din DITA-karta.

### PDF | Använd egen stil på innehållsförteckningsposter och ämnesinnehåll

I AEM kan du använda anpassade format för innehållsförteckningsposterna eller ett visst ämne i PDF. Du kan till exempel ändra färg på texten i innehållsförteckningen och ämnestiteln. Du kan också använda format på hela innehållet i ämnet.


### PDF | Formatera sidmarkören i fotnotskomponenten

Nu kan du formatera sidmarkören i fotnoterna. Du kan till exempel lägga till hakparenteser eller ändra deras färg. Dessa format gör det enkelt för användarna att identifiera sidmarkörerna i dokumentet.

### PDF | Ändringsfält för att ange ändrade ämnen i innehållsförteckningen

AEM Guides gör att du snabbt kan identifiera ändrade ämnen i innehållsförteckningen för PDF.  En ändringsbar visas till vänster om de ändrade ämnena i innehållsförteckningen. Du kan klicka på ämnet i innehållsförteckningen och visa detaljerade ändringar.

<img src="assets/change-marker-toc.png" alt="Ändra markör i innehållsförteckning " width="500">

## Åtgärdade problem

De buggar som har åtgärdats i olika områden listas nedan:

### Redigering

* Ändringar i HTML-koden för Web Editor orsakar problem med `<dl>` och `<dlentry>`. (11024)
* Vissa attribut behandlas inte som villkorliga och orsakar problem. (10895)
* Tre nivåer eller fler kapslade `<indexterm>` är inte kapslade vid export i PDF. (10799)
* Innehållet försvinner i en uppgiftsdel när du växlar från redigeringsvyn till källvyn. (10735)
* Granskningskommentarer placeras inte i en granskningsuppgift. (10625)
* **Ångra** eller **Gör om** fungerar inte korrekt på vissa filer. (10373)
* Anpassade metadata behålls inte vid kopiera och klistra in-åtgärd. (10367)
* Alternativet Ångra i XML-redigeraren tar användaren längst upp på sidan. (10091)
* Nodegenskaper tas bort efter att en resurs har kopierats och klistrats in. (10053)
* mimeType är hårdkodad för att skapa och uppdatera DITA-resurser. (8979)
* Versionens skaparnamn i Versionshistorik är fmdita-servicuser för filer som överförts via Assets UI. (8910)
* Det går inte att kopiera och klistra in innehållsfragment när AEM har installerats i molnet. (11315)
* Webbläsaren (webbredigeraren) låser sig när innehåll läses in med ett anpassat schema. (11211)

### Förvaltning

* Om du kopierar en DITA-mappningsresurs (från tillgångsgränssnittet) skapas felaktiga baslinjer i den kopierade resursen. (11218)
* Varningsmeddelande visas inte vid överföring av en fil som är större än den gräns som tillåts i AEM (2 GB som standard). (10817)
* Web Editor-Baseline | Beteendet för den senaste kolumnen skiljer sig åt i den nya baslinjepanelen i Web Editor. (10808)
* Översättning | Översättningsjobbet kommer inte igång på grund av ogiltig /libs/fmdita/i18n/ja.json. (10543)
* Översättning | Ett fel inträffar i ett omfångsöversättningsprojekt som skapats från översättningens kontrollpanel (mänsklig översättning). (10526)
* Översättning | Efterbearbetning blockeras för hela språkmappen vars resurser finns i ett aktivt översättningsprojekt. (10332)
* Flera popup-fönster visas för alla resurser om versionen ändras och sparas i Baslinjeredigeraren. (10399)
* Sessionsläckan inträffar vid `com.day.cq.search.impl.builder.QueryBuilderImpl.createResourceResolver(QueryBuilderImpl.java:210)`. (10279)

### Publicering

* Omgenerering av ämnen fungerar inte i vissa scenarier. (10635)
* Publiceringslyssnaren visar inte begärda data i informationsloggar, och den innehåller även skräppostloggar.( 10567)
* PDF | När du skapar en utdatainställning med alternativet Lägg till i mappprofil misslyckas genereringen av PDF med ett Null-pekarundantag. (10950)
* PDF | Problem uppstår när tabellrubriken roteras. (10555)
* PDF | Kapslade `<indexterm>` är inte kapslade vid export i PDF. (10521)
* PDF | Kapslade topicref i tillägg omformas alla till h1 i det temporära HTML. (10454)
* Baslinjepublicering misslyckas för PDF som genererats med FrameMaker Publishing Server 2020. (10551)
* PDF | Lägger till `xref` till en bild återges inte bilden på det genererade PDF. (11346)
* PDF | Taggen Bild lägger till ett visningsinfogat attribut i alla bilder. (10653)
* PDF | Utkastkommentarer är dolda som standard i genererade utdata. (10560)
* PDF | navtitle stöds inte för topichead. (10509)
