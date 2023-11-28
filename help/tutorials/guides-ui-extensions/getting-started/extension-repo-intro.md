---
sidebar_position: 3
source-git-commit: 42052b37724f97e34ab007db4cc3d9f9524ad3a2
workflow-type: tm+mt
source-wordcount: '101'
ht-degree: 0%

---


# Katalogstruktur för AEM Guides Extension Package

```text
├── src
│   ├── **/*{js,ts}
│   ├── index.ts
├── dist
│   ├── guides-extension.js
│   ├── guides-extension.umd.cjs
│   ├── build.css
├── node_modules
├── package.json
├── package-lock.json 
└── .gitignore
└── buildCSS.mjs // for creating tailwind classes
└── vite.config.js // config for specifying TS and javascript build options
└── taliwind.config.js // config for tailwind we can add custom config for a design system here
├── jsons // jsons for the aem app
│   ├── context_menus // jsons for the context menus
│   ├── review_app // jsons for the review app
│   ├── xmleditor // jsons for xmleditor
```

## /src

```text
├── src
│   ├── **/*{js,ts}
│   ├── index.ts
```

Källkatalogen innehåller tilläggets typskript- eller javascript-filer. Filen index.ts är startpunkten för tillägget. Du kan importera alla komponenter här och exportera dem som ett enda objekt. Objektet kommer att användas av tillägget för att återge komponenterna.

### /dist

Det här är den sista byggkatalogen. Detta innehåller den slutliga JS och CSS som måste kopieras till AEM

```test
├── dist
│   ├── gudies-extension.js // you can either choose es module (this one) or .cjs(other one) file
│   ├── gudies-extension.umd.cjs
│   ├── build.css // this is your tailwind css output
```

## /json

Den här katalogen innehåller JSON för de olika vyerna. Du kan använda dessa JSON för att identifiera målen och anpassa vyn.

```text
├── jsons // jsons for the aem app
│   ├── context_menus // jsons for the context menus
│   ├── review_app // jsons for the review app
│   ├── xmleditor // jsons for xmleditor
```
