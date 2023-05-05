---
title: Skapa och hantera baslinjer från Web Editor
description: Lär dig hur du skapar och hanterar baslinjer i Web Editor
exl-id: 9e390489-16f5-4f9a-a821-5150a66c2ed4
source-git-commit: 3bca42f0954afc2362ab24f369e698113324dbc3
workflow-type: tm+mt
source-wordcount: '1190'
ht-degree: 0%

---

# Skapa och hantera baslinjer från Web Editor {#id223MB0ZF043}

>[!TIP]
>
> Du bör använda den här baslinjefunktionen i webbredigeraren om du har uppgraderat till AEM Guides as a Cloud Service March eller senare.

AEM innehåller baslinjefunktionen som är integrerad i Web Editor och som gör att användarna kan skapa baslinjer och använda dem för att publicera eller översätta ämnen från olika versioner.

## Skapa en baslinje

Du kan skapa en baslinje i Web Editor genom att utföra följande steg:

1. Öppna DITA-schemafilen i Kartvyn på databaspanelen.
1. Klicka på **Hantera** -fliken. The **Baslinje** På panelen visas baslinjerna för DITA-kartan.

   ![](images/baseline-manage.png){width="800" align="left"}

1. På **Baslinje** klickar du på +-ikonen längst upp till höger. Du kan skapa en baslinje med en specifik version av ämnen och refererat innehåll som är tillgängligt på ett visst datum och en viss tid, eller med en etikett definierad för en version av ämnen.
1. Ange ett namn för baslinjen i **Baslinjenamn**.
1. I **Baslinjealternativ** kan du antingen välja **Använd filversion** eller **Använd etiketter** alternativ:

   **Använd filversion**: Du kan skapa en statisk baslinje med en specifik version av ämnen och refererat innehåll som är tillgängligt på ett visst datum och en viss tid, eller med en etikett som är definierad för en version av ämnen:

   - I **Ange den senaste versionen baserat på** Välj något av följande alternativ:


      1. **Datum** &lt;time stamp=&quot;&quot;>: Hämtar ämnesversionen som angivet datum och angiven tid.
      1. **Etikett**: Välj det här alternativet om du vill välja ämnen enligt den etikett som används på dem. Om rubrikerna har etiketter som är angivna för dem visas etiketterna i listrutan. Du kan välja en etikett i listan. Du kan också lägga till en etikett i textrutan.\
         När du väljer **Etikett,** Du kan välja direkta och indirekta referenser.
      - För direkta referenser inom DITA-kartan får du ett alternativ att använda den senaste versionen av ämnen som inte har den angivna etiketten.

      >[!NOTE]
      >
      > Om du anger en etikett som inte finns och väljer alternativet **Skapa ingen baslinje** då misslyckas skapandet av baslinjen och ett felmeddelande visas nära baslinjenamnet på baslinjepanelen.

      - För indirekta referenser inom DITA-kartan får du ett extra alternativ att använda den senaste versionen av ämnen som inte har den angivna etiketten. Du kan också välja att **Välj automatiskt** för det refererade innehållet så väljs automatiskt den version av det refererade innehållet som motsvarar den version av innehållet som det refereras till i.

   När du har markerat en etikett eller version som den är, markeras alla refererade ämnen och mediefiler på kartan därefter. Det här valet av ämnen visas inte i användargränssnittet, men sparas i serverdelen.

   **Använd etiketter**: Välj det här alternativet för att skapa baslinjen om du vill välja ämnen enligt den etikett som används på dem.

   Baslinjer som baseras på etiketter uppdateras dynamiskt. Om du genererar en baslinje, hämtar en baslinje eller skapar ett översättningsprojekt med hjälp av en baslinje, hämtas filerna dynamiskt baserat på de uppdaterade etiketterna. Om du till exempel har använt version 1.2 av ett ämne med Label Release 1.0 för baslinjen och senare uppdaterat version 1.5 med Label Release 1.0, uppdateras baslinjen dynamiskt och version 1.5 används.

   ![](images/dynamic-baseline.png){width="550" align="left"}

   - **Markera etiketter**: Om du har angett rubriker för ämnena visas etiketterna i **Markera etiketter** listruta. Du kan välja etiketten/etiketterna i listan. De etiketter som är markerade först får högre prioritet än de som väljs senare.
1. **Indirekta referenser**: För indirekta referenser i DITA-kartan får du följande alternativ:

   - **Välj automatiskt**: Du kan välja att **Välj automatiskt** för det refererade innehållet så väljs automatiskt den version av det refererade innehållet som motsvarar den version av innehållet som det refereras till i.

   - **Använd markerad etikett**: Du kan skapa en baslinje med den valda etiketten definierad för en ämnesversion.
   - **Använd den senaste versionen eller arbetskopian**: Använd den senaste versionen av ämnen som inte har den angivna etiketten tillämpad på dem, eller om ingen version har skapats, använd arbetskopian av ämnena för att skapa baslinjen.
1. Klicka **Använd**.

Baslinjen skapas. Baslinjen skapas asynkront, så du kan fortsätta arbeta med andra filer i Web Editor. När baslinjen har skapats visas ett popup-meddelande som bekräftar att baslinjen har skapats, och du får även ett inkorgsmeddelande för det.

## Hantera baslinjer

Du kan hantera befintliga baslinjer med hjälp av de olika funktionerna på kontrollpanelen för baslinjer.

- Du kan söka efter en befintlig baslinje med textrutan på panelen Baslinje. Använd **Använd filter** om du vill visa alla baslinjer eller visa baslinjer med status Slutfört, Pågående eller Misslyckat när de skapas.
- Använd **Uppdatera** på panelen Baslinje om du vill kontrollera om det finns alla baslinjer och visa en ny lista med baslinjer för DITA-kartan som öppnas i Kartvyn.
- Du kan visa eller redigera innehållet i en befintlig baslinje genom att dubbelklicka på baslinjen i listan på panelen Baslinje. Baslinjeredigeringsfönstret i mitten visar DITA-kartfilen, kartans innehåll eller ämnen samt det refererade innehållet.


![](images/baseline-options.png){width="550" align="left"}

Du kan även utföra följande åtgärder på baslinjen på Alternativ-menyn:

- **Redigera**, **Duplicera,** eller **Ta bort** en befintlig baslinje.
- Lägg till, ta bort eller ändra befintliga etiketter från **Hantera etiketter** alternativ. Om administratören har konfigurerat fördefinierade etiketter visas dessa i listrutan Lägg till etikett. Mer information om hur du lägger till etiketter finns i [Använd etiketter](web-editor-use-label.md#).

   >[!NOTE]
   >
   > Processen att lägga till eller ta bort etiketter sker asynkront, så du kan fortsätta arbeta med andra filer i Web Editor. När etiketten har lagts till eller tagits bort visas ett popup-meddelande som bekräftar att etiketten har lagts till eller tagits bort, och du får även ett inkorgsmeddelande om detta.

- **Redigera egenskaper** av en befintlig baslinje som du har angett när du skapade baslinjen.
- Exportera ögonblicksbilden av en baslinje i en CSV-fil med **Exportera baslinje** alternativ.

**Baslinjefilter**

Använda ikonen Filter i **Baslinjefilter** kan du använda filter på baslinjen som öppnas i redigeringsfönstret för baslinjen:

![](images/baseline-filter.png){width="350" align="left"}

- Filtrera filerna baserat på filnamn eller filplats.
- Filtrera filerna baserat på värdena för olika kolumner som filtyp, referenstyp och så vidare.
- Välj de kolumner som ska visas i redigeringsfönstret för baslinjen.

>[!NOTE]
>
> Du kan klicka på en kolumnrubrik och sortera filerna baserat på kolumnerna i redigeringsfönstret för baslinjen.

**Spara eller återställa en baslinje**

När du har redigerat baslinjen kan du klicka på **Spara** överst för att spara ändringarna i baslinjen. Du kan klicka på **Återställ** om du inte vill spara ändringen och återställa baslinjen. När du klickar på **Återställ** visas en varning om att ändringar som inte sparats går förlorade.

**Överordnat ämne:**[ Arbeta med webbredigeraren](web-editor.md)
