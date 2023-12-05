---
title: Konfigurera autosparande av filer i Web Editor
description: Lär dig hur du konfigurerar autosparande av filer i Web Editor
source-git-commit: 880cd344ceb65ea339be699ebcad41c0d62e168a
workflow-type: tm+mt
source-wordcount: '197'
ht-degree: 0%

---

# Konfigurera autosparande av filer i Web Editor {#id199CC0J0M5Z}

En av de vanligaste funktionerna i den webbläsarbaserade redigeraren är möjligheten att spara data efter en viss tidsperiod. AEM Web Editor har också stöd för att automatiskt spara ämne- och mappfiler med angivet tidsintervall. När den här funktionen aktiveras sparas arbetskopian av ämnet eller kartan. Ingen ny version av ämnet eller kartan skapas. Om du vill skapa en ny version måste du klicka på ikonen Spara ändring i webbredigerarens verktygsfält.

Funktionen för att spara automatiskt är inte aktiverad som standard och du måste aktivera den från configMgr. Gör så här för att aktivera funktionen för att spara automatiskt i Web Editor:

1. Öppna konfigurationssidan för Adobe Experience Manager Web Console.

   Standardwebbadressen för åtkomst till konfigurationssidan är:

   ```http
   http://<server name>:<port>/system/console/configMgr
   ```

1. Sök efter och klicka på **com.adobe.fmdita.xmleditor.config.XmlEditorConfig** paket.

1. I *XmlEditorConfig* inställningar väljer du **Spara automatiskt** alternativ.

1. I **Intervall för automatiskt sparande** anger du tidsintervallet i sekunder för att aktivera funktionen för autosparande.

1. Klicka **Spara**.


**Överordnat ämne:**[ Anpassa Web Editor](conf-web-editor.md)
