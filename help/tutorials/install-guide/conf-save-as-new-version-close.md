---
title: Konfigurera uppmaningen att spara som en ny version vid stängning
description: Lär dig hur du konfigurerar uppmaningen att spara som en ny version vid stängning
source-git-commit: 880cd344ceb65ea339be699ebcad41c0d62e168a
workflow-type: tm+mt
source-wordcount: '214'
ht-degree: 0%

---

# Konfigurera uppmaningen att spara som en ny version vid stängning {#id222HBI00XXA}

När användaren försöker stänga en fil som är öppnad i Web Editor med **Stäng** på fliken eller **Stäng** på Alternativ-menyn visas en dialogruta om filen innehåller osparade data eller en osparad version. Användaren uppmanas att spara filen som en ny version om versionen inte sparas.

The **Spara som ny version** kryssrutan är inte aktiverad som standard och du måste aktivera den från configMgr. Följ de här stegen för att aktivera alternativet som standard i Web Editor:

1. Öppna konfigurationssidan för Adobe Experience Manager Web Console.

   Standardwebbadressen för åtkomst till konfigurationssidan är:

   ```http
   http://<server name>:<port>/system/console/configMgr
   ```

1. Sök efter och klicka på **com.adobe.fmdita.xmleditor.config.XmlEditorConfig** paket.

1. Välj **Fråga efter ny version vid stängning** alternativ.

1. Klicka **Spara**.


När det här alternativet är markerat visas **Spara som ny version** är markerad som standard i dialogrutan.

Mer information finns i *Stäng filer och spara scenarier* i den as a Cloud Service guiden Använda Adobe Experience Manager Guides.

**Överordnat ämne:**[ Anpassa Web Editor](conf-web-editor.md)
