---
title: Versionsinformation | Nyheter i Adobe Experience Manager Guides 4.2.1
description: Läs om de nya och förbättrade funktionerna i 4.2.1-utgåvorna av Adobe Experience Manager Guides
source-git-commit: 8ea7b6d80b94d24910ac00bf1fb1d40d6992a166
workflow-type: tm+mt
source-wordcount: '701'
ht-degree: 0%

---

# Nyheter i version 4.2.1 av Adobe Experience Manager Guides (maj 2023)

I den här artikeln beskrivs de nya och förbättrade funktionerna i version 4.2.1 av Adobe Experience Manager Guides (senare kallat *AEM stödlinjer*).

Mer information om uppgraderingsinstruktioner, kompatibilitetsmatris och problemen som åtgärdas i den här versionen finns i [Versionsinformation](release-notes-4.2.1.md) artikel.

## Navigera från webbredigeraren till AEM hemsida

Nu kan du enkelt navigera från webbredigeraren till AEM navigeringssida.

![](assets/web-editor-launch-page.png){width="800" align="left"}

* Klicka på **Stödlinjer** ikon (![](assets/aem-guides-icon.png) ), för att gå tillbaka till AEM.


Mer information finns i [AEM](../user-guide/web-editor-launch-editor.md#id2056BG00RZJ)

## Avancerat stöd för metadata vid PDF-publicering

AEM Guides har nu avancerat stöd för metadata som mappas till metadata i utdata från PDF. Metadataalternativen innehåller information om dokumentet och dess innehåll, till exempel författarens namn, dokumenttitel, nyckelord, copyrightinformation och andra datafält.

<img src="assets/pdf-metadata.png" alt=" inbyggda PDF-metadata">

Du kan importera en XMP och AEM stödlinjer kan välja information från filen. Du kan också ange metadatanamn och värden i listrutan. Du kan också lägga till anpassade metadata genom att skriva direkt i namnfältet.

Mer information finns i **Metadata** funktionsbeskrivning i [Skapa en förinställning för PDF](../web-editor/native-pdf-web-editor.md).

### Förbättrad dispositionsvy

AEM innehåller en förbättrad panel för dispositionsvy där du kan se den hierarkiska vyn över de element som används i dokumentet.

<img src="assets/select-element-content-outline-view_cs.png" alt=" inbyggda PDF-metadata">

I dispositionsvyn finns följande förbättringar:

* Listrutan Visningsalternativ visas högst upp på panelen Dispositionsvy. Om ett element har ett ID, attribut och text kan du markera dem i listrutan för att visa dem tillsammans med elementet. De attribut som kan visas i dispositionsvyn bestäms av inställningarna för visningsattribut som har konfigurerats av administratören i **Inställningar för Redigeraren**.

* Med sökfunktionen kan du söka efter ett element efter dess namn, id, text eller attributvärde.

Mer information finns i beskrivningen av funktionen Konturvy i [Vänster panel](../user-guide/web-editor-features.md#id2051EA0M0HS) -avsnitt.

## Generera multimedierapporten från webbredigeraren

AEM Guides innehåller en funktion för att generera rapporter för dina tekniska dokument.  Du kan använda den här funktionen för att visa ämneslistan och hantera metadata för dina dokument. Nu kan du även se multimedia som används i alla referenser för den aktuella kartan från **Rapporter** i Web Editor.

Du kan generera multimedierapporten som innehåller detaljerad information om multimedia som används i referenserna på den aktuella kartan. Du kan filtrera och sortera multimediefilerna som visas i rapporten.
Du kan också generera CSV-filen för att hämta den aktuella ögonblicksbilden av multimedia som används i DITA-kartan.

<img src="assets/web-editor-reports-multimedia.png" alt="multimedierapport" width="600">

Mer information finns i beskrivningen av funktionen Generera en multimedierapport i [DITA-kartrapport från Web Editor](../user-guide/reports-web-editor.md) -avsnitt.

## PDF | Ändringsfält för att ange ändrade ämnen i innehållsförteckningen

AEM Guides gör att du snabbt kan identifiera ändrade ämnen i innehållsförteckningen för PDF.  En ändringsbar visas till vänster om de ändrade ämnena i innehållsförteckningen. Du kan klicka på ämnet i innehållsförteckningen och visa detaljerade ändringar.

<img src="assets/change-marker-toc.png" alt="Ändra markör i innehållsförteckning " width="500">

Mer information finns i [Arbeta med anpassade ändringsfältstilar](../native-pdf/change-bar-style.md).



## PDF | Formatera sidmarkören i fotnotskomponenten

Nu kan du formatera sidmarkören i fotnoterna. Du kan till exempel lägga till hakparenteser eller ändra deras färg. Dessa format gör det enkelt för användarna att identifiera sidmarkörerna i dokumentet.

Mer information finns i [Använda anpassade format i fotnoter](../native-pdf/footnote-number-style.md).

## Öppna och spela upp video- eller ljudfiler i Web Editor

AEM Guides innehåller nu en funktion för att öppna och spela upp ljud- och videofiler i Web Editor. Du kan ändra volymen eller vyn för videon. Du kan även välja att **Hämta**, ändra **Uppspelningshastighet**, eller visa **Bild-i-bild**.

<img src="assets/video-web-editor.png" alt="spela upp video" width="600">

Mer information finns i funktionsbeskrivningen för databasvyn i [Vänster panel](../user-guide/web-editor-features.md#id2051EA0M0HS) -avsnitt.
