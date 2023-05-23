---
title: Konfigurera filter för filbläddringsdialogrutan
description: Lär dig hur du konfigurerar filter för filbläddringsdialogrutan
source-git-commit: 5ac066bb8db32944abd046f64da11eeb1bdbe467
workflow-type: tm+mt
source-wordcount: '325'
ht-degree: 0%

---


# Konfigurera filter för filbläddringsdialogrutan {#id20CIL7009GN}

När du arbetar i Web Editor måste du använda dialogrutan för filbläddring för att infoga element som bild, referens eller nyckelreferens. I standarddialogrutan för filbläddring finns inga filfiltreringsalternativ. Du kan lägga till egna filter som gör att du enkelt och snabbt kommer åt de filer som behövs.

Gör så här för att lägga till egna filfiltreringsalternativ i dialogrutan för filbläddring:

1. Logga in AEM och öppna läget CRXDE Lite.

1. Navigera till standardkonfigurationsfilen som finns på följande plats:

   `/libs/fmdita/clientlibs/clientlibs/xmleditor/ui_config.json`

1. Skapa en kopia av standardkonfigurationsfilen på följande plats:

   `/apps/fmdita/xmleditor/ui_config.json`

1. Navigera till och öppna `ui_config.json` i `apps` nod för redigering.

1. I `ui_config.json` lägger du till definitionen av de filter som du vill lägga till.

   Följande kodutdrag visar hur du lägger till två filtreringsalternativ - DITA-filer och Bildfiler.

   ```json
   "browseFilters": [
       {
         "title": "DITA Files",
         "property": "jcr:content/metadata/dita_class",
         "operation": "exists"
       },
       {
         "title": "Image Files",
         "property": "jcr:content/metadata/dc:format",
         "value": [        
           "image/jpeg",
           "image/gif",
           "image/png"
         ]
       }
   ]
   ```

   I ovanstående kodfragment är det första filtret för DITA-filer. Filterdefinitionen har följande parametrar:

   - **titel:**   Filtrets visningsnamn. Titeln visas som filtreringsalternativ i dialogrutan för filbläddring.

   - **egenskap:**   Den egenskap som ska matchas i filens metadata. Om du till exempel bara vill tillåta de filer som har `dita_class` metadata i sin egenskap, tar egenskapsfiltret &quot;`jcr:content/metadata/dita_class`&quot; som värde.

   - **operation:**   Ange &quot;`exists`&quot; för att matcha om värdet som anges i egenskapsparametern finns.

   Det andra filtret är för bildfiler. Parametrarna liknar det första filtret förutom `value` parameter. The `value` parametern har en array med bildtyper som värde. Alla filtyper som anges i parametern value söks efter och visas i dialogrutan för filbläddring. Alla andra filtyper ignoreras.

1. Spara *ui\_config.json* och läsa in webbredigeraren igen.

   När du startar dialogrutan för filbläddring visas de filteralternativ som är konfigurerade i filen ui\_config.json.

   ![](assets/file-browse-custom-filters.png){width="300" align="left"}


