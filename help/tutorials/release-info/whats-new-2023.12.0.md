---
title: Versionsinformation | Nyheter i Adobe Experience Manager Guides, december 2023-versionen
description: Läs om de nya och förbättrade funktionerna i december 2023-utgåvan av Adobe Experience Manager Guides as a Cloud Service.
source-git-commit: 9fcc8faec4631d710dbdfd7e4f8567069d0ba120
workflow-type: tm+mt
source-wordcount: '1012'
ht-degree: 0%

---

# Nyheter i december 2023-utgåvan av Adobe Experience Manager Guides as a Cloud Service

I den här artikeln beskrivs de nya och förbättrade funktionerna i Adobe Experience Manager-handbokens version från december 2023 (senare kallad *as a Cloud Service stödlinjer för Experience Manager*).

Mer information om uppgraderingsinstruktioner, kompatibilitetsmatris och problemen som åtgärdas i den här versionen finns i [Versionsinformation](release-notes-2023.12.0.md).


## Använd variabler i utdata från Native PDF

Du kan använda variabeluppsättningar för att dynamiskt infoga och hantera information som kan ändras baserat på specifika villkor som produktnamn och versioner. Med den här funktionen kan du använda samma PDF-layout och generera utdata med olika värden. Du behöver inte skapa separata layouter för varje värdeuppsättning.

Du kan till exempel skapa en variabeluppsättning för varje produkt. Den här variabeluppsättningen kan bestå av variabler för olika produktdetaljer som ProductName, VersionNumber och ReleaseDate. Sedan kan du lägga till olika värden för dessa variabler.

**Variabeluppsättning 1: Adobe-set1**

* ProductName: Experience Manager Guides
* Versionsnummer: 2311
* Releasedatum: 2023-11-02

**Variabeluppsättning 1: Adobe-set2**

* ProductName: Experience Manager Guides
* Versionsnummer: 2310
* Releasedatum: 2023-09-27


![inbyggda PDF-variabler](assets/native-pdf-variables.png){width="800" align="left"}

*Skapa variabler på fliken Utdata i Web Editor.*

Du kan också skapa variabler med värden som har HTML-taggar. Lägg till exempel till bilder från innehålls-DAM med `<img>` -tagg.

När du har skapat variablerna kan du lägga till variablerna på lämpliga platser i dokumentet med hjälp av sidlayouterna i utdatamallarna. Värdena hämtas automatiskt i utdata från PDF baserat på den variabeluppsättning som du väljer i utdataförinställningen.



<img src="./assets/native-pdf-variable-output.png" alt="Sidfot i utdata från PDF" width="500" border="2px">

*Generera utdata för PDF med hjälp av variabler i layouten PDF.*

Med den här funktionen kan du generera skräddarsytt material med dynamiskt innehåll i dokumentationen och hantera ändringarna effektivt. Du kan också använda format och formatera variablerna med HTML.

Du kan också snabbt uppdatera värdena för variabeluppsättningar när det behövs och återskapa utdata. Om du till exempel behöver uppdatera informationen för en version kan du uppdatera värdet för versionen i VersionNumber och generera om utdata.


## Förbättrad upplevelse för att redigera attributen

Nu får du en omgjord upplevelse som lägger till eller redigerar attributen för ett element från **Innehållsegenskaper** i webbredigeraren.

![Panelen Attribut](assets/attributes-multiple-properties.png){width="300" align="left"}

*Lägg till attribut från panelen Innehållsegenskaper.*

Du kan också enkelt redigera och ta bort attributen.

Mer information finns i **Innehållsegenskaper** funktionsbeskrivning i [Höger panel](../user-guide/web-editor-features.md#id2051EB003YK) -avsnitt.


## Redigera metadata vid redigering

När du redigerar kan du nu uppdatera filens metadatataggar med hjälp av listrutan i **Filegenskaper** i den högra panelen. Du kan också välja **Redigera fler egenskaper** för att uppdatera fler metadata.

![file-properties](assets/file-properties-general.png){width="300" align="left"}

*Uppdatera metadata och redigera filegenskaper från den högra panelen.*

Mer information finns i **Filegenskaper** funktionsbeskrivning i [Höger panel](../user-guide/web-editor-features.md#id2051EB003YK) -avsnitt.

## Möjlighet att publicera innehåll i ServiceNow-kunskapsbasen

Nu kan du även publicera ditt innehåll på ServiceNow-kunskapsbasplattformen.

I december 2023-utgåvan kan du som administratör skapa en publiceringsprofil för ServiceNow-kunskapsbasservern. Som författare eller utgivare kan du sedan välja den ServiceNow-publiceringsprofilen i förinställningen för utdata för att publicera utdata till den angivna kunskapsbasen.

Med den här funktionen kan du publicera innehåll, som text, videoklipp och bilder, på kunskapsbasplattformen ServiceNow och underhålla ett omfattande arkiv.


![service now knowledge base preset](assets/knowledgebase--output-preset.png){width="300" align="left"}

*Skapa en förinställning för utdata för kunskapsbasen ServiceNow.*


## Förbättrad kontrollpanel för kartsamling

Stödlinjerna i Experience Manager har en förbättrad kontrollpanel för kartsamling. I en kartsamling kan du snabbt konfigurera flera metadataegenskaper för DITA-kartorna. Den här funktionen är praktisk eftersom du inte behöver uppdatera metadataegenskaperna för varje DITA-karta separat.

Nu kan du visa filnamnet på DITA-kartan. Du kan också visa baslinjerna. På så sätt kan du snabbt hitta den baslinje som används för en förinställning.

![Kontrollpanel för kartsamling](assets/map-collection-dashboard.png){width="800" align="left"}

*Visa, redigera och generera utdata från kartsamlingens kontrollpanel.*

## Visa nyckelattribut i Kartvyn

När du definierar nyckelattribut för ämnet eller mappningsreferenserna kan du även visa titeln, motsvarande ikon och nyckeln i den vänstra panelen. Tangenten visas som `key=<key-name>`.

Mer information finns i **Kartvy** funktionsbeskrivning i [Vänster panel](../user-guide/web-editor-features.md#id2051EA0M0HS) -avsnitt.

![tangenter i kartvyn](assets/view-key-title-map-view.png) {width="300" align="left"}

*Visa nyckelattributet i Kartvyn.*

## Möjlighet att duplicera en baslinje baserat på etikett

Experience Manager Guides ger nu en bättre användarupplevelse när du skapar baslinjer från Web Editor.\
![skapa ny baslinje](assets/create-new-baseline.png) {width="300" align="left"}
*Skapa baslinje i Web Editor.*

Du kan också duplicera en baslinje baserat på etiketten. Referensversionen väljs baserat på den angivna etiketten (om den finns) när du duplicerar, eller också väljs versionen från den duplicerade baslinjen.


![duplicera en baslinje ](assets/duplicate-baseline.png) {width="300" align="left"}

*Duplicera en baslinje baserat på en etikett eller skapa en exakt kopia.*

## Förbättrad process för att skapa kartsamling med massaktivering

Processen med att skapa en gruppaktiveringskarta är nu mer harmonisk. När nu sidan Aktiveringsresultat visas kan du se resultaten av aktivering och loggar.
Mer information finns i [Skapa en gruppaktiveringskarta](../user-guide/conf-bulk-activation-create-map-collection.md).



## Lösa länkar för korsmappning i AEM webbplatsutdata

Korsmappslänkar (XREF med scope-peer) som återges i AEM webbplatsutdata tolkas nu enligt filtiteln för publiceringskontexten som angetts för den genererade kartan.


## Konfigurera URL:en för AEM som ska använda dokumenttiteln

Med hjälp av stödlinjerna i Experience Manager kan du som administratör konfigurera URL:en för AEM webbplatsutdata. Om filnamnet inte finns eller innehåller alla specialtecken kan du konfigurera så att de ersätts med en avgränsare i URL:en för AEM platsutdata. Du kan även ersätta dem med namnet på det första underordnade ämnet. Lär dig hur [konfigurera URL:en för AEM som ska använda dokumenttiteln](../cs-install-guide/conf-output-generation.md#configure-the-url-of-the-aem-site-output-to-use-the-document-title).

