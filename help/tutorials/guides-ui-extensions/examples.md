---
sidebar_position: 8
source-git-commit: d99be38f5d69a7472909511faad230bea9bc435b
workflow-type: tm+mt
source-wordcount: '372'
ht-degree: 0%

---


# Exempel

I det här paketet har vi även tagit med några exempel på anpassning (finns på `guides_extension/src`) . Nedan följer en kort beskrivning av var och en av dem.

1. [Snabbmeny](./../../src/file_options.ts)
I det här exemplet har vi anpassat `file_options` snabbmeny, ta bort `Delete` och `Edit` och ersätta `Duplicate` med ett `Download` alternativ.

2. [Vänster panel](../../src/left_panel_container.ts)
I det här exemplet har vi anpassat `left tab panel` att ha en annan`tab` &quot;TEST EXTENSION&quot; och en `tab panel` som har en etikett: `Test Tab Panel`

3. [Höger panel](../../src/right_panel_container.ts)
I det här exemplet har vi anpassat `right tab panel` att ha en annan `tab` &quot;TEST EXTENSION&quot; och en `tab panel` som har en etikett: `New Tab Panel`

4. [Databaspanel](../../src/repository_panel.ts)

5. [Verktygsfält](../../src/toolbar.ts)
I detta exempel har vi ersatt `Insert Element`, `Insert Paragraph`, `Insert Numbered List`, `Insert Bulleted List` knappar med en enda `More Insert Options` som innehåller alla dessa.

[Exempel på appar]

1. [Anteckningsverktygslåda](../../src/review_app_examples/annotation_extension.ts)
I det här exemplet har vi lagt till ytterligare en knapp i anteckningsverktygslådan som öppnar det aktuella granskningsämnet i AEM.

2. [Granska kommentar](../../src/review_app_examples/review_comment.ts)
I det här exemplet har vi lagt till ersatt användarnamnet med användarinformation (som består av kommentarens fullständiga namn och titel), lagt till ett unikt kommentar-ID, en mailTo-ikon och lagt till inmatningsfält för omnämnande av kommentarens allvarlighetsgrad och logiska grund.
Vi har också lagt till en `accept with modification` på kommentarer på XMLEditor-sidan som öppnar en dialogruta.

3. [Kommentarsvar](../../src/review_app_examples/comment_reply.ts)
I det här exemplet har vi lagt till en ersatt användarnamn med användarinformation (som består av kommentarens fullständiga namn och titel) och lagt till en mailTo-ikon i kommentarhuvudet.

4. [Panelen Textgranskning](../../src/review_app_examples/inline_review_panel.ts)
I den här filen beräknar och tilldelar vi det unika kommentar-ID som anges i `Review Comment` och `Comment Reply` exempel.
   - The `setCommentId` metoden anger det unika kommentar-ID:t för varje kommentar beroende på antalet kommentarer.

   - The `setUserInfo` ställer in värdet för userInfo, med det fullständiga namnet och titeln för varje kommentar.

   - The `onNewCommentEvent` säkerställer `setUserInfo` metoden anropas för varje ny kommentar eller svar.

   - The `updatedProcessComments` funktionen körs för varje ny kommentarhändelse och ser till att `setCommentId` anropas om vi får en ny kommentarshändelse.

5. [Panelen Ämnesgranskningar](../../src/review_app_examples/topic_reviews.ts): Den här filen utökas [Panelen Textgranskning](../../src/review_app_examples/inline_review_panel.ts) så att nya anpassningar även fungerar på sidan Granska app.

6. [Acceptera med ändringsdialogruta](../../src/review_app_examples/accept_with_modification_dialog.ts)
Det här är ett exempel på hur du lägger till en ny widget i programmet. Här har vi skapat en ny dialogruta med två inmatningsfält: `Revised Text` och `Adjudicator Comment Rationale`

![Dialogrutan Acceptera med ändring](./imgs/accept_with_modification_dialogue.png)

Här är granskningsfönstret före och efter anpassning:

![Granskningspanelen.](./imgs/review_panel.png)
![Dialogrutan Acceptera med ändring](./imgs/customised_review_panel.png)
