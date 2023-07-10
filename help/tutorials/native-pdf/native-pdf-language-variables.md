---
title: PDF | Stöd för språkvariabler
description: Använda språkvariabler i utdata- och utdatamallar för PDF
source-git-commit: 3e922ef7ed9af200aa8fcfb0cbe4489cf059e335
workflow-type: tm+mt
source-wordcount: '1221'
ht-degree: 0%

---


# Stöd för språkvariabler

AEM innehåller funktioner för att använda språkvariabler. Du kan använda språkvariabler för att definiera lokaliserade strängar i utdata från PDF eller för att lokalisera statisk text i utdatamallarna. Du kan använda CSS-format för att lokalisera strängarna som kommer från en CSS.

## Använd språkvariabler i PDF-utdata

Du kan använda språkvariabler för att definiera en lokaliserad version av körklara etiketter som Anteckning, Varning och Varning eller statisk text i utdata från PDF. Variabelnamnet är detsamma för alla språk men kan ha olika värden för de olika språken. Du kan uppdatera värdet för dessa variabler på ett eller flera språk, och sedan hämtas det lokaliserade värdet automatiskt i utdata från PDF.

Du kan till exempel ha följande sätt att presentera etiketten: `Note` i utdata från PDF:

- Engelska: Anteckning

- Franska: Remarque

- Tyska: Hinweis

<img src="./assets/language-variable-output.png" width="550">

>[!NOTE]
>
> Om värdet för en variabel inte definieras i ett visst språk väljs strängen som en reservfunktion i AEM stödlinjer.
>
> Om du inte har definierat värdet på gränssnittets språk söker den efter engelska (`en_us`), annars väljer den engelska(`en`) och visas på samma sätt i utdata från PDF.

### Typer av språkvariabler

AEM har stöd för två typer av variabler: Program- och användarvariabler.

#### Programvariabler

AEM innehåller en uppsättning fördefinierade eller färdiga programvariabler. Du kan använda de här fördefinierade variablerna för att lägga till information om ett dokument som är specifikt för AEM stödlinjer. Till exempel `chapter-number` om den finns med på en sida visar kapitelnumret som sidan tillhör. The `author-label` variabeln visar namnet på dokumentets författare.

>[!NOTE]
>
> Du kan åsidosätta värdet för en programvariabel.


#### Användarvariabler

Du kan också skapa nya språkvariabler. Du kan t.ex. skapa en användarvariabel, Publisher, för etiketten för utgivaren av dokumentet.

>[!NOTE]
>
>  Du bör ha administratörsbehörighet för att skapa användarvariabler och redigera programvariabler.

<img src="./assets/add-language-variables.png" width="550">

### Lägg till en ny språkvariabel

1. Gå till fliken Utdata i Web Editor.
1. Välj **Språkvariabler** <img src="./assets/language-variables.svg" width="25"> i den vänstra panelen.
1. Välj **Redigera** för att öppna **Språkvariabler** -fönstret. Programmet och användarvariablerna som finns i det valda språket visas i alfabetisk ordning. Värdena visas enligt det valda språket. Om du t.ex. väljer franska visas&quot;Tips&quot; som&quot;Konsol&quot;.
1. Från **Språk** väljer du det språk som du vill redigera en variabel på.

   >[!NOTE]
   >
   > Om du inte visar de önskade språken aktiverar du det önskade språket på menyn **Inställningar för språkvariabel**. Välj inställningar <img src="./assets/settings-icon.svg" width="25">  för att öppna **Inställningar för språkvariabler** -dialogrutan.

1. Ange variabelnamnet i dialogrutan **Namn** kolumnen och dess värde i **Värde** kolumn.

   >[!NOTE]
   >
   >Du kan använda valfritt HTML-innehåll som ett variabelvärde om du vill visa variabelvärdet i en viss formatering. Du kan till exempel lägga till `<b>` -taggen till variabelvärdet för att visa utgivaren i fet stil.

1. Välj **Lägg till språkvariabel** <img src="./assets/add-language-variable.svg" width="25"> om du vill lägga till en ny språkvariabel för det valda språket. Om du lägger till en variabel till ett språk läggs den automatiskt till på alla språk. Du kan inte skapa en variabel med samma namn som en befintlig variabel. Ett fel visas.

>[!NOTE]
>
> Om du inte markerar **Lägg till språkvariabel**, skapas inte variabeln och läggs till i listan

### Alternativ för en språkvariabel

Håll pekaren över variabeln för att visa **Alternativ** meny för den.

<img width="550" src="./assets/language-variable-user-options.png">

Du kan förhandsgranska både program- och användarvariabler. Om du vill visa hur variabelns värde visas i utdata väljer du **Förhandsgranska** från **Alternativ** den markerade variabelns meny.
Du kan också välja att **Ta bort** eller **Duplicera** användarvariablerna. Om du tar bort en variabel från ett språk tas den automatiskt bort från alla språk.

### Redigera eller återställa programvariablerna

Du kan också redigera värdena för en programvariabel. Senare kan du återställa en programvariabel till det ursprungliga värdet. **Återställ variabel** <img src="./assets/application-variable-revert.svg" width="25">  visas för en programvariabel med ett ändrat värde.

## Använda språkvariabler i utdatamallarna

Du bör lägga till språkvariabler i dina lokaliserade dokument. Du kan infoga dessa språkvariabler i sidlayouten som visas på olika sidor i dina lokaliserade dokument. Du kan till exempel lägga till språkvariabeln för `author-name` som visas i sidlayoutens sidhuvudsområde (eller andra delar som sidfoten eller brödtexten).

<img src="./assets/language-variable-page-layout.png" width="550">

På följande skärmbild visas författaren och varumärkesnamnet som finns i utdata från PDF som genererats för det franska språket.


Infoga en språkvariabel som `copyright-label` i sidhuvudsområdet utför du följande steg:

1. Öppna önskad sidlayout för redigering.

   >[!NOTE]
   >
   > Visa [Anpassa en sidlayout](../native-pdf/components-pdf-template.md#customize-a-page-layout-customize-page-layout) för att öppna en sidlayout för anpassning eller redigering.

1. Markera rubriken för att aktivera den för att infoga en variabel.
1. Välj **Infoga variabel**  <img src="./assets/insert-language-variable.svg" width="25"> i verktygsfältet.
1. I **Infoga variabel** markerar du namnet på den språkvariabel som ska infogas och klickar på **Infoga** för att infoga den i sidhuvudsområdet.

   >[!NOTE]
   >
   > Du kan också ange söksträngen i textrutan. Variabelnamnen som innehåller den angivna strängen filtreras och visas i listan.
   > Den valda språkvariabeln infogas i sidhuvudsområdet.

På följande skärmbild visas värdet för `copyright-label` läggs till i sidhuvudsområdet.

<img src="./assets/language-variable-header.png" width="550">

### Använd innehållsformat på språkvariabler

Förutom det värde du tilldelar en språkvariabel kan du även använda HTML-taggar för att visa variabelvärdet i en viss formatering. Du kan till exempel visa värdet för `publisher-label` i fet stil.

- Du kan också formatera värdeformaten med <span> -tagg. Om du till exempel använder språkvariabeln för sidnummer kan du visa sidnumret i latinskt nummerformat på engelska och ange formatet för andra språk.

  Värde för engelska:
  `<span data-field="page-number" data-format="upper-roman">1</span>`

  Värde för tamil:
  `<span data-field="page-number" data-format="tamil">1</span>`

På samma sätt kan du lägga till språkvariabler och formatera andra fält som listas i funktionen Infoga fält i sidlayouterna. Mer information om hur du lägger till fält finns i [Lägg till fält och metadata](../native-pdf/design-page-layout.md#add-fields-metadata).

- Du kan också lägga till lokaliserade bilder i värdena. Du kan till exempel lägga till en bildikon på kapitelnummerspråket och få lokaliserade bilder av ikonen i utdata från PDF.

  För engelska kan variabelvärdet för en bild vara som `<img src="banner-en.jpg">`och för samma variabel på tyska kan den `<img src="banner-de.jpg">`. Så bilderna tas upp beroende på språk.

## Lokalisera strängarna med CSS-format

Med CSS-format kan du också lokalisera strängarna som används i ett autonummer som Kapitel, Avsnitt, Figur och Tabell. Eftersom de här strängarna kommer från CSS-filer kan du inte lokalisera dem med språkvariabler. Om du vill lokalisera de här strängarna kan du skapa CSS-format för varje språk där du vill lokalisera dem.
Du kan till exempel använda följande CSS för att visa kapitelprefixet och motsvarande talformat på olika språk.
Du kan till exempel använda följande CSS för att visa Kapitel som Hoofdstuk på tyska och kapitelnumret i decimalformat. För japanska kan du använda det japanska nummerformatet för att visa kapitelnumren i innehållsförteckningen.

```
// for English
h1:before {
  counter-increment: h11;
  content: "Chapter " counter(h11, decimal)".";
}

// for German
:root:lang(de) h1:before {
  content: "Hoofdstuk " counter(h11, decimal)".";
}

// for Japanese
:root:lang(ja) h1:before {
  content: "章 " counter(h11, japanese-formal)".";
}
```

På följande skärmbilder visas strängarna på tyska och japanska PDF.

<img src="./assets/localize-chapter-german.png" width="550">

<img src="./assets/localize-chapter-japanese.png" width="550">

### Formatera prefixen

Med CSS-format kan du även formatera prefixen. Du kan till exempel formatera etiketten `Note` som ska visas i röd färg i utdata från PDF på olika språk.

```
.note .prefix-content 
{
color: red;
} 
```



