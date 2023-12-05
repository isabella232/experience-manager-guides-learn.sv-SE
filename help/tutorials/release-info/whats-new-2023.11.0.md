---
title: Versionsinformation | Nyheter i Adobe Experience Manager Guides, november 2023-versionen
description: Läs om de nya och förbättrade funktionerna i november 2023-utgåvan av Adobe Experience Manager Guides as a Cloud Service.
source-git-commit: 880cd344ceb65ea339be699ebcad41c0d62e168a
workflow-type: tm+mt
source-wordcount: '803'
ht-degree: 0%

---

# Nyheter i november 2023-utgåvan av Adobe Experience Manager Guides as a Cloud Service

I den här artikeln beskrivs de nya och förbättrade funktionerna i versionen från november 2023 av Adobe Experience Manager Guides (senare kallad *as a Cloud Service stödlinjer för Experience Manager*).

Mer information om uppgraderingsinstruktioner, kompatibilitetsmatris och problemen som åtgärdas i den här versionen finns i [Versionsinformation](release-notes-2023.11.0.md).

## Förbättringar av inbyggda PDF

Följande förbättringar av ursprungligt PDF har gjorts i november 2023:

### Använda och duplicera färdiga PDF-mallar

Experience Manager Guides innehåller färdiga mallar eller PDF-mallar. Duplicera PDF-mallarna i fabriken för att skapa anpassade PDF-mallar.

Nu kan du även förhandsvisa miniatyrbilden för en mall när du skapar och duplicerar en mall. Du kan också redigera eller ta bort den här bilden. Den här funktionen är användbar när du vill märka ut eller skilja ut mallar med liknande namn.
Läs mer om [PDF-mall](../native-pdf/pdf-template.md).

![Mallen Duplicera PDF](assets/duplicate-template.png){width="550" align="left"}

*Duplicera en befintlig PDF-mall.*


### Ändra ordningen på sidorna och publicera flera sidor per ark

Förutom att publicera sidorna enligt källdokumentet kan du även ändra ordningen på sidorna i PDF när du publicerar ett flersidigt dokument.  Detta ger dig flexibilitet att publicera sidorna i olika ordningsföljd, som alla udda eller alla jämna sidor först. Du kan även publicera som ett häfte och läsa sidorna som en bok. Du kan också bestämma hur många sidor du vill publicera på ett enda pappersark. Mer information finns i [Sidorganisation](../native-pdf/components-pdf-template.md#page-organization) -avsnitt.

### Sortera ordlistor baserat på sorteringsnycklar

Nu kan du även sortera ordlistorna baserat på sorteringsnycklar. Du kan använda taggen&quot;sort-as&quot; för att definiera en sorteringsnyckel för ordlistorna. Sedan kan du sortera dem baserat på sorteringsnycklar i stället för villkoren. På så sätt kan du sortera ordlistorna efter termer som används på olika språk. Du kan också definiera en sorteringsnyckel för en ordlista med en fras eller en grupp med ord.
Mer information finns i [Avancerade PDF-inställningar](../native-pdf/components-pdf-template.md#advanced-pdf-settings).


### Förbättrad resurshantering för mallar i Native PDF

Experience Manager Guides har nu förbättrat resurshanteringen för mallar för inbyggda PDF. Nu kan du dela och återanvända resurser, som bilder, CSS-filer och teckensnittsfiler, i flera olika PDF-mallar. I och med den här förbättringen är det mycket enklare att hantera resurser för en stor uppsättning mallar. Du behöver inte skapa dubblettresurser för varje mall, och du kan behålla dem i en delad mapp och använda dem i alla mallar i PDF.
Mer information finns i [PDF-mall](../native-pdf/pdf-template.md).

## Förbättringar i Web Editor

Följande förbättringar av webbredigeraren har gjorts i november 2023:


### Visa filer efter namn eller filnamn

Nu kan du välja standardsättet att visa filerna i Web Editor. Du kan visa fillistan efter titlarna eller filnamnen från de olika panelerna i redigeringsvyn.

![Dialogrutan Användarinställningar](assets/user-preferences-2311.png){width="550" align="left"}

*Ändra standardsättet att visa filerna från **Användarinställningar**-dialogrutan.*


### Hantera villkorsförinställningar

Du kan definiera villkorsattribut i dina DITA-avsnitt. Använd sedan villkorsattributen i villkorsförinställningen för att publicera innehållet i en DITA-karta. Nu kan du även skapa och hantera villkorsförinställningar i Web Editor med hjälp av stödlinjerna i Experience Manager. Du kan också enkelt redigera, duplicera eller ta bort dem.

![Förinställda villkor på fliken Hantera i webbredigeraren ](assets/web-editor-manage-condition-presets.png){width="550" align="left"}

Mer information finns i [Använda förinställningar för villkor](../user-guide/generate-output-use-condition-presets.md).

### Återställ filflikar när webbläsaren uppdateras

Stödlinjer i Experience Manager återställer läget för de öppna filflikarna i webbredigeraren när du uppdaterar webbläsaren. Mer information finns i **Uppdatera webbläsaren när filerna redigeras** avsnitt under [Redigera ämnen i Web Editor](../user-guide/web-editor-edit-topics.md).

### Frigör enkelt ett element

Nu kan du enkelt frigöra ett element med hjälp av alternativet på snabbmenyn för ett element i Web Editor. Det gör det enklare att sammanfoga elementets text med dess överordnade element.
Mer information finns i **Dela upp ett element** från [andra funktioner i Web Editor](../user-guide/web-editor-other-features.md).

### Kortkommandon för att flytta markören

Nu kan du använda kortkommandon för att flytta markören i webbredigeraren med hjälp av stödlinjerna i Experience Manager. Du kan använda kortkommandona för att snabbt flytta ett ord åt vänster eller höger. Du kan också gå till början eller slutet av raden med hjälp av kortkommandona.
Nu kan du också använda kortkommandon för att flytta markören till början av nästa element eller till slutet av föregående element.
Läs mer om [kortkommandon i Web Editor](../user-guide/web-editor-keyboard-shortcuts.md).
