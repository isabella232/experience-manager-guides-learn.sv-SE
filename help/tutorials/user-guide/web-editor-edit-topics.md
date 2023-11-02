---
title: Redigera ämnen i Web Editor
description: Lär dig redigera ämnen i webbredigeraren. Lär dig olika redigeringsfunktioner för att ändra ämnesfilerna i AEM.
exl-id: 8da37a81-e8c3-434f-b3f4-4723d87c2ade
source-git-commit: 22d364d28859e6aa3ae147a72b736669f56788b3
workflow-type: tm+mt
source-wordcount: '572'
ht-degree: 0%

---

# Redigera ämnen i Web Editor {#id2056B040VUI}

Webbredigeraren innehåller en rad redigeringsfunktioner som du kan använda för att enkelt skapa och ändra ämnesfiler. Dessutom utför du följande steg för att redigera ett ämne i Web Editor.

>[!IMPORTANT]
>
> Om du råkar ut för ett programfel när du arbetar i Web Editor uppdaterar du sidan för att fortsätta arbeta.

1. Om du vill göra ändringar i ditt ämne klickar du inom textgränsen för det önskade elementet och börjar redigera.

1. Om du vill infoga ett visst element klickar du i slutet av det element efter vilket du vill infoga det nya elementet och klickar på motsvarande elementikon i verktygsfältet. Du kan också använda kortkommandot `Alt+Enter` för att anropa **Infoga element** popup.

   En lista över element som kan användas i ämnet visas. AEM Guides gör en smart placering av element utifrån deras giltiga plats i ämnet.

   >[!NOTE]
   >
   > Du kan också välja vilken ikon som ska visas i verktygsfältet genom att konfigurera `ui_config.json` filen finns på - `/etc/designs/fmdita/clientlibs/xmleditor/`. Kontakta systemadministratören om du vill ha mer information om hur du anpassar funktioner.

1. När du har redigerat dokumentet klickar du **Spara**.

   >[!NOTE]
   >
   > Om du inte vill spara ändringarna i AEM databas klickar du på **Stäng** och klicka sedan på **Stäng utan att spara** i dialogrutan Osparade ändringar.

   **Uppdatera webbläsaren när filerna redigeras**
Guiderna i Experience Manager har stöd för att uppdatera webbläsaren medan du redigerar innehåll i Web Editor. Med den här funktionen kan du fortsätta redigera innehåll om ett programfel skulle uppstå när du arbetar. Om du trycker på Uppdatera i webbläsaren medan en eller flera filer med osparade ändringar öppnas för redigering, får du ett varningsmeddelande om att de osparade ändringarna kan gå förlorade. Du får ett alternativ för att avbryta uppdateringsåtgärden och spara filerna för att bevara ändringarna.

   Även när du uppdaterar webbläsaren behålls vyerna till vänster och till höger i webbredigeraren. Stödlinjerna i Experience Manager återställer det senast sparade läget för de filer som öppnats i webbredigeraren när du uppdaterar webbläsaren. De filer som öppnas i databaspanelen öppnas till exempel igen. Kartpanelen behålls tillsammans med den tidigare öppnade kartan.

   Det aktiva ämnet eller DITA-kartan öppnas på nytt i området för innehållsredigering.

   Den högra panelen öppnas också igen och visar samma vy som före uppdateringen.

   **Arbetskopia**
AEM innehåller en indikator för arbetskopiering som visar om den aktuella \(arbetskopia\) av filen är synkroniserad med den sparade versionen eller inte. Om du har gjort ändringar i den aktuella kopian och inte har sparat filen, visas ett \*-märke tillsammans med titeln på ämnesfliken. Den här indikatorn fungerar som en påminnelse om att spara ändringarna och försvinner när du sparar filen.

   ![](images/working-copy-text-update-indicator.png){width="550" align="left"}

   AEM visar också om den senast sparade kopian av filen är synkroniserad med den sparade versionen eller inte. Om du har gjort ändringar som inte har sparats mellan arbetskopian och den senast sparade versionen visas en \*-markering tillsammans med versionsinformationen som visas i det övre högra hörnet på avsnittets filflik. Den här indikatorn fungerar som en påminnelse om att spara och skapa en version av din aktuella \(arbetskopia\) av filen.

   ![](images/version-update-indicator.png){width="550" align="left"}


**Överordnat ämne:**[ Arbeta med webbredigeraren](web-editor.md)
