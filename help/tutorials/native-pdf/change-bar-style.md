---
title: Publiceringsfunktion för PDF | Arbeta med anpassade ändringsfältstilar
description: Lär dig hur du använder format på ändringsfält.
source-git-commit: 79de97e667bffae8d120deee68a0a82011047cf5
workflow-type: tm+mt
source-wordcount: '348'
ht-degree: 0%

---

# Arbeta med anpassade ändringsfältstilar

Ett ändringsfält är en lodrät linje som visuellt identifierar nytt eller ändrat innehåll. Med AEM stödlinjer kan du visa ett ändringsfält till vänster om det ändrade innehållet i ämnen och även de ändrade avsnitten i innehållsförteckningen för PDF.

Mer information om hur du visar ändringsfältet finns i *Skapa PDF med ändringsfältet mellan publicerade versioner* ange
[Publicera PDF-utdata](../web-editor/native-pdf-web-editor.md).

## Ändrat innehåll i ämnen

Ändringsfältet visas till vänster om innehållet i de ämnen som har infogats, ändrats eller tagits bort.

Du kan ändra följande format för att visa det ändrade innehållet och bland annat för ändringsfälten.


>[!NOTE]
>
>Dessa format ingår i `layout.css` och du kan redigera dem efter behov.

Du kan till exempel använda färgattributet i `.inserted-block` -format för att definiera hur det infogade innehållet ska visas i det publicerade PDF-utdata.


```css
...
.inserted-block { 
  color: #2ECC40; 
  display: inline; 
  -ro-comment-content: " "; 
  -ro-comment-style: underline; 
  -ro-comment-title: "Inserted"; 
  -ro-comment-date: attr(data-time); 
  -ro-comment-dateformat: "yyyy/dd/MM HH:mm:ss"; 
} 
...
```

På samma sätt kan du använda `.deleted-block` -format för att definiera hur borttaget innehåll ska visas i publicerade PDF-utdata.

```css
...
.deleted-block { 
  display: inline; 
  color: #FF6961; 
  text-decoration: line-through; 
  -ro-comment-content: " "; 
  -ro-comment-style: strikeout; 
  -ro-comment-title: "Deleted"; 
  -ro-comment-date: attr(data-time); 
  -ro-comment-dateformat: "yyyy/dd/MM HH:mm:ss"; 
} 
...
```

Du kan använda `.inserted-change-bar` och `.deleted-change-bar` om du vill ändra utseendet på ändringsfälten som visas till vänster om det uppdaterade innehållet.

Du kan till exempel använda `-ro-change-bar-color` attribute in `.inserted-change-bar` om du vill visa det infogade ändringsfältet i grön färg. Du kan också använda `-ro-change-bar-color` attribute in `.deleted-change-bar` om du vill visa det borttagna ändringsfältet i röd färg.

```css
...
.inserted-change-bar { 
  -ro-change-bar-color: #2ECC40; 
} 

.deleted-change-bar { 
  -ro-change-bar-color: #FF6961; 
  } 
...
```

<img src="./assets/changed-bar-content.png" alt="Innehåll i ändrat fältavsnitt" width="500">

## Ändrade ämnen i innehållsförteckningen

Du kan också lägga till ett ändringsfält till vänster om de ändrade avsnitten i innehållsförteckningen för PDF. Du kan använda `-ro-change-bar-color` i `.changed-topic` om du vill lägga till ett ändringsfält i den färg du väljer för de uppdaterade avsnitten i innehållsförteckningslistan.

Du kan till exempel lägga till ett ändringsfält med grön färg.

```css
...
.changed-topic { 
 -ro-change-bar-color: #2ECC40; 
}  
...
```


Det här visar ett grönt ändringsfält för alla ämnen i innehållsförteckningen där vissa uppdateringar har gjorts. Du kan klicka på det ändrade ämnet i innehållsförteckningen och visa de detaljerade ändringarna.

<img src="./assets/changed-bar-TOC.png" alt="Innehållsförteckning för ändrat fält" width="500">
