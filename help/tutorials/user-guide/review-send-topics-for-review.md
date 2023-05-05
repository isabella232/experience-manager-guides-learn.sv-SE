---
title: Skicka ämnen för granskning
description: Lär dig hur du skickar ämnen för granskning
exl-id: 7a9b36ad-44d4-4952-9906-d95feb95d0c6
source-git-commit: 8823669fd29e8a40a41f9ca5d654b38fbea8e2fa
workflow-type: tm+mt
source-wordcount: '2733'
ht-degree: 0%

---

# Skicka ämnen för granskning {#id199RD0S035Z}

Granskningsarbetsflödet skapar en miljö med flera granskare där initieraren anger en lista med ämnen för granskning, lägger till flera granskare och tilldelar en tidslinje för granskningsaktiviteten. AEM Guides tillåter användare som tillhör grupperna Författare och Utgivare att initiera en granskning.

Eftersom granskningsarbetsflödet är projektspecifikt måste granskningsinitieraren vara en del av projektteamet eller ha behörighet att skapa ett projekt. När du skapar ett projekt definierar du teammedlemmarna för projektet och tilldelar dem olika roller eller grupper. Mer information om projekt finns i [Skapa ett DITA-projekt](authoring-create-dita-project.md#).

Du kan skapa en granskningsuppgift från:

- **Web Editor**: Skicka ett enskilt ämne eller en DITA-karta för granskning. Observera att arbetsflödet som används för att skapa en granskningsåtgärd är vanligt i webbredigeraren och resursgränssnittet. Det är bara metoden för att starta granskningsarbetsflödet som skiljer sig. Information om hur du startar granskningsarbetsflödet i Web Editor finns i [Skapa granskningsuppgift](web-editor-features.md#id215OCJ00JXA) i Web Editor.

- **Resurser, användargränssnitt**: Gör att du kan skicka ett eller flera ämnen och DITA-karta för granskning. Delning av dokument för granskning från Assets UI-arbetsflödet beskrivs i det här avsnittet.


I resursgränssnittet finns det två sätt som en författare/utgivare kan skapa en granskningsuppgift på:

- Skicka ett eller flera ämnen för granskning
- Skicka flera ämnen från en DITA-karta för granskning

## Skicka ett eller flera ämnen för granskning {#id1721E600FY4}

>[!IMPORTANT]
>
> Innan du skapar en granskningsuppgift bör du kontrollera att du har skapat ett projekt och lagt till granskare i det projektet.

Så här skapar du en granskningsuppgift och skickar ämnen för granskning:

>[!NOTE]
>
> Du kan bara skapa en granskningsåtgärd om du är författare eller utgivare i ett DITA-projekt.

1. Navigera till önskad mapp i resursgränssnittet.

1. Klicka på ikonen Välj i snabbåtgärden och välj de ämnen som du vill skicka för granskning.

   ![](images/select-asset-62.png){width="300" align="left"}

1. Klicka på i verktygsfältet **Skapa granskningsuppgift**. Sidan där granskningsaktiviteten skapas visas.

   >[!NOTE]
   >
   > Du kan skapa en granskningsåtgärd för endast de ämnen som har en revision. Om det markerade ämnet inte har någon revidering visas ett meddelande.

   ![](images/create-review-task-023.png){width="650" align="left"}

1. Ange **Titel** för uppgiften och välj en DITA **Projekt** i listrutan.

1. I **Tilldela till** väljer du de granskare som du vill skicka ämnena till för granskning.

   Du kan tilldela en granskningsuppgift till enskilda användare i projektet eller till användargrupper. Observera att du bara kan tilldela en granskningsuppgift till enskilda användare när du är en del av projektets administratörsgrupp, annars visas bara användargrupperna i fältet Tilldela till.

   >[!NOTE]
   >
   > Granskningsarbetsflödet är projektspecifikt. När du skapar projekt lägger du till teammedlemmarna i projektet och tilldelar dem till grupper. När du väljer projektet här kan du alltså välja vilka medlemmar som ingår i det projektet. Mer information om projekt finns i [Skapa ett DITA-projekt](authoring-create-dita-project.md#).

1. Ange **Beskrivning** för uppgiften.

   Beskrivningen används som brödtext i det e-postmeddelande som skickas till granskarna.

1. Välj **Förfallodatum** och tid för att markera deadline för granskningen.

   >[!NOTE]
   >
   > När tidsgränsen har nåtts skickas ett e-postmeddelande till initieraren som meddelar att granskningsåtgärden har slutförts. Initieraren kan förlänga deadlinen för granskningsaktiviteten från [Kontrollpanelen](review-manage-tasks-review-dashboard.md#).

1. Välj rotkartan på menyn **Rotmappsbana**. Den här rotmappen används för att matcha alla nyckelreferenser och ordlistor som används i granskningsinnehållet. Om du inte markerar rotmappen kommer inte de nyckelreferenser eller ordlistor som är associerade med DITA-avsnittet att matchas innan avsnittet skickas för granskning.

   Om du skapar granskningen för en DITA-karta är det som standard **Rotmappsbana** är inställt på kartans sökväg. Om du skapar en granskning för ett eller flera ämnen är standardinställningen **Rotmappsbana** är inställt på den karta som definieras i användarinställningarna.

   >[!NOTE]
   >
   > Den markerade rotkartan har högsta prioritet för att lösa nyckelreferenser. Mer information finns i [Lös nyckelreferenser](map-editor-other-features.md#id176GD01H05Z).

1. Eftersom du kan tilldela olika granskare till olika ämnen, **Tillåt att uppdragsgivare granskar alla ämnen** styr om granskarna kan granska alla ämnen i en granskningsuppgift eller endast de ämnen som de har tilldelats för granskning.

   Om du vill att alla granskare ska kunna granska något ämne i granskningsuppgiften väljer du **Tillåt att uppdragsgivare granskar alla ämnen**.

   Om du inte markerar det här alternativet läggs granskare till i **Tilldela till** -fältet har bara åtkomst att granska de ämnen som är tilldelade dem.

1. Klicka på **Nästa**.

   Sidan Innehåll visas.

   ![](images/content_page_review.png){width="800" align="left"}

1. På sidan Innehåll väljer du en version av ämnet som du vill dela för granskning.

   Du kan använda någon av följande metoder för att välja en version:

   - *\(Standard\)* Välj alternativ **Deras senaste version** för att välja den senast sparade versionen av ämnena.
   - Välj **Version på** och ange datum och tid för att välja en version på angivet datum och angiven tid. Om det inte finns någon tillgänglig version av ämnet på det angivna datumet är en version tillgänglig direkt efter det angivna datumet och tiden markerad.
   - Välj **Välj en etikett** och välj en etikett i listrutan.
1. När du har valt en version klickar du på **Använd**.

   Versionen som baseras på det valda alternativet väljs för ämnena.

   >[!NOTE]
   >
   > Du kan också välja önskad version manuellt från **Version** nedrullningsbar lista med varje ämne.

1. Klicka på **Nästa**.

   Sidan Granskare visas där du kan lägga till eller ta bort granskare. Som standard läggs granskarna som läggs till i fältet Tilldela till automatiskt till varje ämne som markeras för granskningen.

   ![](images/add-reviewers-topics.png){width="650" align="left"}

1. På sidan Granskare kan du lägga till eller ta bort granskare. Följande åtgärder är tillgängliga på sidan Granskare:

   - **Markera alla**: Väljer alla ämnen i ämneslistan. Du kan enkelt utföra en gruppåtgärd när du har valt alla ämnen.
   - **Radera markering**: Avmarkerar ämnen som är markerade i ämneslistan.

      >[!NOTE]
      >
      > Du kan också markera eller avmarkera ett ämne separat genom att klicka i kryssrutan bredvid ämnet.

   - **Lägg till**: Visar dialogrutan Lägg till granskare. Du kan skriva namnet på en granskare eller användarroll \(eller grupp\) som du vill lägga till som granskare i de valda avsnitten.
   - **Ta bort**: Visar dialogrutan Ta bort granskare. Du kan skriva namnet på en granskare eller användarroll \(eller grupp\) som du vill ta bort som granskare i de markerade avsnitten.

      >[!NOTE]
      >
      > Du kan också ta bort en granskning från ett ämne genom att klicka på krysset i rutan för granskare.

   - **Tilldela igen**: Visar dialogrutan Tilldela granskare igen. Du kan skriva namnet på en granskare eller användarroll \(eller grupp\) som du vill tilldela granskningsaktiviteten till. Detta tar bort alla befintliga granskare från de markerade avsnitten och tilldelar de nyvalda granskarna till dessa ämnen.
   - **Exportera**: Gör att du kan exportera information om granskningsåtgärder i en CSV-fil. Filen innehåller information om ämnessökväg och rubrik, namn på granskare och version av ämnen som skickats för granskning.
   - **Redigera granskare**: Klicka på ![](images/edit_pencil_icon.svg)-ikonen i ämneslistan visar dialogrutan Redigera granskare. Du kan lägga till eller ta bort granskare för det valda ämnet från den här dialogrutan.
1. Klicka **Skapa** för att skapa granskningsaktiviteten.

   Ett bekräftelsemeddelande visas när granskningsåtgärden har skapats. The [Dokumenttillstånd](web-editor-document-states.md#) för ämnen som skickas för granskning anges till Granskning.

   >[!NOTE]
   >
   > Du kan också klicka på meddelandeklockan längst upp till höger på skärmen och bekräfta att granskningsåtgärden har skapats. På meddelandepanelen hittar du ett meddelande för varje granskare som var en del av granskningsaktiviteten och ett för initieraren av granskningen.


Ett e-postmeddelande skickas till alla granskare som meddelar att de har tilldelats ett eller flera ämnen för granskning. E-postmeddelandet innehåller en direkt länk som de kan klicka på och komma åt ämnet i ett webbläsarfönster.

Om flera ämnen har tilldelats kan granskarna visa och välja dem i en nedrullningsbar lista med ämnen i webbläsaren.

## Skicka flera ämnen för granskning från en DITA-karta

En DITA-karta är en logisk organisation av ämnen i en bok. När du skickar ett enskilt ämne för granskning får granskaren ingen information om var ämnet finns i boken. Om en granskare har information om exakt var det ämne som granskas finns, får granskaren ett bättre sammanhang för det ämne som granskas.

Med AEM Guides kan du skicka ett eller flera ämnen i en DITA-karta för granskning samtidigt. Granskaren får se hela kartan tillsammans med ämnen som delats för granskning. Detta gör det enklare för granskaren att få en översikt över ämnet i kartan eller bokfilen.

Du kan dela samma DITA-karta i för granskning i flera granskningsåtgärder. Om det till exempel finns avsnitt A, B, C, D och E på en DITA-karta. I en granskningsuppgift kan du dela A, B och C för granskning och i en annan granskningsuppgift kan du skicka ämnen C, D och E för granskning. Granskningsprocessen gör det möjligt att dela samma ämne och kartfil i flera granskningsåtgärder. För det vanliga ämnet i flera granskningsuppgifter skrivs inte kommentarerna som ges i en granskningsuppgift över eller sammanfogas med kommentarerna i de andra granskningsuppgifterna.

>[!IMPORTANT]
>
> Om ett ämne i en kartfil har delats i flera granskningsåtgärder visas statusen Granskning tills alla granskningsåtgärder har slutförts.

Så här skickar du ett eller flera avsnitt tillsammans med kartfilen för granskning:

>[!IMPORTANT]
>
> När du har initierat en granskning via en kartfil får du inte ändra strukturen på mappningsfilen genom att lägga till nya ämnen eller ta bort befintliga ämnen.

1. Navigera till önskad mapp i resursgränssnittet.

   >[!NOTE]
   >
   > Kontrollera att konsolvyn är inställd på antingen kortvy eller listvy.

1. Markera kartan som du vill skicka ämnena från för granskning.

1. Klicka på i verktygsfältet **Skapa granskningsuppgift**. Sidan där granskningsaktiviteten skapas visas.

1. Ange **Titel** för uppgiften och välj en DITA **Projekt** i listrutan.

   >[!NOTE]
   >
   > Du kan skapa en granskningsåtgärd för endast de ämnen som har en revision. Om kartan innehåller ämnen som inte har någon revidering visas ett meddelande med en lista över sådana filer. Filer utan revision exkluderas från granskningsaktiviteten.

1. I **Tilldela till** väljer du de granskare som du vill skicka ämnena till för granskning.

   Du kan tilldela en granskningsuppgift till enskilda användare i projektet eller till användargrupper. Observera att du bara kan tilldela en granskningsuppgift till enskilda användare när du är en del av projektets administratörsgrupp, annars visas bara användargrupperna i fältet Tilldela till.

   >[!NOTE]
   >
   > Granskningsarbetsflödet är projektspecifikt. När du skapar projekt lägger du till teammedlemmarna i projektet och tilldelar dem till grupper. När du väljer projektet här kan du alltså välja vilka medlemmar som ingår i det projektet. Mer information om projekt finns i [Skapa ett DITA-projekt](authoring-create-dita-project.md#).

1. Ange **Beskrivning** för uppgiften.

   Beskrivningen används som brödtext i det e-postmeddelande som skickas till granskarna.

1. Välj **Förfallodatum** och tid för att markera deadline för granskningen.

   >[!NOTE]
   >
   > När tidsgränsen har nåtts skickas ett e-postmeddelande till initieraren som meddelar att granskningsåtgärden har slutförts. Initieraren kan förlänga deadlinen för granskningsaktiviteten från [Kontrollpanelen](review-manage-tasks-review-dashboard.md#).

1. Eftersom du kan tilldela olika granskare till olika ämnen, **Tillåt att uppdragsgivare granskar alla ämnen** styr om granskarna kan granska alla ämnen i en granskningsuppgift eller endast de ämnen som de har tilldelats för granskning.

   Om du vill att alla granskare ska kunna granska något ämne i granskningsuppgiften väljer du **Tillåt att uppdragsgivare granskar alla ämnen**.

   Om du inte markerar det här alternativet läggs granskare till i **Tilldela till** -fältet har bara åtkomst att granska de ämnen som är tilldelade dem.

1. Klicka på **Nästa**.

   Innehållssidan visas med alla ämnen som kartfilen refererar till. Om din DITA-karta innehåller kapslade kartor listas även ämnen från kapslade kartor här.

   ![](images/content-page-map-review.png){width="800" align="left"}

1. På sidan Innehåll väljer du en version av ämnet som du vill dela för granskning.

   Du kan använda någon av följande metoder för att välja en version:

   - *\(Standard\)* Välj alternativ **Deras senaste version** för att välja den senast sparade versionen av ämnena.
   - Välj **Version på** och ange datum och tid för att välja en version utifrån datum och tid. Om det inte finns någon tillgänglig version av ämnet på det angivna datumet är en version tillgänglig direkt efter det angivna datumet och tiden markerad.
   - Välj **Välj en etikett** och välj en etikett i listrutan. Alla ämnen som innehåller den valda etiketten markeras i **Version** nedrullningsbar lista.
   - Välj **Markera en baslinje** och välj en baslinje i listrutan. Alla ämnesversioner som är en del av den valda baslinjen markeras i **Version** nedrullningsbar lista.
1. När du har valt en version klickar du på **Använd**.

   Versionen som baseras på det valda alternativet väljs för ämnena.

   >[!NOTE]
   >
   > Du kan också välja önskad version manuellt från **Version** nedrullningsbar lista med varje ämne.

1. Klicka på **Nästa**.

   Sidan Granskare visas där du kan lägga till eller ta bort granskare. Som standard läggs granskarna som läggs till i fältet Tilldela till automatiskt till varje ämne som markeras för granskningen.

1. På sidan Granskare kan du lägga till eller ta bort granskare. Följande åtgärder är tillgängliga på sidan Granskare:

   - **Markera alla**: Väljer alla ämnen i ämneslistan. Du kan enkelt utföra en gruppåtgärd när du har valt alla ämnen.
   - **Radera markering**: Avmarkerar ämnen som är markerade i ämneslistan.

      >[!NOTE]
      >
      > Du kan också markera eller avmarkera ett ämne separat genom att klicka i kryssrutan bredvid ämnet.

   - **Lägg till**: Visar dialogrutan Lägg till granskare. Du kan skriva namnet på en granskare eller användarroll \(eller grupp\) som du vill lägga till som granskare i de valda avsnitten.
   - **Ta bort**: Visar dialogrutan Ta bort granskare. Du kan skriva namnet på en granskare eller användarroll \(eller grupp\) som du vill ta bort som granskare i de markerade avsnitten.
   - **Tilldela igen**: Visar dialogrutan Tilldela granskare igen. Du kan skriva namnet på en granskare eller användarroll \(eller grupp\) som du vill tilldela granskningsaktiviteten till. Detta tar bort alla befintliga granskare från de markerade avsnitten och tilldelar de nyvalda granskarna till dessa ämnen.
   - **Exportera**: Gör att du kan exportera information om granskningsåtgärder i en CSV-fil. Filen innehåller information om ämnessökväg och rubrik, namn på granskare och version av ämnen som skickats för granskning.
   - **Redigera granskare**: Klicka på ![](images/edit_pencil_icon.svg)-ikonen i ämneslistan visar dialogrutan Redigera granskare. Du kan lägga till eller ta bort granskare för det valda ämnet från den här dialogrutan.

   >[!IMPORTANT]
   >
   > Du måste tilldela minst en granskare för att skapa granskningsaktiviteten.

1. Klicka **Skapa** för att skapa granskningsaktiviteten.

   Ett bekräftelsemeddelande visas när granskningsåtgärden har skapats. The [Dokumenttillstånd](web-editor-document-states.md#) för ämnen som skickas för granskning anges till Granskning.

   >[!NOTE]
   >
   > Du kan också klicka på meddelandepanelen längst upp till höger i gränssnittet och bekräfta att uppgiften har skapats. På meddelandepanelen hittar du ett meddelande för varje granskning som var en del av granskningsaktiviteten och ett meddelande till initieraren av granskningen.

   >[!IMPORTANT]
   >
   > När du har initierat en granskning får du inte flytta eller ta bort DITA-kartan eller -avsnitten till en annan plats. Om du gör det avbryts granskningsprocessen.


Ett e-postmeddelande skickas till alla granskare som meddelar att de har tilldelats ämnen för granskning. E-postmeddelandet innehåller en direkt länk som de kan klicka på och komma åt ämnet i ett webbläsarfönster. Ämnen tillsammans med DITA-kartan öppnas i granskningsläget.

**Överordnat ämne:**[ Granska ämnen och kartor](review.md)
