---
title: Publiceringsfunktion för PDF | Designa en sidlayout
description: Lär dig hur du utformar sidlayouten för att presentera information i olika delar av PDF.
hide: true
hidefromtoc: true
exl-id: b4d3bdc4-0d01-46eb-b182-540380220485
source-git-commit: 651409beb88468bfb5ab35e45028b01fccd91cd5
workflow-type: tm+mt
source-wordcount: '3289'
ht-degree: 0%

---


# Utforma en sidlayout

När du skapar ett PDF-dokument har du olika avsnitt för olika typer av information. Ett PDF-dokument kan till exempel börja med en framsida eller en försättssida, som skulle innehålla företagets logotyp, boktitel eller versionsinformation. Då finns det kapitel, bilagor eller ordlistor. Varje avsnitt i ett PDF-dokument ser olika ut och det uppnås genom att sidlayouten skapas och anpassas.

När du utformar en sidlayout kan du definiera de olika elementen som utgör en sida. Du kan till exempel definiera sidstorlek, marginaler, sidhuvud och sidfot, orientering och andra sidspecifikationer på en sida. Med funktionen för publicering i PDF kan du utforma din sida i enlighet med CSS-standarderna för sidindelad media. De flesta inställningar som täcks av CSS Paged Media kan enkelt anpassas med hjälp av PDF-funktionens användargränssnitt. För viss annan formatering på avancerad nivå kan du använda källvyn för att skriva egen CSS-kod.

När du har utformat sidlayouten måste du koppla de här layouterna till deras respektive avsnitt i inställningarna för sidlayout på PDF. Se _Skapa och anpassa sidlayouter_ om du vill ha mer information om hur du skapar och öppnar en sidlayout för anpassning.

## Typer av sidlayouter och deras varianter

Ett PDF-dokument innehåller vanligtvis följande avsnitt:

* Försättssida
* Innehållsförteckning
* Sifferlyft
* Tabellens lyft
* Kapitel- eller ämnessidor
* Ordlista
* Index
* Baksida

Dessa avsnitt behöver en motsvarande sidlayout för att visa informationen i ett visst format. Dessutom kan du ha en tom sida som används som utfyllnadstecken för att starta ett nytt kapitel från en udda eller jämn sida. I så fall behöver du en tom sidlayout.

Inställningarna för sidlayout under **Mall > Inställningar** kan du definiera vilken mall som ska användas för olika avsnitt i PDF. Varje sidlayout kan ha olika kombinationer av första, högra och vänstra sidan. Dessa regleras av de regler som definieras i *CSS Page Media* standarder.

## Skapa den första, högra eller vänstra sidlayouten

Olika sidlayouter i PDF kan anpassas ytterligare genom att ha olika sidlayouter för första, högra eller vänstra sidan. Du kan utforma dessa sidor på ett annat sätt med hjälp av layoutdesignern.

>[!NOTE]
>
>Om du vill ha en enda sidlayout för ett avsnitt i boken behöver du inte skapa sidlayouterna Första, Höger eller Vänster.


Tänk på följande när du skapar sidlayouterna:

* Om du vill använda en enda sidlayout för alla sidor i ett kapitel skapar du bara en enda kapitelsidlayout.
* Om du vill ha ett annat utseende och en annan känsla för den första sidan för kapitel i boken måste du skapa en layout för första sidan för kapitlen.
* Om du vill ha ett annat utseende och en annan känsla för alla sidor på vänster och höger sida i boken måste du skapa varianterna på vänster och höger sida för kapitelsidans layout.
* Om du vill att kapitlen ska börja från en udda eller jämn sida måste du skapa en tom sidlayout. Den här sidlayouten används för att fylla mellanrummet mellan två kapitel så att kapitlet börjar från önskad udda eller jämn sida.

I följande exempel får du hjälp med att skapa varianter av en sidlayout:

1. Skapa en kapitelsidlayout med hjälp av stegen i *Skapa en ny sidlayout* procedur.

   En tom kapitelsidlayout skapas och läggs till under Sidlayouter.

   När du skapar en sidlayout öppnas den som standard även för redigering. På följande skärmbild visas en tom (standard) sidlayout:

   <img src="./assets/default-blank-page-layout.png" width="300">

   Sidhuvudet, sidfoten och innehållsområdet i en mall skapas som standard. Du kan enkelt anpassa dessa områden med de verktyg, sidegenskaper och innehållsegenskaper som finns i användargränssnittet. Om du vill ha en mer avancerad konfiguration kan du använda källvyn och lägga till din anpassade HTML- och CSS-kod.

1. Så här skapar du en variant för kapitelsidans layout:

   1. Håll muspekaren över **Kapitel** layout och klicka **Alternativ** för att visa snabbmenyn.

   1. Klicka eller hovra muspekaren över **Lägg till layoutvariant** och välj önskad sidlayout (Första, Vänster eller Höger) som du vill skapa.

   Den valda sidlayouten skapas med en kopia av den grundläggande kapitellayouten. Det innebär att om du har gjort några ändringar i standardlayouten för kapitelsidor, kommer samma ändringar att replikeras i variantsidlayouten.

## Arbeta med bilder i en sidlayout

Beroende på dina behov kan det vara bra att lägga till en bild som visas på varje första sida i ett kapitel (PDF). The <u>**Lägg till bild**</u> i sidlayoutredigeraren används för att infoga bilder i en sidlayout.

Om du till exempel vill infoga en bild i sidhuvudsområdet på första sidan i kapitelutdata utför du följande steg:

1. Öppna önskad sidlayout för redigering.

   >[!NOTE]
   >
   >Se _Anpassa en sidlayout_ för att öppna en sidlayout för anpassning eller redigering.

1. Klicka på Redigera sidhuvud (<img src="./assets/header-icon.svg" width="25">) för att föra markören in i sidhuvudsområdet.

1. Klicka på Infoga bild (<img src="./assets/insert-image-icon.svg" width="25">).

   Popup-fönstret Välj bana visas.

1. Bläddra till bildplatsen och klicka på Välj för att infoga den i sidhuvudsområdet.

   I följande skärmbild visas en exempelbild som lagts till i sidhuvudsområdet.

   <img src="./assets/image-in-header-area.png" width="500">

   När en bild har infogats kan du ändra dess attribut så att den ser ut som du vill ha den. Det enklaste sättet att ändra hur en bild eller något annat element på sidlayouten ser ut är att använda panelen Innehållsegenskaper. Se _Arbeta med panelen Innehållsegenskaper_ för de olika egenskaper som är tillgängliga via användargränssnittet för anpassning.

## Arbeta med fält

Fält är mycket användbara när du vill infoga en del av informationen som är fördefinierad. Du kan till exempel inkludera ett fält för kapitelrubrik i kapitlets rubrikområde som ersätts med det verkliga kapitlets rubrik när det publiceras.

Det finns följande kategorier för fält som du kan infoga i sidlayouten:

* Date
* Time
* Ämnestitel
* Projektets titel
* Sidnummer
* Total sida
* Kapitelrubrik
* Kapitelnummer
* Metadata

Var och en av dessa fältkategorier innehåller olika variationer där fältinformationen kan infogas. Ett datumfält kan t.ex. ha olika variationer, t.ex. `YYYY-MM-DD`, `MM/DD/YY`, `MM/DD/YYYY` och så vidare.

I följande exempel infogar vi ett sidnummer och en avsnittsrubrik i sidfotsområdet i sidlayouten.

1. Öppna önskad sidlayout för redigering.

   >[!NOTE]
   >
   >Se _Anpassa en sidlayout_ för att öppna en sidlayout för anpassning eller redigering.

1. Klicka på Redigera sidfot (![](./assets/footer-icon.svg)) för att placera markören i sidfotsområdet.

1. Infoga ett styckeelement genom att klicka på Infoga HTML-element <img src="./assets/insert-html-element-2.svg" width="25"> och väljer Stycke i listan med element.

1. Klicka på Infoga fält ( ![](./assets/insert-fields-icon.svg)).

   Popup-fönstret Fält visas.

1. Välj **Sidnummer** -kategorin i fältlistan, **default(1)** sidnummerformat i formatlistan och klicka på **Infoga**.

   <img src="./assets/insert-page-number-field.svg" width="400">

   <img src="./assets/transparent-background.png" width="70">

   >[!NOTE]
   >
   >Du kan också redigera formatet för alla fält, förutom standardformatet. Om du vill göra det klickar du på ikonen Redigera bredvid formatet som du vill redigera, gör ändringar och klickar på OK.

   Standardsidnummerfältet infogas i sidfotsområdet i sidlayouten.

   <img src="./assets/page-number-field-in-footer.png" width="400">

   Den översta vägledningen visar de element som informationen lagras i.

1. Ange ett tomt utrymme efter sidnummerfältet och klicka på **Infoga fält** ikon.

1. Välj **Ämnestitel** -kategorin i fältlistan, **Kapitel.ptl** titelformat i formatlistan och klicka på Infoga.

   The `Chapter.ptl` -fältet, som fylls med ämnesrubriken vid publiceringen, infogas i sidfotsområdet. För närvarande avgränsas sidnummerfälten och ämnesrubrikfälten med ett blanksteg.

   <img src="./assets/page-number-topic-title-near-footer.png" width="400">

1. Så här högerjusterar du ämnestiteln:

   1. Klicka på fältelementet i vägbeskrivningsfilen för att välja ämnestitelfältet.

   1. Klicka på Egenskaper för HTML-innehåll i den högra panelen.

      <img src="./assets/right-pane-content-properties.png" width="350">

   1. Expandera **Layout** egenskapsavsnittet och ange **Float** egenskapsvärde till **höger**.

      <img src="./assets/float-prop-html-content.png" width="350">

      Ämnestitelfältet är justerat mot sidfotens högra sida.

      <img src="./assets/topic-title-moved-right-footer.png" width="500">

| _Developer Corner_: <img src="./assets/developer-corner-icon.svg" width="25"> |
|---|

Om du vill arbeta direkt med CSS- och HTML-koden kan du även göra det genom att gå till källvyn i sidlayouten och göra ändringar i koden. I följande kodutdrag visas samma sidfotsinställning som i koden:

```md
…
<div data-region="footer">
	<p>
		<span data-field="page-number" data-format="default">1</span>
		<span data-field="title" data-format="default" style="float: right">Chapter.plt</span>
	</p>
</div>
…
```

## Lägga till en kapitelinnehållsförteckning

Ett kapitel eller en liten innehållsförteckning fungerar som en snabb referens för läsarna så att de vet vad som finns i kapitlet. Vanligtvis läggs ett kapitel till i början av ett kapitel. Om du vill använda en kapitelinnehållsförteckning kan du lägga till den i huvudkapitelsidans layout eller på första sidans layout för ett kapitel.

I följande exempel infogar vi en kapitelinnehållsförteckning i första sidlayouten i ett kapitel:

1. Öppna önskad sidlayout för redigering.

   >[!NOTE]
   >
   >Se _Anpassa en sidlayout_ för att öppna en sidlayout för anpassning eller redigering.

1. Placera markören i innehållsområdet i sidlayouten.
1. Klicka på kapitelinnehållet (<img src="./assets/chapter-toc-icon.svg">).

   Standardkapitelinnehållsförteckningen infogas i innehållsområdet.

   <img src="./assets/chapter-toc-default.png" width="400">
    <img src="./assets/transparent-background.png" width="70">

   >[!NOTE]
   >
   >Standardkapitlet innehåller rubrikerna 1 till 4. Här är rubrik 1 kapitelrubriken. Du kanske inte vill ha kapiteltiteln igen i innehållsförteckningen eller du kanske vill öka nivån på rubrikerna i innehållsförteckningen. Du kan anpassa innehållsförteckningen genom att ändra egenskaperna.

1. Öppna panelen Innehållsegenskaper för HTML om du vill anpassa rubriknivåerna för innehållsförteckningen.

   Om du till exempel vill börja med Rubrik 2, ändrar du den första listrutan till att börja med 2.

   <img src="./assets/customize-chapter-toc.png" width="400">

   Om du vill ha rubriker upp till nivå 5 ändrar du den andra listrutan till 5. Den uppdaterade innehållsförteckningen kommer att se ut så som visas nedan:

   <img src="./assets/chapter-toc-updated.png" width="400">

   <img src="./assets/transparent-background.png" width="70">

   >[!NOTE]
   >
   >I den slutliga publicerade PDF visas bara innehållsförteckningsposterna baserat på innehållet i dina kapitel. Om du inte har rubriker på nivå 5 i ett kapitel visas det inte i det slutliga resultatet.

## Arbeta med sidlayout med flera kolumner

Layouter med flera spalter är mycket vanliga när du publicerar tidskrifter eller index i en bok. Med publiceringsfunktionen för PDF kan du enkelt dela upp dokument i flera kolumner. Om du använder olika sidlayouter kan du välja att bara behålla ett visst avsnitt uppdelat i flera kolumner samtidigt som de andra avsnitten behålls i en enda spaltlayout (eller normal layout).

Så här skapar du en sidlayout med flera kolumner:

1. Öppna önskad sidlayout för redigering.

   >[!NOTE]
   >
   >Se _Anpassa en sidlayout_ för att öppna en sidlayout för anpassning eller redigering.

1. När layouten med flera kolumner används på innehållet, med undantag för sidhuvud och sidfot, måste du markera innehållselementet i sidhuvudet.

   När du har markerat innehållsfältet visas egenskaperna för flera spalter på panelen Egenskaper för HTML.

   <img src="./assets/multiple-columns-properties.png" width="400">

1. Använd egenskaperna för flera kolumner för att anpassa sidlayouten med flera kolumner:

   * **Antal kolumner:** Ange antalet kolumner som sidan ska delas upp i. Använd upp- och nedpilsikonerna eller ange ett tal för att ange antalet kolumner.

   * **Kolumnbredd:** Ange bredden på en kolumn i en layout med flera kolumner. Som standard anges storleken i pixlar (px), och du kan även ange den i pt, rem, em, % eller i enheter.

      >[!NOTE]
      >
      >Om du inte anger någon storlek ändras kolumnernas storlek automatiskt så att de passar i de angivna sidmarginalerna.

   * **Kolumnmellanrum** : Ange avståndet mellan enskilda kolumner.

   * **Kolumnintervall** : Om du vill att ett element på sidlayouten ska spänna över flera kolumner måste du använda den här egenskapen. Detta uppnås genom att formatet för det önskade elementet ändras med formatmallarna. Mer information finns i _\&lt;section explaining=&quot;&quot; style=&quot;&quot; customization=&quot;&quot;>_.

   Om du i sidlayouten vill att en viss text ska visas på den första sidan i alla kapitelsidlayouter, kan du lägga till den i varianten för den första sidan i kapitelsidlayouten.

   Som framgår av följande exempel är egenskapen Spänn över spalt för rubriktexten inställd på alla. Detta garanterar att även om dokumentet är flerspaltig, sträcker sig rubriken över flera spalter.

   <img src="./assets/element-span-across-columns.png" width="400">

   <img src="./assets/transparent-background.png" width="70">

   >[!IMPORTANT]
   Du kan använda Span Column-egenskapen för alla DITA-element.

   * **Kolumnfyllning** : Ange hur innehåll ska fylla kolumner. Som standard är det inställt på Balans, vilket fyller varje kolumn med samma mängd innehåll.

   * **Kolumnregel** : Om du vill ha en linje mellan kolumnerna använder du den här egenskapen för att definiera linje- eller linjestilar. Ange värden för linjens format, färg och bredd om du vill lägga till en linje mellan kolumnerna.


## Använd Sidegenskaper för olika sidorienteringar

När du utformar en sidlayout är det viktigt att du har kontroll över olika sidegenskaper. Funktionen för inbyggda PDF kapslar in alla större sidegenskaper under panelen Sidegenskaper. På panelen Sidegenskaper finns olika egenskaper i följande avsnitt:

* **Sidstorlek**: Ange den sidstorlek som du vill använda för sidlayouten. I listrutan Sidstorlek kan du välja mellan över 15 sidstorlekar.

* **Orientering**: Ange den sidorientering som ska användas för sidlayouten. Du kan välja mellan stående eller liggande sidorientering. Observera att du kan välja att använda olika orienteringar för olika sidvarianter i en sidlayout. Du kan t.ex. ange stående orientering på första sidan och Liggande på vänster och höger sida.

* **Visa rotation**: Ange i vilken vy eller i vilken riktning innehållet på sidan ska placeras. Du kan välja mellan 90 grader medsols, 90 grader moturs eller 180 grader moturs. Detta är mycket användbart i en situation där du vill använda en kombination av stående och liggande layouter i utdata. Du kan till exempel använda stående som allmän sidlayout och du kan ange liggande sidlayout för att hämta långa tabeller. I så fall kan du välja att visa tabellinnehållet medsols 90 grader. På så sätt orienteras sidan liggande och innehållet roteras 90 grader för att kontinuiteten ska kunna bibehållas. Vi kommer att se hur detta uppnås som ett exempel senare i detta avsnitt.

* **Starta om numrering från**: Ange vilket sidnummer som sidlayouten ska börja från. Du kan t.ex. skapa en sidlayout för avsnittet Tillägg i boken och ange att numreringen ska starta om från 1.

* **Layout**: Ange sidmarginaler tillsammans med utfyllnad för övre, nedre, vänstra och högra sidor.

* **Bakgrund**: Inkludera en bild som bakgrundsbild i sidlayouten. Du kan ange bildens höjd och bredd tillsammans med repetitions- och positionsegenskaperna.

* **Fotnot**: Ange de egenskaper som fotnoterna ska visas i utdata. Du kan välja att ange marginaler och utfyllnadsegenskaper tillsammans med ett kantlinjeformat.

Låt oss titta på ett exempel där en kombination av stående och liggande sidorientering och vyrotationsegenskaper används. I det här exemplet skapar vi en PDF med stående orientering som standard, men en tabell återges i liggande orientering med innehåll i 90-gradersvyn medurs. Resultatet ser ut ungefär så här:

<img src="./assets/portrait-landscape-page-layouts.png" width="400">

I ovanstående utdata visas informationen i kontaktlistan i liggande läge med innehållet roterat i 90 grader. Det återstående innehållet visas i normalt stående läge.

För att uppnå den här typen av utdata måste vi utföra följande huvudsakliga uppgifter:

1. Skapa en sidlayout med liggande orientering.
1. Ändra egenskapen Visa rotation om du vill återge innehåll 90 grader medsols.
1. Skapa ett anpassat format för den nya sidlayouten.
1. Lägg till formatet i utdataklassdefinitionen för den tabell som ska återges i liggande layout.

Utför följande steg för att utföra ovanstående åtgärder:

1. Skapa en sidlayout med liggande orientering.
   1. Skapa en liggande sidlayout med hjälp av stegen under Skapa en ny sidlayout.

   1. Klicka på i den högra panelen **Sidegenskaper**.

      <img src="./assets/page-properties-panel.png" width="300">
   1. Ändra **Orientering** till **Liggande**.

1. Ändra egenskapen Visa rotation om du vill återge innehåll 90 grader medsols.

   1. Välj **90° medsols** i listrutan Vyrotation.

   1. Klicka **Savel All** om du vill spara de uppdaterade sidlayoutegenskaperna.

1. Skapa ett anpassat format för den nya sidlayouten.
   1. Expandera den vänstra sidlisten och dubbelklicka på mallen som du vill skapa formatet i.

   1. Expandera avsnittet Formatmallar.

   1. Håll muspekaren över layoutformatmallen och klicka på (_Alternativ_ ikon) **...** och välja **Redigera**.

      Layoutformatmallen öppnas för redigering.

   1. Högerklicka på **Andra format** och välja **Nytt format**.

      <img src="./assets/stylesheet-other-new-style.png" width="300">

   1. I **Lägg till format** popup, enter `landscape-style` i **Klass** namnfält.

      <img src="./assets/stylesheet-new-landscape-style.png" width="400">

   1. Klicka **Klar**.

      Ett nytt format med namnet `.landscape-style` skapas och läggs till i slutet av **Andra format** lista.

   1. Dubbelklicka på `.landscape-style` stil för att öppna den för redigering.

   1. Expandera **Sidnumrering** -egenskap.

   1. Retur `Landscape` i **Sidlayout** -egenskap.

      <img src="./assets/new-style-with-landscape-layout.png" width="500">

1. Lägg till formatet i utdataklassdefinitionen för den tabell som ska återges i liggande layout.

   1. Öppna filen där du vill använda den nya sidlayouten i Web Editor.

   1. Hitta `<table>` -element som ska återges i liggande läge.

   1. Klicka på `table` för att markera tabellen.

      <img src="./assets/new-style-table-element.png" width="400">

   1. I den högra panelen klickar du på och öppnar **Innehållsegenskaper** -panelen.

   1. I **Innehållsegenskaper** panel, lägga till en ny `outputclass` egenskap med `landscape-style` som egenskapsvärde.

      <img src="./assets/new-style-table-outputclass.png" width="300">

   1. Klicka **Spara alla** för att spara den uppdaterade filen.

   1. Generera utdata från PDF.

Tabellinnehållet återges i liggande läge i det slutliga PDF, vilket visas i början av exemplet.

## Arbeta med panelen Innehållsegenskaper

Med panelen Innehållsegenskaper kan du enkelt uppdatera utseendet och känslan hos elementen i sidlayouten. Egenskaperna under panelen Innehållsegenskaper är uppdelade i följande avsnitt:

>[!NOTE]
Mer information om hur dessa egenskaper används finns i dokumentationen till W3C CSS Page Media Standards.

* **Attribut**: Innehåller egenskaperna ID, Class och Translate. Om du ställer in egenskapen Translate på no översätts inte innehållet i det specifika elementet.

* **Teckensnitt**: Innehåller teckensnittsrelaterade egenskaper. Du kan ange Teckensnittsfamilj, Teckenbredd, Storlek, Textdekoration (som understrykning, överstrykning, genomstrykning), Textformat (som fet, Kursiv med mera), Textjustering (som vänster, höger, mitten eller marginaljusterad), Hantera blanksteg (som fördefinierat format, ingen radbrytning, radmellanrum med mera), Radhöjd, Teckenavstånd och Textindrag.

* **Kant**: Innehåller egenskaper för att lägga till och formatera en kant i ett element i sidlayouten. Du kan ange Kantsida (som alla, översta, nedersta, högra eller vänstra), Kantformat (som heldragen, streckad, prickade linjer eller fler), Kantfärg, Bredd och Radius för en böjd kant. I följande exempel har en böjd kantlinje lagts till i sidhuvudsområdet på sidan.

   <img src="./assets/border-properties.png" width="500">

* **Layout**: Innehåller egenskaper för att konfigurera layouten för ett element i sidlayouten. Du kan ange Höjd, Bredd, Marginaler och Utfyllnad (för överkant, nederkant, vänster eller höger), Vågrät eller Lodrät justering, Flyt (som vänster, höger eller ingen), Rensa (som vänster, höger, båda eller ingen), Elementets position (som absolut, fast, relativ eller mer), Visa (som block, innehåll, korrigera eller mer), Z-index, Genomskinlighet, Omforma (genom att rotera eller rotera skalförändring) och Omforma ursprung (med X- och Y-förskjutning).

* **Bakgrund**: Innehåller egenskaper som innehåller en bakgrundsbild eller färgskugga. Du kan ställa in bildstorlek (genom att ställa in höjd eller bredd), Upprepa bakgrund (som upprepning, ingen upprepning, rund eller mer) och Bakgrundsposition (som vänster överkant, höger mittpunkt, centrera nederkant eller mer).

* **Flera kolumner**: Innehåller egenskaper för att konfigurera egenskaper med flera kolumner för sidan eller för specifika element, t.ex. kapitelinnehållsförteckning. Mer information om egenskaperna och hur du använder dem finns i _Arbeta med sidlayout med flera kolumner_.
