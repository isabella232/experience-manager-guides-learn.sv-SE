---
title: Konfigurera visning av UUID-baserade länkar
description: Lär dig hur du konfigurerar visning av UUID-baserade länkar
source-git-commit: 4f15166b1b250578f07e223b0260aacf402224be
workflow-type: tm+mt
source-wordcount: '160'
ht-degree: 0%

---


# Konfigurera visning av UUID-baserade länkar {#id2035G20M0QN}

Som standard skapas länken med UUID för det refererade innehållet när du skapar en länk med alternativet Infoga referens eller Infoga återanvänd innehåll i webbredigeraren. The **Länk** egenskapen \(i egenskapspanelen\) för det refererade innehållet kan konfigureras så att den relativa filsökvägen för det refererade innehållet eller UUID:t visas. Som standard visas UUID för det refererade innehållet på egenskapspanelen.

Använd instruktionerna i [Konfigurationsåsidosättningar](download-install-additional-config-override.md#) för att skapa konfigurationsfilen. Ange följande \(egenskap\)-information i konfigurationsfilen för att visa den relativa sökvägen eller UUID för det refererade innehållet i Web Editor:

| PID | Egenskapsnyckel | Egenskapsvärde |
|---|------------|--------------|
| `com.adobe.fmdita.xmleditor.config.XmlEditorConfig` | `xmleditor.uuid` | Boolean \(true/false\). Om du vill visa den relativa sökvägen för det länkade innehållet anger du egenskapen till false. <br> **Standardvärde**: true |

**Överordnat ämne:**[ Anpassa Web Editor](conf-web-editor.md)

