---
title: Versionsinformation | Nyheter i Adobe Experience Manager Guides, juli 2023
description: Läs om de nya och förbättrade funktionerna i juli 2023-versionen av Adobe Experience Manager Guides as a Cloud Service
source-git-commit: 880cd344ceb65ea339be699ebcad41c0d62e168a
workflow-type: tm+mt
source-wordcount: '691'
ht-degree: 0%

---

# Nyheter i juli 2023-versionen av Adobe Experience Manager Guides as a Cloud Service

I den här artikeln beskrivs de nya och förbättrade funktionerna i version från juli 2023 av Adobe Experience Manager-handboken (senare kallad *AEM stödlinjer as a Cloud Service*).

Mer information om uppgraderingsinstruktioner, kompatibilitetsmatris och problemen som åtgärdas i den här versionen finns i [Versionsinformation](release-notes-2023.7.0.md).

## Ansluta till en datakälla och infoga data i dina ämnen

Nu kan du snabbt ansluta till dina datakällor med färdiga anslutningar från AEM. Om du ansluter till en datakälla kan du synkronisera informationen med källan och alla uppdateringar av data återspeglas automatiskt, vilket gör AEM stödlinjer till ett verkligt innehållsnav. Den här funktionen hjälper dig att spara tid och arbete med att manuellt lägga till eller kopiera data.

Med AEM Guides kan administratören konfigurera färdiga anslutningar för JIRA- och SQL-databaser (MySQL, PostgreSQL, SQL Server, SQLite). De kan även lägga till andra kopplingar genom att utöka standardgränssnitten.

När du har lagt till dem kan du visa de konfigurerade anslutningarna som listas under **Datakällor** i webbredigeraren.

![](assets/code-snippet-generator.png){width="300" align="left"}

Du kan skapa en generator för innehållsavdrag som hämtar data från en ansluten datakälla. Sedan kan du infoga data i dina ämnen och redigera dem.

När du har skapat en generator för innehållsfragment kan du återanvända den för att infoga data i alla ämnen. Mer information finns i [Infoga ett innehållssfragment från datakällan](../user-guide/web-editor-content-snippet.md).



## Granskningspanelen för att visa granskningsprojekt och aktiva granskningsåtgärder

Nu gör AEM guider granskningarna smidigare. Här finns panelen Recensioner i Web Editor. På panelen Granska visas alla granskningsprojekt och de aktiva granskningsåtgärderna i granskningsprojekten som du är en del av.

Som författare kan du använda den här funktionen för att enkelt öppna granskningsuppgifterna, visa kommentarerna och snabbt hantera kommentarerna i en centraliserad vy.
![](assets/active-review-task-comments.png){width="800" align="left"}
Mer information finns i **Granska** funktionsbeskrivning i [Vänster panel](../user-guide/web-editor-features.md#id2051EA0M0HS) -avsnitt.


## Förbättringar av kartsamling

Med en kartsamling kan du ordna flera kartor och grupppublicera dem. Många nya förbättringar har gjorts i kartsamlingen:

- Nu kan du även lägga till förinställningar för inbyggda PDF-utdata i en kartsamling och använda dem för att generera utdata från PDF.
- Du kan visa de förinställningar för global profil och mappprofil som har skapats av administratören och använda dem för att generera utdata från PDF.
- Nu kan du inte bara välja en enskild förinställning, utan även aktivera alla förinställningar för mappprofiler för en DITA-karta på en gång.
  ![](assets/edit-map-collection.png){width="800" align="left"}

Mer information finns i [Använd kartsamling för generering av utdata](../user-guide/generate-output-use-map-collection-output-generation.md).

## Möjlighet att få åtkomst till temporära HTML-filer när du genererar PDF-utdata

Nu kan du ladda ned de temporära HTML-filerna som skapas när du genererar PDF-utdata AEM stödlinjer. Välj alternativet att hämta de temporära filerna i inställningarna för förinställningar för utdata.  AEM Guides kan du sedan hämta de temporära filer som skapades när du genererade utdata med den förinställningen.

Den här funktionen ger bättre insikter i genereringsprocessen med tillgång till tillfälliga format och layouter och hjälper dig att korrigera eller ändra dina CSS-format efter dina behov.

![](assets/native-pdf-advanced-settings.png){width="800" align="left"}

Mer information finns i [Skapa en förinställning för PDF](../web-editor/native-pdf-web-editor.md#create-output-preset).

## Microservice-baserad publicering för att generera utdata för HTML5 och Custom

Med den nya publiceringsmikrotjänsten kan du köra stora publiceringsarbetsbelastningar samtidigt AEM Guides as a Cloud Service och utnyttja den branschledande Adobe I/O Runtime serverlösa plattform. Med mikrotjänsten kan du nu också generera utdata för HTML5 och Custom.
Du kan köra flera publiceringsbegäranden och få bättre prestanda för att generera dessa utdataformat.
Mer information finns i [Konfigurera mikrotjänstbaserad publicering för AEM Guides as a Cloud Service](../knowledge-base/publishing/configure-microservices.md).

## Visa information om AEM stödlinjernas version i Om-informationen

Nu med AEM **Om** kan du även visa versionsinformation AEM stödlinjerna. Du kan visa den aktuella versionsinformationen i **Om** alternativ för **Hjälp** på sidan AEM.

![](assets/about-aem-help.png)(width=&quot;800&quot; align=&quot;left&quot;)
