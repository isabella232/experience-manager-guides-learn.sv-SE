---
title: Konfigurera filter för filbläddringsdialogrutan
description: Lär dig hur du konfigurerar filter för filbläddringsdialogrutan
source-git-commit: 880cd344ceb65ea339be699ebcad41c0d62e168a
workflow-type: tm+mt
source-wordcount: '376'
ht-degree: 0%

---

# Konfigurera filter för filbläddringsdialogrutan {#id20CIL7009GN}

När du arbetar i Web Editor måste du använda dialogrutan för filbläddring för att infoga element som bild, referens eller nyckelreferens. I standarddialogrutan för filbläddring finns inga filfiltreringsalternativ. Du kan lägga till egna filter som gör att du enkelt och snabbt kommer åt de filer som behövs.

Gör så här för att lägga till egna filfiltreringsalternativ i dialogrutan för filbläddring:

1. Om du vill hämta UI-konfigurationsfilen loggar du in på Adobe Experience Manager som administratör.

1. Klicka på länken Adobe Experience Manager överst och välj **verktyg**.
1. Välj **Stödlinjer** i listan med verktyg och klicka på **Mappprofiler**.
1. Klicka på **Global profil** platta.
1. Välj **Konfiguration av XML-redigerare** och klicka **Redigera** ikonen längst upp
1. Klicka på **Ladda ned** om du vill hämta filen ui\_config.json på ditt lokala system. Du kan sedan göra ändringar i filen och sedan överföra samma fil.
1. I `ui_config.json` lägger du till definitionen av de filter som du vill lägga till.

   Följande kodutdrag visar hur du lägger till två filtreringsalternativ - DITA-filer och Bildfiler.

   ```
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

   title : Filtrets visningsnamn. Titeln visas som filtreringsalternativ i dialogrutan för filbläddring.

   property : Den egenskap som ska matchas i filens metadata. Om du till exempel bara vill tillåta de filer som har `dita_class` metadata i sin egenskap, tar egenskapsfiltret &quot; `jcr:content/metadata/dita_class`&quot; som värde.

   operation : ange &quot; `exists`&quot; för att matcha om värdet som anges i egenskapsparametern finns.

   Det andra filtret är för bildfiler. Parametrarna liknar det första filtret förutom `value` parameter. The `value` parametern har en array med bildtyper som värde. Alla filtyper som anges i parametern value söks efter och visas i dialogrutan för filbläddring. Alla andra filtyper ignoreras.

1. Spara *ui\_config.json* och överföra samma fil. Läs sedan in webbredigeraren igen.

   När du startar dialogrutan för filbläddring visas de filteralternativ som är konfigurerade i filen ui\_config.json.

   ![](assets/file-browse-custom-filters.png)


**Överordnat ämne:**[ Anpassa Web Editor](conf-web-editor.md)
