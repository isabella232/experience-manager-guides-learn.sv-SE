---
title: Publiceringsfunktion för PDF | Använd JavaScript för att arbeta med innehåll eller format
description: Lär dig hur du skapar formatmallar och skapar format för ditt innehåll.
source-git-commit: 09918abbdade934468dea1c55d0ca2cd60622b35
workflow-type: tm+mt
source-wordcount: '425'
ht-degree: 0%

---


# Använd JavaScript för att arbeta med innehåll eller stil

Med funktionen för publicering i PDF kan du köra JavaScript för att ändra innehåll eller format som används på innehåll innan PDF skapas. Med den här funktionen får du fullständig kontroll över hur det slutliga resultatet genereras. Du kan till exempel lägga till juridisk information till utdata från PDF, som finns i andra PDF. Med JavaScript kan du lägga till juridisk information när PDF har skapats för basinnehållet, men innan PDF skapas.\
För att JavaScript-körning ska fungera får du följande callback-funktioner i Native PDF-publiceringsfunktionen:

* `window.pdfLayout.onBeforeCreateTOC(callback)`: Den här återanropsfunktionen körs innan innehållsförteckningen genereras.
* `window.pdfLayout.onBeforePagination(callback)`: Den här återanropsfunktionen körs efter att innehållsförteckningen har genererats, men innan sidbrytningar läggs till i PDF.
* `window.pdfLayout.onAfterPagination(callback)`: Den här återanropsfunktionen körs efter innehållsförteckningen och sidbrytningarna läggs till i PDF.

>[!NOTE]
>
>Internt underhålls en körningssekvens för dessa bildtextfunktioner. Först körs onBeforeCreateTOC, följt av onBeforePagination och slutligen körs onAfterPagination.

Beroende på vilken typ av innehåll eller formatändring du vill utföra kan du välja vilken callback-funktion som ska användas. Om du till exempel vill lägga till innehåll bör du göra det innan innehållsförteckningen genereras. Om du vill göra vissa formatuppdateringar kan de göras antingen före eller efter sidnumreringen.

I följande exempel ändras positionen för figurtitlarna från ovanför bilderna till under bilderna. Därför måste du aktivera alternativet för JavaScript-körning i förinställningen. Gör så här:

1. Öppna förinställningen för redigering.
1. Gå till **Avancerat** -fliken.
1. Välj **Aktivera JavaScript** alternativ.
1. Spara förinställningen och stäng den.

Skapa sedan en JavaScript-fil med följande kod och spara den i mappen Resources i mallen:

```css
...
/*
* DITA only allows the figure title to be placed above images 
* This JavaScript code is used to move the figure title below the image
* */
window.addEventListener('DOMContentLoaded', function () {
    window.pdfLayout.onBeforeCreateTOC(function() {
        var titleNodes = document.querySelectorAll('.fig > .title')
        for (var i = 0; i < titleNodes.length; i++) {
            var titleNode = titleNodes[i]
            var figNode = titleNode.parentNode
            var imageNode = figNode.querySelector('.image')
            if(imageNode && imageNode.parentNode !== figNode) {
              imageNode = imageNode.parentNode
            }
            if (figNode && imageNode && imageNode.parentNode === figNode) {
                figNode.insertBefore(imageNode, titleNode)
            }
        }
    })
});
...
```

>[!NOTE]
>
>The `window.addEventListener('DOMContentLoaded', function ()` funktionen måste anropas innan callback-funktionerna används.

Sedan måste skriptet anropas från en mallfil som används för att generera utdata från PDF. Vi kommer till exempel att lägga till det i innehållsförteckningsmallen. Se till att `<script>` läggs till i en fördefinierad `<div>` -taggen inuti `<body>` -tagg. Om du lägger till den i `<head>` eller utanför `<body>` -taggen kommer skriptet inte att köras.

<img src="./assets/js-added-resources-template.png" width="500">

De utdata som skapas med den här koden och mallen visar figurtiteln nedanför bilden:

<img src="./assets/fig-title-below-image.png" width="500">
