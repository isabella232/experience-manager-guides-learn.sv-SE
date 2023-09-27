---
title: Hantera granskningsåtgärder med hjälp av Kontrollpanelen
description: Hantera granskningsuppgifter från granskningspanelen i AEM. Lär dig hur du utför åtgärder under uppgiften, innehållet, fliken Granskare och kontrollera status för en granskningsåtgärd.
exl-id: 617017fe-59b6-4b38-b375-a126fa9dddf5
source-git-commit: 8504a0a52d381044bf1f0d6e7de3585ebecf3a7b
workflow-type: tm+mt
source-wordcount: '1300'
ht-degree: 0%

---

# Hantera granskningsåtgärder med hjälp av Kontrollpanelen {#id2056B0Y70X4}

Arbetsflödet för granskningshantering kan innehålla en mängd olika uppgifter. Du kan till exempel lägga till granskare för ett visst ämne eller förlänga tidsgränsen för en granskning. Du kan också markera granskningen som slutförd om du tror att alla intressenter har gett sin feedback. Dessa uppgifter kan hanteras med hjälp av kontrollpanelen för granskning.

Utför följande steg för att komma åt och använda kontrollpanelen:

>[!NOTE]
>
> Du kan bara hantera granskningsåtgärder för de projekt som du är författare \(eller initierare\) för. Även om du är granskare eller utgivare \(användare\) har du inte åtkomst till någon av projektuppgifterna.

1. I **Projekt** klickar du på granskningsprojektet som du vill hantera.

   En projektpanel med åtgärdsrutor visas.

   ![](images/review-management.png){width="800" align="left"}

1. Klicka på de tre punkterna i **Recensioner** platta.

   Kontrollpanelen för granskning visas. Kontrollpanelen visar alla granskningsåtgärder som du har skapat.

   ![](images/review-dashboard.png){width="800" align="left"}

   På kontrollpanelen Granska visas information om granskningsaktiviteten, t.ex. aktivitetsnamn, vem som startade granskningen, datum när granskningen startades, förfallodatum, status, antal nya kommentarer som inte har godkänts eller avvisats av författaren samt namn på granskarna. Uppgifterna visas i ordningen för nyligen skapade uppgifter till äldre uppgifter.

   >[!NOTE]
   >
   > Om du klickar på länken Granska uppgift öppnas det ämne eller den karta som skickats för granskning.

1. Välj en granskningsåtgärd.

   Redigera egenskaper och [Status](#check-review-status-id199RF0A0UHS) i verktygsfältet.

1. Klicka **Redigera egenskaper** visas sidan Uppgiftsinformation.

   Det finns tre flikar på sidan Uppgiftsinformation - Aktivitet, Innehåll och Granskare. I följande avsnitt beskrivs de olika funktioner som är tillgängliga under varje flik.


## Fliken Uppgift

![](images/review-task-page.png){width="800" align="left"}

Du kan utföra följande åtgärder under **Uppgift** tab:

- Ändra aktivitetens titel i **Titel** fält.
- Lägg till standardtilldelningar i **Tilldela till** listruta. De granskare du lägger till härifrån får åtkomst till alla ämnen som ingår i denna granskningsuppgift. Du kan välja att ta bort eller selektivt lägga till fler granskare i specifika ämnen i [Fliken Granskare](#reviewer-tab-id199RF0N0MUI).
- Uppdatera beskrivningen av aktiviteten i **Beskrivning** fält.
- Ändra **Förfallodatum**. Du kan fördröja eller skjuta upp deadline för slutförandet av uppgiften.
- Välj alternativet att begränsa användarnas behörighet till att endast granska de ämnen som är tilldelade dem.
- Klicka **Uppdatera** för att uppdatera den ändrade informationen.
- Klicka **Complete** om du vill markera granskningsaktiviteten som slutförd före förfallodatumet. När ett enskilt temats uppgift har markerats som Fullständig stängs granskningen av det valda ämnet. Om ämnen delas för granskning via en DITA-karta och DITA-kartan markeras som fullständig, kommer dock granskningen av alla ämnen på kartan som delats för granskning att stängas.
- Klicka **Duplicera** om du vill skapa en kopia av granskningsaktiviteten. Processen att skapa en dubblettgranskningsuppgift påminner om att skapa en ny granskningsuppgift. När du har startat det duplicerade arbetsflödet visas sidan Skapa granskningsuppgift. Du måste ange den nya uppgiftsinformationen enligt beskrivningen i [Skicka ämnen för granskning](review-send-topics-for-review.md#).

  Om du har valt en granskningsuppgift som skapats av en DITA-karta visas de ämnen som är en del av kartan. Du kan sedan välja vilka ämnen du vill ta med i den nya granskningsaktiviteten.

  Om en granskningsuppgift dupliceras från en eller flera ämnesgranskningar visas endast dessa ämnen i listan över granskningsåtgärder. Du kan dela dessa ämnen för granskning med en annan uppsättning granskare.

- Klicka **Stäng** för att gå till sidan Inkorg.

## Fliken Innehåll

![](images/review-content-page.png){width="800" align="left"}

Du kan utföra följande åtgärder under **Innehåll** tab:

- Ändra versionen av ämnet som skickats för granskning. Du kan välja den senaste versionen av ämnet, version per datum, version med specifik etikett eller version med en viss baslinje \(för en DITA-karta\).

- Klicka **Uppdatera** för att dela den uppdaterade versionen av ämnet med granskarna. Granskarna får ett e-postmeddelande om att den nyare versionen av ämnet har skickats för granskning. Nästa gång en granskare öppnar ämnet ser de den uppdaterade versionen av ämnet.

  >[!NOTE]
  >
  > Om det finns en uppdaterad version av ett ämne behålls de gamla kommentarerna även i den nyare versionen. Granskarna kan också se skillnaderna mellan de två versionerna.

- Klicka **Complete** om du vill markera granskningsaktiviteten som slutförd före förfallodatumet. När ett enskilt temats uppgift har markerats som Fullständig stängs granskningen av det valda ämnet. Om ämnen delas för granskning via en DITA-karta och DITA-kartan markeras som fullständig, kommer dock granskningen av alla ämnen på kartan som delats för granskning att stängas.

- Klicka **Duplicera** om du vill skapa en ny granskningsuppgift med den aktuella uppgiften som bas.


## Fliken Granskare {#reviewer-tab-id199RF0N0MUI}

![](images/reviewers-tab.png){width="800" align="left"}

Du kan utföra följande åtgärder under **Granskare** tab:

- **Markera alla**: Markerar alla ämnen i ämneslistan. Du kan enkelt utföra en gruppåtgärd när du har valt alla ämnen.
- **Radera markering**: Avmarkerar ämnen som är markerade i ämneslistan.

  >[!NOTE]
  >
  > Du kan också markera eller avmarkera ett ämne separat genom att klicka i kryssrutan bredvid ämnet.

- **Lägg till**: Visar dialogrutan Lägg till granskare. Du kan skriva namnet på en granskare eller användarroll \(eller grupp\) som du vill lägga till som granskare i de valda avsnitten.
- **Ta bort**: Visar dialogrutan Ta bort granskare. Du kan skriva namnet på en granskare eller användarroll \(eller grupp\) som du vill ta bort som granskare i de markerade avsnitten.
- **Tilldela igen**: Visar dialogrutan Tilldela granskare igen. Du kan skriva namnet på en granskare eller användarroll \(eller grupp\) som du vill tilldela granskningsuppgiften till. Detta tar bort alla befintliga granskare från de markerade avsnitten och tilldelar de nyvalda granskarna till dessa ämnen.
- **Exportera**: Gör att du kan exportera information om granskningsåtgärder i en CSV-fil. Filen innehåller information om ämnessökväg och rubrik, namn på granskare och version av ämnen som skickats för granskning.
- **Redigera granskare**: Klicka på ![](images/edit_pencil_icon.svg)i ämneslistan visas dialogrutan Redigera granskare. Du kan lägga till eller ta bort granskare för det valda ämnet från den här dialogrutan.

## Kontrollera status för en granskningsaktivitet {#check-review-status-id199RF0A0UHS}

Om du väljer en granskningsuppgift och klickar på **Status** visas statusrapporten för granskningsaktiviteten:

![](images/review-status-report.png){width="800" align="left"}

Statusrapporten för granskningsaktiviteten innehåller följande information:

- Namn på den granskare som granskningsuppgiften är tilldelad.
- Statuskolumnen anger granskningsstatusen. Status kan vara något av följande:
   - **Har inte startats**: Granskaren har inte öppnat granskningslänken än.
   - **Pågår**: Granskaren har öppnat granskningslänken och håller på att granska avsnittet.
   - **Complete**: Granskaren har slutfört granskningen genom att slutföra den granskningsuppgift som tilldelats honom/henne. Granskningsaktiviteten finns i AEM för varje granskare.
- När en granskare öppnar en granskningslänk och navigerar till ett visst ämne läggs det ämnet till i listan Ämnen som granskats. Detta hjälper författarna att avgöra om granskarna har öppnat respektive avsnitt eller inte. Om några kommentarer ges visas de inom parentes.
- Totalt antal kommentarer som gjorts i alla ämnen. Om det finns flera ämnen som är under granskning anges antalet kommentarer för varje ämne \(inom parentes\) mot temanamnet.
- Det datum då granskaren senast öppnade ett ämne.

**Överordnat ämne:**[ Granska ämnen och kartor](review.md)
