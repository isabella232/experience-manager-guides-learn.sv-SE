---
title: Konfigurera generering av PDF för ett enskilt ämne
description: Lär dig hur du konfigurerar generering av enskilda ämnen i PDF
source-git-commit: 880cd344ceb65ea339be699ebcad41c0d62e168a
workflow-type: tm+mt
source-wordcount: '268'
ht-degree: 0%

---

# Konfigurera generering av PDF för ett enskilt ämne {#id22ADC70M0XA}

Med AEM stödlinjer kan du generera PDF för enskilda ämnen eller en hel kartfil. Du kan publicera ämnen i PDF-format med den inbyggda PDF- eller DITA-OT-metoden. Använd inbyggd PDF-metod för att generera funktionsrika utdata för PDF baserat på W3C CSS3 och CSS-sidindelad mediestandard. Du kan använda metoden DITA-OT för att generera utdata från PDF för en karta från kontrollpanelen för kartan.

>[!NOTE]
>
> Inbyggd PDF är standardmetoden för att skapa en PDF i den aktuella versionen av AEM stödlinjer.

Så här aktiverar du den gamla PDF-genereringen via DITA-OT i läget för ämnesförhandsgranskning:

1. Logga in på Adobe Experience Manager som administratör och hämta UI-konfigurationsfilen.

1. Klicka på länken Adobe Experience Manager överst och välj **verktyg**.
1. Välj **Stödlinjer** i listan med verktyg och klicka på **Mappprofiler**.
1. Klicka på **Global profil** platta.
1. Välj **Konfiguration av XML-redigerare** och klicka **Redigera** ikonen längst upp
1. Klicka på **Ladda ned** om du vill hämta filen ui\_config.json på ditt lokala system. Du kan sedan göra ändringar i filen och sedan överföra samma fil.
1. I `ui_config.json` -fil, hitta följande konfiguration:

   ```
   {
                           "component": "button",
                           "variant": "action",
                           "quiet": true,
                           "icon": "filePDF",
                           "title": "Download as PDF",
                           "on-click": "EDITOR_SAVE_AS_PDF"
                           }
   ```

   och ersätta den med

   ```
   {
                           "component": "button",
                           "icon": "filePDF",
                           "variant": "action",
                           "quiet": true, "title": "Export as PDF",
                           "on-click": "DOWNLOAD_TOPIC_PDF",
                           "show" : ["@isPreviewMode", "@isXmlMode"]
                           }
   ```

1. Spara filen och överför den.

När du har utfört stegen ovan och väljer samma mappprofil i Användarinställningar i Web Editor visas alternativet för generering av PDF i ett ämnes förhandsgranskningsläge.

**Överordnat ämne:**[ Anpassa Web Editor](conf-web-editor.md)
