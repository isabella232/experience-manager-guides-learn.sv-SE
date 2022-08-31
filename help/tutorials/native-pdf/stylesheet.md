---
title: Publiceringsfunktion för PDF | Arbeta med vanliga innehållsformat
description: Lär dig hur du skapar formatmallar och skapar format för ditt innehåll.
hide: true
hidefromtoc: true
source-git-commit: 78db1486af3eb99b165a136d6bae6f7f15a1b527
workflow-type: tm+mt
source-wordcount: '3500'
ht-degree: 0%

---


# Arbeta med vanliga innehållsformat

En formatmall innehåller definitioner av format för de element som används i utdata från PDF. Du kan välja att arbeta med exempelformatmallarna eller skapa nya. I de flesta fall kan du snabbt komma igång genom att skapa en kopia av OTB-exempelformatmallen.

Formatredigeraren är en WYSIWYG-redigerare som döljer alla komplexa CSS-koder bakom användargränssnittet. Med stilredigeraren kan du enkelt och mycket snabbt anpassa stilarna för de element du vill använda. Formaten är kategoriserade under följande rubriker:

* Rubrikformat
* Styckeformat
* Teckenformat
* Hyperlänkformat
* Bildformat
* Listformat
* Tabellformat
* Div-format
* Sidformat
* Andra format

När du arbetar med strukturerat DITA-innehåll finns formatmappningen för de flesta DITA-elementen på plats i standardformatmallen. Om du arbetar med DITA-standardelement kan du ändra deras utseende och känsla genom att ändra formatdefinitionen direkt. Dessa formatdefinitioner är tillgängliga under kategorin Annat format. Mer information finns i *Arbeta med andra format* senare i det här avsnittet.

I följande avsnitt beskrivs de vanligaste formatinställningarna i form av exempel.

>[!NOTE]
>
>I följande exempel antas du arbeta med den exempelformatmall som levereras med produkten.

## Arbeta med rubrikformat

Rubrikformaten kapslar in alla basformat för de rubriker som används i innehållet. OTB får du 6 basrubrikformat och ett rubrikformat för ämnet/kapitlet och bilagans rubrikrubrik. I ett strukturerat dokument representerar H1 ämnets eller kapitlets rubrik och H2 till H6 används för underämnen eller avsnitt i ett ämne/kapitel. Den här rubrikhierarkin används automatiskt på innehållet när motsvarande rubrik hittas.

>[!NOTE]
>
>Du kan skapa egna rubrikformat och de kan användas i ditt innehåll med hjälp av klassen output. Mer information finns i steg 4 i *Använda sidorientering och vyrotation* exempel.

### Skapa anpassade rubriker på kapitelnivå

I en bok (eller en bokmapp) arbetar du med kapitel. Basrubrikformaten är utformade på ett sådant sätt att de tillämpas på rubriker på kapitelnivå utan anpassningar. Men om du vill skapa rubriker för innehållet måste du skapa rubrikerna. Som standard `h1.chapter` rubriken används på kapitlets namn. Om du vill att kapiteltiteln ska visas i ett annat format måste du anpassa `h1.chapter` stil. På samma sätt kan du skapa egna format för underrubriker i kapitlet. Om du till exempel vill skapa ett anpassat format för alla 2<sup>end</sup> och 3<sup>rd</sup> nivårubriker i kapitlet måste du skapa ett nytt format som `h2.chatper` och `h3.chatper`.

Eftersom publiceringsfunktionen för ursprungliga PDF innehåller basformatsdefinitionerna för de vanligaste formaten, används standardformatet för innehållet även om du av misstag tar bort ett format. Om det t.ex. inte finns någon formatdefinition för h2-formatet i din formatmall kommer publiceringsfunktionen för PDF att använda en grundstil på h2-innehåll.

I det här exemplet skapar vi en kapitelrubrikstil på den andra nivån:

1. Öppna den formatmall du vill använda för redigering.
   >[!NOTE]
   >
   >Se *Anpassa ett fördefinierat eller nytt format* för att öppna en formatmall för anpassning eller redigering.

1. I **Stilar** listan, expandera **Rubrikformat**.
1. Högerklicka på **Rubrikformat** stil och välj **Nytt format**.
1. I *Lägg till format* dialogrutan, behålla **Tagg** namn som `h2` och ange `chapter` i **Klass** namnfält.
1. Klicka **Klar**.

Ett nytt rubrikformat med namnet `h2.chapter` skapas och läggs till i listan Rubrikformat.

När du har skapat ett format kan du anpassa de önskade egenskaperna för formatet med hjälp av formatredigeraren.

### Skapa rubriker med automatisk numrering

Ett av de vanligaste utdataformaten är autonumrerade rubriker. Dessa rubriker representerar kapitelnummer, ämne och underteman. Rubrikerna för automatisk numrering skiljer sig från listformaten där en lista med objekt i ett ämne tilldelas automatiska nummer.

I det här exemplet anpassar vi rubrikerna från nivå 1 till nivå 3 för att använda automatiska nummer i olika format.

1. Öppna den formatmall du vill använda för redigering.

   >[!NOTE]
   >
   >Se *Anpassa ett fördefinierat eller nytt format* för att öppna en formatmall för anpassning eller redigering.

1. I **Stilar** listan, expandera **Rubrikformat**.

1. Välj **h1** i listan.
Egenskaperna för formatet h1 visas på egenskapspanelen tillsammans med förhandsvisningen.

   >[!NOTE]
   >
   >På panelen Förhandsgranska får du en realtidsvy över alla formatuppdateringar som du kan använda på ett element.

1. Välj **Autonummer** -egenskap.

   De format som du kan använda i listan med automatiska nummer visas under egenskapen för autonummer.

1. Ange följande egenskaper:
   * **Stil**: Välj bland en mängd olika språkområdesspecifika eller generiska numreringsformat. Du kan välja format som arabiska-indiska, Devanagari, Georgiska, Decimal, Lower-Alpha med flera. För det aktuella exemplet väljer du `upper-alpha`.

   * **Format**: Standardformatet är `<x>`, där `x` värdet ersätts med det numreringsformat som du valde i egenskapen Format. Om du till exempel har valt `decimal` (1) och sedan värdet för `x` autostega steg för varje instans av `h1` och blir 2, 3 och så vidare. Du kan också lägga till egen text i fältet för att formatera rubrikformatet. Om du till exempel vill att alla h1-rubriker ska ha prefixet `Chapter`måste du ange det här fältet som `Chapter <x>`.

   * **Infoga tecken**: Om du vill lägga till ett specialtecken i formatet klickar du på Infoga tecken (<img src="./assets/insert-chars.png" width="25">). Markera det tecken du vill lägga till i formatformatet och klicka på Infoga. Det finns olika typer av specialtecken som du kan välja i listrutan Välj kategori. Välj till exempel högerpekande dubbelt vinkelcitattecken i kategorin Interpunktion.

      <img src="./assets/insert-special-chars.png" width="400">


   * **Starta numrering från**: Om du vill att numreringen ska börja från ett visst nummer anger du det värdet. Behåll till exempel standardvärdet 1.

   * **Indrag**: Om du vill dra in rubriken måste du ange värdet för Indrag. Ange det till exempel till 0 px.

      >[!NOTE]
      >
      >Du kan ange värdet i pixlar, pt (punkter), rem, em, % (procent) eller in (tum).

   * **Prefixbredd**: Det här är området som upptas av det automatiska nummerformatet. Den ställs automatiskt in på en storlek som enkelt kan anpassas till det valda formatformatet. Om du vill öka storleken kan du ersätta standardvärdet.

      När du anger det här värdet manuellt kan du prova att ändra de andra egenskaperna som påverkar bredden. Ändra till exempel teckenstorlek, format med prefix (kapitel) eller suffix (:) och ange det maximala värdet i *Starta numrering från* och de olika teckensnittsegenskaperna för den optimala storleken.

      Behåll till exempel standardvärdet.

   * **Mellanrum**: Ange det vågräta och lodräta avståndet. Behåll till exempel standardvärdena.

      Med ovanstående anpassningar anpassas formatet så som visas nedan:

      <img src="./assets/h1-style-custmization.png" width="500">

   * **Använd formatering på**: Egenskaperna under kategorin Autonom hjälper dig att definiera numreringsformatet. Om du vill anpassa numreringsformatet ytterligare eller innehållet i rubrikformatet kan du välja Numrering eller Stycke i det här fältet. Om du väljer Numrering tillämpas alla ändringar av kategorierna Teckensnitt, Kant, Layout och andra endast på numreringsformatet i rubriken. Om du väljer Stycke används dock ändringarna på rubrikinnehållet och inte på numreringsformatet.

   Använd följande inställningar för att generera utdata som visas på följande skärmbild:

   |**Rubrikformat**|**Egenskap**|**Värde**|**Ytterligare kommentarer**| | :- | :- | :- | :- | |h1|Style|Decimal|De här egenskaperna finns under kategorin Autonum | ||Format|`Capter <x>:`|| ||Prefixbredd|160 px|| ||Teckensnitt > Textjustering|Vänster|Kontrollera att Använd formatering för är inställt på Numrering| |h2|Format|Decimal|De här egenskaperna finns under kategorin Autonum | ||Format|`Section <x>:`|| ||Prefixbredd|125 px|| ||Teckensnitt > Textjustering|Vänster|Kontrollera att Använd formatering för är inställt på Numrering| |h3|Format|Decimal|De här egenskaperna finns under kategorin Autonum | ||Infoga nivå|2|| ||Format|`Section <2>.<x>:`|| ||Prefixbredd|125 px|| ||Teckensnitt > Textjustering|Vänster|Kontrollera att Använd formatering för är inställt på Numrering| ||

   <img src="./assets/auto-number-output.png" width="500">

## Arbeta med styckeformat

Du kan skapa ett styckeformat om du vill använda specialformatering för ett helt stycke. Med pseudoklassen kan du emellertid bara använda ett format på en viss del av texten. I följande exempel skapar vi ett styckeformat som använder anfangsformatet.

### Skapa anfangsstil

En anfangsstil (eller en versalstil som tappats) används i tidskrifter och litterära dokument där det första tecknet i ett stycke eller avsnitt får en viss speciell formatering. Du kan uppnå samma effekt med publiceringsfunktionen för PDF.

I följande exempel skapar vi en anfangsstil:

1. Öppna den formatmall du vill använda för redigering.

   >[!NOTE]
   Se *Anpassa ett fördefinierat eller nytt format* för att öppna en formatmall för anpassning eller redigering.

1. I **Stilar** listan, expandera **Styckeformat**.

1. Högerklicka på **Styckeformat** och välja **Nytt format**.

1. I *Lägg till format* dialogrutan, behålla **Tagg** namn som p och i **Pseudo** **Klass** fält, markera `::first-letter`.

1. Klicka **Klar**.

   Ett nytt styckeformat med namnet `::first-letter`  skapas och läggs till under **Styckeformat** lista.

1. Välj `::first-letter` under stilen p och ange följande egenskaper:

   * **Teckensnitt**: Ange önskat teckensnitt för den första bokstaven i stycket. Du kan till exempel ställa in teckensnittsfamiljen till kursiv, teckenbredden till 500, teckenstorleken till 30 pt och välja en teckensnittsfärg.

   * **Layout**: Ange lodrät justering för texten runt anfangsformatet. Vi ställer till exempel in Lodrät justering till Underkant.

Som `p` -taggen är kopplad till `<p>` i DITA behöver du inte lägga till det här formatet explicit med attributet outputClass. Var du än befinner dig i ditt innehåll `<p>` används anfangsformatet automatiskt. På följande skärmbild har kapitelrubriker, korta beskrivningar och definitionslistelement inte formaterats med anfangsformatet. Endast styckeformatet formateras med anfangsformatet:

<img src="./assets/char-style-drop-cap.png" width="500">

## Arbeta med teckenformat

Med teckenformat kan du skapa format för formatering av tecken och ord i innehållet. Du kan till exempel skapa ett teckenformat för infogad kod eller ett filnamn, eller skapa ett format som använder flera formatformat för markerat innehåll.

### Skapa ett textbundet teckenformat

Formatering av infogade tecken eller ord i ett stycke är ett mycket vanligt format. Det krävs två åtgärder för att skapa ett infogat format: först skapar du ett nytt format i formatmallen och sedan tillämpar du formatet i innehållet med `outputclass` -attribut.

I följande exempel skapar vi ett infogat teckenformat:

1. Öppna den formatmall du vill använda för redigering.

   >[!NOTE]
   Se *Anpassa ett fördefinierat eller nytt format* för att öppna en formatmall för anpassning eller redigering.

1. I **Stilar** listan, expandera **Teckenformat**.

1. Högerklicka på **Teckenformat** och välja **Nytt format**.

1. I dialogrutan Lägg till format behåller du **Tagg** namn som intervall och ange `BoldItalic` i **Klass** namnfält.

   <img src="./assets/create-char-style.png" width="400">

1. Klicka **Klar**.

   Ett nytt teckenformat med namnet code skapas och läggs till i listan Teckenformat.

1. Välj `span.BoldItalic` från **Teckenformat** och ange följande egenskaper:

   * **Teckensnitt**: Alla teckensnittsrelaterade egenskaper kan anpassas i det här avsnittet. Som standard medföljer vissa teckensnitt. Du kan välja önskat teckensnitt för teckenformatet. Ange till exempel teckensnittsfamiljen som *Serif,* och markera *Fet* och *Kursiv* i egenskapen Teckensnittsformat. Du kan också anpassa andra teckensnittsegenskaper som Teckenbredd (som fet, ljusare), Textdekoration (som understrykning, överstrykning), Teckenstorlek, Teckenfärg, Textjustering med mera.

      >[!NOTE]
      Du kan också lägga till teckensnitt i mallen, som lagras i avsnittet Resurser i mallen. Mer information om hur du lägger till teckensnitt och arbetar med resurser finns i **Lägg till en länk till avsnittet Resurser**.

   * **Layout**: Du kan ange layoutrelaterade egenskaper som höjd och bredd, marginal, utfyllnad, justering med mera.

   * **Bakgrund**: Med bakgrundsegenskaperna kan du formatera bakgrundsfärgen för ett visst format. Du kan definiera bakgrundsfärgen eller bilden för alla format.

När du har skapat det infogade teckenformatet måste du använda det i innehållet. Om du vill använda det infogade kodformatet går du till källvyn och lägger till `outputclass` -attribut i önskat innehåll:

`outputclass="BoldItalic"`

I följande exempel visas det fetkursiva formatet som används på olika ställen i den text som körs:

<img src="./assets/char-format-applied.png" width="500">

## Anpassa listformat

Listformaten innehåller standardformatinställningarna för de sorterade och osorterade listorna. Du kan enkelt anpassa de här listformaten så att de uppfyller dokumentationskraven.

I följande exempel anpassar vi det numrerade eller ordnade listformatet:

1. Öppna den formatmall du vill använda för redigering.

   >[!NOTE]
   Se *Anpassa ett fördefinierat eller nytt format* för att öppna en formatmall för anpassning eller redigering.

1. I **Stilar** listan, expandera **Listformat**.

1. Välj **ol** i listan.

   Egenskaperna för verktygstilen visas på egenskapspanelen tillsammans med förhandsvisningen.

   <img src="./assets/list-style-default.png" width="500">

1. Välj **Avancerad formatering** alternativ.

   Ett bekräftelsemeddelande visas.

1. Klicka **Ja** på *Bekräftelse* meddelande för att öppna **Avancerad formatering** egenskaper.

   Följande egenskaper är tillgängliga som standard:

   * **Nivå**: Som standard finns det sex nivåer med numrerade listor. Den nivå du väljer i den här listrutan styr formatändringen på den valda nivån och alla efterföljande nivåer. Om du t.ex. väljer nivå 4, ställs alla formatändringar du gör in på nivåerna 4, 5 och 6.

   * **Listformatstyp**: Det finns ett antal listnumreringsformat som du kan välja mellan. Listan innehåller språkspecifika och generiska numreringsformat som används för att skapa en numrerad lista. Vissa listformat är arabiska, kambodjanska, devanagari, etiopisk, hangul, hebreiska, japanska, koreanska, enkel kinesiska, urdu med flera.

   Dessutom kan du arbeta med följande avancerade formateringsegenskaper:

   * **Nummerformat**: Standardformatet är `<x>`, där `x` värdet ersätts med det numreringsformat som du valde i egenskapen Listformattyp. Om du till exempel har valt `decimal` (1) och sedan värdet för `x` stega automatiskt efter varje förekomst av listelementet och blir 2, 3 osv. Du kan också lägga till egen text i fältet för att formatera listformatet. Om du till exempel vill att alla listformat på första nivån ska ha suffixet &quot;`)`&quot;, måste du ange det här fältet som listformat på första nivån som &quot;`<x>)`&quot;.

   * **Infoga tecken**: Om du vill lägga till ett specialtecken i nummerformatet klickar du på Infoga tecken (<img src="./assets/insert-chars.png" width="25">). Markera det tecken du vill lägga till i formatformatet och klicka på Infoga. Det finns olika typer av specialtecken som du kan välja i listrutan Välj kategori.

   * **Infoga nivå**: Du kan inkludera talet från någon av de föregående nivåerna i talformatet. Om du till exempel vill inkludera nummerformatet från 5 på 6:e nivån i talformatet väljer du 5 i listrutan Infoga nivå. Observera att listrutan Infoga nivå endast visar siffrorna för föregående nivåer och inte för följande nivå. När du till exempel är på nivå 3 visas bara nivåerna 1 och 2 i listan Infoga nivå.

      <img src="./assets/list-insert-level.png" width="400">

      Du kan också ändra nummerformatet för att visa listvärdena efter behov. Om du t.ex. använder ett kapslat nummerformat för nivå 3 kan du formatera det som &quot;`<2>.<x>))`&quot;. Här visas listnummer 2, följt av en punkt, följt av listnummer 3 och sedan två hakparenteser, som `2.3))`.

   * **Indrag**: Om du vill dra in listan måste du ange värdet för Indrag. Alla ändringar i indraget kan granskas på panelen Förhandsgranska och justeras.

      >[!NOTE]
      Du kan ange värdet i pixlar, pt (punkter), rem, em, % (procent) eller in (tum).

   * **Prefixbredd**: Det här är det område som upptas av nummerformatet. Den ställs automatiskt in på en storlek som lätt kan anpassas till det valda formatet. Om du vill öka storleken kan du ersätta standardvärdet.

      När du anger det här värdet manuellt kan du prova att ändra de andra egenskaperna som påverkar bredden. Du kan till exempel ändra teckensnittsstorlek, format med prefix eller suffix och de olika teckensnittsegenskaperna så att den optimala storleken visas.

   * **Mellanrum**: Ange det vågräta avståndet mellan listnummerformatet och innehållet. Det lodräta avståndet styr mellanrummet mellan de två listobjekten.

      I följande skärmbild visas den anpassade sorterade listan för varje nivå:

      <img src="./assets/list-number-format-final.png" width="500">


## Arbeta med tabellformat

Med formatmallarna kan du designa *n* antal tabellformat. Med tabellformaten kan du utforma hur hela tabellen, en viss rad eller kolumn, ska se ut. Med kontroll för formatering på cellnivå kan du skapa mycket presenterbara tabellformat.

I följande exempel ser vi hur du skapar ett tabellformat och de olika tabellformateringsalternativen som du kan anpassa:

1. Öppna den formatmall du vill använda för redigering.

   >[!NOTE]
   Se *Anpassa ett fördefinierat eller nytt format* för att öppna en formatmall för anpassning eller redigering.

1. I **Stilar** högerklicka på **Tabellformat** och välja **Nytt format**.

1. I *Lägg till format* dialogrutan, behålla **Tagg** namn som `table` och ange `double-border` i **Klass** namnfält.

1. Klicka **Klar**.

   Ett nytt tabellformat med namnet `table.double-border` skapas och läggs till i listan Tabellformat.

1. Välj `table.double-border` från **Tabellformat** och ange följande egenskaper:

   * **Använd formatering på**: Du kan välja att formatera hela tabellen, udda/jämna rader eller kolumner, eller första/sista raden eller kolumnen.

      >[!NOTE]
      Följande inställningar är tillgängliga under **Allmänt** sektion när **Använd formatering på** är inställd på **Hela tabellen**.

   * **Figursättning**: Välj hur text ska radbrytas runt tabellen. Detta är användbart när tabellen finns i ett annat blocknivåelement och tabellen måste återges tillsammans med annat innehåll i blockelementet. Radbrytningsalternativen är *vänster* eller *höger* justerad, eller *ingen*.

   * **Dölj kantlinje**: Välj utseende på tabellkanten. Om du markerar komprimering ritas bara en kantlinje mellan tabellcellerna. För olika format visas emellertid kantlinjen runt varje cell med ytterligare utfyllnad.

      <img src="./assets/table-style-collapse-separate.png" width="500">

   * **Kantavstånd**: Den här inställningen är bara tillgänglig när kryssrutan Komprimera är inställd på Separat. Med den här inställningen kan du ange det lodräta och vågräta avståndet mellan cellkanterna.

      <img src="./assets/table-border-spacing.png" width="500">

      >[!NOTE]
      Följande inställningar är tillgängliga under **Cell** sektion när **Använd formatering på** är inställd på **Hela tabellen**.

   * **Utfyllnad**: Ange utfyllnaden mellan tabellceller. Du kan ange olika utfyllnadsvärden för de övre, nedre, vänstra och högra sidorna.

   * **Lodrät justering**: Ange den lodräta justeringen för cellinnehåll. Tillgängliga alternativ är: Överkant, Mitten och Nederkant.

   * **Kantsida, stil, färg, bredd, radie:** Ange kantrelaterade egenskaper. Du kan välja att bara ha kantlinjer på vissa sidor, som vänster eller höger. I kantlinjeformatet visas tillgängliga kantlinjeformat som Heldragen, Streckad, Dubbel rad med mera. Ange kantfärgen med färgpaletten. Du kan ange kantbredden i px, pt, rem, em, % och i enheter. Radien definierar kurvan för att skapa runda hörn.

   Övriga egenskaper under Teckensnitt, Kant, Layout, Sidnumrering och Bakgrund beskrivs i andra exempel i det här avsnittet. Beroende på vad du har valt i **Använd formatering på** kan du använda dessa värden för hela tabellen eller för markerade rader eller kolumner.

   En förhandsvisning av en exempeltabell med olika rader formaterade på ett annat sätt visas nedan:

   <img src="./assets/table-final-design.png" width="500">

## Arbeta med andra format

Om du arbetar med strukturerat (DITA) innehåll kommer du att märka att nästan alla DITA-element har en formatkoppling i standardformatmallen. Till exempel en `<shortdesc>` elementets format definieras under **Annat format** > **.shortdesc** formatdefinition. Du kan enkelt anpassa alla dessa format och de används automatiskt i PDF-utdata som genereras från ditt strukturerade innehåll. Det innebär att du, till skillnad från andra anpassade format, inte behöver lägga till ett `outputclass` på innehållet i dessa format.

Om du vill skapa en formatdefinition för ett element som inte är tillgängligt som standard, eller om du har ett anpassat element, kan du enkelt skapa det i formatmallen. Det enda du behöver tänka på är att skapa formatet med samma namn som det strukturerade elementets namn.

I följande exempel skapar vi ett nytt fönsternamn (`wintitle`):

1. Öppna den formatmall du vill använda för redigering.

   >[!NOTE]
   Se *Anpassa ett fördefinierat eller nytt format* för att öppna en formatmall för anpassning eller redigering.

1. I **Stilar** lista, expandera **Andra format**.

1. Högerklicka på **Annat format** och välja **Nytt format**.

1. I *Lägg till format* dialogrutan, behålla **Tagg** namn som *blank* och ange `wintitle` i **Klass** namnfält.

   Som `wintitle` är ett känt DITA-elementnamn, formatdefinitionen mappas automatiskt till `<wintitle>` -element i källan.

1. Klicka **Klar**.

   Ett nytt format med namnet `.wintitle` skapas och läggs till under **Andra format** lista.

1. Välj .wintitle på menyn **Andra format** och ange egenskaperna efter behov.

På följande skärmbild visas den wintitle-stil som används på texten &quot;Primär kontroll&quot;.

<img src="./assets/other-style-wintitle.png" width="500">