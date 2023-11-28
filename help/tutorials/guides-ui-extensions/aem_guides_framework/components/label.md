---
sidebar_position: 2
source-git-commit: 0f20681fa4de859053c8d2baae0e53f347ce5859
workflow-type: tm+mt
source-wordcount: '44'
ht-degree: 0%

---


# Etikett

Om du vill visa text eller strängar använder vi komponenten, label.
Etikettkomponenten i JUI representerar en html `<label/>`.

Nedan visas ett exempel på hur du lägger till en statisk etikett

```js title="staticLabel.js"
const staticLabelJSON =  {
    "component": "label", //tells the component name
    "label": "This is an example label", // the string to be displayed
}
```

Under JSON visas en dynamisk sträng:

```js title="dynamicLabel.js"
const labelJSON =  {
    "component": "label", //tells the component name
    "label": "@name", // the variable storing the text to be displayed
},
```

Den återgivna etiketten ser ut så här:

![label](./imgs/label.png "Etikett")