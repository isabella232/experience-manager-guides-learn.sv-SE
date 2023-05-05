---
title: Hantera publiceringsuppgifter med Publish Dashboard
description: Lär dig hur du hanterar publiceringsuppgifter med hjälp av Publish Dashboard
exl-id: 5ede608d-f905-44b7-9147-ab678ad68ee7
source-git-commit: c74badebbcb4733fb9caa79c646b1d1e5c8bfe8e
workflow-type: tm+mt
source-wordcount: '513'
ht-degree: 0%

---

# Hantera publiceringsuppgifter med Publish Dashboard {#id205CC08305Z}

När du har ett stort antal publiceringsuppgifter som körs på datorn blir det praktiskt taget omöjligt att kontrollera varje DITA-karta individuellt för att övervaka dess publiceringsuppgift. AEM Guides ger administratörer och utgivare en enhetlig vy över alla publiceringsuppgifter som körs i systemet. En lista över alla aktiva publiceringsåtgärder finns på Publish Dashboard.

På Publish Dashboard finns en fullständig översikt över alla publiceringsåtgärder som för närvarande körs i systemet.

![](images/publish-dashboard.png){width="800" align="left"}

Kontrollpanelen för publicering innehåller följande information:

- **Karttitel** - Titeln på en kartfil som publiceras eller finns i publiceringskön.

- **Filnamn** - Filnamnet på DITA-kartan.

- **Förinställning för utdata** - Namnet på den förinställning som används för att generera utdata.

- **Initierad av** - Användarnamn för den användare som initierade publiceringsaktiviteten.

- **Startades den** - Datum och tid då publiceringsaktiviteten startades.

- **Förfluten tid** - Tid sedan publiceringsaktiviteten körs i systemet.

- **Ikonen Ta bort** - Avbryt eller avsluta en publiceringsaktivitet.

Den vänstra panelen på kontrollpanelen Publicera innehåller följande filtreringsalternativ:

- **Förinställning för utdata** - Välj en eller flera förinställningar som du vill visa de aktuella publiceringsåtgärderna för. På följande skärmbild filtreras publiceringsaktiviteterna så att de endast visar de uppgifter som använder AEM webbplatsens utdataförinställning:

   ![](images/publish-dashboard-preset-filter.png){width="800" align="left"}

- **Initierad av** - Välj ett användarnamn i listan för att visa de publiceringsåtgärder som har initierats av den valda användaren.

- **Karta** - Välj en kartfil i listan för att visa de publiceringsåtgärder som körs för den valda kartan.

## Öppna Publish Dashboard {#id205CC100DY4}

Utför följande steg för att komma åt Publish Dashboard:

>[!NOTE]
>
> Endast en administratör eller en utgivare har åtkomst till Publish Dashboard.

1. Klicka på länken Adobe Experience Manager överst och välj **verktyg**.

1. Välj **Stödlinjer** i listan över verktyg.

1. Klicka på **Publish Dashboard** platta.

   Publish Dashboard öppnas med en lista över alla aktiva publiceringsåtgärder i systemet.

   Om du klickar på länken Filnamn visas DITA-kartkonsolen för den valda kartan.

   ![](images/publish-dashboard-click-filename-link.png){width="800" align="left"}


>[!NOTE]
>
> Du kan även öppna Publish Dashboard från fliken Outputs när du genererar utdata från kartkontrollpanelen. Mer information finns i [Visa status för utdatagenereringsaktiviteten](generate-output-for-a-dita-map.md#viewing_output_history).

## Avbryta en publiceringsaktivitet

Utför följande steg för att avbryta en utdatagenereringsåtgärd från Publish Dashboard:

1. [Öppna Publish Dashboard](#id205CC100DY4).

1. I listan med aktiva publiceringsuppgifter klickar du på ikonen Ta bort för en uppgift som du vill avbryta.

   ![](images/publish-dashboard-cancel-task.png){width="800" align="left"}

1. Klicka **Ja** i meddelandet Bekräfta annullering.

   Kommandot Avbryt accepteras och ett försök att avbryta görs så länge som aktiviteten är aktiv. När aktiviteten har avslutats tas den bort från den aktiva uppgiftslistan. Aktivitetens status uppdateras även i DITA-kartkonsolen som Avbruten. På följande skärmbild visas *HTML5* aktiviteten avbryts från Publish Dashboard och dess status ändras även i DITA-kartkonsolen.

   ![](images/cancelled-output-task.png){width="800" align="left"}


**Överordnat ämne:**[ Generering av utdata](generate-output.md)
