---
sidebar_position: 3
source-git-commit: 42052b37724f97e34ab007db4cc3d9f9524ad3a2
workflow-type: tm+mt
source-wordcount: '62'
ht-degree: 0%

---


# Textfält och textområde

För att ta text som indata använder vi komponenterna, textfältet och textområdet.
Textområdeskomponenten i JUI representerar en html `<textarea/>`.

```js title="textArea.js"
const textAreaJSON =  {
    "component": "textarea", //tells the component name
    "id": "input_name", // can be used to give a unique identifier to a component
    "data": "@name", // the variable storing the inputted text
    "on-keyup": {
        "name": "submitName",
        "eventArgs": {
            "keys": [
            "ENTER"
            ]
        }
    },
},
```

Här, `on-keyup` är syntaxen för att anropa kommandona i kontrollenheterna.
Detta skapar ett textArea där händelsen anropas när du trycker på Retur `submitName`

Det återgivna textområdet ser ut så här:

![textområde](./imgs/text_area.png "Textområde")
