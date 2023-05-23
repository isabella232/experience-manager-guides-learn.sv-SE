---
title: Anpassa verktygsfältet
description: Lär dig hur du anpassar verktygsfältet
source-git-commit: ef2e99db8c298d34af5777baa48886a55ac32590
workflow-type: tm+mt
source-wordcount: '894'
ht-degree: 0%

---


# Anpassa verktygsfältet {#id172FB00L0V6}

Som standard levereras webbredigeraren med de vanligaste redigeringsfunktionerna som krävs av alla DITA-redigerare. Du kan använda funktioner som att infoga element av typen lista \(numrerad eller punktad\), korsreferens, innehållsreferens, tabell-, stycke- och teckenformatering i redigeraren. Förutom dessa grundläggande element kan du anpassa Web Editor för att infoga element som används i redigeringsmiljön.

Det finns två sätt att anpassa Web Editors verktygsfält:

- Lägga till en ny funktion i verktygsfältet

- Ta bort alla befintliga funktioner från verktygsfältet


## Lägga till en funktion i verktygsfältet

Om du lägger till en funktion i Web Editor innebär det två primära åtgärder - att lägga till en ikon för funktionen i *ui\_config.json* och lägga till bakgrundsfunktioner i JavaScript.

**Lägga till en ikon i verktygsfältet**

Gör så här för att lägga till en funktion i Web Editor-verktygsfältet:

1. Logga in AEM och öppna läget CRXDE Lite.

1. Navigera till standardkonfigurationsfilen som finns på följande plats:

   `/libs/fmdita/clientlibs/clientlibs/xmleditor/ui_config.json`

1. Skapa en kopia av standardkonfigurationsfilen på följande plats:

   `/apps/fmdita/xmleditor/ui_config.json`

1. Navigera till och öppna `ui_config.json` i `apps` nod för redigering.

1. I `ui_config.json` lägger du till definitionen av den nya funktionen i verktygsfältsavsnittet. Vanligtvis kan du skapa en ny verktygsfältsknappgrupp och lägga till en eller flera knappar i den. Du kan också lägga till en ny verktygsfältsknapp i en befintlig verktygsfältgrupp. Följande information krävs för att skapa en ny verktygsfältgrupp:

   - **type:**Ange `blockGroup` som `type` värde. Detta värde anger att du skapar en blockgrupp som skulle innehålla en eller flera verktygsfältsgrupper.

   - **extraclass:** Namnet på klassen eller klasserna avgränsade med blanksteg.

   - **objekt:** Ange definitionen för alla grupper i verktygsfältet. Varje grupp kan innehålla en eller flera verktygsfältsikoner. Om du vill definiera ikoner i en verktygsfältgrupp måste du definiera `type` i `items`och ange värdet till `buttonGroup`. Ange ett eller flera klassnamn i `extraclass` -egenskap. Ange funktionsnamnet i `label` -egenskap. Följande utdrag från `ui_config.json` filen visar definitionen för huvudverktygsfältets block, följt av `buttonGroup` definition:

      ```json
      "toolbar": {    
        "type": "blockGroup",    
        "extraclass": 
        "toolbar operations",    
          "items": [      
            {        
              "type": "buttonGroup",        
              "extraclass": "left-controls",        
              "label": "Left Controls",        
              "items": [
      ```

      I `items` -samling måste du ange definitionen för en eller flera verktygsfältsikoner.
Du måste definiera följande egenskaper för att lägga till en verktygsfältsikon:

   - **typ:** Ange `button` som `type` värde. Detta värde anger att du lägger till en verktygsfältsknapp.

   - **ikon:** Ange namnet på den korallikon som du vill använda i verktygsfältet.

   - **variant:** Ange `quiet` som `variant` värde.

   - **titel:** Ange verktygstipset för ikonen.

   - **on-click:** Ange det kommandonamn som är definierat för funktionen i JavaScript-filen. Om kommandot kräver indataparametrar anger du kommandonamnet som:

      ```JavaScript
      "on-click": {"name": "AUTHOR_INSERT_ELEMENT", "args": "simpletable"}
      ```

   - **visa eller dölja:** Om du definierar `show` anger sedan de lägen som ikonen ska visas i. Möjliga värden är - `@isAuthorMode`, `@isSourceMode`, `@isPreviewMode`, `true` \(visas i alla lägen\), eller `false` \(dölj i alla lägen\).

   I stället för `show`kan du också definiera `hide` -egenskap. Möjliga värden är desamma som i `show` -egenskapen med den enda skillnaden att ikonen inte visas för det angivna läget.

1. Skapa en *clientlib* och lägg till JavaScript i den här mappen.

1. Uppdatera kategoriegenskapen för *clientlib* genom att tilldela den värdet *apps.fmdita.xml\_editor.page\_overrides*.

1. Spara *ui\_config.json* och läsa in webbredigeraren igen.


**JavaScript-kodexempel**

I det här avsnittet finns två exempel på JavaScript-kod som hjälper dig att komma igång med att lägga till anpassade funktioner. I följande exempel visas versionsnumret AEM stödlinjerna när en användare klickar på ikonen Visa version i verktygsfältet.

Lägg till följande kod i en JavaScript-fil:

```JavaScript
/**
* This file contains an example to show AEM Guides version 
* number when a user clicks on the Show Version icon in the toolbar. 
* Step 1. Create a clientlib folder and add save a file with your *JavaScript code into this folder. A code sample is shared below.
* Step 2: Update the categories property of the clientlib folder by *assigning it the value of 
* "apps.fmdita.xml_editor.page_overrides".
* Step 3: Add the feature in the ui_config.json file as shown after the *sample code. Save the ui_config.json file and reload the Web Editor
 */

(function (window) {
  "use strict";

  window.addEventListener('DOMContentLoaded', function () {
    fmxml.ready(function () {
      fmxml.eventHandler.subscribe({
        key: 'user.alert',
        next: function next() {
          alert("AEM Guides version x.x");
        }
      });
    });
  });
})(window);
```

Lägg till funktionen i filen ui\_config.json som:

```json
 {
      "type": "button",
      "icon": "alert",
      "title": "About AEM Guides",
      "variant": "quiet",

  "show": "true",
      "on-click": "user.alert"
  } 
```

I följande exempel visas hur du ändrar ett dokuments tillstånd för en aktiv fil till&quot;Under granskning&quot;.

```JavaScript
/**
* This file contains an example to set the document state of an active *open documen to "In-Review". 
* Step 1. Create a clientlib folder and add save a file with your *JavaScript code into this folder. A code sample is shared below.
* Step 2: Update the categories property of the clientlib folder by *assigning it the value of 
* "apps.fmdita.xml_editor.page_overrides".
* Step 3: Add the feature in the ui_config.json file as shown after the *sample code. Save the ui_config.json file and reload the Web Editor
 */

(function (window) {
  "use strict";

  //Wait for the page has been completely loaded 

  window.addEventListener('DOMContentLoaded', function () {

    //Wait for the xml editor to start
    fmxml.ready(function () {

      //Subscribe to 'user.docstate.to.in-review' event
      fmxml.eventHandler.subscribe({
        key: 'user.docstate.to.in-review',
        next: function next() {
          var docstate = "In-Review"; // New docstate name
          var filePath = fmxml.curEditor.filePath; 
// Get the file path of active open file
          if (filePath) {
            //Call API to change the doc state
            $.ajax({
              type: 'POST',
              url: '/bin/fmdita/states',
              data: {
                paths: filePath,
                operation: "setdocstates",
                docstate: docstate
              }
            }).fail(function (xhr, textStatus, errorThrown) {
              console.error("Cannot update docstate to " + docstate);
            }).success(function (data) {
              console.log('docstate updated to ' + docstate);
            });
          }
        }
      });
    });
  });
})(window);
```

Lägg till funktionen i filen ui\_config.json som:

```json
 {
      "type": "button",
      "icon": "actions",
      "title": "Change document state to In-Review",
      "variant": "quiet",
      "show": "true",
      "on-click": "user.docstate.to.in-review"
    } 
```

## Ta bort en funktion från verktygsfältet

Ibland kanske du inte vill ge alla funktioner som är tillgängliga i Web Editor. Då kan du ta bort den oönskade funktionen från Web Editors verktygsfält.

Så här tar du bort oönskade funktioner från verktygsfältet:

1. Logga in AEM och öppna läget CRXDE Lite.

1. Navigera till standardkonfigurationsfilen som finns på följande plats:

   `/libs/fmdita/clientlibs/clientlibs/xmleditor/ui_config.json`

1. Skapa en kopia av standardkonfigurationsfilen på följande plats:

   `/apps/fmdita/xmleditor/ui_config.json`

1. Navigera till och öppna `ui_config.json` i `apps` nod för redigering.
The `ui_config.json` filen har tre avsnitt:

- **verktygsfält:**   Det här avsnittet innehåller en definition av alla funktioner som är tillgängliga i redigerarens verktygsfält, t.ex. Infoga/ta bort numrerad lista, Stäng, Spara, Kommentarer med mera.

- **kortkommandon:**   I det här avsnittet finns en definition av kortkommandon för en viss funktion i redigeraren.

- **mallar:**   Det här avsnittet innehåller den fördefinierade strukturen för DITA-element som du kan använda i ditt dokument. Som standard innehåller mallavsnittet malldefinitioner för ett stycke-, enkel tabell-, tabell- och body-element. Du kan skapa en malldefinition för vilket element som helst genom att lägga till en giltig XML-struktur för det önskade elementet. Om du till exempel vill lägga till en `p` element med alla nya `li` -element i en lista kan du lägga till följande kod i slutet av mallavsnittet för att uppnå detta:

```HTML
"li": "<li><p></p></li>"
```

1. I verktygsfältsavsnittet tar du bort den funktion som du inte vill visa för användarna.

1. Spara *ui\_config.json* och läsa in webbredigeraren igen.


**Överordnat ämne:**[ Anpassa Web Editor](conf-web-editor.md)

