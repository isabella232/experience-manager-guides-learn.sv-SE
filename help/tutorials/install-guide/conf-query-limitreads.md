---
title: Konfigurera antalet LimitReads för en fråga
description: Lär dig hur du konfigurerar antalet LimitReads för en fråga
source-git-commit: 880cd344ceb65ea339be699ebcad41c0d62e168a
workflow-type: tm+mt
source-wordcount: '99'
ht-degree: 0%

---

# Konfigurera antalet LimitReads för en fråga {#id231RC0HL0ID}

Utför följande steg om du vill öka antalet noder som en fråga kan läsa samtidigt:

1. Öppna Adobe Experience Manager Web Console JMX-sidan.

   Standardwebbadressen för åtkomst till konfigurationssidan är:

   ```http
   http://<server name>:<port>/system/console/jmx
   ```

1. Sök efter och klicka på **QueryEngineSettings**.

1. Ändra attributvärde för **LimitReads** -attribut.

1. Klicka **Spara**.


När du ökar det här attributvärdet hjälper det dig att generera rapporten för större DITA-kartor.

**Överordnat ämne:**[ Anpassa Web Editor](conf-web-editor.md)
