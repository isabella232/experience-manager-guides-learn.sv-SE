---
title: Installera paket för artikelbaserad publicering
description: Lär dig hur du installerar paket för artikelbaserad publicering
source-git-commit: 6051181e243cf71919901093c1b5590f21832545
workflow-type: tm+mt
source-wordcount: '360'
ht-degree: 0%

---


# Installera paket för artikelbaserad publicering {#id21BNL02052Z}

AEM Guides är en kraftfull artikelbaserad publiceringsfunktion som är integrerad med Web Editor. Med den här funktionen kan du publicera ett eller flera ämnen samtidigt. När du har öppnat en karta i kartredigeraren kan du navigera till fliken Utdata för att skapa en förinställning och sedan välja ett eller flera avsnitt för att generera utdata. Du kan använda den artikelbaserade publiceringsfunktionen för att stegvis generera utdata för ett eller flera ämnen eller publicera innehållet på en kunskapsbasplattform på ett artikel-för-artikel-sätt. Mer information finns i *Artikelbaserad publicering från Web Editor* i användarhandboken.

Så här skapar du en AEM webbplats för publicering av artikelbaserade utdata:

1. Hämta **XML Documentation Components Content Package for Cloud Service** från [Adobe Software Distribution Portal](https://experience.adobe.com/#/downloads/content/software-distribution/en/general.html).
1. Öppna AEM Package Manager. Standardwebbadressen för att få åtkomst till pakethanteraren är: `https://<hostname>/crx/packmgr/index.jsp`
1. Ladda upp XML Documentation Components Content Package för Cloud Service och installera det sedan.
1. Ladda ned `Knowledge-base-template-for-article-based-publishing-for-cloud-service.zip` från [Adobe Software Distribution Portal](https://experience.adobe.com/#/downloads/content/software-distribution/en/general.html).
1. Välj **Webbplatser**.
1. Klicka på i webbplatsgränssnittet **Skapa** i det övre högra hörnet.
1. Välj **Plats från mall** från **Skapa** listruta.
1. Klicka på **Importera** och sedan `Knowledge-base-template-for-article-based-publishing-for-cloud-service.zip` laddas ned till datorn. När platsmallen har importerats visas den längst ned.

   >[!NOTE]
   >
   > Du behöver bara importera ZIP-filen för första gången. När du har importerat webbplatsmallen är den tillgänglig i listan.

   Välj **Kunskapsbasmall för artikelbaserad publicering** för att skapa AEM och klicka på **Nästa** i det övre högra hörnet.

1. Ange **Platsrubrik** och **Platsnamn** och klicka **Skapa** i det övre högra hörnet. En AEM skapas med hjälp av en Tragopan-webbplatsmall. \(Tragopan site är ett exempel på en kunskapsbas AEM webbplats med mallar för en kategori, avsnitt och artikelsidor.\)

   >[!NOTE]
   >
   > Du kan skapa flera AEM med samma mall.


Du kan använda AEM webbplats för att publicera artikeln med hjälp av förinställningarna från Web Editor.

**Överordnat ämne:**[ Anpassa Web Editor](conf-web-editor.md)

