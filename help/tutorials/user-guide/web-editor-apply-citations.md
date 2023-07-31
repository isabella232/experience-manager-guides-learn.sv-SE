---
title: Lägga till och hantera citat i ditt innehåll
description: Lär dig hur du implementerar referenser genom att lägga till och tillämpa citat i ditt innehåll.
source-git-commit: 85eb0228908134080f3f1e2644f3f7c37b8d7497
workflow-type: tm+mt
source-wordcount: '1863'
ht-degree: 0%

---


# Lägga till och hantera citat i ditt innehåll

Citat är referenser till den informationskälla som har lagts till i innehållet. Med citat kan du kreditera författarna till källinformationen och hjälpa läsarna att följa upp källinformationen. Genom att lägga till citat blir innehållet mer tillförlitligt och det förhindrar plagiarism. De gör det även möjligt att visa genomtänkt innehåll.

I AEM kan du lägga till och importera citat och använda dem i ditt innehåll. Du kan lägga till dessa citat från alla typer av böcker, webbplatser och journaler.


AEM hjälper dig att redigera, förhandsgranska och sortera dina citat. När du har lagt till dina citat i innehållet kan du generera utdata med PDF. Du kan också lägga till litteraturförtecknings- eller referenssidan i utdata från PDF.

AEM Guides har stöd för många olika typer av citationer, som Modern Language Association (MLA), American Psychological Association (APA), Chicago, Institute for Electrical and Electronics Engineers (IEEE) och American Heart Association (AHA). Rekommendationen är att använda dem tydligt och konsekvent.


>[!NOTE]
>
>För närvarande har AEM endast stöd för inbyggda PDF för citat.


## Lägg till citat

Så här lägger du till citat:

1. Välj **Citat** ![citat, ikon](images/citations-icon.svg) i den vänstra panelen.
The **Citat** panelen öppnas.

   ![](images/citation-panel.png){width="300" align="left"}

1. I **Citat** panel, markera ![Ikonen Lägg till](images/Add_icon.svg). I listrutan kan du välja att lägga till en ny källhänvisning eller att importera en källhänvisning.

1. Välj **Ny källhänvisning** för att lägga till en ny källhänvisning.
The **Lägg till källhänvisning** öppnas.

   ![citationspanelen i webbredigeraren](images/citation-add.png) {width="300" align="left"}


1. Fylla i fälten i **Lägg till källhänvisning** -dialogrutan.

   >[!NOTE]
   >
   >Du kan också lägga till ISBN- eller DOI- eller PubMed-ID:t. AEM stödlinjer fyller i de andra fälten automatiskt.

   | Bok | Webbplats | Journal |
   | --- | ---|---|
   | **Källa** <br> I listrutan väljer du källtexten till citatet som en bok. | **Källa**<br> I listrutan väljer du källtexten till citatet som en webbplats. | **Källa** <br> I listrutan väljer du källan till citatet som Journal. |
   | **Sök efter** <br> Välj **ISBN** eller **DOI** från listrutan för att söka efter det elektroniska ID som är länkat till citatet.  <br> DOI: ID för digitalt objekt <br> ISBN: Unik identifierare för numerisk bok | **Sök efter** <br> Välj **DOI** från listrutan för att söka efter det elektroniska ID som är länkat till citatet. | **Sök efter** <br> Välj **DOI** eller PubMed ID i listrutan för att söka efter det elektroniska ID som är länkat till citatet. <br>  <br> |
   | **Upphovsman** <br> Lägg till för- och efternamnet på författaren till citatet. Välj ![](images/Add_icon.svg) om du vill lägga till fler namn. | **Upphovsman** <br> Lägg till för- och efternamnet på författaren till citatet. Välj ![](images/Add_icon.svg)  om du vill lägga till fler namn. | **Upphovsman** <br> Lägg till för- och efternamnet på författaren till citatet. Välj ![](images/Add_icon.svg)om du vill lägga till fler namn. |
   | **Titel** <br> Lägg till bokens titel. | **Titel** <br> Lägg till webbsidans titel. | **Titel** <br> Lägg till artikelns titel. |
   | **Redigerare** <br> Lägg till bokens redigerare. | **Webbplatsnamn** <br> Lägg till webbplatsens namn. | **Journaltitel** <br> Lägg till titeln på det arbete som artikeln finns i. |
   | **Edition** <br> Lägg till utgåvan av boken. | **URL** <br> Lägg till webblänken för webbplatsen för att bläddra bland innehållet. | **År** <br> Lägg till det år då artikeln publiceras. |
   | **Ort** <br> Lägg till publikationens ort. | **Åtkomstdatum**<br> Lägg till det datum då webbplatsens innehåll öppnas. | **Volym** <br> Lägg till arbetsvolymen i serien. |
   | **Utgivare** <br> Lägg till namnet på utgivaren av boken. | **Publiceringsdatum** <br> Lägg till det datum då webbplatsens innehåll publiceras. | **Nummer** <br> Lägg till numret på volymen i serien. |
   | **År** <br> Lägg till det år då boken publiceras. | **Uppdateringsdatum** <br> Lägg till det datum då webbplatsens innehåll uppdateras. | **Sidor** <br> Lägg till det sidnummer eller sidintervall där artikeln finns. |
   | **Version** <br> Lägg till bokens version. | **Unikt ID** <br> Lägg till ett unikt ID för citatet. Ett unikt ID är en unik identifierare för den referensen. | **URL** <br>Lägg till webblänken i journalen. |
   | **Serier** <br>Lägg till bokens serie. |  | **Unikt ID** <br> Lägg till ett unikt ID för citatet.Ett unikt ID är en unik identifierare för den referensen. |
   | **URL**  <br>  Lägg till webblänken i boken. |
   | **Unikt ID** <br> Lägg till ett unikt ID för citatet. Ett unikt ID är en unik identifierare för den referensen. |





1. Välj **Klar**.

   En ny källhänvisning läggs till i citatteckenpanelen.

>[!NOTE]
>
> Det är obligatoriskt att lägga till ett unikt ID för fältet för källhänvisning.  Du kan inte ändra det unika ID:t när citatet har lagts till.

## Importera citat

Så här importerar du citat:

1. I den vänstra panelen väljer du **Citat** ![citat, ikon](images/citations-icon.svg).

   The **Citat** panelen öppnas.

1. I **Citat** panel, markera ![Ikonen Lägg till](images/Add_icon.svg)och sedan markera **Importera** i listrutan.
1. Bläddra i en bib-fil från datorn och importera den.

   >[!TIP]
   >
   > Ett .bib-filnamnstillägg är en BibTeX Bibliografisk databasfil. Det är en särskilt formaterad textfil som listar referenser om en viss informationskälla.

   När filen har importerats kan du visa referenserna på citationspanelen.

   >[!NOTE]
   > <ol><li> AEM Guides importerar endast de citat som är unika och inte redan finns.
    &gt; <li> AEM Guides kan importera citat från en bok, journal eller en webbplats. För närvarande stöder den inte citat från andra källor.

## Hantera citat

Citaten sorteras i bokstavsordning i den vänstra panelen. Sök efter citationerna utifrån de källor som ska användas i ditt ämne.

### Filter

Välj **Filter** ![](images/filter-search-icon.svg) -ikonen bredvid sökfältet och välj källalternativen i listrutan för att filtrera listan med citattecken. Det tillåter både en och flera markeringar.

* **Alla källor**: Den visar en fullständig lista med citat, inklusive alla källor.

* **Bok**: Den visar en lista med citat från böcker.

* **Webbplats**: Den visar en lista med citat från webbplatser.

* **Journal**: Den visar en lista med citat som hämtats från journaler.

### Sökning

Sök i källtexten efter ditt innehåll.

1. Välj Citat i den vänstra panelen.
The **Citat** panelen öppnas.

1. Använd sökfältet för att söka efter lämpliga citat från en lång lista.

### Ändra format för citattecken {#change-citation-style}

Systemadministratören kan ändra formatet för citat från **Citat**  listrutan i **Allmänna inställningar** i **Inställningar för Redigeraren**.
Dessa format styr hur citat visas i förhandsgranskningsfönstret eller i utdata från PDF.

Följande alternativ är tillgängliga i listrutan:

| MLA | APA | Chicago | IEEE | AHA |
|---|---|---|---|---|
| Modernt språkassociationsformat <br> | American Psychological Association Style | Chicago Manual of Style | Institute for Electrical and Electronics Engineers Style | American Heart Association Style |
| Exempel:<br> Crawford, Claire, et al. *Emotionellt innehåll i mörka minnen* Redigerad av Memory, 16, 2010, Amsterdam. | Exempel: <br> Crawford, C., J. och C. (2010) *Emotionellt innehåll i mörka minnen* (505-16 ed.). 10.1080/ 09658210902067289 | Exempel: <br> Crawford, Claire, et al. *Emotionellt innehåll i mörka minnen*. 505-16, 2010. | Exempel: <br> C. Crawford, J. och C. , *Emotionellt innehåll i mörka minnen*. Amsterdam 2010. | Exempel: <br> C. Crawford, J. och C. , *Emotionellt innehåll i mörka minnen*. Amsterdam 2010. |


## Redigera en källhänvisning

Så här redigerar du citatet:

1. Håll pekaren över namnet på citatet från listan. Välj  ![](images/options.svg) den **Alternativ** -ikon.

1. Välj  **Redigera**.

The **Redigera källhänvisning** öppnas.

1. Gör de ändringar som krävs. Välj **Klar**.
Den markerade citattecknet redigeras.

>[!NOTE]
>
>Du kan inte ändra det unika ID:t när citatet har lagts till.

## Förhandsgranska ett citat

Så här förhandsgranskar du en källhänvisning:

Håll pekaren över namnet på citatet från listan. Välj     ![](images/options.svg) **Alternativ** -ikon.

1. Välj **Förhandsgranska**.
Du kan förhandsgranska innehållet i och formatet för citatet i förhandsgranskningsfönstret.

   >[!NOTE]
   >
   >Förhandsgranskningen baseras på den typ av källhänvisning som administratören har valt i dialogrutan **Inställningar för Redigeraren**.

1. Klicka var som helst på skärmen för att stänga förhandsvisningsrutan.

   ![](images/citation-preview.png){width="550" align="left"}

>[!NOTE]
>
> Du kan också förhandsgranska en hänvisning som infogats i ett ämne från resursgränssnittet eller fliken Förhandsgranska i Web Editor.

## Infoga citat

Följ de här stegen för att infoga citat i ett ämne:
1. Markera ämnet på databaspanelen och dubbelklicka sedan på det för att öppna det i redigeringsfönstret.
1. Placera markören på den plats i ämnet där du vill lägga till citatet.



Du kan infoga citat från huvudverktygsfältet eller den vänstra panelen i avsnittet.

### Från huvudverktygsfältet

1. Välj **Citat** ![citat, ikon ](images/citations-icon.svg) i verktygslisten.
1. I **Citat** väljer du citat. Du kan också markera flera citat.
   ![citatdialogruta](images/citation-dialog-main-toolbar.png){width="300" align="left"}
1. Du kan filtrera citat genom att skriva de första alfabeten på sökpanelen i **Citat** -dialogrutan.

1. Klicka **Klar**.
Den markerade texten läggs till vid markörens plats i ditt ämne.


### Från den vänstra panelen

>[!NOTE]
> 
>Så här visar du **Citat** -ikonen från den vänstra panelen måste systemadministratören välja **Citat** i **Panel** tabba in **Inställningar för Redigeraren**.

1. Välj **Citat** ![citat, ikon ](images/citations-icon.svg) i den vänstra panelen.
1. Dra citatet från **Citat** och släppa den på lämplig plats i ämnet.

   Du kan också välja **Infoga** från  ![](images/options.svg) **Alternativ** för att infoga en citat.

   ![infoga citat](images/citation-panel-insert.png)
1. Om du vill markera flera citat högerklickar du på en citat i ämnet och väljer **Ändra citat** på kortkommandomenyn.
1. Markera de citat du vill infoga i dialogrutan **Citat** -dialogrutan.
1. Välj **Klar** för att lägga till dem i ämnet.

När du har infogat citat i ämnet kan du förhandsgranska dem i webbredigeraren. Du kan också publicera innehåll med citat med hjälp av PDF.



## Ta bort en källhänvisning

Du kan ta bort citat från panelen Citat eller från ett ämne där du har infogat.

### Ta bort en källhänvisning från panelen Citat

Så här tar du bort en källhänvisning från panelen Citat:

1. Håll pekaren över namnet på citatet från listan.
1. Välj ![](images/options.svg) **Alternativ** -ikon.
1. Välj   **Ta bort** ![](images/Delete_icon.svg).
Bekräftelsedialogrutan öppnas.
1. Välj **Ja**.
Den markerade källtexten tas bort från citationspanelen.



### Ta bort en källhänvisning från ett ämne

Så här tar du bort en hänvisning som redan används i ämnet:

Placera markören i slutet av citattecknet.

1. Högerklicka på en hänvisning i ämnet och välj **Ändra citat** på kortkommandomenyn. Dialogrutan Citation öppnas.
   ![snabbmeny för en hänvisning](./images/modify-citation.png)

1. Du kan välja de citat du vill infoga i dokumentet.

   >[!NOTE]
   >
   >De citat som redan används i ämnet ersätts med de citat som du väljer i dialogrutan.


1. Välj **Klar**.

## Generera utdata av innehåll med citationer

När du har infogat citat i avsnittet kan du publicera innehåll med citat med hjälp av PDF.

I utdata för PDF visas citaten i det innehåll där du infogat dem. Du kan också skapa en litteraturförteckningssida. När du klickar på ett citat omdirigeras du till litteraturförteckningssidan.

Skapa en **Citat** sidlayout i mallarna för PDF och inkludera den i dokumentet. Alla citat som används i boken listas på en sida som visas i utdata från PDF. Mer information om hur du skapar en sidlayout finns i [Skapa en sidlayout](../native-pdf/components-pdf-template.md#create-page-layout).


Visa om du vill ändra vy och känsla för citatteckningssidan [Anpassa PDF-mallar](../native-pdf/pdf-template.md).



### Använda innehållsformat på en källhänvisning

Formatera källtexten när den läggs till i avsnittet.

1. Välj **Formatmallar** i **Mallar** panelen för en förinställning för inbyggda PDF.   Den öppnar **STILAR** som innehåller alla formateringsalternativ.

1. Sök efter `<cite>`.

Om du vill veta mer om format kan du visa [Arbeta med vanliga innehållsformat](../native-pdf/stylesheet.md).