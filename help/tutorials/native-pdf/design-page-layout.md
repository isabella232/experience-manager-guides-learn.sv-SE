---
title: Publiceringsfunktion för PDF | Designa en sidlayout
description: Lär dig hur du utformar sidlayouten för att presentera information i olika delar av PDF.
exl-id: b4d3bdc4-0d01-46eb-b182-540380220485
source-git-commit: a1367a6915e760e533bb984705f4be37596b5477
workflow-type: tm+mt
source-wordcount: '4649'
ht-degree: 0%

---


# Utforma en sidlayout {#design-page-layout}

När du skapar ett PDF-dokument har du olika avsnitt för olika typer av information. Ett PDF-dokument kan till exempel börja med en framsida eller en försättssida, som skulle innehålla företagets logotyp, boktitel eller versionsinformation. Då finns det kapitel, bilagor eller ordlistor. Varje avsnitt i ett PDF-dokument ser olika ut och det uppnås genom att sidlayouten skapas och anpassas.

När du utformar en sidlayout kan du definiera de olika elementen som utgör en sida. Du kan till exempel definiera sidstorlek, marginaler, sidhuvud och sidfot, orientering och andra sidspecifikationer på en sida. Med publiceringsfunktionen för PDF kan du utforma din sida enligt [Page Media-standarder](https://www.w3.org/TR/css-page-3/). De flesta inställningar som omfattas av Paged Media-standarderna kan enkelt anpassas med hjälp av Native PDF Publishing-funktionens användargränssnitt. För viss annan formatering på avancerad nivå kan du använda källvyn för att skriva egen CSS-kod.

När du har utformat sidlayouten måste du koppla de här layouterna till deras respektive avsnitt i inställningarna för sidlayout på PDF. Se [Skapa och anpassa sidlayouter](components-pdf-template.md#create-customize-page-layout) om du vill ha mer information om hur du skapar och öppnar en sidlayout för anpassning.

## Typer av sidlayouter {#types-of-page-layout}

Ett PDF-dokument innehåller vanligtvis följande avsnitt:

* Försättssida
* Innehållsförteckning
* Sifferlyft
* Tabellens lyft
* Kapitel- eller ämnessidor
* Ordlista
* Index
* Baksida

Dessa avsnitt behöver en motsvarande sidlayout för att visa informationen i ett visst format. Dessutom kan du ha en tom sida som används som utfyllnadstecken för att starta ett nytt kapitel från en udda eller jämn sida. I så fall kan du antingen använda standardsidlayouten eller skapa en sidlayout för en tom sida. Se [Skapa en ny sidlayout](components-pdf-template.md#create-page-layout) för mer information.

Inställningarna för sidlayout under **Template>Settings** kan du definiera vilken sidlayout som ska användas för olika avsnitt i PDF. Varje sidlayout kan ha olika varianter för första, högra och vänstra sidan.

### Skapa de första, högra eller vänstra sidlayoutvarianterna {#page-layout-variants}

Olika sidlayouter i PDF-mallen kan anpassas ytterligare genom att ha olika layoutvarianter för första, högra och vänstra sidan. Du kan utforma dessa sidor på ett annat sätt med hjälp av layoutdesignern.

>[!NOTE]
>
>Om du vill ha en enda sidlayout för ett avsnitt i boken behöver du inte skapa sidlayouterna Första, Höger eller Vänster.

Tänk på följande när du skapar sidlayouterna:

>[!NOTE]
>
>Följande punkter har tagit kapitelsidlayouten som exempel. Dessa punkter gäller dock även för andra sidlayouter.

* Om du vill använda en enda sidlayout för alla sidor i ett kapitel skapar du bara en enda kapitelsidlayout utan någon variant.

* Om du vill ha ett annat utseende och en annan känsla för den första sidan för kapitel i boken måste du skapa en layout för första sidan för kapitlen.

* Om du vill ha ett annat utseende och en annan känsla för alla sidor på vänster och höger sida i boken måste du skapa varianterna på vänster och höger sida för kapitelsidans layout.

* Om du vill att kapitlen ska börja från en udda eller jämn sida kan du välja att skapa en sidlayout för den tomma sidan. Den här sidlayouten används för att fylla mellanrummet mellan två kapitel så att kapitlet börjar från önskad udda eller jämn sida.

   >[!NOTE]
   >
   >Om du inte skapar en separat tom sidlayout används standardsidlayouten. Information om hur du skapar en sidlayout finns i [Skapa en ny sidlayout](components-pdf-template.md#create-page-layout).

I följande exempel får du hjälp med att skapa varianter av en sidlayout:

1. Skapa en kapitelsidlayout med hjälp av stegen under Skapa en ny sidlayout.

   En tom kapitelsidlayout skapas och läggs till under Sidlayouter.

   När du skapar en sidlayout öppnas den som standard även för redigering. På följande skärmbild visas en tom (standard) sidlayout:

   <img src="./assets/default-blank-page-layout.png" width="300">

   Sidhuvudet, sidfoten och innehållsområdet i en mall skapas som standard. Du kan enkelt anpassa dessa områden med de sidegenskaper, innehållsegenskaper och olika verktyg (som att infoga bilder, fält med mera) som finns i användargränssnittet.

   >[!NOTE]
   >
   >Om du vill ha en mer avancerad konfiguration kan du använda källvyn och lägga till din anpassade HTML- och CSS-kod.

1. Håll muspekaren över **Kapitel** layout och klicka **Alternativ** för att visa snabbmenyn.

1. Klicka eller hovra muspekaren över **Lägg till layoutvariant** och välj önskad sidlayout (Första, Vänster eller Höger) som du vill skapa.

Den valda sidlayouten skapas med en kopia av den grundläggande kapitellayouten. Det innebär att om du har gjort några ändringar i standardlayouten för kapitelsidor, kommer samma ändringar att replikeras i variantsidlayouten när sidlayouten skapas.

## Arbeta med sidegenskaperna för en sidlayout {#page-props-page-layout}

När du utformar en sidlayout är det viktigt att du har kontroll över olika sidegenskaper. Publiceringsfunktionen i PDF kapslar in alla större sidegenskaper under panelen Sidegenskaper. På panelen Sidegenskaper finns olika egenskaper i följande avsnitt:

>[!NOTE]
>
>Panelen Sidegenskaper kapslar in egenskaperna och följer regler som definierats under [Page Media-standarder](https://www.w3.org/TR/css-page-3/).

* **Sidstorlek** : Ange den sidstorlek som du vill använda för sidlayouten. I listrutan Sidstorlek kan du välja mellan över 15 sidstorlekar. Du kan också skapa en sidlayout med en anpassad sidstorlek, se [Ange sidstorlek](#set-page-size) för mer information.

* **Orientering** : Ange den sidorientering som ska användas för sidlayouten. Du kan välja mellan stående eller liggande sidorientering. Observera att du kan välja att använda olika orienteringar för olika sidvarianter i en sidlayout. Om innehållet till exempel innehåller en bred tabell eller en stor bild kan du skapa en liggande sidlayout och använda den layouten på den bredare tabellen eller bilden.

* **Visa rotation** : Ange den sida eller riktning som den ursprungliga översta sidan visas i efter rotation. Du kan välja mellan 90 grader medsols, 90 grader moturs eller 180 grader moturs. Detta är mycket användbart i en situation där du vill använda en kombination av stående och liggande layouter i utdata. Du kan till exempel använda stående som allmän sidlayout och du kan ange en liggande sidlayout för att återge breda tabeller. I så fall kan du ange att tabellinnehållet ska visas medsols 90 grader. På så sätt orienteras sidan liggande och innehållet roteras 90 grader för att kontinuiteten ska kunna bibehållas. Vi kommer att se hur detta uppnås som ett exempel senare i detta avsnitt.

* **Starta om numrering från** : Ange vilket sidnummer som sidlayouten ska börja från. Du kan till exempel ange att sidnumret ska startas om för varje kapitel. I så fall måste du ange egenskapen Starta om numrering från till 1 på layoutvarianten för första sidan i kapitelsidans layout.

* **Layout** : Ange sidmarginaler tillsammans med utfyllnad för övre, nedre, vänstra och högra sidor. Följande bild förklarar hur marginaler, utfyllnad och kanter återges runt innehållet. Observera att marginalen längst upp och längst ned på en sida innehåller sidhuvudet och sidfoten.

   <img src="./assets/margins-padding-illustration.png" width="300">

* **Bakgrund** : Inkludera en bild eller en färg som bakgrund i sidlayouten. För en bild kan du ange bildens höjd och bredd tillsammans med repeterings- och positionsegenskaper.

* **Fotnot** : Ange de egenskaper som fotnoterna ska visas i utdata. Du kan välja att ange marginaler och utfyllnadsegenskaper tillsammans med ett kantlinjeformat.

### Ange sidstorlek {#set-page-size}

Det första du behöver definiera i en sidlayout är sidstorleken. I Sidegenskaper finns det över 15 sidstorlekar som du kan välja för en sidlayout. Du kan också skapa en anpassad sidstorlek genom att utföra följande steg:

1. Öppna önskad sidlayout för redigering.

   >[!NOTE]
   >
   >Se [Anpassa en sidlayout](components-pdf-template.md#customize-page-layout) för att öppna en sidlayout för anpassning eller redigering.

1. Klicka på i den högra panelen **Sidegenskaper**.
1. I **Sidstorlek** nedrullningsbar lista, välja **Egen**.

   Fälten Sidbredd och Sidhöjd visas.

1. Ange önskade sidmått i dialogrutan **Sidbredd** och **Sidhöjd** fält.

   >[!NOTE]
   >
   >Några av de vanligaste enheterna är px (pixlar), pt (punkter), rem, em, % (procent) och in (tum).

### Använda sidorientering och vyrotation {#page-orientation-rotation}

Låt oss titta på ett exempel där en kombination av stående och liggande sidorientering och vyrotationsegenskaper används. I det här exemplet skapar vi en PDF med stående orientering som standard, men en tabell återges i liggande orientering med innehåll i 90-gradersvyn medurs. Resultatet ser ut ungefär så här:

<img src="./assets/portrait-landscape-page-layouts.png" width="400">

I ovanstående utdata visas informationen i kontaktlistan i liggande läge med innehållet roterat i 90 grader. Det återstående innehållet visas i normalt stående läge.

För att uppnå den här typen av utdata måste vi utföra följande huvudsakliga uppgifter:

1. Skapa en sidlayout med liggande orientering.

1. Ändra **Visa rotation** för att återge innehåll i 90°.

1. Skapa ett anpassat format för den nya sidlayouten.

1. Lägg till formatet i utdataklassdefinitionen för den tabell som ska återges i liggande sidlayout.

Utför följande steg för att utföra ovanstående åtgärder:

1. Skapa en sidlayout med liggande orientering.
   1. Skapa en liggande sidlayout med hjälp av stegen under Skapa en ny sidlayout.

   1. Klicka på i den högra panelen **Sidegenskaper**.

      <img src="./assets/page-properties-panel.png" width="300">
   1. Ändra **Orientering** till **Liggande**.

1. Ändra egenskapen Visa rotation om du vill återge innehåll 90° medsols.

   1. Välj **90° medsols** i listrutan Vyrotation.

   <img src="./assets/view-rotation-page-props.png" width="300">

   1. Klicka **Savel All** om du vill spara de uppdaterade sidlayoutegenskaperna.

1. Skapa ett anpassat format för den nya sidlayouten.
   1. Expandera den vänstra sidlisten och dubbelklicka på mallen som du vill skapa formatet i.

   1. Expandera avsnittet Formatmallar.

   1. Håll muspekaren över layoutformatmallen och klicka på (_Alternativ_ ... och välj Redigera.

      Layoutformatmallen öppnas för redigering.

   1. Högerklicka på **Andra format** och välja **Nytt format**.
      <img src="./assets/stylesheet-other-new-style.png" width="300">

   1. I popup-rutan Lägg till format anger du **liggande stil** i **klassnamn**.
      <img src="./assets/stylesheet-new-landscape-style.png" width="400">

   1. Klicka **Klar**.

      Ett nytt format med namnet `.landscape-style` skapas och läggs till i slutet av listan Andra format.

   1. Dubbelklicka på `.landscape-style` stil för att öppna den för redigering.

   1. Expandera **Sidnumrering** -egenskap.

   1. Retur `Landscape` i **Sidlayout** -egenskap.

      <img src="./assets/new-style-with-landscape-layout.png" width="500">

   1. Klicka **Savel All** om du vill spara de uppdaterade formategenskaperna.

1. Lägg till formatet i `outputclass` definition av den tabell som ska återges i liggande sidlayout.
   1. Öppna filen där du vill använda den nya sidlayouten i en DITA-filredigerare.

   1. Hitta `<table>` -element som ska återges i liggande läge.

   1. Markera tabellen genom att klicka på tabellelementet i den synliga sökvägen.

      <img src="./assets/new-style-table-element.png" width="400">

   1. Klicka på och öppna panelen Innehållsegenskaper i den högra panelen.

   1. Lägg till en ny i panelen Innehållsegenskaper **outputClass** egenskap med **liggande stil** som egenskapsvärde.

      <img src="./assets/new-style-table-outputclass.png" width="300">

1. Klicka **Savel All** för att spara den uppdaterade filen.
1. Generera utdata från PDF.

Tabellinnehållet återges i liggande läge i det slutliga PDF, vilket visas i början av exemplet.

### Lägga till en bakgrundsbild {#add-bg-image}

Beroende på dina behov kan det vara bra att lägga till en bakgrundsbild som visas på varje första sida i ett kapitel (PDF). Med bakgrundsegenskaperna under Sidegenskaper kan du enkelt lägga till en bakgrundsbild. Du kan välja att replikera bilden över en sida och placera bilden var som helst i sidans övre, nedre eller mitt.

Om du till exempel vill infoga en bakgrundsbild i mitten av innehållsområdet utför du följande steg:

1. Öppna önskad sidlayout för redigering.

   >[!NOTE]
   >
   >Se [Anpassa en sidlayout](components-pdf-template.md#customize-page-layout) för att öppna en sidlayout för anpassning eller redigering.

1. Klicka var som helst i innehållsområdet.

1. Klicka på i den högra panelen **Sidegenskaper**.

1. Expandera **Bakgrund** -avsnitt.

1. Klicka på bläddringsknappen i dialogrutan **Bildbana** platsfält.

1. Bläddra till och välj den bild som du vill använda som bakgrundsbild.

   Bilden infogas och replikeras för att täcka hela sidan.

1. Ändra bildstorleken genom att justera egenskaperna height och width.

   >[!NOTE]
   >
   >Du kan ange egenskaperna height eller width eftersom bilden skalas automatiskt för att behålla proportionerna.

1. Ange de andra egenskaperna för att justera hur du vill att bakgrundsbilden ska visas.

   * **Upprepa bakgrund** : Ange om du vill att bakgrunden ska upprepas eller inte.

   * **Bakgrundsposition** : Ange en position för bakgrundsbilden på sidan.

På följande skärmbild visas bakgrundsbilden med egenskapen Bakgrundsupprepa inställd på _ingen upprepning_ och egenskapen Bakgrundsposition är inställd på _mitten_.

<img src="./assets/background-image.png" width="500">

## Arbeta med sidhuvud och sidfot {#work-header-footer}

När du tar med information i ett sidhuvud eller en sidfot i en sidlayout upprepas informationen på alla sidor som använder den sidlayouten. Vanligtvis används sidhuvudsområdet för kapitel- eller ämnesrubriker och sidfotsområdet används för att visa sidnummer.

När du skapar en ny sidlayout skapas sidhuvuds- och sidfotsområdet som standard. Du kan göra många anpassningar i sidhuvuds- och sidfotsområdet i en sidlayout. Du kan till exempel infoga en bild (som en logotyp), variabler (som innehåller dynamisk information) eller statiskt innehåll.

### Ändra marginaler och linjer för sidhuvud och sidfot {#header-footer-margins}

Som standard är sidhuvud- och sidfotsmarginalerna inställda på 1 tum. Du kan ändra det här standardvärdet genom att ändra inställningen Marginal på panelen Sidegenskaper. Gör så här för att ändra sidhuvuds- och sidfotsstorlek:

1. Öppna önskad sidlayout för redigering.

   >[!NOTE]
   >
   >Se [Anpassa en sidlayout](components-pdf-template.md#customize-page-layout) för att öppna en sidlayout för anpassning eller redigering.

1. Klicka på i den högra panelen **Sidegenskaper**.
1. Expandera **Layout** -avsnitt.
1. Klicka på låsikonen bredvid **Marginal** -egenskap.
1. Om du vill ändra rubrikstorleken anger du det önskade värdet i fältet Övre marginal.

   >[!NOTE]
   >
   >Några av de vanligaste enheterna är px (pixlar), pt (punkter), rem, em, % (procent) och in (tum).

1. Om du vill ändra sidfotsstorleken anger du det önskade värdet i fältet Undre marginal.

Du kan utforma sidhuvuds- och sidfotsområdet så att det innehåller flera rader. Om du vill göra det lägger du till ett \&lt;p> tagg med Infoga HTML-element (<img src="./assets/insert-html-element-2.svg" width="25">) i sidhuvuds- och sidfotsområdet.

| _Developer Corner_: <img src="./assets/developer-corner-icon.svg" width="25"> |
|---|

Om du vill arbeta direkt med CSS- och HTML-koden kan du ändra marginalvärdena enligt följande kodutdrag:

```css
…

<meta name="page-style" content="size:A4 portrait;margin-top:3cm;margin-right:30pt;margin-bottom:1in;margin-left:90px;" />

…
```

>[!NOTE]
>
>I ovanstående exempel används olika enheter för att ange marginalvärden.

### Ta bort sidhuvud och sidfot {#remove-header-footer}

Sidhuvudet och sidfoten överlagras i de övre och nedre marginalerna. Tekniskt sett innebär det att om du vill ha ett sidhuvud och en sidfot i sidlayouten måste du reservera det utrymme som behövs i den övre och undre marginalen.

Om du inte vill att en sidlayout ska ha ett sidhuvud och en sidfot, finns det två sätt att uppnå detta:

* Om du vill behålla de övre och nedre marginalerna lämnar du sidhuvuds- och sidfotsområdet tomt.
* Om du inte vill behålla de övre och nedre marginalerna (som att utforma fram- och bakomliggande omslag för ett magasin) kan du ta bort marginalerna genom att ange egenskaperna för den övre och den nedre marginalen till 0. Detta lämnar inget utrymme för sidhuvudet och sidfoten.

### Lägga till en bild eller logotyp i sidhuvudet {#add-image-header}

Beroende på dina behov kan du lägga till en bild som visas i sidhuvudsområdet (eller någon annan del) i sidlayouten. Det finns två sätt att lägga till en bild i sidlayouten:

* Använd en bild från mallresurserna.
* Använd \&lt;add image=&quot;&quot;> i sidlayoutredigeraren.

>[!NOTE]
>
>Vi rekommenderar att du använder resursmappen för att hantera alla mallresurser, som bilder och teckensnitt.

Så här infogar du en bild som ditt företags logotyp i sidhuvudsområdet:

1. Öppna önskad sidlayout för redigering.

>[!NOTE]
>
>Se [Anpassa en sidlayout](components-pdf-template.md#customize-page-layout) för att öppna en sidlayout för anpassning eller redigering.

1. Klicka på Redigera sidhuvud (<img src="./assets/header-icon.svg" width="25">) för att föra markören in i sidhuvudsområdet.

   Du kan också klicka inuti sidhuvudsområdet.

1. Om du vill lägga till en bild väljer du någon av följande metoder:
1. Klicka på **Infoga bild** (<img src="./assets/insert-image-icon.svg" width="25">) i verktygsfältet. i **Markera bana** popup-fönster, bläddra till bildplatsen och klicka **Välj** för att infoga den i sidhuvudsområdet.
1. Dra och släpp en bild från resursmappen i sidhuvudsområdet.

I följande skärmbild visas en exempelbild som lagts till i sidhuvudsområdet.

<img src="./assets/image-in-header-area.png" width="500">

När en bild har infogats kan du ändra dess attribut så att den ser ut som du vill ha den. Det enklaste sättet att ändra hur en bild eller något annat element på sidlayouten ser ut är att använda panelen Innehållsegenskaper. Se [Arbeta med panelen Innehållsegenskaper](#work-with-content-props) för de olika egenskaper som är tillgängliga via användargränssnittet för anpassning.

### Lägg till fält och metadata {#add-fields-metadata}

Fält är mycket användbara när du vill infoga en del av informationen som är fördefinierad. Du kan till exempel inkludera ett fält för kapitelrubrik i kapitlets rubrikområde som ersätts med det verkliga kapitlets rubrik när det publiceras.

Det finns följande kategorier för fält som du kan infoga i sidlayouten:

* Datum
* Tid
* Ämnestitel
* Projektets titel
* Sidnummer
* Total sida
* Kapitelrubrik
* Kapitelnummer
* Metadata

Var och en av dessa fältkategorier innehåller olika variationer där fältinformationen kan infogas. Ett datumfält kan t.ex. ha olika variationer, t.ex. `YYYY-MM-DD`, `MM/DD/YY`, `MM/DD/YYYY` och så vidare. På samma sätt kan sidnummer ha variationer i form av latinska, decimala eller till och med språkspecifika format som _Arabiska_, _Devanagari_, _Hebreiska_, med mera.

Förutom de fördefinierade fälten kan du även lägga till metadatainformation som variabler eller fält i sidlayouten. Dessa metadata lagras i DITA-kartinnehållet och kan enkelt infogas i sidlayouten. <!--For more information, see [Add fields and metadata](design-page-layout.md#add-fields-and-metadata).-->

I följande exempel infogar vi ett sidnummer och en kapitelrubrik i sidfotsområdet i en sidlayout.

1. Öppna önskad sidlayout för redigering.

   >[!NOTE]
   >
   >Se [Anpassa en sidlayout](components-pdf-template.md#customize-page-layout) för att öppna en sidlayout för anpassning eller redigering.

1. Klicka på **Redigera sidfot** (![](./assets/footer-icon.svg)) för att placera markören i sidfotsområdet.

   Du kan också klicka inuti sidfotsområdet.

1. Infoga ett styckeelement genom att klicka på **Infoga HTML-element** (<img src="./assets/insert-html-element-2.svg" width="25">) och väljer Stycke i listan med element.

1. Klicka på **Infoga fält** (![](./assets/insert-fields-icon.svg)).

   Popup-fönstret Fält visas.

1. Välj **Sidnummer** -kategorin i fältlistan, **default(1)** sidnummerformat i formatlistan och klicka på **Infoga**.

   <img src="./assets/insert-page-number-field.svg" width="400">

   >[!NOTE]
   >
   >Du kan också redigera formatet för alla fält, förutom standardformatet. Om du vill göra det klickar du på ikonen Redigera bredvid det format du vill redigera, gör ändringar och klickar på OK. Mer information finns i [Lägg till fält och metadata](#add-fields-metadata).

   Standardsidnummerfältet infogas i sidfotsområdet i sidlayouten.

   <img src="./assets/page-number-field-in-footer.png" width="400">

   Den översta vägledningen visar de element som informationen lagras i.

1. Ange ett tomt utrymme efter sidnummerfältet och klicka på **Infoga fält** ikon.

1. Välj **Kapitelrubrik** -kategorin i fältlistan, **Kapitelrubrik** i formatlistan och klicka på **Infoga**.

   The _Kapitelrubrik_ -fältet, som fylls i med kapitlets namn vid publiceringen, infogas i sidfotsområdet. För närvarande är sidnummerfälten och kapiteltitelfälten avgränsade med ett blanksteg.

   <img src="./assets/page-number-topic-title-near-footer.png" width="400">

1. Så här högerjusterar du kapiteltiteln:

   1. Klicka på fältelementet på vägbeskrivningssidan för att välja fältet Kapitelrubrik.

   1. Klicka på knappen **Innehållsegenskaper** (<img src="./assets/content-properties-icon.png" width="25">).

   1. Expandera **Layout** egenskapsavsnittet och ange **Float** egenskapsvärde till **höger**.
      <img src="./assets/float-prop-html-content.png" width="400">

      Fältet Kapiteltitel är justerat mot sidfotens högra sida.
      <img src="./assets/topic-title-moved-right-footer.png" width="500">


| _Developer Corner_: <img src="./assets/developer-corner-icon.svg" width="25"> |
|---|

Om du vill arbeta direkt med CSS- och HTML-koden kan du även göra det genom att gå till källvyn i sidlayouten och göra ändringar i koden. I följande kodutdrag visas samma sidfotsinställning som i koden:

```css
…
<p>

<span data-field="page-number" data-format="default">1</span>

<span data-field="chapter-title" data-format="default" style="float: right">Chapter Title</span>

</p>
…
```

## Arbeta med innehållsområdet {#content-area}

Innehållsområdet är det största området när det gäller innehållsområdet. Innehållsområdet fylls i med innehållet i ditt ämne. I vissa speciella fall kan du lägga till mallinnehåll i innehållsområdet. Det här innehållet publiceras på den angivna platsen i sidlayouten. Rubriken i innehållsförteckningen, ordlistan och indexet kan t.ex. läggas till som mallinnehåll, som publiceras &quot;i befintligt skick&quot; i det slutliga resultatet. Ett annat exempel är kapitelinnehållsförteckningen, som vanligtvis läggs till på den första sidan i varje kapitel.

En av de vanligaste anpassningarna i innehållsområdet är layouten med flera kolumner. Med den kraftfulla layoutaren kan du anpassa specifika sidor som ska återges i flera kolumner samtidigt som innehållet på andra sidor behålls i en enda kolumn.

I följande avsnitt beskriver vi olika scenarier för att anpassa innehållsområdet.

### Lägga till en kapitelinnehållsförteckning {#add-chapter-toc}

En kapitelinnehållsförteckning fungerar som en snabb referens för läsarna så att de vet vad som finns i kapitlet. Vanligtvis läggs ett kapitel till i början av ett kapitel. Om du vill använda en kapitelinnehållsförteckning kan du lägga till den i innehållsområdet för huvudkapitelsidans layout eller den första sidlayoutvarianten för ett kapitel.

I följande exempel infogar vi en kapitelinnehållsförteckning i den första sidlayouten i ett kapitel:

>[!NOTE]
>
>I den här proceduren antas att du har skapat varianten Första sidan för en kapitelsidlayout. Instruktioner om hur du skapar en sidvariant finns i [Skapa de första, högra eller vänstra sidlayoutvarianterna](#page-layout-variants).

1. Öppna önskad sidlayout för redigering.

   >[!NOTE]
   >
   >Se [Anpassa en sidlayout](components-pdf-template.md#customize-a-page-layout) för att öppna en sidlayout för anpassning eller redigering.

1. Placera markören i innehållsområdet i sidlayouten.

1. Klicka på kapitelinnehållet (<img src="./assets/chapter-toc-icon.svg">).

   Standardkapitelinnehållsförteckningen infogas i innehållsområdet.

   <img src="./assets/chapter-toc-default.png" width="400">

   >[!NOTE]
   >
   >Standardkapitlet innehåller rubrikerna 1 till 4. Här är rubrik 1 kapitelrubriken. Du kanske inte vill ha kapiteltiteln igen i innehållsförteckningen eller du kanske vill öka nivån på rubrikerna i innehållsförteckningen. Du kan anpassa innehållsförteckningen genom att ändra egenskaperna.

1. Öppna panelen Innehållsegenskaper för att anpassa rubriknivåerna i innehållsförteckningen.

   Om du till exempel vill börja med Rubrik 2, ändrar du den första listrutan till att börja med 2.

   <img src="./assets/customize-chapter-toc.png" width="400">

   Om du vill ha rubriker upp till nivå 5 ändrar du den andra listrutan till 5. Den uppdaterade innehållsförteckningen kommer att se ut så som visas nedan:

   <img src="./assets/chapter-toc-updated.png" width="400">

   >[!NOTE]
   >
   >I den slutliga publicerade PDF visas bara innehållsförteckningsposterna baserat på innehållet i dina kapitel. Om du inte har rubriker på nivå 5 i ett kapitel visas det inte i det slutliga resultatet.

Utseendet på standardinnehållsförteckningen kan anpassas med hjälp av formatmallarna. Det format som börjar med `chaptoc-level-#` (som `chaptoc-level-1`, `chaptoc-level-2`och så vidare) används för att anpassa formaten för kapitelinnehållsförteckningen. <!--For more details on the stylesheet elements used in the TOC and how to customize them, see _Customize default chapter TOC_-->.

>[!IMPORTANT]
>
>Om du uppdaterar en formatmall i en formatmall kanske den inte visas i innehållsförhandsvisningen. Utdata återges dock med de uppdaterade formaten.

### Arbeta med sidlayout med flera kolumner {#multi-column-layout}

Layouter med flera spalter är mycket vanliga när du publicerar tidskrifter eller index i en bok. Med funktionen för publicering i PDF kan du enkelt dela upp dokument i flera kolumner. Om du använder olika sidlayouter kan du välja att bara behålla ett visst avsnitt uppdelat i flera kolumner samtidigt som de andra avsnitten behålls i en enda spaltlayout (eller normal layout).

Så här skapar du en sidlayout med flera kolumner:

1. Öppna önskad sidlayout för redigering.

   >[!NOTE]
   >
   >Se [Anpassa en sidlayout](components-pdf-template.md#customize-a-page-layout) för att öppna en sidlayout för anpassning eller redigering.

1. När layouten med flera kolumner används på innehållet, med undantag för sidhuvud och sidfot, måste du markera innehållselementet i sidhuvudet.

   När du har markerat innehållets kolumnbredd visas egenskaperna för flera kolumner på panelen Innehållsegenskaper.

   <img src="./assets/multiple-columns-properties.png" width="400">

1. Använd egenskaperna för flera kolumner för att anpassa sidlayouten med flera kolumner:

   * **Antal kolumner:** Ange antalet kolumner som sidan ska delas upp i. Använd upp- och nedpilsikonerna eller ange ett tal för att ange antalet kolumner.

   * **Kolumnbredd:** Ange bredden på en kolumn i en layout med flera kolumner. Som standard anges storleken i pixlar (px), och du kan även ange den i pt, rem, em, % eller i enheter.

      >[!NOTE]
      >
      >Om du inte anger någon storlek delas kolumnerna jämnt så att de passar på den angivna sidan. I de flesta fall behöver du inte ange det här värdet.

   * **Kolumnmellanrum** : Ange avståndet mellan enskilda kolumner.

   * **Kolumnintervall** : Om du vill att ett element på sidlayouten ska spänna över flera kolumner måste du använda den här egenskapen. Detta uppnås genom att du ändrar formatet för det önskade elementet med formatmallarna. <!--for more information see _Section explaining style customization_-->.

   Om du i sidlayouten vill att en viss text ska visas på den första sidan i alla kapitelsidlayouter, kan du lägga till den i varianten för den första sidan i kapitelsidlayouten.

   Som framgår av följande exempel är egenskapen Spänn över spalt för rubriktexten inställd på alla. Detta garanterar att även om dokumentet är flerspaltig, sträcker sig rubriken över flera spalter.

   <img src="./assets/element-span-across-columns.png" width="400">

   >[!IMPORTANT]
   >
   >Du kan använda Span Column-egenskapen för alla DITA-element med hjälp av attributet outputClass.

   * **Kolumnfyllning** : Ange hur innehåll ska fylla kolumner. Som standard är det inställt på Balans, vilket fyller varje kolumn med samma mängd innehåll.

   * **Kolumnregel** : Om du vill ha en linje mellan kolumnerna använder du den här egenskapen för att definiera linje- eller linjestilar. Ange värden för linjens format, färg och bredd om du vill lägga till en linje mellan kolumnerna.


## Arbeta med panelen Innehållsegenskaper {#work-with-content-props}

Med panelen Innehållsegenskaper kan du enkelt uppdatera utseendet och känslan hos elementen i sidlayouten. Egenskaperna under panelen Innehållsegenskaper är uppdelade i följande avsnitt:

* **Teckensnitt** : Innehåller textrelaterade egenskaper. Du kan ange Teckensnittsfamilj, Teckenbredd, Storlek, Textdekoration (som understrykning, överstrykning, genomstrykning), Textformat (som fet, Kursiv med mera), Textjustering (som vänster, höger, mitten eller marginaljusterad), Hantera blanksteg (som fördefinierat format, ingen radbrytning, radmellanrum med mera), Radhöjd, Teckenavstånd och Textindrag.

* **Kant** : Innehåller egenskaper för att lägga till och formatera en kant i ett element i sidlayouten. Du kan ange Kantsida (som alla, översta, nedersta, högra eller vänstra), Kantformat (som heldragen, streckad, prickade linjer eller fler), Kantfärg, Bredd och Radius för en böjd kant. I följande exempel har en böjd kantlinje lagts till i sidhuvudsområdet på sidan.

   <img src="./assets/border-properties.png" width="500">

* **Layout** : Innehåller egenskaper för att konfigurera layouten för ett element i sidlayouten. Du kan ange Höjd, Bredd, Marginaler och Utfyllnad (för överkant, nederkant, vänster eller höger), Vågrät eller Lodrät justering, Flyt (som vänster, höger eller ingen), Rensa (som vänster, höger, båda eller ingen), Elementets position (som absolut, fast, relativ eller mer), Visa (som block, innehåll, korrigera eller mer), Z-index, Genomskinlighet, Omforma (genom att rotera eller rotera skalförändring) och Omforma ursprung (med X- och Y-förskjutning).

* **Bakgrund** : Innehåller egenskaper som innehåller en bakgrundsbild eller färgskugga. Du kan ställa in bildstorlek (genom att ställa in höjd eller bredd), Upprepa bakgrund (som upprepning, ingen upprepning, rund eller mer) och Bakgrundsposition (som vänster överkant, höger mittpunkt, centrera nederkant eller mer).
* **Flera kolumner** : Innehåller egenskaper för att konfigurera egenskaper med flera kolumner för sidan eller för specifika element, t.ex. kapitelinnehållsförteckning. Mer information om egenskaperna och hur du använder dem finns i [Arbeta med sidlayout med flera kolumner](#multi-column-layout).
