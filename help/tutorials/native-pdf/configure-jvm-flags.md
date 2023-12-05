---
title: PDF | Konfigurera JVM-flaggor för Native PDF Publishing
description: Konfigurera JVM-flaggor för Native PDF Publishing
source-git-commit: 880cd344ceb65ea339be699ebcad41c0d62e168a
workflow-type: tm+mt
source-wordcount: '125'
ht-degree: 0%

---

# Konfigurera JVM-flaggor för Native PDF Publishing

Inbyggd PDF-publicering startar en separat JVM-process för att generera en PDF. Du kan behöva justera konfigurationerna för denna JVM för att stödja olika scenarier. Om du till exempel vill köra större arbetsbelastningar bör du öka den maximala stackstorleken som är tillgänglig för den skapade JVM-processen.

Utför följande steg för att konfigurera AEM Guides Native PDF Publishing JVM-flaggor:

1. Öppna konfigurationssidan för Adobe Experience Manager Web Console.

   Standardwebbadressen för åtkomst till konfigurationssidan är:

   ```http
   http://<server name>:<port>/system/console/configMgr
   ```

1. Sök efter och välj *com.adobe.fmdita.config.ConfigManager* paket.

1. Uppdatera egenskapen **Java-kommandoradsalternativ för inbyggd PDF-fil** (*native.pdf.java.opts*) för att skicka alla vanliga JVM-flaggor.



1. Klicka **Spara**.
