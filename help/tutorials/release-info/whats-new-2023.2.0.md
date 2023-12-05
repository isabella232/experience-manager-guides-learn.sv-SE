---
title: Versionsinformation | Adobe Experience Manager Guides as a Cloud Service, februari 2023-versionen
description: Februariversion av Adobe Experience Manager Guides as a Cloud Service
source-git-commit: 880cd344ceb65ea339be699ebcad41c0d62e168a
workflow-type: tm+mt
source-wordcount: '1426'
ht-degree: 0%

---

# Nyheter i februari 2023-versionen av Adobe Experience Manager Guides as a Cloud Service

I den här artikeln beskrivs de nya och förbättrade funktionerna i version från februari 2023 av Adobe Experience Manager Guides (senare kallad *AEM stödlinjer as a Cloud Service*).

Mer information om uppgraderingsinstruktioner, kompatibilitetsmatris och problemen som åtgärdas i den här versionen finns i [Versionsinformation](release-notes-2023.2.0.md) artikel.


## Generera rapporter från Web Editor

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

## Förbättrat användargränssnitt för granskningsfunktioner

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


  <img alt="granskningsåtgärd" src="assets/comment-pop-up-panel.png" width="600">



## Översättningsförbättringar

Nu finns det användarvänliga förbättringar på kontrollpanelen Översättning som gör det enklare att översätta dokument från webbredigeraren.

**Skicka versionsetiketten till målversionen**

Med AEM stödlinjer kan du skicka källfilens etikett till målfilen. Det gör det enklare att identifiera källversionen för den översatta filen.

<img alt="översättningsetiketter" src="assets/translation-pass-source-label.png" width="600">

Om du t.ex. har källfiler med versionsetiketten Version 1.0 tillämpad kan du även skicka källetiketten (version 1.0) till den översatta filen.

**Tvinga synkronisering av osynkroniserade resurser**

Om du gör ändringar i vissa resurser markeras de som inte synkroniserade av AEM stödlinjer. Du kan antingen översätta de ändrade resurserna på nytt eller välja att inte längre synkronisera. Om du till exempel har gjort några mindre ändringar som verkligen inte behöver en översättning, kan du markera deras status som Synkroniserad.

<img src="assets/translation-version-diff.png" alt="översättningskort" width="600">

**Visa pågående översättningsprojekt för ett ämne eller en karta**

Vissa referenser på översättningsinstrumentpanelen kanske pågår. Nu finns det en funktion i AEM Guides som du kan använda för att visa listan över alla pågående översättningsprojekt (tillsammans med målspråket) som innehåller den valda referensen.


## Generera utdata i olika format från Web Editor

Nu kan du enkelt generera utdata för dina ämnen eller DITA-kartor från Web Editor. Du kan konfigurera olika utdataförinställningar som AEM Site, PDF, HTML5, JSON (ett headless output-format) och anpassade utdata. Du kan sedan använda dessa för att generera respektive utdata.

Du kan definiera attribut i dina DITA-avsnitt och sedan använda villkorsförinställningen för att tillämpa ett villkor när du publicerar utdata. Du kan också använda publiceringsfunktionen Baslinje för att selektivt publicera en specifik version av DITA-kartan eller -avsnittet.


## Söka efter och ersätta text på mappningsnivå

Med AEM stödlinjer kan du söka efter filer på en karta som innehåller viss text. Den sökta texten markeras i filerna. Nu kan du även ersätta det sökda ordet eller frasen med ett annat ord eller en annan fras i alla filer. Du kan välja **Ersätt alla** ikonen till höger överst i listan om du vill ersätta alla förekomster av den sökta termen i alla filer.

<img src="assets/map-find-replace.png" alt="sök och ersätt" width="600">

## Ta bort och duplicera filer från databaspanelen

Nu kan du enkelt skapa en dubblett eller en kopia av en fil från **Alternativ** den markerade filens meny på databaspanelen. Som standard skapas filen med ett suffix (som `filename_1.extension`).

<img src="assets/options-menu-repo-view-file-level.png" alt="menyn för filalternativ " width="500">


## Andra förbättringar i Web Editor

* I AEM stödlinjer kan du utföra några vanliga åtgärder för bilder och mediefiler med hjälp av snabbmenyn. Nu kan du även hitta den valda bilden eller mediet i databasen eller förhandsgranska filen i resursgränssnittet.

* Namnet på den aktuella mappprofilen visas som etikett för ikonen för användarinställningar i huvudverktygsfältet. Detta hjälper dig att identifiera den mappprofil som du arbetar med.

* När du öppnar en karta i kartvyn visas den aktuella kartans titel i mitten av huvudverktygsfältet. Detta är praktiskt om du vill att användarna ska veta vilken karta som är öppen.


## Visa titeln i stället för UUID i syreredigeraren

Nu kan du välja AEM stödlinjer **Använd titel i redigeraren och karthanteraren** i Inställningar. Om du väljer det här alternativet visas filens titel på filens flik när den öppnas i redigeraren eller i DITA Maps Manager. Om du inte väljer det här alternativet visas filens UUID på filens flik.

## Microservice-baserad publicering för AEM Guides as a Cloud Service

Med den nya publiceringsmikrotjänsten kan du köra stora publiceringsarbetsbelastningar samtidigt AEM Guides as a Cloud Service och utnyttja den branschledande Adobe I/O Runtime serverlösa plattform.

För varje publiceringsbegäran AEM Guides as a Cloud Service körs en separat behållare som skalas vågrätt efter användarens önskemål. På så sätt kan du köra flera publiceringsbegäranden och få bättre prestanda.

Mer information finns i [Konfigurera ny mikrotjänstbaserad publicering för AEM Guides as a Cloud Service](https://experienceleague.adobe.com/docs/experience-manager-guides-learn/tutorials/knowledge-base/publishing/configure-microservices.md).

## PDF | Lägg till ett eget bokmärke i utdata från PDF

Nu kan du lägga till ett eget bokmärke för ett visst innehåll i det slutliga PDF-resultatet för enkel navigering. Detta läggs till i innehållsförteckningen som skapas från avsnittet eller avsnittsrubrikerna på din DITA-karta.

## PDF | Använd egen stil på innehållsförteckningsposter och ämnesinnehåll

I AEM kan du använda anpassade format för innehållsförteckningsposterna eller ett visst ämne i PDF. Du kan till exempel ändra färg på texten i innehållsförteckningen och ämnestiteln. Du kan också använda format på hela innehållet i ämnet.


## PDF | Formatera sidmarkören i fotnotskomponenten

Nu kan du formatera sidmarkören i fotnoterna. Du kan till exempel lägga till hakparenteser eller ändra deras färg. Dessa format gör det enkelt för användarna att identifiera sidmarkörerna i dokumentet.

## PDF | Ändringsfält för att ange ändrade ämnen i innehållsförteckningen

AEM Guides gör att du snabbt kan identifiera ändrade ämnen i innehållsförteckningen för PDF.  Det visas ett ändringsfält till vänster om de ändrade ämnena i innehållsförteckningen. Du kan klicka på ämnet i innehållsförteckningen och visa de detaljerade ändringarna.

<img src="assets/change-marker-toc.png" alt="Ändra markör i innehållsförteckning " width="500">
