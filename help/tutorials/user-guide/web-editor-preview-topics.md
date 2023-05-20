---
title: Förhandsgranska ett ämne
description: Lär dig hur du förhandsgranskar ett avsnitt
exl-id: fb8eb87b-2a98-4540-9329-08a759145497
source-git-commit: 8073716bccacbe8d6a158b44d5106b083e3a5dcd
workflow-type: tm+mt
source-wordcount: '1815'
ht-degree: 0%

---

# Förhandsgranska ett ämne {#id1696II000QR}

När ett ämne har skapats genererar AEM stödlinjer en förhandsgranskning av ämnet. I förhandsgranskningsläget finns olika funktioner som du kan använda för att arbeta med dokumentet.

Utför följande steg för att förhandsgranska ett ämne:

1. Navigera i resursgränssnittet till det ämne som du vill visa.
1. Klicka på det ämne som du vill visa.

   En förhandsgranskning av ämnet visas i resursgränssnittet.

   >[!NOTE]
   >
   > Du kan se versionen av det aktiva ämnet eller DITA-kartan i det övre högra hörnet av ämnesfliken.

   >[!IMPORTANT]
   >
   > Placeringen av följande funktioner i verktygsfältet Förhandsgranska kan variera beroende på AEM. Vissa av funktionerna kan finnas i huvudverktygsfältet, medan andra finns på Mer-menyn.

## Funktioner som är tillgängliga i förhandsgranskningsläge

![](images/preview-screen.png){width="800" align="left"}

Du kan utföra följande åtgärder från verktygsfältet i förhandsgranskningsläget:

**Egenskaper**

Visa egenskaperna för det markerade ämnet. Baserat på din AEM kan du se egenskaper som metadata, schemaaktivering, referenser, dokumenttillstånd med mera.

>[!NOTE]
>
> Ett ämnes title-egenskap fylls i automatiskt från `title` -taggen för DITA-ämnet eller -kartan. Om du ändrar en titel i egenskapsfönstret försvinner ändringen. Om du vill uppdatera egenskapen title bör du göra det med webbredigeraren.

Sidan Egenskaper innehåller användbar information om referenserna, t.ex. var en karta eller ett ämne används eller vilka referenser som finns i ett dokument. På sidan Egenskaper visas två typer av referenser för ett dokument - **Används i** och **Utgående referenser**.

The **Används i** refererar till en lista med de dokument där den aktuella filen refereras eller används. The **Utgående referenser** visar de dokument som det aktuella dokumentet refererar till.

Ikonen \(+\) i **Används i** kan du navigera uppåt för att hitta var ämnet används eller refereras.

![](images/used-in-dialog_cs.png){width="800" align="left"}

Klicka på ![](images/right-arrow-used-in-dialog.svg)-ikonen bredvid ett dokument visar mappnings- eller ämnesfilerna där dokumentet hänvisas vidare.

**Villkorlig filtrering \(A/B\)**

Om ditt ämne har villkorsstyrt innehåll visas A/B-ikonen i verktygsfältet. Om du klickar på den här ikonen öppnas ett popup-fönster där du kan filtrera innehållet enligt de tillgängliga villkoren i avsnittet.

>[!NOTE]
>
> Det villkorliga innehållet markeras med ljus bakgrundsfärg i Web Editor.

![](images/conditional-popup_cs.png){width="300" align="left"}

**Redigera**

- Öppna ämnet för redigering i Web Editor. The **Redigera** alternativet är inte tillgängligt om administratören har aktiverat **Inaktivera redigering utan utcheckning** alternativ. När alternativet är aktiverat visas **Redigera** bara efter utcheckning av en ämnesfil.

**Nyckelupplösning**

- Om du vill använda en nyckelutrymmesfil för ämnet klickar du på ikonen för nyckelupplösningen. Du kan sedan välja ett nyckelområde i popup-fönstret Tangentupplösning.

**Källa**

- Öppna XML-källkoden för en fil. Du kan visa den underliggande XML-koden för en karta, ett ämne eller en DITAVAL-fil genom att öppna filen i förhandsgranskningsläget och klicka på källikonen. I popup-fönstret XML-källa visas XML-källkoden. Du kan välja en viss kod från filen eller trycka på `Ctrl`+`a` om du vill markera hela innehållet.

   >[!NOTE]
   >
   > Om du vill visa källkodsvyn för en DITA-mappningsfil markerar du filen i resursgränssnittet och klickar på Källa.

   ![](images/xml-source-code-view-from-preview_cs.png){width="800" align="left"}

**Dela UUID-länk**

- Med AEM Guides kan du dela UUID-baserade länkar för DITA-kartor, ämnen och bildfiler från följande platser:

   - Resurser, användargränssnitt
   - DITA-kartans konsol
   - Ämne eller bildens förhandsvisning

Ett nytt alternativ **Dela UUID-länk** visas i verktygsfältet för de ovannämnda områdena. På följande skärmbild visas **Dela UUID-länk** i förhandsgranskningsläget för ett ämne:

![](images/share-uuid-link_cs.png){width="800" align="left"}

I resursgränssnittet är det här alternativet synligt när du markerar en fil. I förhandsgranskningsläget är det här alternativet tillgängligt som standard i huvudverktygsfältet. I en DITA-kartkonsol är det här alternativet synligt i avsnittet Utdataförinställningar.

När du har kopierat URL-adressen kan samma sak delas med andra användare så att de får direkt åtkomst till filen. Den här länken förblir giltig även när filen flyttas till en annan plats i databasen. Den enda gången länken misslyckas är när filen tas bort från databasen.

Om du delar länken från DITA-kartkonsolen eller en fils förhandsgranskningsläge, kommer användaren till samma filvy. När du delar en mappningsfils länk från resursgränssnittet, flyttas användaren till kartans konsol. På samma sätt visas filens förhandsgranskning för ett ämne eller en bildfil.

>[!IMPORTANT]
>
> Länken kan inte användas som en referenslänk i andra ämnen, den ger bara direkt åtkomst till filen i databasen. Länken är också giltig så länge som filen är tillgänglig i databasen. Även om filen flyttas till en annan plats i databasen är länken fortfarande giltig. Länken misslyckas bara när filen tas bort från databasen.

**Checka ut/Checka in**

- Växlar mellan funktionerna Checka ut och Checka in. När en fil är utcheckad får den aktuella användaren exklusiv skrivbehörighet för filen. En utcheckad fil kan öppnas i Web Editor för redigering. När du har gjort ändringarna klickar du på ikonen Checka in för att spara filen i DAM.

När du checkar ut ett ämne visas filens status som utcheckad i kortvyn och i listvyn.

Utcheckad fil i kortvyn:

![](images/checkout-card-62.png){width="300" align="left"}

Utcheckad fil i listvyn:

![](images/checkout-list-62.png){width="550" align="left"}

Om kolumnen Utcheckad inte visas väljer du **Visa inställningar** under **Listvy** och väljer **Utcheckad** i **Konfigurera kolumner** -dialogrutan.

![](images/list-view-settings-check-out_cs.png){width="800" align="left"}

>[!TIP]
>
> Mer information om hur du arbetar med utcheckning och incheckning av filer finns i avsnittet Version av innehåll i guiden Bästa metoder.

**Webbaserad versionsskillnad**

- Om ditt ämne har ändrats kan du enkelt ta reda på ändringarna som gjorts i olika versioner av det ämnet. Så här tar du reda på ändringar i olika versioner av ett ämne:

   >[!IMPORTANT]
   >
   > Den metod som beskrivs i följande procedur gäller endast DITA-filer. För icke-DITA-filer använder du tidslinjevyn för att skapa versioner eller återställa en befintlig version av en fil.

   1. Öppna ämnet i förhandsgranskningsläget.

   1. Klicka på **Versionshistorik** och välja en version.

      ![](images/timeline-versions62_cs.png){width="800" align="left"}

   1. Välj den som du vill använda som grundversion i listan och klicka på **Förhandsgranska version**. Förhandsgranskningen av den valda versionen visas i fönstret Förhandsgranska version.

   1. Från **Visa differens** väljer du den version som du vill jämföra basversionen med.

      ![](images/show-diff-list-cropped.png){width="800" align="left"}

      Det ändrade innehållet markeras i ämnesförhandsvisningen. Innehåll som är markerat med grönt innebär att det nya innehållet och det nya röda innehållet är det borttagna innehållet.

      ![](images/version-difference.png){width="800" align="left"}


### Förgrena, återställ och efterföljande versionshantering {#id193PG0Y051X}

- I en vanlig redigeringsmiljö måste du skapa en ny gren av ett ämne för att kunna hantera en viss version. På samma sätt som med andra versionshanteringssystem kan du med hjälp av AEM Guides skapa en gren från en befintlig version av ett ämne eller återgå till en äldre version av ett ämne. Med versionshanteringsfunktionerna i AEM kan du utföra följande åtgärder:

   - Skapa en gren från en befintlig version av ett ämne
   - Skapa efterföljande versioner i en ny gren
   - Återgå till en specifik version av ett ämne

   Följande bild visar det typiska förgrenade och efterföljande versionshanteringssystemet:

   ![](images/branching_illustration.png){width="550" align="center"}

   För alla nya ämnen numreras den första versionen som 1.0. Därefter sparas alla nya versioner av ämnet med ett stegvis nummer som 1.1, 1.2 osv. När du har skapat en gren av ett ämne skapas en ny gren med versionsnumret som grenen har skapats från och med vilken en .0 läggs till i slutet av versionen. Som framgår av teckningen skapas en ny gren från version 1.1 av ett ämne. Den nya grenen får versionsnumret 1.1.0. Varje gång du sparar en ny version av ämnet i den här grenen får den sedan ett inkrementellt versionsnummer som 1.1.1, 1.1.2 och så vidare.

   På samma sätt som vid förgreningar kan du även återställa din nuvarande version eller version till en version som finns i databasen. Om du vill återgå till en version väljer du bara önskad version av ämnet och klickar på **Återställ till den här versionen** i **Versionshistorik** -panelen.

   Så här skapar du en gren, återgår till en version och underhåller efterföljande versioner av ett ämne:

   >[!IMPORTANT]
   >
   > Den metod som beskrivs i följande procedur gäller endast DITA-filer. För icke-DITA-filer använder du tidslinjevyn för att skapa versioner eller återställa en befintlig version av en fil.

   1. Gå till ämnet i Assets UI.

      >[!NOTE]
      >
      > Du kan också öppna ämnet i förhandsgranskningsläget och fortsätta med steg 3.

   1. Välj det ämne som du vill skapa en gren för.

   1. Klicka på **Versionshistorik**.

      >[!NOTE]
      >
      > En lista över tillgängliga versioner för det valda ämnet visas. Varje version innehåller tidsstämpel, användarnamn, versionskommentar och [label](web-editor-use-label.md#) information.

   1. Välj en version från vilken du vill skapa en gren. På följande skärmbild väljs version 1.2 för att skapa en gren.

      ![](images/branching.png){width="300" align="left"}

      >[!NOTE]
      >
      > Den aktuella versionen av ett ämne innehåller *\(Aktuell\)* anges bredvid versionsnumret.

   1. Klicka **Återställ till den här versionen**.

      Ett meddelande visas med en uppmaning om att bekräfta skapandet av en ny gren.

   1. *\(Valfritt\)* I meddelandet får du ett alternativ för att välja **Spara aktuell arbetskopia som ny version**. Följande två åtgärder är möjliga baserat på valet av det här alternativet:

      - Om du väljer det här alternativet skapas en gren från version 1.1. Och en ny version av ämnet skapas också från den aktuella arbetskopian av ämnet och sparas som nästa version - 1.4.

         ![](images/next_version_created_over_working_copy.png){width="300" align="left"}

         Version 1.2 blir din nuvarande arbetskopia av ämnet. Alla versioner som har sparats efter att detta har skapats under den nya grenen i 1.1. Den efterföljande versionen av ett nytt ämne i den här grenen sparas till exempel som 1.2.0.

         ![](images/new_version_in_branch.png){width="300" align="left"}

      - Om du inte väljer det här alternativet skapas ingen ny version från den aktuella arbetskopian av ämnet. En ny gren skapas från version 1.2 av ämnet. Alla efterföljande versioner av ämnet sparas under 1.2-grenen som 1.2.0, 1.2.1 och så vidare.

         ![](images/new_version_without_working_copy.png){width="300" align="left"}
   1. Klicka **OK**.
   En ny gren skapas från den valda versionen av ämnet. Processen ovan gäller även för återställning till en specifik version av ett ämne. Att återgå till en viss version innebär tekniskt sett att du skapar en ny gren från den valda versionen och gör den versionen till aktuell arbetskopia av ämnet. Du kan också visa historiken för filer som har återförts i rapporten Återgå till tidigare version. Mer information om den här rapporten finns i [Rapport över versionshistorik för återskapade filer](reports-reverted-file-version-history.md#).

**Överordnat ämne:**[ Skapa och förhandsgranska ämnen](create-preview-topics.md)
