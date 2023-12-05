---
title: Konfigurera visning av UUID-baserade länkar
description: Lär dig hur du konfigurerar visning av UUID-baserade länkar
source-git-commit: 880cd344ceb65ea339be699ebcad41c0d62e168a
workflow-type: tm+mt
source-wordcount: '209'
ht-degree: 0%

---

# Konfigurera visning av UUID-baserade länkar {#id2035G20M0QN}

Som standard skapas länken med UUID för det refererade innehållet när du skapar en länk med alternativet Infoga referens eller Infoga återanvänd innehåll i webbredigeraren. The **Länk** egenskapen \(i egenskapspanelen\) för det refererade innehållet kan konfigureras så att den relativa filsökvägen för det refererade innehållet eller UUID:t visas. Den här visningen styrs av **Aktivera UUID** i configMgr. Som standard är den PÅ, vilket betyder att UUID för det refererade innehållet visas på egenskapspanelen.

Utför följande steg för att visa den relativa sökvägen eller UUID för det refererade innehållet i Web Editor:

1. Öppna konfigurationssidan för Adobe Experience Manager Web Console.

   Standardwebbadressen för åtkomst till konfigurationssidan är:

   ```http
   http://<server name>:<port>/system/console/configMgr
   ```

1. Sök efter och klicka på **com.adobe.fmdita.xmleditor.config.XmlEditorConfig** paket.

1. I *XmlEditorConfig* inställningar, **Aktivera UUID** är aktiverat som standard. Det innebär att UUID för det refererade innehållet visas i **Länk** i egenskapspanelen.

   Om du vill visa den relativa sökvägen för det länkade innehållet avmarkerar du **Aktivera UUID** alternativ.

1. Klicka **Spara**.


**Överordnat ämne:**[ Anpassa Web Editor](conf-web-editor.md)
