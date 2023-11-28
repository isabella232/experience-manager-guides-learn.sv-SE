---
sidebar_position: 4
source-git-commit: 0f20681fa4de859053c8d2baae0e53f347ce5859
workflow-type: tm+mt
source-wordcount: '50'
ht-degree: 0%

---


# Ikon

För att visa en ikon använder vi komponenten, icon.
Textområdeskomponenten i JUI representerar en html `<icon/>`.

Ikoner finns på [Adobe-spektrumikoner](https://spectrum.adobe.com/page/icons/) är kompatibla med vår app.

```js title="icon.js"
const iconJSON =  {
    "component": "icon", //tells the component name
    "icon": "info", // name of the icon to be used
    "size": "S", // size of the icon
    "title": "Information" // tooltip corresponding to the icon.
},
```

ikoner kan också läggas till knappar.

Den återgivna ikonen ser ut så här:

![icon](./imgs/info_icon.png "Ikon")
