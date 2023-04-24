---
title: Starta Web Editor
description: Lär dig hur du startar Web Editor
source-git-commit: cc0fbca257d82cc82db5b5da8d263309fd71de55
workflow-type: tm+mt
source-wordcount: '501'
ht-degree: 0%

---


# Starta Web Editor {#id2056B0140HS}

Du kan starta Web Editor från följande platser:

- [AEM](#id2056BG00RZJ)
- [AEM Assets UI](#id2056BG0307U)
- [DITA map console](#id2056BG090BF)

I följande avsnitt beskrivs hur du kommer åt och startar webbredigeraren från olika platser.

## AEM {#id2056BG00RZJ}

När du loggar in AEM visas navigeringssidan:

![](images/web-editor-from-navigation-page_cs.png){width="800" align="left"}

Klicka på **XML Editor** går direkt till webbredigeraren.

![](images/web-editor-launch-page.png){width="800" align="left"}

När du har startat webbredigeraren utan att välja någon fil visas en tom webbredigeringsskärm. Du kan öppna en fil för redigering AEM databasen eller din favoritsamling.

## AEM Assets UI {#id2056BG0307U}

En annan plats där du kan starta Web Editor är från AEM Assets-gränssnittet. Du kan markera ett eller flera ämnen och öppna dem direkt i Web Editor. Så här öppnar du ett ämne i Web Editor:

1. Navigera i resursgränssnittet till det ämne som du vill redigera.

   >[!NOTE]
   >
   > Du kan också se Ämnets UUID.

   .

   ![](images/assets_ui_with_uuid_cs.png){width="800" align="left"}

   >[!IMPORTANT]
   >
   > Kontrollera att du har läs- och skrivbehörighet för mappen som innehåller det ämne som du vill redigera.

1. Om du vill låsa ämnet exklusivt markerar du ämnet och klickar på **Checka ut**.

   >[!IMPORTANT]
   >
   > Om administratören har konfigurerat **Inaktivera redigering utan utcheckning** måste du checka ut filen innan du redigerar. Om du inte checkar ut filen kan du inte se redigeringsalternativet.

1. Stäng resursurvalsläget och klicka på det ämne som du vill redigera.

   Ämnets förhandsgranskning visas.

   Du kan öppna Web Editor från listvyn, kortvyn och förhandsgranskningsläget.

   >[!IMPORTANT]
   >
   > Om du vill öppna flera ämnen för redigering väljer du önskade ämnen i resursgränssnittet och klickar på Redigera. Kontrollera att webbläsaren inte har aktiverat popup-blockering, annars öppnas bara det första avsnittet i den markerade listan för redigering.

   ![](images/edit-from-preview_cs.png){width="800" align="left"}

   Om du inte vill förhandsgranska ett ämne och vill öppna det direkt i Web Editor klickar du på ikonen Redigera på snabbmenyn i kortvyn:

   ![](images/edit-topic-from-quick-action_cs.png){width="800" align="left"}

1. Klicka **Redigera** om du vill öppna ämnet i webbredigeraren.

   ![](images/edit-mode.png){width="800" align="left"}


## DITA map console {#id2056BG090BF}

Så här öppnar du Web Editor från DITA-kartkonsolen:

1. Navigera till och klicka på DITA-mappningsfilen som innehåller det ämne som du vill redigera i resursgränssnittet.

   DITA-kartkonsolen visas.

1. Klicka **Ämnen**.

   En lista med ämnen i kartfilen visas. UUID för ämnen visas under ämnesrubriken.

1. Markera ämnesfilen som du vill redigera.

1. Klicka **Redigera ämne**.

   ![](images/edit-topics-map-console_cs.png){width="800" align="left"}

1. Ämnet öppnas i webbredigeraren.

   >[!IMPORTANT]
   >
   > Om administratören har konfigurerat **Inaktivera redigering utan utcheckning** måste du checka ut filen innan du redigerar. Om du inte checkar ut filen öppnas dokumentet i skrivskyddat läge i redigeraren.


**Överordnat ämne:**[ Arbeta med webbredigeraren](web-editor.md)

