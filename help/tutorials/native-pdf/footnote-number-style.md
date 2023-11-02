---
title: Publiceringsfunktion för PDF | Använda egna format i fotnoter
description: Lär dig hur du använder format på siffror i fotnoter.
exl-id: f1068f2f-2ace-4bdb-b5a4-46b03d4e43d6
source-git-commit: cb2aa028330c1e1b8b71e9e928d724cc0d87bf44
workflow-type: tm+mt
source-wordcount: '664'
ht-degree: 0%

---

# Använda fotnotformat


Fotnoter är anteckningar som placeras längst ned på en sida som kommenterar eller anger en referens för en viss del av texten.

Alla fotnoter har en fotnotsmärke längst ned på sidan, vilket vanligtvis är en siffra eller en symbol som en asterisk. I huvudinnehållet visas samma fotnotsmärke som ett fotnotsanrop och anges med samma nummer eller symbol som upphöjd text.




## Ändra format för fotnotsanrop och -markörer

Du kan ändra format för fotnotsanrop och fotnotsmärken och hantera deras utseende i utdata från PDF. Med de här formaten kan du snabbt identifiera fotnoterna i dokumentet.


**Exempel 1**:

Använd det givna exemplet för att lägga till en hakparentes före och efter fotnotsanropet och fotnotsmärket:

* Lägg till prefixet&quot;(&quot; och suffixet&quot;)&quot; med innehållsattributet i `footnote-call` som lägger till parenteserna runt fotnotsnumret i ämnesinnehållet.
* Lägg till prefixet&quot;(&quot; och suffixet&quot;)&quot; med innehållsattributet i `footnote-marker` som lägger till hakparenteserna runt fotnotsnumret längst ned på sidan.

```css
...
.fn::footnote-call { 
content: "(" counter(footnote, decimal) ")"; 
} 

.fn::footnote-marker { 
content: "(" counter(footnote, decimal) ")"; 
} 

...
```



<img src="./assets/pdf-output-footer-numbers.png" alt="Sidfot i utdata från PDF" width="500" border="2px">

*Lägg till hakparenteser runt fotnotsanropet och fotnotsmärket.*

**Exempel 2**:

Du kan också flagga fotnotsanropet och fotnotsmärket med en asterisk eller en lägre grekisk bokstav i stället för en siffra.


```css
.fn::footnote-call {
 content: counter(footnote, asterisks);
}
.fn::footnote-marker {
 content: counter(footnote, asterisks) " ";
}
```

I utdata kan du visa något som:

<img src="./assets/footnote-number-2.png" alt="Sidfot i utdata från PDF" width="500" border="2px">

*Lägg till en asterisk i ett fotnotsanrop och markör.*

## Dölja ett fotnotsanrop

Du kan också använda ett format på fotnotsanrop med särskilda attribut. Använd till exempel följande format om du vill dölja en fotnot med ID:n: Fotnotsanropet är dolt i huvudinnehållet, men fotnotsmärket visas längst ned på sidan.

```css
.fn[id]::footnote-call {
		display: none;
                        }
```

## Formatera fotnotsområdet

Fotnotsområdet är där alla fotnoter placeras, vanligtvis längst ned på en sida. Du kan formatera fotnotsområdet med sidlayouterna eller CSS-formaten.


### Sidlayouter

Du kan använda sidegenskaperna för sidlayouter för att formatera fotnotsområdet i olika avsnitt i ett PDF-dokument. Du kan till exempel ange marginaler och utfyllnadsegenskaper för fotnotsområdet i ett kapitel. Du kan också ändra kantlinjens sida, format, färg, bredd och radie.

Lär dig mer om [arbeta med sidegenskaperna i en sidlayout](./design-page-layout.md#page-props-page-layout).

### CSS

Du kan använda format och formatera fotnotsområdet i ett PDF-dokument. Du kan till exempel ändra kantlinjens längd, format, färg och bredd.

```css
	@page {
	  @footnote {
   		border-top-style: solid;
   		border-top-color: #FF0000;
   		border-top-width: 3px;
 		        }
	      }
```

## Starta om numreringen av fotnoter

Som standard numreras fotnoterna kontinuerligt i ett dokument. Du kan dock använda sidlayouter eller CSS-format för att starta om numreringen av fotnoter.


### Sidlayouter

Du kan ange en siffra i sidlayouterna om du vill starta om fotnotsnumreringen i de olika avsnitten i ett PDF-dokument. Välj till exempel ett tal i **Starta om numrering från** om du vill starta om fotnotsnumreringen för varje kapitel i panelen Sidegenskaper.

### CSS

Använd följande format för att återställa fotnotsnumreringen på varje sida i PDF-utdata:

```css
@page
{
counter-reset: footnote
}
```

Fotnoterna på varje sida startar alltså om från 1.

## Visa textbundna fotnoter

Oftast visas varje fotnot som ett block eller börjar på en ny rad. Men du kan också placera dem i linje eller bredvid varandra.

```css
.fn{
  	display: inline;
              }
```

## Använda format på fotnotskorsreferenser

Du kan också korsreferera en fotnot och använda samma fotnot flera gånger i utdata från PDF. Det gör det lättare att referera till samma citat eller detaljerade anteckning flera gånger i dokumentet utan att du behöver skapa en fotnot för den igen.

På följande skärmbild visas hur samma fotnot korsrefereras till alla städer i utdata från PDF.
<img width="550" alt="fotnotsreferenser i en PDF-fil" src="./assets/link-footnotes.png" border="2px">

*Infoga korsreferensen i en fotnot.*





Med CSS-format kan du även formatera korsreferenserna till fotnoter. Du kan till exempel ändra bakgrundsfärgen för korsreferenserna.

```css
    .xref-fn{
	background-color: red;
	}
```



