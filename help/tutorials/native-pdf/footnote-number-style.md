---
title: Publiceringsfunktion för PDF | Använda egna format i fotnoter
description: Lär dig hur du använder format på siffror i fotnoter.
exl-id: f1068f2f-2ace-4bdb-b5a4-46b03d4e43d6
source-git-commit: 7b48633ef2418fa7c91842a8d2c2a4177017ef58
workflow-type: tm+mt
source-wordcount: '171'
ht-degree: 0%

---

# Använda anpassade format i fotnoter

Fotnoter är anteckningar som placeras längst ned på en sida som kommenterar eller citerar en referens för en viss del av texten.

Du kan formatera numren i fotnotsanropet som finns i ämnesinnehållet och fotnotsmärket som finns längst ned på sidan. Du kan till exempel lägga till hakparenteser runt numret eller ändra deras färg. Med de här formaten kan du enkelt identifiera fotnoterna i dokumentet.

```css
...
.footnote::footnote-call { 
content: "(" counter(footnote, decimal) ")"; 
} 

.footnote::footnote-marker { 
content: "(" counter(footnote, decimal) ")"; 
} 

...
```

I det aktuella exemplet läggs en hakparentes till före och efter fotnotsanropet och fotnotsmärket:

* Lägg till prefixet&quot;(&quot; och suffixet&quot;)&quot; med innehållsattributet i `footnote-call` som lägger till parenteserna runt fotnotsnumret i ämnesinnehållet.
* Lägg till prefixet&quot;(&quot; och suffixet&quot;)&quot; med innehållsattributet i `footnote-marker` som lägger till parenteserna runt fotnotsnumret längst ned på sidan.

<img src="./assets/pdf-output-footer-numbers.png" alt="Sidfot i utdata från PDF" width="500">
