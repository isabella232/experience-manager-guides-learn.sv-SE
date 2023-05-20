---
title: Arbetsflöde efter generering
description: En översikt över arbetsflödet efter generering med ett exempel
exl-id: e19fdc0b-0ec6-46ce-81ed-e9490d12c029
source-git-commit: 3cfa0a58c5681668fbb3c97dcbe1e8f7e32335fc
workflow-type: tm+mt
source-wordcount: '317'
ht-degree: 0%

---

# Publicering av AEM - arbetsflöde efter generering

AEM Guides ger dig flexibilitet att ange ett arbetsflöde för postutdata. Du kan utföra vissa efterbehandlingsåtgärder på utdata som genereras med hjälp av AEM.
Du kan till exempel ange vissa egenskaper för utdata från PDF eller skicka ett e-postmeddelande till en uppsättning användare när utdata har genererats.


## Vilka steg ingår för att använda arbetsflöden efter generering?

### Skapa en arbetsflödesprocess

Skapa en Java- eller ECMA-baserad arbetsflödesprocess som utför åtgärden på genererade utdata. Du kan till exempel kopiera vissa metadata från källan till det genererade innehållet eller ändra metadata för genererade utdata.
- Vi tar ett exempel på hur man skapar en sådan process med ECMA-skript (du kan referera till det bifogade paketet)
- För Java-baserad arbetsflödesprocess, se avsnitt &quot;*Anpassa arbetsflödet för efterhandsproduktion*&quot; från [Installations- och konfigureringshandbok](https://helpx.adobe.com/content/dam/help/en/xml-documentation-solution/4-2/Adobe-Experience-Manager-Guides_UUID_Installation-Configuration-Guide_EN.pdf#page=119)


### Skapa en arbetsflödesmodell

Skapa en arbetsflödesmodell och lägg till det steget i med den anpassade arbetsflödesprocessen som du skapade i föregående steg.
- Du måste också lägga till ett obligatoriskt processteg *Slutför postgenerering*&quot; som det sista steget i arbetsflödet.

Se exempelarbetsflödesmodellen nedan:

![Arbetsflödesmodell efter generering](../assets/workflows/pgwf-workflow-model.png)


### Använd det här arbetsflödet efter generering på en karta

Arbetsflödet efter generering är en egenskap som kan konfigureras för alla förinställningar i publiceringsmekanismen AEM Guides. Exempel:

![Arbetsflöde efter generering på förinställning av utdata](../assets/workflows/pgwf-preset-settings.png)


Anta att den valda modellen redan har skapats.


### Testning

Nu kan du köra publiceringen med den här förinställningen och validera processstegets utdata


## Exempel

Som referens kan du använda paketet nedan och installera det via pakethanteraren för att testa arbetsflödet för eftergenerering (*enligt skärmbilderna ovan*)

[Exempel på ECMA-baserad arbetsflödesmodell för postgenerering](../assets/workflows/sample-pgwf-ecma-test-wfmetadata.zip)
