---
title: Publiceringsfunktion för PDF | Lägg till ett eget bokmärke i utdata från PDF
description: Lär dig hur du skapar formatmallar och skapar format för ditt innehåll.
source-git-commit: 880cd344ceb65ea339be699ebcad41c0d62e168a
workflow-type: tm+mt
source-wordcount: '230'
ht-degree: 0%

---

# Lägga till ett eget bokmärke i utdata från PDF

Vanligtvis återges innehållsförteckningen i en DITA-karta som bokmärken i den slutliga utskriften för PDF. Innehållsförteckningen skapas utifrån avsnittet eller avsnittsrubrikerna på din DITA-karta. Ibland kanske du vill lägga till ett eget bokmärke för ett visst innehåll i utdata från PDF för enkel navigering. Detta kan du uppnå genom att lägga till en `outputclass` -attributet i elementet och följande attribut tillämpas på det:

`bookmark-level: 3`

Här är `bookmark-level` är ett attribut och ett tal `3` är värdet som anger nivån i bokmärkeshierarkin där bokmärket läggs till. I följande exempel innehåller ämnet Kontakter på första nivån en tabell, Kontaktlista, där vi har lagt till en `outputclass` attribut med värdet för `custom-bookmark`.


<img src="./assets/custom-bookmark-attribute.png" width="500">

Följande definition av `custom-bookmark` klassen läggs till i CSS-filen:

```css
…
/*Adding a custom bookmark*/
.custom-bookmark{
    bookmark-level: 2
}
…
```

I PDF-utdata visas *Kontaktlista* tabellen läggs till på den andra nivån i PDF-bokmärkeslistan enligt nedan:

<img src="./assets/custom-bookmark-in-pdf-output.png" width="500">

>[!NOTE]
>
>Du måste välja rätt nivå där det anpassade bokmärket ska läggas till. Om du anger ett tal som är mindre än det överordnade objektets bokmärke, får det anpassade bokmärket det överordnade bokmärkets position och alla andra bokmärken visas som underordnade. Detta kan leda till oväntad bokmärkesstruktur.
