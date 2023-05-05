---
title: Rapport över versionshistorik för återskapade filer
description: Lär dig hur du rapporterar versionshistorik för återskapade filer
exl-id: fa90b373-742a-4102-b00f-07e4113fef98
source-git-commit: c74badebbcb4733fb9caa79c646b1d1e5c8bfe8e
workflow-type: tm+mt
source-wordcount: '451'
ht-degree: 0%

---

# Rapport över versionshistorik för återskapade filer {#id205BBC00PRK}

När du arbetar med flera samtidiga utgåvor tillsammans med flera författare måste innehållet ha flera versioner. Det kan finnas viss gemensam information i flera versioner, som olika författare kan använda i sitt projekt. För att hantera sådana arbetsuppgifter kan författarna få flera versioner av filerna. Sådana versioner kan helt enkelt vara en nyare version av en fil eller en återställning till en tidigare version. Det är en komplex uppgift att identifiera när en fil har återställts och varför.

Med AEM Guides kan du generera en versionshistorik för en enskild fil eller för alla filer i en mapp. Den här versionshistoriken ger dig en sammanslagen vy över alla versioner av en fil som har återförts och vem som har skapat dessa versioner, samt orsaken till att versionerna har skapats.

Du kommer åt den här rapporten från följande platser:

- **Resurser, användargränssnitt**: genom att markera en fil och öppna **Versionshistorik** från den vänstra listen. The **Versionshistorik** vyn innehåller **Återställ versionsloggar** längst ned på panelen. När du klickar på den här länken visas den markerade filens historik för de återskapade versionerna.

   ![](images/revert-log-from-assets-ui.png){width="300" align="left"}

- **Förhandsgranskning av ämne**: när du förhandsgranskar ett ämne kan du även visa **Versionshistorik** från den vänstra listen. Du får en panel som liknar resursgränssnittet där du kan klicka på **Återställ versionsloggar** om du vill komma åt det aktiva dokumentets återskapade versionshistorik.

- **AEM**: du kan även komma åt den här rapporten från AEM. I proceduren nedan beskrivs hur du får åtkomst till historiken för återställningsversioner i AEM Verktyg.


Utför följande steg för att komma åt rapporten Återgå historik:

1. Klicka på länken Adobe Experience Manager överst och välj **verktyg**.

1. Välj **Stödlinjer** i listan över verktyg.

1. Klicka på **Historik för versionsåterställning** platta.

   En tom sida för att återställa versionshistorik visas där du behöver bläddra till och välja en fil eller mapp för att generera rapporten.

1. Klicka **Visa loggar** för att generera rapporten för den valda filen eller mappen.

   ![](images/revert-version-history-report.png){width="800" align="left"}

   Rapporten innehåller följande information:

   - **Filnamn**: Ämnets namn. Om du klickar på ämneslänken öppnas ämnesförhandsgranskningen.

   - **Tidsstämpel**: Datum och tid då ämnet återgick till en tidigare version.

   - **Användare**: Namnet på den användare som återgick till en tidigare version.

   - **Återställ från**: Det ursprungliga versionsnumret för filen som filen återskapades från.

   - **Återställ till**: Versionen som filen återgick till.

   - **Kommentar**: Alla kommentarer som ges av den användare som har återställt filen.


**Överordnat ämne:**[ Rapporter](reports-intro.md)
