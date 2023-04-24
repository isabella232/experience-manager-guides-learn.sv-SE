---
title: Skapa förinställningar från Web Editor
description: Lär dig hur du skapar förinställningar för utdata från Web Editor
source-git-commit: 7cd719921e68ac1763d09d9665d912e3697e5849
workflow-type: tm+mt
source-wordcount: '359'
ht-degree: 0%

---


# Skapa förinställningar från Web Editor {#id218CL400JW3}

Följ de här stegen för att skapa förinställningar för DITA-kartan:

1. Navigera i resursgränssnittet till den kartfil som du vill redigera.

1. Om du vill låsa kartfilen exklusivt markerar du kartfilen och klickar på **Checka ut**.

1. Välj **Redigera ämnen** på kartfilens åtgärdsmeny.

   Kartfilen öppnas för redigering i Web Editor.

   >[!NOTE]
   >
   > Du kan lägga till eller ta bort alla ämnen från kartan med hjälp av den avancerade kartredigeraren. Mer information finns i [Arbeta med den avancerade kartredigeraren](map-editor-advanced-map-editor.md#).

1. I **Utdata** väljer du ikonen + för att skapa en förinställning för DITA-kartan.

   ![](images/output-tab-preset_cs.png)

1. Ange namnet på förinställningen i dialogrutan Lägg till förinställning och klicka sedan på **Lägg till**.

1. Ange följande konfigurationsinformation.

   1. Välj önskade alternativ i dialogrutan **Allmänt** -fliken. Du kan välja att skapa en förinställning för utdata med eller utan villkor. Du kan också använda en DITVAL-fil. Med AEM kan du även välja en baslinje för publicering av en specifik version av DITA-kartan.
   1. Ange AEM platsinformation i dialogrutan **AEM** -fliken. **Plats** I visas en lista med de AEM Sites som finns i din AEM. **Kategori**, **Avsnittsmall** och **Artikelmall** är de strukturella komponenter som används för att ordna utdatafilens utseende och känsla. Dessa är fördefinierade i AEM platsmall.

      >[!NOTE]
      >
      > Uppdatera varje listruta för att få ytterligare klassificering i nästa listruta.

   1. Från **Artiklar** väljer du de ämnen som du vill generera utdata för.
1. Välj **Generera förinställning** längst upp för att generera utdata.

   ![](images/add-preset-articles-tab_cs.png)

1. Du ser status för genereringsprocessen för utdata. The **Ämnen** -kolumnen listar de ämnen som utdata genereras för när **Status** -kolumnen visar publiceringsstatusen för varje ämne.

   Om du vill visa utdata för du muspekaren över avsnittet och klickar på Visa utdata.

   ![](images/add-preset-output-generated_cs.png)


>[!NOTE]
>
> Du kan också redigera, byta namn på, duplicera eller ta bort en befintlig förinställning på Alternativ-menyn.

![](images/edit-preset_cs.png)

**Överordnat ämne:**[ Artikelbaserad publicering från webbredigeraren](web-editor-article-publishing.md)

