---
title: Versionsinformation | Nyheter i Adobe Experience Manager Guides 4.3.0
description: Läs om de nya och förbättrade funktionerna i 4.3.0-utgåvorna av Adobe Experience Manager Guides
source-git-commit: 7581085859785c5b8b597ecfeb7dbe58c7c9e2bc
workflow-type: tm+mt
source-wordcount: '2639'
ht-degree: 0%

---

# Nyheter i version 4.3.0 av Adobe Experience Manager Guides (juli 2023)

I den här artikeln beskrivs de nya och förbättrade funktionerna i version 4.3.0 av Adobe Experience Manager Guides (senare kallat *AEM stödlinjer*).

Mer information om uppgraderingsinstruktioner, kompatibilitetsmatris och problemen som åtgärdas i den här versionen finns i [Versionsinformation](./release-notes-4.3.md).


## Ansluta till en datakälla och infoga data i dina ämnen

Nu kan du snabbt ansluta till dina datakällor med färdiga anslutningar från AEM. Om du ansluter till en datakälla kan du synkronisera informationen med källan och alla uppdateringar av data återspeglas automatiskt, vilket gör AEM stödlinjer till ett verkligt innehållsnav. Den här funktionen hjälper dig att spara tid och arbete med att manuellt lägga till eller kopiera data.

Med AEM Guides kan administratören konfigurera färdiga anslutningar för JIRA- och SQL-databaser (MySQL, PostgreSQL, SQL Server, SQLite). De kan även lägga till andra kopplingar genom att utöka standardgränssnitten.
När du har lagt till dem kan du visa de konfigurerade anslutningarna som listas under panelen Datakällor i webbredigeraren.

<img src="assets/data-sources.png" alt="Lista med datakällor i panelen" width="300">

Skapa ett innehållsavdrag för att hämta data från en ansluten datakälla. Sedan kan du infoga data i dina ämnen och redigera dem. När du har skapat en generator för innehållsfragment kan du återanvända den för att infoga data i alla ämnen.

Nu kan du även skapa ett ämne från en ansluten datakälla. Ett ämne kan innehålla data i olika format, som tabeller, listor och stycken. Du kan också skapa en DITA-karta för alla ämnen. Du kan koppla metadata till ämnet när du drar från en datakälla.

Mer information finns i [Använd data från datakällan](../user-guide/web-editor-content-snippet.md).

## Lägg till citat i innehållet

Citat är referenser till den informationskälla som har lagts till i innehållet. Citat hjälper er att skapa trovärdighet och förebygga plagiarism. Citat hjälper läsarna att hitta källan och verifiera den information som finns i texten.

I AEM kan du lägga till citat eller importera citat och använda dem i ditt innehåll. Du kan lägga till dessa citat från alla typer av böcker, webbplatser och journaler.

När du har infogat dina citat i dina ämnen kan du förhandsgranska dem i webbredigeraren. Du kan också publicera innehåll med citat med hjälp av PDF.

![Citat från en panel](assets/citation-panel.png){width="300" align="left"}


Mer information finns i [Lägga till och hantera citat i ditt innehåll](../user-guide/web-editor-apply-citations.md).

## Publicera till ett innehållsfragment

Innehållsfragment är separata innehållsdelar i AEM. De är strukturerade innehåll baserat på en innehållsmodell. Innehållsfragment är rent innehåll utan design- eller layoutinformation. De kan redigeras och hanteras oberoende av de kanaler som AEM stöder. Innehållsfragmentens modularitet och återanvändbarhet ger större flexibilitet, enhetlighet, effektivitet och enklare hantering.

Nu kan du publicera ett ämne eller elementen i ett ämne till ett innehållsfragment med hjälp av AEM. Du kan skapa en JSON-baserad mappning mellan ett ämne och en innehållsfragmentmodell. Använd den här mappningen för att publicera innehåll som finns i vissa eller alla element i ett ämne till ett innehållsfragment.

Använd kraftfulla guider AEM innehållsfragment och använd innehållsfragment på alla AEM. Du kan också extrahera informationen via API:er som stöds av innehållsfragment.

![alternativ för publicering av innehållsfragment](assets/content-fragment-publish.png){width="550" align="left"}


## Förbättrade granskningar

AEM Guides har nu förbättrad granskningsfunktion med följande funktioner:

### Granskningspanelen för att visa granskningsprojekt och aktiva granskningsåtgärder

Nu gör AEM guider granskningarna smidigare. Här finns panelen Recensioner i Web Editor. På panelen Granska visas alla granskningsprojekt och de aktiva granskningsåtgärderna i granskningsprojekten som du är en del av.

Som författare kan du använda den här funktionen för att enkelt öppna granskningsuppgifterna, visa kommentarerna och snabbt hantera kommentarerna i en centraliserad vy.
![](assets/active-review-task-comments.png){width="800" align="left"}
Mer information finns i **Granska** funktionsbeskrivning i [Vänster panel](../user-guide/web-editor-features.md#id2051EA0M0HS) -avsnitt.

### Sök i granskningsämnen

Att genomföra granskningar är en viktig funktion i AEM. Det hjälper granskarna att granska de dokument de tilldelats.
Nu kan du söka efter ett ämne genom att ange en del av texten i titeln eller filsökvägen i sökfältet i ämnesvyn på granskningspanelen. Du kan också välja att visa alla ämnen eller ämnen med kommentarer. Som standard kan du visa alla ämnen som ingår i granskningsaktiviteten.


![Söka i en ämnespanel för granskning](assets/review-search-topic.png){width="800" align="left"}

Mer information finns i [Granska ämnen](../user-guide/review-topics.md).

## Guides Extension Framework

Skapa anpassade paket ovanpå AEM guider för att få utbyggbarhet med hjälp AEM Guides Extension Framework. De här paketen är användbara för utvecklare och konsulter och ger dem utökningsbarhet till komponenterna i redigeraren. De kan ha knappar, dialogrutor och listrutor som mål och lägga till anpassade JavaScript-skript som enkelt kan samverka med AEM för användargränssnittet för stödlinjer.



## Förbättringar av inbyggda PDF

Följande förbättringar av det inbyggda PDF har gjorts i version 4.3.0 för att göra AEM Guides till en mer robust produkt:

### Stöd för språkvariabler

AEM Guides har stöd för språkvariabler. Du kan använda språkvariabler för att definiera en lokaliserad version av körklara etiketter som Anteckning, Varning och Varning eller statisk text i utdata från PDF.
Du kan lägga till språkvariablerna eller den lokaliserade versionen av etiketterna i lämpliga avsnitt i utdata från PDF och i utdatamallarna.

#### Språkvariabler i utdata från PDF

Du kan använda språkvariablerna för att definiera lokaliserade etiketter för element som Anteckning, Varning och Varning. Du kan uppdatera värdet för dessa variabler på ett eller flera språk, och sedan hämtas det lokaliserade värdet automatiskt i utdata från PDF.
Du kan till exempel visa etiketten Note i PDF-utdata på följande sätt:

* Engelska: Note
* Franska: Remarque
* Tyska: Hinweis

#### Språkvariabler i utdatamallarna

Om du vill skapa PDF-utdata på olika språk måste du skapa olika PDF-mallar med lokaliserad text för varje språk. Med funktionen för språkvariabler behöver du bara skapa mallen en gång. För statisk text som du behöver lokalisera kan du sedan skapa motsvarande språkvariabler och använda dem i mallen.
Du kan skapa språkvariabler för längre text, till exempel en hel mening eller till och med ett stycke. Du kan också använda format och formatera dessa språkvariabler med HTML-kod.

Mer information finns i [Stöd för språkvariabler](../native-pdf/native-pdf-language-variables.md).

### Lägga till en vattenstämpel i utdata från PDF för utkast till dokument

Nu kan du lägga till en vattenstämpel i utdata från PDF i dokumentet som ännu inte är godkänt. Den här vattenstämpeln visas inte om du genererar PDF för dokumentet i dokumentet Godkänt. Du kan till exempel lägga till en vattenstämpel i Utkast för PDF.

Mer information finns i [Lägga till en vattenstämpel i PDF för utkast till dokument](../native-pdf/use-javascript-content-style.md#watermark-draft-document).

### Möjlighet att använda AEM metadata i PDF-layouter

Metadata är beskrivningen eller definitionen av ditt innehåll. Dessa metadata lagras i DITA-källans kartinnehåll.

I AEM kan du nu även välja metadataegenskaper för dina resurser och lägga till dem i sidlayouten. Sedan AEM Guides dessa metadataegenskaper för dina resurser och publicerar dem i utdata från PDF.


![lägga till metadata för PDF-filer](assets/native-pdf-metadata-asset.png){width="300" align="left"}

>[!NOTE]
>
> AEM har också stöd för metadataegenskaperna för dina DITA-kartor.

Mer information finns i [Lägga till fält och metadata](../native-pdf/design-page-layout.md#add-fields-metadata).


### Ordna sidor i utdata från PDF

Du kan visa eller dölja följande avsnitt i PDF och även ordna i vilken ordning de ska visas i det slutliga PDF-resultatet:

* Innehåll
* Kapitel och ämnen
* Lista över figurer
* Lista över tabeller
* Index
* Ordlista
* Citat
* Sidlayouter

Om du inte vill visa ett visst avsnitt i utdata för PDF kan du dölja det genom att stänga av växlingsknappen.

Mer information finns i [Sidordning](../native-pdf/components-pdf-template.md#page-order).

### Sammanfoga sidor

I utdata från PDF som är inbyggda börjar alla avsnitt som standard på en ny sida. Nu kan du sammanfoga ett avsnitt med föregående sida eller nästa sida. Detta publicerar avsnittet tillsammans med den markerade sidan i utdata från PDF och det finns ingen sidbrytning däremellan.

Mer information finns i beskrivningen av funktionen Sammanfoga sidor i [Sidordning](../native-pdf/components-pdf-template.md#page-order) -avsnitt.

### Statiska sidor

Du kan också skapa anpassade sidlayouter och publicera dem som statiska sidor i utdata från PDF. Detta hjälper dig att lägga till statiskt innehåll som anteckningar eller tomma sidor.

Mer information finns i beskrivningen av funktionen Statiska sidor i [Sidordning](../native-pdf/components-pdf-template.md#page-order) -avsnitt.


### Variabler i korsreferenser

Du kan använda variabler för att definiera en korsreferens. När du använder en variabel hämtas dess värde från egenskaperna.

Nu kan du också använda {figure} och {table}.
Använd {figure}om du vill lägga till en korsreferens till bildnumret. Numret väljs bland de automatiska nummerformat som du har definierat för bildtext.

Använd {table} om du vill lägga till en korsreferens till tabellnumret. Tabellnumret väljs bland de automatiska nummerformat som du har definierat för bildtext.

Mer information finns i [Korsreferenser](../native-pdf/components-pdf-template.md##cross-references).

### Starta ett kapitel från den aktuella sidan

Du kan ange grundläggande konfigurationsinställningar för att starta ett kapitel från udda eller jämn sida, innehållsförteckningsstrukturen och definiera ledarradformatet för posterna i innehållsförteckningen.

Nu kan du också starta ett kapitel från den aktuella sidan. Om du väljer att göra det publiceras alla kapitel vidare utan sidbrytningar. Om ett kapitel t.ex. slutar mitt på sidan 15, börjar nästa kapitel också från den 15:e sidan.


### Möjlighet att få åtkomst till temporära HTML-filer när du genererar PDF-utdata

Nu kan du ladda ned de temporära HTML-filerna som skapas när du genererar PDF-utdata AEM stödlinjer. Välj alternativet att hämta de temporära filerna i inställningarna för förinställningar för utdata.  AEM Guides kan du sedan hämta de temporära filer som skapades när du genererade utdata med den förinställningen.

Den här funktionen ger bättre insikter i genereringsprocessen med tillgång till tillfälliga format och layouter och hjälper dig att korrigera eller ändra dina CSS-format efter dina behov.

![den avancerade inställningsdialogrutan för den inbyggda PDF-filen](assets/native-pdf-advanced-settings.png){width="800" align="left"}

Mer information finns i [Skapa en förinställning för PDF](../web-editor/native-pdf-web-editor.md#create-output-preset).


### Omdesign av CSS-redigeraren

Nu har CSS-redigeraren fått en ny design för att ge en bättre användarupplevelse med väljare och formategenskaper.

#### Förbättring av dialogrutan Lägg till format

Nu kan du använda anpassade väljare för att lägga till komplexa format. Det nya fältet Väljare hjälper dig att lägga till anpassade väljare förutom kombinationen Klass, Tagg och Pseudoklass. Du kan till exempel skapa `table a.link` format för alla hyperlänkar i en tabell.

![lägga till format i de ursprungliga PDF-mallarna](assets/add-styles-native-pdf.png){width="300" align="left"}

#### Anpassa egenskaper för format

Nu visar AEM stödlinjer en ny egenskapspanel under förhandsvisningsavsnittet för format. Du kan redigera egenskaperna för formaten effektivare och snabbare på egenskapspanelen.


## Byta namn på och flytta filer i databasvyn

Nu kan du även byta namn på eller flytta en fil från databaspanelen. Den här funktionen är praktisk och hjälper dig att hantera dina filer enkelt från panelen Databas. Du kan markera en fil och byta namn på den eller flytta den med **Alternativ** -menyn för den markerade filen. AEM Guides visar ett meddelande när du flyttar eller byter namn på en fil.

![alternativmeny för en fil](assets/rename-move-assets.png){width="550" align="left"}

Mer information om alternativmenyn för en fil finns i **Databasvy** funktionsbeskrivning i [Vänster panel](../user-guide/web-editor-features.md#id2051EA0M0HS) -avsnitt.

## Rapporten Brutna länkar i Web Editor

Med AEM Guides kan du kontrollera om dina tekniska dokument är fullständiga och generera rapporter från Web Editor. I juni 2023 AEM Guides finns en funktion för att visa och åtgärda brutna länkar. Det här är en användbar rapport som hjälper dig att hantera brutna länkar. Du kan enkelt visa de brutna länkar som finns på DITA-kartan och även åtgärda dem.
![rapport över bruten länk](assets/broken-link-report.png){width="800" align="left"}

När du har åtgärdat en länk visas den inte under listan med brutna länkar.

Mer information finns i [Visa och korrigera brutna länkar](../user-guide/reports-web-editor.md#report-broken-links).

## Förbättringar av schematron

### Använd rapportsatser för att kontrollera regler i schemat

AEM Guides har nu även stöd för rapportprogramsatser med Schematron. En rapportprogramsats genererar ett meddelande när en testprogramsats utvärderas till true. Om du till exempel vill att den korta beskrivningen ska innehålla högst 150 tecken kan du definiera en rapportsats för att kontrollera ämnen där den korta beskrivningen innehåller mer än 150 tecken.

Mer information finns i [Använd assert- och report-satser för att kontrollera regler](../user-guide/support-schematron-file.md#schematron-assert-report).

### Använd Regex-uttryck

Du kan också använda Regex-uttryck för att definiera en regel med funktionen match() och sedan utföra valideringen med filen Schematron.

Mer information finns i [Använd Regex-uttryck](../user-guide/support-schematron-file.md#schematron-assert-report).


### Definiera abstrakta mönster

AEM har även stöd för abstrakta mönster i Schematron. Du kan definiera allmänna abstrakta mönster och återanvända dessa abstrakta mönster. Abstrakta mönster kan förenkla schemat i Schematron och även hjälpa dig att hantera och uppdatera valideringslogiken.


Mer information finns i [Definiera abstrakta mönster](../user-guide/support-schematron-file.md#schematron-abstract-patterns).

## Stöd för XLIFF-format i översättning

AEM Guides har också stöd för XLIFF-formatet (XML Localization Interchange File Format) vid översättning. Nu kan du också välja att **Skapa ett nytt XLIFF-översättningsprojekt** för att konvertera XML-innehållet till XLIFF-format. AEM har stöd för XLIFF version 1.2.

Med det här formatet kan du exportera innehållet till det branschledande XLIFF-formatet och sedan tillhandahålla samma format till översättningsleverantörerna. Mer information finns i [Skapa ett översättningsprojekt](../user-guide/translate-documents-web-editor.md#create-translation-project).

![typer av översättningsprojekt](assets/translation-project-types.png){width="350" align="left"}


## Förbättringar av kartsamling

Med en kartsamling kan du ordna flera kartor och grupppublicera dem. Många nya förbättringar har gjorts i kartsamlingen:

* Nu kan du lägga till förinställningar för inbyggda PDF-utdata i en kartsamling och använda dem för att generera utdata från PDF.
* Du kan visa de förinställningar för global profil och mappprofil som har skapats av administratören och använda dem för att generera utdata från PDF.
* Nu kan du inte bara välja en enskild förinställning, utan även aktivera alla förinställningar för mappprofiler för en DITA-karta på en gång.
  ![redigera en kartsamling](assets/edit-map-collection.png){width="800" align="left"}

Mer information finns i [Använd kartsamling för generering av utdata](../user-guide/generate-output-use-map-collection-output-generation.md).

## Inbyggt PDF-stöd i kontrollpanelen för masspublicering


Med AEM Guides funktion för massaktivering kan du snabbt och enkelt aktivera ditt innehåll från redigering till publicering. På kartan för massaktivering kan du inkludera utdataförinställningen för PDF, AEM Site, PDF, HTML5, Custom och JSON.
Mer information finns i [Massaktivering av publicerat innehåll](../user-guide/conf-bulk-activation.md).

## Förbättrat verktyg för massflyttning

Som administratör kan du nu använda det förbättrade verktyget för massflyttning för att flytta mappar med många filer från en plats till en annan.
Du kan använda dialogrutan Bläddra efter filer för att välja de källmappar som du vill flytta. Du kan också bläddra och välja målplats att flytta källmapparna till. Välj ![informationsikon](assets/info-icon.svg) {width="25" align="left"} i närheten av ett fält för att visa mer information om det.

Mer information finns i [Flytta flera filer samtidigt](../user-guide/authoring-file-management.md#move-files-bulk).

## Förbättrad Favoritpanel

AEM hjälper dig att skapa en samling eller favoritlista över filer och mappar och använda dem enkelt. Nu **Alternativ** finns även i **Favoriter** -panelen. Du kan byta namn på den markerade samlingen eller ta bort den från **Alternativ** -menyn. Du kan välja **Uppdatera** om du vill få en ny lista över filer eller mappar från databasen. Du kan även visa mappinnehållet i resursgränssnittet.

![panelen Favoriter](assets/favorites-options.png){width="650" align="left"}

>[!NOTE]
>
> Du kan även uppdatera listan med **Uppdatera** överst.

Mer information om **Alternativ** -menyn i en Favoriter-samling, visa **Favoriter** funktionsbeskrivning i [Vänster panel](../user-guide/web-editor-features.md#id2051EA0M0HS) -avsnitt.

## Växla till systemtemat

Nu kan du även använda enhetstemat. Använda **Användarinställningar** kan du konfigurera AEM för att automatiskt växla mellan ljusa och mörka teman baserat på temat på din enhet.

![användarinställningar](assets/device-theme-user-preferences.png){width="550" align="left"}

Mer information finns i **Användarinställningar** funktionsbeskrivning i [Huvudverktygsfältet](../user-guide/web-editor-features.md#id2051EA0G05Z) -avsnitt.
