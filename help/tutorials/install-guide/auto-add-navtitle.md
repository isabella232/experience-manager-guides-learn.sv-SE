---
title: Inkludera @navtitle-attribut som standard
description: Lär dig hur du inkluderar @navtitle-attribut som standard
source-git-commit: 880cd344ceb65ea339be699ebcad41c0d62e168a
workflow-type: tm+mt
source-wordcount: '222'
ht-degree: 0%

---

# Inkludera @navtitle-attribut som standard {#id2115BC0J0XA}

Du kan lägga till olika typer av referensfiler på en karta, till exempel avsnitt-, referens-, uppgift-, \(sub\)-kartor. De flesta av dessa filer har stöd för `@navtitle` -attribut. Men det är inte många som använder det konsekvent. Om du vill använda `@navtitle` i alla refererade filer på en karta kan du göra det med en enkel konfiguration.

När du har aktiverat kommer alla referensfiler som du lägger till på en karta automatiskt att få `@navtitle` attribut som lagts till i dess egenskaper. The `@navtitle` får även värdet för `title` -element för det refererade innehållet.

Inkludera `@navtitle` som standard i referensfilens egenskaper utför du följande steg:

1. Hämta filen ui\_config.json.

   Du kan göra ändringen på global nivå eller på en mappnivåprofil. Beroende på var du vill göra den här ändringen måste du hämta respektive ui\_config.json-fil. Mer information om hur du hämtar filen ui\_config.json finns i [Konfigurera och anpassa XML Web Editor](conf-folder-level.md#id2065G300O5Z).

1. Sök efter `ditaAttributes` definition.

   Standarddefinitionen för `ditaAttributes` är:

   ```json
   "ditaAttributes": {
   "attributes": [],
   "constraint": false,
   "required": {}
   },
   ```

1. Ändra `required` parameter som:

   ```json
   "required": {"navtitle": true}
   ```

1. Spara filen.

1. Överför filen i motsvarande profil \(global eller mapp\).


Med den här konfigurationen kommer alla referensfiler som du lägger till på en karta att innehålla `@navtitle` som standard.
