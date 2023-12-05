---
title: Avinstallera AEM
description: Lär dig hur du avinstallerar AEM
source-git-commit: 880cd344ceb65ea339be699ebcad41c0d62e168a
workflow-type: tm+mt
source-wordcount: '148'
ht-degree: 0%

---

# Avinstallera AEM {#id21BHG0C0SXA}

Du kan avinstallera AEM guider med hjälp av CRX Package Manager. Under avinstallationen återställs innehållet i databasen till ögonblicksbilden som gjordes omedelbart innan paketet installerades.

Så här avinstallerar du AEM stödlinjer:

1. Logga in i AEM och navigera till CRX Package Manager. Standardwebbadressen för att få åtkomst till pakethanteraren är:

   ```http
   http://<server name>:<port>/crx/packmgr/index.jsp
   ```

1. Sök efter paketet com.adobe.fmdita.
1. Klicka på paketet för att expandera det.
1. Klicka **Mer** för att öppna listrutan.
1. Klicka **Avinstallera** och vänta tills avinstallationen är klar.
1. Om du inte längre behöver det här paketet klickar du på **Ta bort** efter avinstallation av paketet.

## Efter avinstallation

Så här rensar du de återstående filerna efter avinstallationen:

1. Rensa skriptcachen med:

   ```http
   http://<host>:<port>/system/console/scriptcache
   ```

1. Du kan göra cacheminnet ogiltigt med:

   ```http
   http://<host>:<port>/libs/granite/ui/content/dumplibs.rebuild.html?back=true
   ```

1. Klicka **Ogiltig cache**.
1. Rensa webbläsarens cache.

**Överordnat ämne:**[ Hämta och installera](download-install.md)
