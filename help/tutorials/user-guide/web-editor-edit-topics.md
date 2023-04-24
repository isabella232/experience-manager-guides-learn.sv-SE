---
title: Redigera ämnen i Web Editor
description: Lär dig hur du redigerar ämnen i Web Editor
source-git-commit: cc0fbca257d82cc82db5b5da8d263309fd71de55
workflow-type: tm+mt
source-wordcount: '538'
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

1. När du är klar med redigeringen av dokumentet klickar du på **Spara**.

   >[!NOTE]
   >
   > Om du inte vill spara ändringarna i AEM databas klickar du på **Stäng** och klicka sedan på **Stäng utan att spara** i dialogrutan Osparade ändringar.

   **Uppdatera webbläsaren när filerna redigeras**
AEM har stöd för att uppdatera webbläsaren medan du redigerar innehållet i webbredigeraren. Med den här funktionen kan du fortsätta redigera innehåll om ett programfel uppstår under arbetet. Om du trycker på Uppdatera i webbläsaren medan en eller flera filer med osparade ändringar öppnas för redigering, får du ett varningsmeddelande om att de osparade ändringarna kan gå förlorade. Du får ett alternativ för att avbryta uppdateringsåtgärden och spara filerna för att bevara ändringarna.

   Även när du uppdaterar webbläsaren behålls vyerna till vänster och till höger i webbredigeraren. Det aktiva ämnet på databaspanelen öppnas till exempel igen. Kartpanelen behålls tillsammans med den tidigare öppnade kartan.

   Det aktiva ämnet eller DITA-kartan öppnas på nytt i området för innehållsredigering.

   Den högra panelen öppnas också igen och visar samma vy som före uppdateringen.

   **Indikator för arbetskopia**
AEM innehåller en indikator för arbetskopiering som visar om den aktuella \(arbetskopia\) av filen är synkroniserad med den sparade versionen eller inte. Om du har gjort ändringar i den aktuella kopian och inte har sparat filen, visas ett \*-märke tillsammans med titeln på ämnesfliken. Den här indikatorn fungerar som en påminnelse om att spara ändringarna och försvinner när du sparar filen.

   ![](images/working-copy-text-update-indicator.png){width="550" align="left"}

   AEM visar också om den senast sparade kopian av filen är synkroniserad med den sparade versionen eller inte. Om du har gjort ändringar som inte har sparats mellan arbetskopian och den senast sparade versionen visas en \*-markering tillsammans med versionsinformationen som visas i det övre högra hörnet på avsnittets filflik. Den här indikatorn fungerar som en påminnelse om att spara och skapa en version av din aktuella \(arbetskopia\) av filen.

   ![](images/version-update-indicator.png){width="550" align="left"}


**Överordnat ämne:**[ Arbeta med webbredigeraren](web-editor.md)

