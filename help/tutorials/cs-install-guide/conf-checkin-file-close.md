---
title: Konfigurera en uppmaning om att checka in en fil vid stängning
description: Lär dig hur du konfigurerar uppmaningen att checka in en fil vid stängning
source-git-commit: 4f15166b1b250578f07e223b0260aacf402224be
workflow-type: tm+mt
source-wordcount: '174'
ht-degree: 0%

---


# Konfigurera en uppmaning om att checka in en fil vid stängning {#id222HC040PE8}

När användaren försöker stänga en fil som är öppnad i Web Editor med **Stäng** på filens flik eller **Stäng** på Alternativ-menyn visas en dialogruta om filen innehåller data som inte har sparats eller en version som inte har sparats. Användaren uppmanas att låsa upp filen om den är låst.

Använd instruktionerna i [Konfigurationsåsidosättningar](download-install-additional-config-override.md#) för att skapa konfigurationsfilen. Ange följande \(egenskap\)-information i konfigurationsfilen för att konfigurera en uppmaning att checka in en fil vid stängning:

| PID | Egenskapsnyckel | Egenskapsvärde |
|---|------------|--------------|
| `com.adobe.fmdita.xmleditor.config.XmlEditorConfig` | `xmleditor.checkin` | Boolean \( true/ false\).<br> **Standardvärde**: false |

När den här konfigurationen är aktiverad visas **Lås upp filen** är markerad som standard i dialogrutan.

Mer information finns i *Stäng filer och spara scenarier* i den as a Cloud Service guiden Använda Adobe Experience Manager Guides.

**Överordnat ämne:**[ Anpassa Web Editor](conf-web-editor.md)

