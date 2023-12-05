---
title: Versionsinformation | Nyheter i Adobe Experience Manager Guides 4.2
description: Läs om de nya och förbättrade funktionerna i 4.2-utgåvorna av Adobe Experience Manager Guides
source-git-commit: 880cd344ceb65ea339be699ebcad41c0d62e168a
workflow-type: tm+mt
source-wordcount: '2423'
ht-degree: 0%

---

# Nyheter i version 4.2 av Adobe Experience Manager Guides (februari 2023)

I den här artikeln beskrivs de nya och förbättrade funktionerna i version 4.2 av Adobe Experience Manager Guides (kallas senare *AEM stödlinjer*).

Mer information om uppgraderingsinstruktioner, kompatibilitetsmatris och problemen som åtgärdas i den här versionen finns i [Versionsinformation](release-notes-4.2.md) artikel.

## Generera rapporter från Web Editor

AEM Guides innehåller en funktion i Web Editor som gör att du kan kontrollera att dina tekniska dokument är fullständiga och generera rapporter för dem.
Du kan visa ämneslistan och hantera metadata för alla referenser för den aktuella kartan från
**Rapporter** i Web Editor.

**Generera ämneslistvyn**

Du kan generera ämneslistan med detaljerad information om ämnen, som referenstyp, dokumenttillstånd och författare. Du kan också generera CSV-filen för att hämta den aktuella ögonblicksbilden av ämnena i DITA-kartan.

**Hantera metadata och ändra dokumentstatus**

Du kan lägga till taggar i ett enskilt ämne eller använda funktionen för grupptaggning för att lägga till flera taggar i flera ämnen, en DITA-karta eller en delkarta. Du kan också ändra dokumentläget för alla markerade ämnen till nästa möjliga gemensamma dokumentläge.

<img src="assets/web-editor-metadata-panel.png" alt="hantera metadata" width="600">

## Förbättrat användargränssnitt för granskningsfunktioner

Nu har AEM ett förbättrat användargränssnitt som hjälper dig att granska de ämnen som delas ut för granskning. I den senaste versionen har granskningsfunktionen följande förbättringar:

* Uppdaterat användargränssnitt
* Med villkorspanelen kan du markera innehållet enligt de tillgängliga villkoren i ämnet.
* Varje kommentar på kommentarspanelen är länkad till motsvarande text i det aktuella ämnet. Den hjälper dig att identifiera kommenterad text.
* Kommentarerna visas i den ordning som de kommenteras i dokumentet.
* Namnet på granskningsaktiviteten visas i granskningsarbetsflödet.
* Välj en rotmapp för granskningsaktiviteten som används för att matcha alla nyckelreferenser och ordlistor som används i granskningsinnehållet.
* Sammanhangsberoende verktygsfält som hjälper dig att snabbt markera eller genomstryka text.
* Alternativ-menyn för att redigera eller ta bort egna kommentarer.
* För inaktuella kommentarer har du tillgång till sida vid sida-vy som hjälper dig att jämföra den tidigare versionen av ämnet med den aktuella granskningsversionen
* När du använder filtren filtreras kommentarerna på den högra panelen efter markeringen, och antalet kommentarer på den vänstra panelen uppdateras därefter.


<img alt="granskningsåtgärd" src="assets/comment-pop-up-panel.png" width="600">


Mer information finns i *Granska ämnen och kartor* i guiden Använda Adobe Experience Manager-stödlinjer.

## Översättningsförbättringar

Nu finns det användarvänliga förbättringar på kontrollpanelen Översättning som gör det enklare att översätta dokument från webbredigeraren.


**Kolumnen Versionsetikett har lagts till på översättningsinstrumentpanelen**

På översättningens kontrollpanel kan du även se kolumnen Versionsetikett. Då visas etiketten för den valda versionen av källfilen. Detta kan hjälpa dig att markera alla filer med en viss etikett och översätta dem på en gång.

**Visa versionsskillnad för filer som inte är synkroniserade från översättningsinstrumentpanelen**

Nu kan du kontrollera skillnaderna mellan den valda versionen och den senaste översatta källversionen av ämnena. Du kan också välja att översätta **Slut på synkronisering** filer baserat på ändringar som gjorts mellan de två versionerna av ett ämne.

<img src="assets/translation-version-diff.png" alt="översättningskort" width="600">



**Skicka versionsetiketten till målversionen**

Med AEM stödlinjer kan du skicka källfilens etikett till målfilen. Det gör det enklare att identifiera källversionen för den översatta filen.

<img alt="översättningsetiketter" src="assets/translation-pass-source-label.png" width="600">

Om du t.ex. har källfiler med versionsetiketten Version 1.0 tillämpad kan du även skicka källetiketten (version 1.0) till den översatta filen.

**Tvinga synkronisering av osynkroniserade resurser**

Om du gör ändringar i vissa resurser markeras de som inte synkroniserade av AEM stödlinjer. Du kan antingen översätta de ändrade resurserna på nytt eller välja att inte längre synkronisera. Om du till exempel har gjort några mindre ändringar som verkligen inte behöver en översättning, kan du markera deras status som Synkroniserad.

**Visa pågående översättningsprojekt för ett ämne eller en karta**

Vissa referenser på översättningsinstrumentpanelen kanske pågår. Nu finns det en funktion i AEM Guides som du kan använda för att visa listan över alla pågående översättningsprojekt (tillsammans med målspråket) som innehåller den valda referensen.

Mer information finns i *Översätta dokument från Web Editor* i guiden Använda Adobe Experience Manager-stödlinjer.

## Generera utdata i olika format från Web Editor

Nu kan du enkelt generera utdata för dina ämnen eller DITA-kartor från Web Editor. Du kan konfigurera olika utdataförinställningar som AEM Site, PDF, HTML5, JSON (ett headless output-format) och anpassade utdata. Använd dessa för att generera respektive utdata. Du kan definiera attribut i dina DITA-avsnitt och sedan använda villkorsförinställningen för att tillämpa ett villkor när du publicerar utdata. Du kan också använda publiceringsfunktionen Baslinje för att selektivt publicera en specifik version av DITA-kartan eller -avsnittet.

**Hantera förinställningar för utdata för global profil och mappprofil**

I AEM Guides kan du skapa och hantera förinställningar för globala profiler och mappprofiler. Sedan kan du enkelt använda de här förinställningarna för att generera utdata för alla kartor som är relaterade till den globala profilen eller mappprofilen.

<img alt="lägg till förinställning" src="assets/add-global-output-preset.png" width="400">


Dessa globala förinställningar visas under **Utdata** -fliken för alla relaterade kartor. Du kan använda dem för att generera utdata för alla relaterade kartor. Du kan välja förinställningen som standardförinställning för PDF för att generera utdata från PDF. Du kan också **Redigera**, **Byt namn**, **Duplicera**, eller **Ta bort** en befintlig förinställning från **Alternativ** -menyn.

>[!NOTE]
>
>Endast administratörer på mappnivå kan skapa förinställningar för global profil och mappprofil.

## Söka efter och ersätta text på mappningsnivå

Nu kan du söka efter filer på en karta som innehåller viss text. Den sökta texten markeras i filerna. Du kan också ersätta det sökda ordet eller frasen med ett annat ord eller en annan fras i filerna. Välj **Ersätt enstaka förekomst** ikonen som ersätter den aktuella förekomsten och **Ersätt alla i filen** om du vill ersätta alla förekomster i den markerade filen. Du kan välja **Ersätt alla** om du vill ersätta alla förekomster av den sökta termen i alla filer.

<img src="assets/map-find-replace.png" alt="sök och ersätt" width="600">


Som standard är alternativen **Checka ut filen före ersättning** och **Skapa ny version efter ersättning** är markerade, så en fil checkas ut innan du ersätter texten och en ny version skapas när texten har ersatts. Du kan också söka efter strängen i de indirekta referenserna på DITA-kartan. Som standard är detta inaktiverat, så sökningen utförs endast på direktreferenser.

## Layoutvyn i kartredigeraren


Nu kan du visa den fullständiga layouten för en DITA-karta i kartredigeraren. När du öppnar en karta för redigering öppnas layoutvyn i kartredigeraren. I den här vyn kan du se mappningshierarkin i en trädvy. Du kan också redigera och ordna eller strukturera ämnen i en karta.

<img src="assets/layout-view-map.png" alt=" mappningslayoutvy" width="600">

Layoutvyn innehåller ett separat verktygsfält som du kan använda för att utföra många åtgärder på de ämnen som finns på en karta.
Du kan infoga ämnesreferenser, ämnesgrupper och nyckeldefinitioner på en karta. Du kan ordna om ämnen som finns på en karta genom att flytta dem uppåt, nedåt, åt vänster eller åt höger. Du kan också dra och släppa ämnen för att flytta dem på en karta. Karteditorn innehåller även ikoner för att låsa eller låsa upp filer, kontrollera versionshistoriken och göra en versionsetiketthantering.


I layoutvyn finns även **Visningsalternativ** om du vill visa eller dölja radnummer, visa eller dölja kryssrutan eller visa filnamnet eller titeln för ämnena i en karta.
Du kan också visa ämnen baserat på villkorsstyrda filter.

Förutom att ordna ämnen i kartfilen kan du även lägga till, flytta, kopiera, klistra in eller ta bort referenser med **Alternativ** -menyn som är tillgänglig för ett element i layoutvyn.

<img src="assets/layout-inline-attributes.png" alt=" mappningslayoutattribut" width="600">


På den högra panelen visas Innehållsegenskaper och Kartegenskaper i layoutvyn i kartredigeraren. Nu kan du även ange metadatainformation för avsnitten eller kartan. Du kan definiera navigeringstiteln, länktexten, den korta beskrivningen och nyckelorden för det markerade ämnet eller kartan.

Mer information finns i *Layoutvyn* i guiden Använda Adobe Experience Manager-stödlinjer.

## Snabbgenereringspanelen

Nu finns AEM stödlinjer i panelen Snabbgenerering, som du kan använda för att snabbt generera och visa utdata för förinställningar som skapats för DITA-kartan.

<img src="assets/quick-generate-map-view.png" alt=" snabb genereringspanel" width="600">

I **Snabbgenerering** visas en lista med alla förinställningar för DITA-kartan. Du kan också snabbt visa utdata som genererats för förinställningarna. Ett meddelande om att åtgärden lyckades eller misslyckades visas när utdatagenereringen har slutförts. Du kan också visa felloggen som innehåller information om felet som uppstod under genereringsprocessen.

## Skapa en dynamisk baslinje baserad på etiketter

Nu kan du skapa dynamiska baslinjer baserat på etiketter med hjälp av AEM stödlinjer. Om du genererar en baslinje, hämtar en baslinje eller skapar ett översättningsprojekt med hjälp av en baslinje, hämtas filerna dynamiskt baserat på de uppdaterade etiketterna. Den här funktionen är praktisk eftersom du inte behöver ändra baslinjen när du uppdaterar etiketterna.

<img src="assets/dynamic-baseline.png" alt=" dynamisk baslinje" width="400">

## Ta bort och duplicera filer från databaspanelen

Nu kan du enkelt ta bort filer (en fil i taget) från **Alternativ** den valda filens meny från databaspanelen. En bekräftelse visas innan filen tas bort. Om det inte finns någon referens till filen från någon annan fil tas den bort och ett meddelande om att åtgärden lyckades visas.

<img src="assets/options-menu-repo-view-file-level.png" alt="menyn för filalternativ " width="500">

Du kan också skapa en dubblett eller en kopia av den markerade filen. Som standard skapas filen med ett suffix (som filename_1.extension).


## Andra förbättringar i Web Editor

* I AEM stödlinjer kan du utföra några vanliga åtgärder för bilder och mediefiler med hjälp av snabbmenyn. Nu kan du även hitta den valda bilden eller mediet i databasen eller förhandsgranska filen i resursgränssnittet.

* Namnet på den aktuella mappprofilen visas som etikett för ikonen för användarinställningar i huvudverktygsfältet. Detta hjälper dig att identifiera den mappprofil som du arbetar med.

* När du öppnar en karta i kartvyn visas den aktuella kartans titel i mitten av huvudverktygsfältet. Detta är praktiskt om du vill att användarna ska veta vilken karta som är öppen.

## Rensa valda versioner av filer

När du skapar och underhåller ditt innehåll kan många versioner skapas för dina DITA-filer i din databas. Med AEM Guides kan du rensa bort äldre versioner av dina DITA-filer från databasen och frigöra diskutrymme.

<img src="assets/preview-purge-report.png" alt="Förhandsgranska rensningsrapport" width="500">

AEM tar inte bort den första versionen av filen eller en version som ingår i en baslinje, eller har en etikett tillämpad på den. Rensningsåtgärden tar inte ens bort filer som ingår i en översättning eller ett granskningsarbetsflöde. Du kan välja hur många versioner som ska behållas och även välja att ta bort filer som är äldre än det angivna antalet dagar.

Innan du startar rensningsåtgärden kan du förhandsgranska rapporten och se vilka versioner som kommer att rensas. Du kan sedan välja att starta eller avbryta rensningsåtgärden.

<img src="assets/download-purge-report.png" alt="PDownload tömningsrapport" width="500">

När rensningsåtgärden är klar kan du kontrollera rensningsrapporten för att se de rensade filerna.

## Visa titeln i stället för UUID i syreredigeraren

Nu kan du välja AEM stödlinjer **Använd titel i redigeraren och karthanteraren** i Inställningar. Om du väljer det här alternativet visas filens titel på filens flik när den öppnas i redigeraren eller i DITA Maps Manager. Om du inte väljer det här alternativet visas filens UUID på filens flik.

## Metadatagränssnitt för förinställningar för PDF

Du kan ställa in metadata från utdataförinställningen för en DITA-karta. Du kan ange metadata för titel, författare, ämne och nyckelord. Dessa metadata mappas till metadata i filegenskaperna för utdata-PDF. Dessa metadata åsidosätter metadata som definierats på boknivå. Du kan definiera metadata specifikt för varje utdatainställning och skicka den vidare till PDF.

## PDF | PDF med ändringsfält som visar skillnaden mellan dokumentversioner

Nu kan du skapa en PDF som visar skillnaderna i innehåll mellan två versioner med hjälp av ändringsfältet. Du kan välja att jämföra den aktuella versionen med en baslinje från den tidigare versionen eller jämföra de två valda baslinjeversionerna.

<img src="assets/pdf-change-version.png" alt="pdf-change-version" width="600">

Ett ändringsfält visas i PDF för att ange det ändrade, infogade eller borttagna innehållet. Du kan även göra följande:
* Visa det infogade innehållet i grön färg och understruken
* Visa borttaget innehåll i röd färg och markerat med genomstrykning

## PDF | Variabelstöd för utdatasökväg och PDF-filnamn

Nu kan du även använda följande variabler för att definiera utdatasökväg och PDF-fil. Du kan definiera dessa alternativ med en eller flera variabler:
* `${map_filename}`
* `${map_title}`
* `${preset_name}`
* `${language_code}`
* `${map_parentpath}` (Endast för utdatasökväg)
* `${path_after_langfolder}` (Endast för utdatasökväg)

## PDF | Generera innehållsförteckning för DITA-kartor och ändra ordning på sidlayouter

Nu kan du även generera innehållsförteckningen i DITA-kartor med en avancerad PDF-inställning för mallen. Du kan välja att aktivera eller inaktivera visningen av de olika sidlayouterna och även ändra ordningen på deras position.

## PDF | Lägg till ett eget bokmärke i utdata från PDF

Nu kan du lägga till ett eget bokmärke för ett visst innehåll i det slutliga PDF-resultatet för enkel navigering. Detta läggs till i innehållsförteckningen som skapas från avsnittet eller avsnittsrubrikerna på din DITA-karta.

## PDF | Använd egen stil på innehållsförteckningsposter och ämnesinnehåll

I AEM kan du använda anpassade format för innehållsförteckningsposterna eller ett visst ämne i PDF. Du kan till exempel ändra färg på texten i innehållsförteckningen och ämnestiteln. Du kan också använda format på hela innehållet i ämnet.
