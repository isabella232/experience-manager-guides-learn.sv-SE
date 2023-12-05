---
title: Hämta och installera AEM för första gången
description: Lär dig hur du hämtar och installerar AEM för första gången
source-git-commit: 880cd344ceb65ea339be699ebcad41c0d62e168a
workflow-type: tm+mt
source-wordcount: '232'
ht-degree: 0%

---

# Hämta och installera AEM för första gången {#id213BCL00KEV}

Så här hämtar och installerar du AEM Guides för första gången på en dator:

>[!IMPORTANT]
>
> Om du vill använda Livefyre tillsammans med AEM Guides måste du installera Livefyre-versionerna tidigare än 3.0 innan du installerar AEM Guides. Om du använder Livefyre version 3.0 eller senare finns det ingen sådan begränsning.

1. Ladda ned AEM från Adobe Software Distribution Portal.

1. Logga in i AEM och navigera till CRX Package Manager. Standardwebbadressen för att få åtkomst till pakethanteraren är:

   ```http
   http://<server name>:<port>/crx/packmgr/index.jsp
   ```

   Pakethanteraren hanterar paketen i din lokala AEM. Mer information om hur du arbetar med Pakethanteraren finns i [Så här arbetar du med paket](https://helpx.adobe.com/experience-manager/6-5/sites/administering/using/package-manager.html) i AEM.

   ![](assets/package-manager.png){width="650" align="left"}

1. Om du vill överföra AEM stödlinjer klickar du på **Överför paket**.

1. I dialogrutan Överför paket går du till filen AEM stödlinjer som du laddade ned i steg 1 och klickar på **OK**.

   Paketet överförs till din AEM.

1. Klicka på **Installera**.

   ![](assets/install-package.png){width="650" align="left"}

1. I dialogrutan Installera paket klickar du på **Installera**.

1. Klicka på knappen Hem för att komma igång med AEM stödlinjer ![](assets/home-button.png) i det övre vänstra hörnet av CRX Package Manager.


>[!NOTE]
>
> Utför installationsproceduren på alla instanser av AEM servrar i installationen.

**Överordnat ämne:**[ Hämta och installera](download-install.md)
