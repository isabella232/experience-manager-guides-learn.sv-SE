---
title: Skapa en gruppaktiveringskarta
description: Lär dig hur du skapar en gruppaktiveringskarta i AEM.
exl-id: 7d17fb37-9486-4a3b-a421-08e279c95b6c
source-git-commit: 8504a0a52d381044bf1f0d6e7de3585ebecf3a7b
workflow-type: tm+mt
source-wordcount: '486'
ht-degree: 0%

---

# Skapa en gruppaktiveringskarta {#id214GG0E90EV}

Så här skapar du en gruppaktiveringskarta:

1. Välj **Stödlinjer** i listan över verktyg.

1. Klicka på länken Adobe Experience Manager överst och välj **verktyg**.

1. Klicka på **Publish Dashboard** platta.

   För första gången visas en tom samlingssida. Om du har skapat gruppaktiveringssamlingar tidigare visas de på den här sidan.

1. Klicka **Skapa**.

1. Ange en titel för din gruppaktiveringskarta och klicka på **Skapa**.

   Ett meddelande om att åtgärden lyckades visas när en kartsamling för gruppaktivering skapades.

1. Klicka **Öppna** i meddelandet Slutfört.

1. Klicka **Redigera** och sedan klicka **Lägg till kartor**.

1. Leta reda på och lägg till de DITA-kartor som du vill lägga till i den gruppaktiveringskarta.

   Som standard läggs alla förinställningar och språkinställningar som är kopplade till kartan till automatiskt.

1. Välj önskade utdata genom att aktivera eller inaktivera skjutknappen.

   Du kan välja flera förinställningar för olika språk.

1. Klicka **Klar**.

   DITA-kartfilerna läggs till i din gruppaktiveringskarta.

   ![](images/bulk-activation-collection-created.png){width="800" align="left"}


Fliken Kartor och förinställningar innehåller information i följande kolumner:

- **Karta**: Visar DITA-kartfilens namn.
- **Kartsökväg**: Visar den fullständiga sökvägen till DITA-mappningsfilen.

- **UUID**: Visar den unika identifierare som är associerad med filen.

- **Språk**: Visar språkkoden för DITA-kartan.
- **Förinställning**: Visar titeln på förinställningen som konfigurerats på kartfilen. Ikonen visas också baserat på vilken typ av förinställning som används.

  >[!NOTE]
  >
  > Den lilla ![](images/global-preset-icon.svg) anger en förinställning på mappprofilnivå.
- **Ändrad**: Anger om DITA-kartan uppdateras efter den senaste publikationen. Baserat på den här informationen kan du bestämma om du vill aktivera utdata för den här DITA-kartan eller inte.
- **Genererad**: Visar datum och tid för den senaste genererade utdata.
- **Publicerad**: Visar datum och tid för det senaste publicerade \(eller aktiverade\) resultatet. Om du klickar på länken visas sidan Aktiveringsresultat med information om rotsökvägen där innehållet aktiveras.


Följande filteralternativ är tillgängliga på den vänstra panelen:

- **Ändrad**: Välj Ja eller Nej. Om du väljer ja visas bara de ändrade DITA-kartorna. En ändrad karta är en karta som har genererats sedan den publicerades senast.
- **Förinställning**: Välj en förinställning som du vill filtrera ut kartfilerna för. Om du till exempel väljer *AEM* förinställning visas bara de kartor som har *AEM* förinställning för utdata konfigurerad för dem.
- **Språk**: Du kan välja någon av de tillgängliga språkkoderna och endast visa det valda språket på fliken Kartor och förinställningar.

- **Filter:** I den senaste rälen visas följande filter:
- **Kartor och förinställningar** tabell: Tabellen Kartor och förinställningar innehåller följande kolumner:

**Överordnat ämne:**[ Massaktivering av publicerat innehåll](conf-bulk-activation.md)
