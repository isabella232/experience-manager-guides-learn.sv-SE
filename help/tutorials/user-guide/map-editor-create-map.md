---
title: Skapa en karta
description: Lär dig hur du skapar en karta
source-git-commit: 66915827a0b169069cc482763f0f50b9e9b6aa64
workflow-type: tm+mt
source-wordcount: '452'
ht-degree: 0%

---


# Skapa en karta {#id176FEN0D05Z}

AEM Guides innehåller två färdiga mallar för kartor - DITA-karta och Bookmap. Du kan också skapa egna mappningsmallar och dela dem med författarna för att skapa mappningsfiler.

Så här skapar du en kartfil:

1. I resursgränssnittet navigerar du till den plats där du vill skapa kartfilen.

1. Klicka **Skapa** \> **DITA-karta**.

1. På sidan Design väljer du den typ av kartmallar som du vill använda och klickar på **Nästa**.

   >[!NOTE]
   >
   > Hur ämnen hänvisas till i en kartfil beror på kartmallen. Om du till exempel väljer mallen Karta refererar ämnet till \(`topicref`\) används för att referera till ämnen. Om det är en bokmapp skapas ämnesreferenser med `chapter` i DITA.

   ![](images/map-template.png)

1. Ange kartan på sidan Egenskaper **Titel**.

1. \(Valfritt\) Ange filen **Namn**.

   Om administratören har konfigurerat det automatiska filnamnet baserat på UUID-inställningen visas inte alternativet att ange filnamnet. Ett UUID-baserat filnamn tilldelas automatiskt till filen.

   Om alternativet för filnamngivning är tillgängligt föreslår vi automatiskt ett namn baserat på kartans titel. Om du vill ange kartfilens namn manuellt kontrollerar du att filnamnet inte innehåller blanksteg, apostrof eller klammerparenteser och slutar med `.ditamap`.

1. Klicka **Skapa**.

   Meddelandet Kartan har skapats visas.

   Alla nya mappningsfiler som du skapar från resursgränssnittet **Skapa** \> **DITA-karta** eller webbredigeraren tilldelas ett unikt mappnings-ID. Dessutom sparas den nya kartan som den senaste arbetskopian i DAM. Om du inte sparar en revision av en nyligen skapad karta visas inget versionsnummer i Tidigare versioner. Om du öppnar kartan för redigering visas versionsinformationen i det övre högra hörnet på mappningsfilens flik:

   ![](images/first-version-map-none.png)

   Versionsinformationen för en nyligen skapad karta visas som *ingen*. När du sparar en ny version tilldelas den ett versionsnummer som 1.0. Mer information om hur du sparar en ny version finns i [Spara som ny version](web-editor-features.md#save-as-new-version-id209ME400GXA).

   Du kan välja att öppna kartan för redigering i den konfigurerade kartredigeraren eller spara kartefilen i AEM.

   >[!NOTE]
   >
   > Om du vill använda den avancerade kartredigeraren öppnar du kartfilen i webbredigeraren. Om administratören har konfigurerat den avancerade kartredigeraren som standardredigerare i kartfilerna öppnas kartfilen direkt i den avancerade kartredigeraren för redigering. Se *Ange avancerad kartredigerare som standard* i Installera och konfigurera Adobe Experience Manager Guides as a Cloud Service.


**Överordnat ämne:**[ Arbeta med kartredigeraren](map-editor.md)

