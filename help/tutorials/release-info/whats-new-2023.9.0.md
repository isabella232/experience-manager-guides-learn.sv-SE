---
title: Versionsinformation | Nyheter i Adobe Experience Manager Guides, september 2023
description: Läs om de nya och förbättrade funktionerna i september 2023-versionen av Adobe Experience Manager Guides as a Cloud Service
source-git-commit: 880cd344ceb65ea339be699ebcad41c0d62e168a
workflow-type: tm+mt
source-wordcount: '1683'
ht-degree: 0%

---

# Nyheter i september 2023-versionen av Adobe Experience Manager Guides as a Cloud Service

I den här artikeln beskrivs de nya och förbättrade funktionerna i versionen från september 2023 av Adobe Experience Manager Guides (kallas senare *AEM stödlinjer as a Cloud Service*).

Mer information om uppgraderingsinstruktioner, kompatibilitetsmatris och problemen som åtgärdas i den här versionen finns i [Versionsinformation](release-notes-2023.9.0.md).

## Ansluta till en datakälla och infoga ämnen

AEM Guides har färdiga kopplingar som hjälper dig att ansluta till datakällor, vilket gör AEM stödlinjer till ett verkligt innehållsnav. Detta ger dig en fördel av att spara tid och arbete som annars skulle ha ägnats åt manuell datainmatning eller replikering.

Tillsammans med de befintliga färdiga anslutningarna som JIRA och SQL (MySQL, PostgreSQL, SQL Server, SQLite) kan administratören även konfigurera anslutningarna för databaserna MariaDB, H2DB, Adobe Commerce och Elasticsearch. De kan även lägga till andra kopplingar genom att utöka standardgränssnitten.

Du kan visa konfigurerade anslutningar under **Datakällor** i webbredigeraren.

<img src="assets/data-sources.png" alt="Lista med datakällor i panelen" width="300">

*Visa de anslutna datakällorna.*

Nu kan du även skapa ett ämne från en ansluten datakälla. Ett ämne kan innehålla data i olika format, som tabeller, listor och stycken. Du kan också skapa en DITA-karta för alla ämnen. Du kan koppla metadata till ämnet när du drar från en datakälla.

Mer information finns i [Använd data från datakällan](../user-guide/web-editor-content-snippet.md).

## Lägg till citat i innehållet

Citat är referenser till den informationskälla som har lagts till i innehållet. Citat hjälper er att skapa trovärdighet och förebygga plagiarism. Citat hjälper läsarna att hitta källan och verifiera den information som finns i texten.

I AEM kan du lägga till citat eller importera citat och använda dem i ditt innehåll. Du kan lägga till dessa citat från alla typer av böcker, webbplatser och journaler.

När du har infogat dina citat i dina ämnen kan du förhandsgranska dem i webbredigeraren. Du kan också publicera innehåll med citat med hjälp av PDF.

![Citat från en panel](assets/citation-panel.png){width="300" align="left"}

*Visa listan med citat på panelen Citat.*

Mer information finns i [Lägga till och hantera citat i ditt innehåll](../user-guide/web-editor-apply-citations.md).


## Publicera till ett innehållsfragment

Innehållsfragment är separata innehållsdelar i AEM. De är strukturerade innehåll baserat på en innehållsmodell. Innehållsfragment är rent innehåll utan design- eller layoutinformation. De kan redigeras och hanteras oberoende av de kanaler som AEM stöder. Innehållsfragmentens modularitet och återanvändbarhet ger större flexibilitet, enhetlighet, effektivitet och enklare hantering.

Nu kan du publicera ett ämne eller elementen i ett ämne till ett innehållsfragment med hjälp av AEM. Du kan skapa en JSON-baserad mappning mellan ett ämne och en innehållsfragmentmodell. Använd den här mappningen för att publicera innehåll som finns i vissa eller alla element i ett ämne till ett innehållsfragment.

Använd kraftfulla guider AEM innehållsfragment och använd innehållsfragment på alla AEM. Du kan också extrahera informationen via API:er som stöds av innehållsfragment.

![alternativ för publicering av innehållsfragment](assets/content-fragment-publish.png){width="550" align="left"}

*Publicera ett ämne till ett innehållsfragment.*

Mer information finns i [Publicera till ett innehållsfragment](../user-guide//publish-content-fragment.md).

## Förbättrade granskningar

AEM Guides har nu förbättrad granskningsfunktion med följande funktioner:

### Sök i granskningsämnen

Att genomföra granskningar är en viktig funktion i AEM. Det hjälper granskarna att granska de dokument de tilldelats.
Nu kan du söka efter ett ämne genom att ange en del av texten i titeln eller filsökvägen i sökfältet i ämnesvyn på granskningspanelen. Du kan också välja att visa alla ämnen eller ämnen med kommentarer. Som standard kan du visa alla ämnen som ingår i granskningsaktiviteten. Mer information finns i [Granska ämnen](../user-guide/review-topics.md).

![Söka i en ämnespanel för granskning](assets/review-search-topic.png){width="800" align="left"}

*Sök i ett granskningsavsnitt på granskningspanelen.*



## Guides Extension Framework

Skapa anpassade paket ovanpå AEM guider för att få utbyggbarhet med hjälp AEM Guides Extension Framework. De här paketen är användbara för utvecklare och konsulter och ger dem utökningsbarhet till komponenterna i redigeraren. De kan ha knappar, dialogrutor och listrutor som mål och lägga till anpassade JavaScript-skript som enkelt kan samverka med AEM för användargränssnittet för stödlinjer.



## Förbättringar av inbyggda PDF

Följande förbättringar av det inbyggda PDF gjordes i versionen från september 2023 för att göra AEM Guides till en mer robust produkt:



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

I utdata från PDF som är inbyggda börjar alla avsnitt som standard på en ny sida. Nu kan du sammanfoga ett avsnitt med föregående sida eller nästa sida. Detta publicerar avsnittet tillsammans med den markerade sidan i utdata från PDF och det finns ingen sidbrytning mellan dem.

Mer information finns i **Sammanfoga sidor** funktionsbeskrivning i [Sidordning](../native-pdf/components-pdf-template.md#page-order) -avsnitt.

### Starta ett kapitel från den aktuella sidan

Du kan ange grundläggande konfigurationsinställningar för att starta ett kapitel från udda eller jämn sida, innehållsförteckningsstrukturen och definiera ledarradformatet för posterna i innehållsförteckningen.

Nu kan du också starta ett kapitel från den aktuella sidan. Om du väljer att göra det publiceras alla kapitel vidare utan sidbrytningar. Om ett kapitel t.ex. slutar mitt på sidan 15, börjar nästa kapitel också från den 15:e sidan.

Mer information finns i **Allmänt** tabbbeskrivning i  [Avancerade PDF-inställningar](../native-pdf/components-pdf-template.md#advanced-pdf-settings-advanced-pdf-settings).

### Statiska sidor

Du kan också skapa anpassade sidlayouter och publicera dem som statiska sidor i utdata från PDF. Detta hjälper dig att lägga till statiskt innehåll som anteckningar eller tomma sidor.

Mer information finns i **Statiska sidor** funktionsbeskrivning i [Sidordning](../native-pdf/components-pdf-template.md#page-order) -avsnitt.


### Variabler i korsreferenser

Du kan använda variabler för att definiera en korsreferens. När du använder en variabel hämtas dess värde från egenskaperna.

Nu kan du också använda {figure} och {table}.
Använd {figure}om du vill lägga till en korsreferens till bildnumret. Numret väljs bland de automatiska nummerformat som du har definierat för bildtext.

Använd {table} om du vill lägga till en korsreferens till tabellnumret. Tabellnumret väljs bland de automatiska nummerformat som du har definierat för bildtext.

Mer information finns i [Korsreferenser](../native-pdf/components-pdf-template.md##cross-references).



### Omdesign av CSS-redigeraren

Nu har CSS-redigeraren fått en ny design för att ge en bättre användarupplevelse med väljare och formategenskaper.

#### Förbättring av dialogrutan Lägg till format

Nu kan du använda anpassade väljare för att lägga till komplexa format. Det nya fältet Väljare hjälper dig att lägga till anpassade väljare förutom kombinationen Klass, Tagg och Pseudoklass. Du kan till exempel skapa `table a.link` format för alla hyperlänkar i en tabell.

![lägga till format i de ursprungliga PDF-mallarna](assets/add-styles-native-pdf.png){width="300" align="left"}

*Lägg till information om det nya formatet.*

#### Anpassa egenskaper för format

Nu visar AEM stödlinjer en ny egenskapspanel under förhandsvisningsavsnittet för format. Du kan redigera egenskaperna för formaten effektivare och snabbare på egenskapspanelen.


## Stöd för olika ämnesdefinitioner i en och samma uppräkningsdefinition

Du kan nu definiera en eller flera ämnesdefinitioner i en karta och uppräkningsdefinitionerna i en annan karta och sedan lägga till kartreferensen. Ämnesuppräkningsreferenserna löses i samma karta eller i den refererade kartan.

Du kan nu även definiera villkor och använda dem för vissa specifika element i ett ämne.  Villkoren visas bara för dessa specifika element och inte för alla andra element.

Mer information om hur du hanterar hierarkiska definitioner för ämnesdefinitioner och uppräkningar finns i objektschemats funktionsbeskrivning i [Vänster panel](../user-guide/web-editor-features.md#id2051EA0M0HS) -avsnitt.





## Markera alla förinställningar i en kartsamling

Du kan inte bara aktivera en enskild förinställning och alla förinställningar för mappprofiler, utan även aktivera alla förinställningar för en DITA-karta på en gång.
![redigera en kartsamling](assets/edit-map-collection-cs.png){width="800" align="left"}\
*Markera alla förinställningar i en kartsamling.*

Mer information finns i [Använd kartsamling för generering av utdata](../user-guide/generate-output-use-map-collection-output-generation.md).


## Inbyggt PDF-stöd i kontrollpanelen för masspublicering


Med AEM Guides funktion för massaktivering kan du snabbt och enkelt aktivera ditt innehåll från redigering till publicering. På kartan för massaktivering kan du inkludera utdataförinställningen för PDF, AEM Site, PDF, HTML5, Custom och JSON.
Mer information finns i [Massaktivering av publicerat innehåll](../user-guide/conf-bulk-activation.md).

## Förbättrat verktyg för massflyttning

Som administratör kan du nu använda det förbättrade verktyget för massflyttning för att flytta mappar med många filer från en plats till en annan.
Du kan använda dialogrutan Bläddra efter filer för att välja de källmappar som du vill flytta. Du kan också bläddra och välja målplats att flytta källmapparna till. Välj ![informationsikon](assets/info-icon.svg) {width="25" align="left"} i närheten av ett fält för att visa mer information om det.

Mer information finns i [Flytta flera filer samtidigt](../user-guide/authoring-file-management.md#move-files-bulk).


## Förbättrad förhandsgranskning på snabbmenyn

Använd snabbmenyn för att snabbt förhandsgranska filen (.dita, .xml, audio, video eller image) utan att öppna den. Du kan nu ändra storlek på förhandsgranskningsfönstret, och om innehållet innehåller en referenslänk kan du markera den och öppna den på en ny flik.

![Förhandsgranskningsfönster ](assets/quick-preview_cs.png){width="800" align="left"}

*Förhandsgranska filen i rutan.*

Mer information om snabbmenyn finns i **Alternativ för en fil** funktionsbeskrivning i [Vänster panel](../user-guide/web-editor-features.md#id2051EA0M0HS) -avsnitt.


## Använd variabler för aktuellt datum och aktuell tid i alternativen Målsökväg, Platsnamn eller Filnamn

När du genererar utdata AEM Site eller PDF kan du använda variabler för att ställa in **Målsökväg**, **Platsnamn**, eller **Filnamn** alternativ. Nu kan du även använda `${system_date}`och `${system_time}` variabler. Dessa variabler hjälper dig att lägga till aktuellt datum och aktuell tid till dessa alternativ.

Lär dig hur [använd variabler för att ange alternativen Målsökväg, Platsnamn eller Filnamn](../user-guide/generate-output-use-variables.md).
