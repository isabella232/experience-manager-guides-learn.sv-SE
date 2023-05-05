---
title: Skicka metadata till utdata med DITA-OT
description: Lär dig hur du skickar metadata till utdata med DITA-OT
exl-id: 637895e5-aece-4827-a32e-f2ae3e3704ef
source-git-commit: c74badebbcb4733fb9caa79c646b1d1e5c8bfe8e
workflow-type: tm+mt
source-wordcount: '306'
ht-degree: 0%

---

# Skicka metadata till utdata med DITA-OT {#id21BJ00QD0XA}

Metadata är ytterligare information om utdata. I AEM kan du skicka vidare befintliga metadata eller skapa anpassade metadatataggar. Du kan skicka metadata till AEM, PDF, HTML 5, EPUB och anpassade format via DITA-OT-publicering.

Utför följande steg för att skicka metadata till utdata med DITA-OT-publicering:

1. I **Resurser, användargränssnitt** navigera till och klicka på den DITA-kartfil för vilken du vill skicka metadata till DITA-OT.
1. Markera och redigera en förinställning som du vill skicka metadatafälten till. Välj t.ex. förinställningen PDF.
1. Välj **DITA-OT** under Generera &lt;output> Använda alternativet i den valda förinställningen för utdata.

   ![](images/custom-meta-data-output-preset.png){width="800" align="left"}

1. I listrutan Egenskaper väljer du de metadata som du vill skicka till DITA-OT-publicering.

   I listrutan Egenskaper visas både de anpassade egenskaperna och standardegenskaperna. I skärmbilden ovan är författaren till exempel den anpassade egenskapen while `dc:description`, `dc:language`, `dc:title`och `docstate` är standardegenskaperna.

   >[!NOTE]
   >
   > Dessa egenskaper hämtas från filen metadataList som finns på följande plats:`/libs/fmdita/config/metadataList`. Som standard visas fyra egenskaper i den här filen: `dc:description`, `dc:language`, `dc:title`och `docstate`.

   Filen kan överlappas av: `/apps/fmdita/config/metadataList`.

   Information om hur du skickar en anpassad egenskap som du redan har definierat värdena för finns i [Använd AEM metadata i DITA-OT PDF-utdata](https://experienceleaguecommunities.adobe.com/t5/xml-documentation-discussions/use-aem-metadata-in-dita-ot-pdf-output/td-p/411880).

1. Från **Egenskaper** väljer du önskade anpassade egenskaper och standardegenskaper. Välj till exempel `author`, `dc:title`och `dc:description`. Dessa är standard `metadata/properties` som skapas när vi skapar en fil. De valda egenskaperna visas under listrutan.

   ![](images/selected-metadata-properties.png){width="300" align="left"}

1. Klicka **Klar** längst upp till vänster för att spara ändringarna.
1. Generera utdata.

De valda metadataegenskaperna skickas till utdata som genereras med DITA-OT.

**Överordnat ämne:**[ Generering av utdata](generate-output.md)
