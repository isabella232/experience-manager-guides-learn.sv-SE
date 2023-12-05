---
title: Konfigurera autosparande av filer i Web Editor
description: Lär dig hur du konfigurerar autosparande av filer i Web Editor
source-git-commit: 880cd344ceb65ea339be699ebcad41c0d62e168a
workflow-type: tm+mt
source-wordcount: '182'
ht-degree: 0%

---

# Konfigurera autosparande av filer i Web Editor {#id199CC0J0M5Z}

En av de vanligaste funktionerna i den webbläsarbaserade redigeraren är möjligheten att spara data efter en viss tidsperiod. Webbredigeraren AEM stödlinjer har även stöd för att automatiskt spara ämne- och mappfiler med angivet tidsintervall. När den här funktionen aktiveras sparas arbetskopian av ämnet eller kartan. Ingen ny version av ämnet eller kartan skapas. Om du vill skapa en ny version måste du klicka på ikonen Spara ändring i webbredigerarens verktygsfält.

Funktionen för att spara automatiskt är inte aktiverad som standard och du måste aktivera den med konfigurationsfilen.

Använd instruktionerna i [Konfigurationsåsidosättningar](download-install-additional-config-override.md#) för att skapa konfigurationsfilen. Ange följande \(egenskap\)-information i konfigurationsfilen för att konfigurera tidsintervallet för autosparande och autosparande av filer:

| PID | Egenskapsnyckel | Egenskapsvärde |
|---|------------|--------------|
| `com.adobe.fmdita.xmleditor.config.XmlEditorConfig` | `xmleditor.autosave` | Boolean \(true/false\).<br> **Standardvärde**: false |
| `xmleditor.autosaveinterval` | Ange tidsintervallet i sekunder för att aktivera funktionen för autosparande. |

**Överordnat ämne:**[ Anpassa Web Editor](conf-web-editor.md)
