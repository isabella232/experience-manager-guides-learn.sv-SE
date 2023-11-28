---
sidebar_position: 2
source-git-commit: 42052b37724f97e34ab007db4cc3d9f9524ad3a2
workflow-type: tm+mt
source-wordcount: '338'
ht-degree: 0%

---


# Installera och använda tilläggspaketet för AEM stödlinjer

Med tillägg kan du anpassa appen AEM Guides så att den passar dina behov bättre. Det här tilläggsramverket stöds av AEM Guides v4.3 och senare (on-prem) och 2310 (cloud).

## Krav

Det här paketet kräver [git bash](https://github.com/git-guides/install-git) och npm

## Installation

Det enklaste sättet att starta installationen av AEM Guides Framework är via cli

```bash
npx @adobe/create-guides-extension
```

## Lägga till anpassningsbar kod

1. Lägga till kodfiler för varje komponent som du vill utöka i dialogrutan `src/` katalog. Vissa exempelfiler har redan lagts till.
2. Nu i `index.ts` filen som finns i `src/` katalog:
   - Importera `.ts` filer med de anpassningar du vill lägga till i bygget.
   - Lägg till importerna i `window.extension`
   - Registrera den anpassade komponentens `id` och motsvarande import till `tcx extensions`
   - Se exemplet [index.ts](../../../src/index.ts)

## Bygga den anpassade koden

- Kör `npm run build` i rotkatalogen. Du får tre filer i katalogen, `dist/`:
   - `build.css`
   - `guides-extension.js`
   - `guides-extension.umd.cjs`

![Skapa utdata](./../imgs/build_output.png)

## Lägga till anpassningar i AEM

- Gå till `CRXDE` `crx/de/index.jsp#/`
- Under `apps` mapp, skapa en ny nod av typen `cq:ClientLibraryFolder`

![Mappstruktur](./../imgs/crxde_folder_structure.png)

- I `properties` för noden väljer du `Multi` lägg till följande egenskapsnamn: `categories`
Typ: `String []`
Värde: `apps.fmdita.review_overrides`, `apps.fmdita.xml_editor.page_overrides`

![Mappegenskaper](./../imgs/crxde_folder_properties.png)

- Skapa en ny fil, till exempel `tcx1.js` i noden ovan skapade. Här lägger du till koden från `dist/guides-extension.umd.cjs` eller `dist/guides-extension.js`. Skapa nu en ny fil `js.txt`, här lägger vi till namnet på vår js-fil, som i det här fallet skulle vara:

```t
#base=.
tcx1.js
```

- Skapa en ny fil, till exempel `tcx1.css` i noden ovan skapade. Här lägger du till koden från `dist/build.css`. Skapa nu en ny fil `css.txt`här lägger vi till namnet på vår CSS-fil, som i det här fallet skulle vara:

```t
#base=.
tcx1.css
```

- Gör en `shift + refresh` för att läsa in appen med anpassningarna!

## Felsökning

Kontrollera att alla ovanstående steg har utförts korrekt.
När du har lagt till koden i tcx.js måste du göra en hård uppdatering (Skift+Uppdatera).
Öppna AEM och högerklicka `Inspect`
Gå till Källor och sök efter `[node_name].js` (till exempel: extensions.js)-fil. Sök efter filen med Ctrl/Cmd+D. Om `.js` filen finns med den JS-kod som du klistrade in från `dist/guides-extension.umd.cjs` eller `dist/guides-extension.js`är installationen klar
