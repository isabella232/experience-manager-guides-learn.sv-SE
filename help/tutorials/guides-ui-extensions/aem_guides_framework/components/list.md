---
sidebar_position: 5
source-git-commit: 42052b37724f97e34ab007db4cc3d9f9524ad3a2
workflow-type: tm+mt
source-wordcount: '57'
ht-degree: 0%

---


# Lista

Vi använder komponentlistan för att visa en lista.

```js title="list.js"
const listJSON =  {
    "component": "list", //tells the component name
    "data": "@languages", // an array of list items
},
```

Här är språk en enkel matris med strängar. `languages = ["English", "Hindi", "French"]`
Om vi vill återge en lista med objekt kan vi ange strukturen med objektkonfigurationen.

```js title="list.js"
const listJSON =  {
    "component": "list", //tells the component name
    "data": "@projects", // an array of list items
    "itemConfig": { // used to define the structure of the list items.
    "component": "widget",
    "id": "checkbox_label"
    }
},
```

Oftast är itemConfig en `widget`. Om du vill veta mer om widgetar går du till [Widgetar](../Widgets/basic_widget.md)

Den återgivna listan ser ut så här:

![list](./imgs/list.png "Lista")
