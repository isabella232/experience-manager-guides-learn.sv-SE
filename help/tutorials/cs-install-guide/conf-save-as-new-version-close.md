---
title: Konfigurera uppmaningen att spara som en ny version vid stängning
description: Lär dig hur du konfigurerar uppmaningen att spara som en ny version vid stängning
source-git-commit: 4f15166b1b250578f07e223b0260aacf402224be
workflow-type: tm+mt
source-wordcount: '186'
ht-degree: 0%

---


# Konfigurera uppmaningen att spara som en ny version vid stängning {#id222HBI00XXA}

När användaren försöker stänga en fil som är öppnad i Web Editor med **Stäng** på filens flik eller **Stäng** på Alternativ-menyn visas en dialogruta om filen innehåller data som inte har sparats eller en version som inte har sparats. Användaren uppmanas att spara filen som en ny version om versionen inte sparas.

Använd instruktionerna i [Konfigurationsåsidosättningar](download-install-additional-config-override.md#) för att skapa konfigurationsfilen. Ange följande \(egenskap\)-information i konfigurationsfilen för att konfigurera en uppmaning att spara som en ny version vid stängning:

| PID | Egenskapsnyckel | Egenskapsvärde |
|---|------------|--------------|
| `com.adobe.fmdita.xmleditor.config.XmlEditorConfig` | `xmleditor.savenewversion` | Boolean \( true/ false\). <br>  **Standardvärde**: true |

När den här konfigurationen är aktiverad visas **Spara som ny version** är markerad som standard i dialogrutan.

Mer information finns i *Stäng filer och spara scenarier* i den as a Cloud Service guiden Använda Adobe Experience Manager Guides.

**Överordnat ämne:**[ Anpassa Web Editor](conf-web-editor.md)

