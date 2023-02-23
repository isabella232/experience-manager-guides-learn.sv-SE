---
title: Versionsinformation | Adobe Experience Manager Guides 4.2
description: Senaste utgåvan av Adobe Experience Manager Guides
exl-id: 8a7fef77-63af-462f-89c5-054ab31e079b
source-git-commit: 890d64aed5f4005e3f4d3143bc35804e39036ad3
workflow-type: tm+mt
source-wordcount: '3668'
ht-degree: 1%

---

# 4.2-utgåvan av Adobe Experience Manager Guides (februari 2023)

Den här versionsinformationen innehåller uppgraderingsinstruktioner, nya funktioner och förbättringar i version 4.2 av Adobe Experience Manager Guides (senare kallat *AEM stödlinjer*).

## Uppgradera till den senaste versionen

Du kan enkelt uppgradera din nuvarande version av AEM till version 4.2. Innan du uppgraderar till version 4.2 AEM handboken måste du tänka på följande:
* Om du använder version 4.0, 4.1 eller 4.1.x kan du uppgradera direkt till version 4.2.
* Om du använder version 3.8.5 måste du uppgradera till version 4.0 innan du uppgraderar till version 4.2.
* Om du använder en version som är tidigare än 3.8.5, se *AEM* i den produktspecifika installationsguiden.

>[!NOTE]
>
>Du måste installera AEM Service Pack innan du uppgraderar AEM Guides version.

Mer information finns i [Uppgraderingsinstruktioner](assets/Adobe-Experience-Manager-Guides-Upgrade-Instructions-EN.pdf).

## 4.2 | Versionsinformation

## Kompatibilitetsmatris

I det här avsnittet visas kompatibilitetsmatrisen för de program som stöds i AEM 4.2.

### Adobe Experience Manager

**Ej UID**
Version 6.5 Service Pack 15, 14, 13 eller 12

**UUID**
Version 6.5 Service Pack 15, 14, 13 eller 12

Mer information finns i *Tekniska krav* i guiden Installera och konfigurera Adobe Experience Manager Guides.

### FrameMaker och FrameMaker Publishing Server

| Frigör | FMPS 2022 | FMPS 2020 | Fm 2022 | Fm 2020 |
| --- | --- | --- | --- | --- |
| 4.2 (ej UUID) | 2022 eller senare | 2020.2 eller senare* | 2022 eller senare | 2020.3 eller senare |
| 4.2 (UUID) | 2022 eller senare | 2020.2 eller senare* | 2022 eller senare | 2020.4 eller senare |
|  |  |  |  |

*Originalplan och villkor skapade i AEM stöds i FMPS-versioner från och med 2020.2.

### Syrgasanslutning

| Frigör | Syrgasanslutningsfönster | Syrgasanslutning Mac | Redigera i syrgasfönster | Redigera i Syrgas Mac |
| --- | --- | --- |--- |--- |
| 4.2 (ej UUID) | 2.1-regular-4 | 2.1-regular-4 | 1.6 | 1.6 |
| 4.2 (UUID) | 2.8-uuid-8 | 2.8-uuid-8 | 2.3 | 2.3 |
|  |  |  |


## Nya funktioner och förbättringar

AEM innehåller många förbättringar och nya funktioner i version 4.2:

### Generera rapporter från Web Editor

AEM Guides innehåller en funktion i Web Editor som gör att du kan kontrollera att dina tekniska dokument är fullständiga och generera rapporter för dem.
Du kan visa ämneslistan och hantera metadata för alla referenser för den aktuella kartan från
**Rapporter** i Web Editor.

**Generera ämneslistvyn**

Du kan generera ämneslistan med detaljerad information om ämnen, som referenstyp, dokumenttillstånd och författare. Du kan också generera CSV-filen för att hämta den aktuella ögonblicksbilden av ämnena i DITA-kartan.

**Hantera metadata och ändra dokumentstatus**

Du kan lägga till taggar i ett enskilt ämne eller använda funktionen för grupptaggning för att lägga till flera taggar i flera ämnen, en DITA-karta eller en delkarta. Du kan också ändra dokumentläget för alla markerade ämnen till nästa möjliga gemensamma dokumentläge.

<img src="assets/web-editor-metadata-panel.png" alt="hantera metadata" width="600">

### Förbättrat användargränssnitt för granskningsfunktioner

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


<img alt="granskningsuppgift" src="assets/comment-pop-up-panel.png" width="600">


Mer information finns i *Granska ämnen och kartor* i guiden Använda Adobe Experience Manager-stödlinjer.

### Översättningsförbättringar

Nu finns det användarvänliga förbättringar på kontrollpanelen Översättning som gör det enklare att översätta dokument från webbredigeraren.


**Kolumnen Versionsetikett har lagts till på översättningsinstrumentpanelen**

På översättningens kontrollpanel kan du även se kolumnen Versionsetikett. Då visas etiketten för den valda versionen av källfilen. Detta kan hjälpa dig att markera alla filer med en viss etikett och översätta dem på en gång.

**Visa versionsskillnad för filer som inte är synkroniserade från översättningsinstrumentpanelen**

Nu kan du kontrollera skillnaderna mellan den valda versionen och den senaste översatta källversionen av ämnena. Du kan också välja att översätta **Slut på synkronisering** filer baserat på ändringar som gjorts mellan de två versionerna av ett ämne.

<img src="assets/translation-version-diff.png" alt="översättningskort" width="600">



**Skicka versionsetiketten till målversionen**

AEM kan du skicka källfilens etikett till målfilen. Det gör det enklare att identifiera källversionen för den översatta filen.

<img alt="översättningsetiketter" src="assets/translation-pass-source-label.png" width="600">

Om du t.ex. har källfiler med versionsetiketten Version 1.0 tillämpad kan du även skicka källetiketten (version 1.0) till den översatta filen.

**Tvinga synkronisering av osynkroniserade resurser**

Om du gör ändringar i vissa resurser markeras de som inte synkroniserade av AEM stödlinjer. Du kan antingen översätta de ändrade resurserna på nytt eller välja att inte längre synkronisera. Om du till exempel har gjort några mindre ändringar som verkligen inte behöver en översättning, kan du markera deras status som Synkroniserad.

**Visa pågående översättningsprojekt för ett ämne eller en karta**

Vissa referenser på översättningsinstrumentpanelen kanske pågår. Nu finns det en funktion i AEM Guides som du kan använda för att visa listan över alla pågående översättningsprojekt (tillsammans med målspråket) som innehåller den valda referensen.

Mer information finns i *Översätta dokument från Web Editor* i guiden Använda Adobe Experience Manager-stödlinjer.

### Generera utdata i olika format från Web Editor

Nu kan du enkelt generera utdata för dina ämnen eller DITA-kartor från Web Editor. Du kan konfigurera olika utdataförinställningar som AEM Site, PDF, HTML5, JSON (ett headless output-format) och anpassade utdata. Använd dessa för att generera respektive utdata. Du kan definiera attribut i dina DITA-avsnitt och sedan använda villkorsförinställningen för att tillämpa ett villkor när du publicerar utdata. Du kan också använda publiceringsfunktionen för baslinje för att selektivt publicera en specifik version av DITA-kartan eller ditt DITA-avsnitt.

**Hantera förinställningar för utdata för global profil och mappprofil**

I AEM Guides kan du skapa och hantera förinställningar för globala profiler och mappprofiler. Sedan kan du enkelt använda de här förinställningarna för att generera utdata för alla kartor som är relaterade till den globala profilen eller mappprofilen.

<img alt="lägg till förinställning" src="assets/add-global-output-preset.png" width="400">


Dessa globala förinställningar visas under **Utdata** -fliken för alla relaterade kartor. Du kan använda dem för att generera utdata för alla relaterade kartor. Du kan välja förinställningen som standardförinställning för PDF för att generera utdata från PDF. Du kan också **Redigera**, **Byt namn**, **Duplicera**, eller **Ta bort** en befintlig förinställning från **Alternativ** -menyn.

>[!NOTE]
>
>Endast administratörer på mappnivå kan skapa förinställningar för global profil och mappprofil.

### Söka efter och ersätta text på mappningsnivå

Nu kan du söka efter filer på en karta som innehåller viss text. Den sökta texten markeras i filerna. Du kan också ersätta det sökda ordet eller frasen med ett annat ord eller en annan fras i filerna. Välj **Ersätt enstaka förekomst** ikonen som ersätter den aktuella förekomsten och **Ersätt alla i filen** om du vill ersätta alla förekomster i den markerade filen. Du kan välja **Ersätt alla** om du vill ersätta alla förekomster av den sökta termen i alla filer.

<img src="assets/map-find-replace.png" alt="sök efter ersättning" width="600">


Som standard är alternativen **Checka ut filen före ersättning** och **Skapa ny version efter ersättning** är markerade, så en fil checkas ut innan du ersätter texten och en ny version skapas när texten har ersatts. Du kan också söka efter strängen i de indirekta referenserna på DITA-kartan. Som standard är detta inaktiverat, så sökningen utförs endast på direktreferenser.

### Layoutvyn i kartredigeraren


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

### Snabbgenereringspanelen

Nu finns AEM stödlinjer i panelen Snabbgenerering, som du kan använda för att snabbt generera och visa utdata för förinställningar som skapats för DITA-kartan.

<img src="assets/quick-generate-map-view.png" alt=" snabb genereringspanel" width="600">

I **Snabbgenerering** visas en lista med alla förinställningar för DITA-kartan. Du kan också snabbt visa utdata som genererats för förinställningarna. Ett meddelande om att åtgärden lyckades eller misslyckades visas när utdatagenereringen har slutförts. Du kan också visa felloggen som innehåller information om felet som uppstod under genereringsprocessen.

### Skapa en dynamisk baslinje baserad på etiketter

Nu kan du skapa dynamiska baslinjer baserat på etiketter med hjälp av AEM stödlinjer. Om du genererar en baslinje, hämtar en baslinje eller skapar ett översättningsprojekt med hjälp av en baslinje, hämtas filerna dynamiskt baserat på de uppdaterade etiketterna. Den här funktionen är praktisk eftersom du inte behöver ändra baslinjen när du uppdaterar etiketterna.

<img src="assets/dynamic-baseline.png" alt=" dynamisk baslinje" width="400">

### Ta bort och duplicera filer från databaspanelen

Nu kan du enkelt ta bort filer (en fil i taget) från **Alternativ** menyn för den valda filen från databaspanelen. En bekräftelse visas innan filen tas bort. Om det inte finns någon referens till filen från någon annan fil tas den bort och ett meddelande om att åtgärden lyckades visas.

<img src="assets/options-menu-repo-view-file-level.png" alt="menyn för filalternativ " width="500">

Du kan också skapa en dubblett eller en kopia av den markerade filen. Som standard skapas filen med ett suffix (som filename_1.extension).


### Andra förbättringar i Web Editor

* I AEM stödlinjer kan du utföra några vanliga åtgärder för bilder och mediefiler med hjälp av snabbmenyn. Nu kan du även hitta den valda bilden eller mediet i databasen eller förhandsgranska filen i resursgränssnittet.

* Namnet på den aktuella mappprofilen visas som etikett för ikonen för användarinställningar i huvudverktygsfältet. Detta hjälper dig att identifiera den mappprofil som du arbetar med.

* När du öppnar en karta i kartvyn visas den aktuella kartans titel i mitten av huvudverktygsfältet. Detta är praktiskt om du vill att användarna ska veta vilken karta som är öppen.

### Rensa valda versioner av filer

När du skapar och underhåller ditt innehåll kan många versioner skapas för dina DITA-filer i din databas. Med AEM Guides kan du rensa bort äldre versioner av dina DITA-filer från databasen och frigöra diskutrymme.

<img src="assets/preview-purge-report.png" alt="Förhandsgranska rensningsrapport" width="500">

AEM tar inte bort den första versionen av filen eller en version som ingår i en baslinje, eller har en etikett tillämpad på den. Rensningsåtgärden tar inte ens bort filer som ingår i en översättning eller ett granskningsarbetsflöde. Du kan välja hur många versioner som ska behållas och även välja att ta bort filer som är äldre än det angivna antalet dagar.

Innan du startar rensningsåtgärden kan du förhandsgranska rapporten och se vilka versioner som kommer att rensas. Du kan sedan välja att starta eller avbryta rensningsåtgärden.

<img src="assets/download-purge-report.png" alt="PDownload tömningsrapport" width="500">

När rensningsåtgärden är klar kan du kontrollera rensningsrapporten för att se de rensade filerna.

### Visa titeln i stället för UUID i syreredigeraren

Nu kan du välja AEM stödlinjer **Använd titel i redigeraren och karthanteraren** i Inställningar. Om du väljer det här alternativet visas filens titel på filens flik när den öppnas i redigeraren eller i DITA Maps Manager. Om du inte väljer det här alternativet visas filens UUID på filens flik.

### Metadatagränssnitt för förinställningar för PDF

Du kan ställa in metadata från utdataförinställningen för en DITA-karta. Du kan ange metadata för titel, författare, ämne och nyckelord. Dessa metadata mappas till metadata i filegenskaperna för utdata-PDF. Dessa metadata åsidosätter metadata som definierats på boknivå. Du kan definiera metadata specifikt för varje utdatainställning och skicka den vidare till PDF.

### PDF | PDF med ändringsfält som visar skillnaden mellan dokumentversioner

Nu kan du skapa en PDF som visar skillnaderna i innehåll mellan två versioner med hjälp av ändringsfältet. Du kan välja att jämföra den aktuella versionen med en baslinje från den tidigare versionen eller jämföra de två valda baslinjeversionerna.

<img src="assets/pdf-change-version.png" alt="pdf-change-version" width="600">

Ett ändringsfält visas i PDF för att ange det ändrade, infogade eller borttagna innehållet. Du kan även göra följande:
* Visa det infogade innehållet i grön färg och understruken
* Visa borttaget innehåll i röd färg och markerat med genomstrykning

### PDF | Variabelstöd för utdatasökväg och PDF-filnamn

Nu kan du även använda följande variabler för att definiera utdatasökväg och PDF-fil. Du kan definiera dessa alternativ med en eller flera variabler:
* `${map_filename}`
* `${map_title}`
* `${preset_name}`
* `${language_code}`
* `${map_parentpath}` (Endast för utdatasökväg)
* `${path_after_langfolder}` (Endast för utdatasökväg)

### PDF | Generera innehållsförteckning för DITA-kartor och ändra ordning på sidlayouter

Nu kan du även generera innehållsförteckningen i DITA-kartor med en avancerad PDF-inställning för mallen. Du kan välja att aktivera eller inaktivera visningen av de olika sidlayouterna och även ändra ordningen på deras position.

### PDF | Lägg till ett eget bokmärke i utdata från PDF

Nu kan du lägga till ett eget bokmärke för ett visst innehåll i det slutliga PDF-resultatet för enkel navigering. Detta läggs till i innehållsförteckningen som skapas från avsnittet eller avsnittsrubrikerna på din DITA-karta.

### PDF | Använd egen stil på innehållsförteckningsposter och ämnesinnehåll

I AEM kan du använda anpassade format för innehållsförteckningsposterna eller ett visst ämne i PDF. Du kan till exempel ändra färg på texten i innehållsförteckningen och ämnestiteln. Du kan också använda format på hela innehållet i ämnet.




## Åtgärdade problem

De buggar som har åtgärdats i olika områden listas nedan:

### Redigering

* Vänster panel bryts när en flik läggs till. (11126)
* Ändringar i HTML-koden för Web Editor orsakar problem med `<dl>` och `<dlentry>`. (11024)
* Vissa attribut behandlas inte som villkorliga och orsakar problem. (10895)
* Tre nivåer eller fler kapslade `<indexterm>` är inte kapslade vid export i PDF. (10799)
* Innehållet försvinner i en uppgiftsdel när du växlar från redigeringsvyn till källvyn. (10735)
* Granskningskommentarer placeras inte i en granskningsuppgift. (10625)
* `<conref>` anteckning inuti en paragraftagg visas inte i förhandsgranskningsläget. (10559)
* Hela listan tas bort om du placerar backstegstangenten i slutet av ett listobjekt. (10540)
* Skärmen visas som tom i Chrome v106 när du drar och släpper ett element från gränssnittet (till exempel från panelen Villkor). (10524)
* Knappen för automatiskt indrag saknas i verktygsfältet i **Källa** vy. (10448)
* Det första tecknet i ett listobjekt går förlorat ibland när listan redigeras.( 10447)
* **Ångra** eller **Gör om** fungerar inte korrekt på vissa filer. (10373)
* Anpassade metadata behålls inte vid kopiera och klistra in-åtgärd. (10367)
* Ett fel inträffar när du kopierar (Ctrl+C) och klistrar in (Ctrl+V) innehåll. (10304)
* Dispositionspanelen visar inte innehåll när den växlar från redigeringsläge till källäge. (10296)
* Submap skapas inte när den refererar till en huvudkarta i DITA-mallar. (10231)
* Navigeringsproblem uppstår i Web Editor efter 4.0-uppgraderingen. (10159)
* Alternativet Ångra i XML-redigeraren tar användaren längst upp på sidan. (10091)
* Nodegenskaper tas bort efter att en resurs har kopierats och klistrats in. (10053)
* SVG-filer som lagts till i DITA-avsnitt visas inte i redigerarens förhandsgranskningsläge. (10010)
* Sökresultaten för att söka och ersätta i Web Editor kan inte läsas i mörkt läge. (9978)
* Det finns ingen inläsare när en karta skapas från mappningsmallen. (9891)
* Conref i ämnesmallen fungerar inte och det hash-id som kopieras uppdateras inte i innehållskopian. (9890)
* Inget alternativ visas för att bläddra bland ämnen eller mappningsmallar i undermapparna till ämnet eller mappningsmappen. (9889)
* Det finns inget alternativ för att skapa en ny mall i undermapparna till ämnen eller kartor. (9888)
* XML-redigeraren uppdaterar inte bilderna i ämnen. (9500)
* mimeType är hårdkodad för att skapa och uppdatera DITA-resurser. (8979)
* Ett vanligt bindestreck infogas när du väljer Hårt bindestreck i dialogrutan **Infoga specialtecken** -dialogrutan. (8919)
* Versionens skaparnamn i Versionshistorik är fmdita-servicuser för filer som överförts via Assets UI. (8910)
* Redigeringsalternativet fungerar inte för bilder när du arbetar i kolumnvyn i resursgränssnittet. (8758)
* DITA-avsnittet uppdateras inte automatiskt med ändringar gjorda på **Egenskaper** sida. (8745)
* När du flyttar element inom avsnittet i Web Editor skrivs de tilldelade ID:n för element över av automatiskt tilldelade ID:n. (7895)

### Förvaltning

* Om du kopierar en DITA-mappningsresurs (från tillgångsgränssnittet) skapas felaktiga baslinjer i den kopierade resursen. (11218)
* Varningsmeddelande visas inte vid överföring av en fil som är större än den gräns som tillåts i AEM (2 GB som standard). (10817)
* Web Editor-Baseline | Beteendet för den senaste kolumnen skiljer sig åt i den nya baslinjepanelen i Web Editor. (10808)
* Översättning | Översättningsjobbet kommer inte igång på grund av ogiltig /libs/fmdita/i18n/ja.json. (10543)
* Översättning | Ett fel inträffar i ett omfångsöversättningsprojekt som skapats från översättningens kontrollpanel (mänsklig översättning). (10526)
* Översättning | Efterbearbetning blockeras för hela språkmappen vars resurser finns i ett aktivt översättningsprojekt. (10332)
* Översättning| Metadata och taggar sprids inte till de översatta kopiorna. (4696)
* Flera popup-fönster visas för alla resurser om versionen ändras och sparas i Baslinjeredigeraren. (10399)
* Sessionsläckan inträffar på com.day.cq.search.impl.builder.QueryBuilderImpl.createResourceResolver(QueryBuilderImpl.java:210). (10279)
* Videofilen saknas från baslinjen om den överordnade mappen innehåller utrymme i namnet. (10031)

### Publicering

* Omgenerering av ämnen fungerar inte i vissa scenarier. (10635)
* Publicering i PDF misslyckas när utdata genereras för en dubblettförinställning (för en befintlig förinställning). (10584)
* Knappen Visa logg fungerar inte om genereringen av PDF misslyckas för en förinställning. (10576)
* Publiceringslyssnaren visar inte begärda data i informationsloggar, och den innehåller även skräppostloggar.( 10567)
* PDF | Det går inte att skapa PDF med ett Null-pekarundantag. (10950)
* PDF | conkeyref löses inte i genererade utdata. (10564)
* PDF | Problem uppstår med metadata för en karta som behöver refereras till i utdata från PDF.( 10556)
* PDF | Problem uppstår när tabellrubriken roteras. (10555)
* PDF | Problem uppstår vid borttagning av ämnen med processing role=&#39;resource-only&#39;. (10554)
* PDF | Tomma nyckeltal visas i utdata från PDF. (10553)
* PDF | Kapslade `<indexterm>` är inte kapslade vid export i PDF. (10521)
* PDF | Inbyggd PDF använder inline-format i stället för klassnamn för de genererade taggarna. (10498)
* PDF | Kapslade topicref i tillägg omformas alla till h1 i det temporära HTML.( 10454)
* PDF | Det går inte att dölja ämnen som ligger före varandra i innehållsförteckningen. (10355)
* PDF | Tabellens bildruteattribut sprids inte till det temporära HTML (som klass). (10353)
* PDF | Temporära HTML-filer lägger till klasserna colsep och rowsep i <td> och <th> även om deras värde är 0 i käll-DITA. (10352)
* PDF | Om du startar om sidnummer i kapitellayouten startas numreringen slumpmässigt från slutet av föregående kapitel. (10154)
* PDF | Nyckelreferenser för nyckeldefinitioner med bilder eller externa länkar kommer inte att matchas. (10063)
* PDF | Bilaga visas som ett kapitel i genererad PDF. (9829)
* Fliken Mall i xml-redigeraren visas inte för mappprofiladministratörer. (10266)
* Baslinjepublicering misslyckas för PDF som genererats med FrameMaker Publishing Server 2020. (10551)
* Ett programfel inträffar när du klickar på knappen Redigera efter att ha markerat alla förinställningar via kryssrutan Utdatainställningar i snabbgenereringsfönstret. (10388)
* Om fliken Utdata i Web Editor har fler förinställningar går det inte att rulla avsnittet med förinställningar lodrätt och inte alla tillgängliga förinställningar visas. (9787)
* Det går inte att ta bort förinställningar från utdataarbetsflödet vid publicering via redigeraren. (9100)
* Peer-länken återges som normal text i stället för som en länk på den genererade sidan. (7774)

### Känt fel

Adobe har identifierat följande kända problem i AEM 4.2-versionen:

* Användare kan utföra granskningsåtgärder även när granskningsuppgifterna har slutförts.
