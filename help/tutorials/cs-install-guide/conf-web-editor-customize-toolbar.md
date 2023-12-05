---
title: Anpassa verktygsfältet
description: Lär dig hur du anpassar verktygsfältet
source-git-commit: 880cd344ceb65ea339be699ebcad41c0d62e168a
workflow-type: tm+mt
source-wordcount: '956'
ht-degree: 0%

---

# Anpassa verktygsfältet {#id172FB00L0V6}

Som standard levereras webbredigeraren med de vanligaste redigeringsfunktionerna som krävs av alla DITA-redigerare. Du kan använda funktioner som att infoga element av typen lista \(numrerad eller punktad\), korsreferens, innehållsreferens, tabell-, stycke- och teckenformatering i redigeraren. Förutom dessa grundläggande element kan du anpassa Web Editor för att infoga element som används i redigeringsmiljön.

Det finns två sätt att anpassa Web Editors verktygsfält:

- Lägga till en ny funktion i verktygsfältet

- Ta bort alla befintliga funktioner från verktygsfältet


## Lägga till en funktion i verktygsfältet

Om du lägger till en funktion i Web Editor innebär det två primära åtgärder - att lägga till en ikon för funktionen i *ui\_config.json* och lägga till bakgrundsfunktioner i JavaScript.

Gör så här för att lägga till en funktion i Web Editor-verktygsfältet:

1. Om du vill hämta UI-konfigurationsfilen loggar du in på Adobe Experience Manager som administratör.

1. Klicka på länken Adobe Experience Manager överst och välj **verktyg**.
1. Välj **Stödlinjer** i listan med verktyg och klicka på **Mappprofiler**.
1. Klicka på **Global profil** platta.
1. Välj **Konfiguration av XML-redigerare** och klicka **Redigera** ikonen längst upp
1. Klicka på **Ladda ned** om du vill hämta filen ui\_config.json på ditt lokala system. Du kan sedan göra ändringar i filen och sedan överföra samma fil.
1. I `ui_config.json` lägger du till definitionen av den nya funktionen i verktygsfältsavsnittet. Spara filen och överför den.

   Vanligtvis kan du skapa en ny verktygsfältsknappgrupp och lägga till en eller flera knappar i den. Du kan också lägga till en ny verktygsfältsknapp i en befintlig verktygsfältgrupp. Följande information krävs för att skapa en ny verktygsfältgrupp:

   **type**: Ange `blockGroup` som `type` värde. Detta värde anger att du skapar en blockgrupp som skulle innehålla en eller flera verktygsfältsgrupper.

   **extraclass**: Namnet på klassen eller klasserna avgränsade med blanksteg.

   **objekt**: Ange definitionen för alla grupper i verktygsfältet. Varje grupp kan innehålla en eller flera verktygsfältsikoner. Om du vill definiera ikoner i en verktygsfältgrupp måste du definiera `type` -attribut i `items`och ange värdet till `buttonGroup`. Ange ett eller flera klassnamn i `extraclass` -egenskap. Ange funktionsnamnet i dialogrutan `label` -egenskap. Följande utdrag från `ui_config.json` filen visar definitionen för huvudverktygsfältets block, följt av `buttonGroup` definition:

       &quot;
       &quot;toolbar&quot;: {
       &quot;type&quot;: &quot;blockGroup&quot;,
       extraklass:
       &quot;verktygsfältsoperationer&quot;,
       &quot;items&quot;: [
       {
       &quot;type&quot;: &quot;buttonGroup&quot;,
       &quot;extraclass&quot;: &quot;left-controls&quot;,
       &quot;label&quot;: &quot;Left Controls&quot;,
       &quot;items&quot;: [
       &quot;
   
   I `items` -samling måste du ange definitionen för en eller flera verktygsfältsikoner.

   Du måste definiera följande egenskaper för att lägga till en verktygsfältsikon:

   **type**: Ange `button` som `type` värde. Detta värde anger att du lägger till en verktygsfältsknapp.

   **icon**: Ange namnet på den korallikon som du vill använda i verktygsfältet.

   **variant**: Ange `quiet` som `variant` värde.

   **title**: Ange verktygstipset för ikonen.

   **klicka**: Ange det kommandonamn som är definierat för funktionen i JavaScript-filen. Om kommandot kräver indataparametrar anger du kommandonamnet som:

       &quot;Javascript
       &quot;on-click&quot;: {&quot;name&quot;: &quot;AUTHOR_INSERT_ELEMENT&quot;, &quot;args&quot;: &quot;simpletable&quot;}
       &quot;
   
   **visa eller dölja**: Om du definierar `show` anger sedan de lägen som ikonen ska visas i. Möjliga värden är - `@isAuthorMode`, `@isSourceMode`, `@isPreviewMode`, `true` \(visas i alla lägen\), eller `false` \(dölj i alla lägen\).

   I stället för `show`kan du också definiera `hide` -egenskap. Möjliga värden är desamma som i `show` -egenskapen med den enda skillnaden att ikonen inte visas för det angivna läget.

   I följande exempel visas versionsnumret AEM stödlinjerna när användaren klickar på ikonen Visa version i verktygsfältet.

   Lägg till följande kod i en JavaScript-fil:

   ```Javascript
   $(document).ready(setTimeout(function() {
                           fmxml.commandHandler.subscribe({
                           key: 'user.alert',
                           next: function() {
                           alert("AEM Guides version x.x")
                           }
                           })
                           }, 1000))
   ```

   Lägg till funktionen i *ui\_config.json* fil som:

   ```Javascript
   "type": "button",
   "icon": "alert","variant": "quiet","title": "About AEM Guides","show": "true","on-click": "user.alert"
   ```

1. Skapa en *clientlib* och lägg till ditt JavaScript i den här mappen.

1. Uppdatera kategoriegenskapen för *clientlib* genom att tilldela den värdet *apps.fmdita.xml\_editor.page\_overrides*.

1. Spara *ui\_config.json* och läsa in webbredigeraren igen.


## Ta bort en funktion från verktygsfältet

Ibland kanske du inte vill ge alla funktioner som är tillgängliga i Web Editor, och då kan du ta bort den oönskade funktionen från Web Editor.

Så här tar du bort oönskade funktioner från verktygsfältet:

1. Om du vill hämta UI-konfigurationsfilen loggar du in på Adobe Experience Manager som administratör.

1. Klicka på länken Adobe Experience Manager överst och välj **verktyg**.
1. Välj **Stödlinjer** i listan med verktyg och klicka på **Mappprofiler**.
1. Klicka på **Global profil** platta.
1. Välj **Konfiguration av XML-redigerare** och klicka **Redigera** ikonen längst upp
1. Klicka på **Ladda ned** om du vill hämta filen ui\_config.json på ditt lokala system. Du kan sedan göra ändringar i filen och sedan överföra samma fil.

   The `ui_config.json` filen har tre avsnitt:

   1. **verktygsfält**: Det här avsnittet innehåller en definition av alla funktioner som är tillgängliga i redigerarens verktygsfält, t.ex. Infoga/ta bort numrerad lista, Stäng, Spara, Kommentarer med mera.

   1. **genvägar**: Det här avsnittet innehåller definitionen av kortkommandon som tilldelats en viss funktion i redigeraren.

   1. **mallar**: Det här avsnittet innehåller den fördefinierade strukturen för DITA-element som du kan använda i ditt dokument. Som standard innehåller mallavsnittet malldefinitioner för ett stycke-, enkel tabell-, tabell- och body-element. Du kan skapa en malldefinition för vilket element som helst genom att lägga till en giltig XML-struktur för det önskade elementet. Om du till exempel vill lägga till en `p` element med alla nya `li` -element i en lista kan du lägga till följande kod i slutet av mallavsnittet för att uppnå detta:

   ```css
   "li": "<li><p></p></li>"
   ```

1. I verktygsfältsavsnittet tar du bort den funktion som du inte vill visa för användarna.

1. Spara *ui\_config.json* och läsa in webbredigeraren igen.


**Överordnat ämne:**[ Anpassa Web Editor](conf-web-editor.md)
