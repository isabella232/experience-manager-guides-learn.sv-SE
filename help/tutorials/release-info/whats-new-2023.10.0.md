---
title: Versionsinformation | Nyheter i Adobe Experience Manager Guides, oktober 2023-versionen
description: Läs om de nya och förbättrade funktionerna i oktober 2023-versionen av Adobe Experience Manager Guides as a Cloud Service.
exl-id: 583bc9fe-1e61-4727-869b-0dbc19625f70
source-git-commit: e8503e1441b7bc365d37c76ab9cf7b5f50374f10
workflow-type: tm+mt
source-wordcount: '619'
ht-degree: 0%

---

# Nyheter i oktober 2023-versionen av Adobe Experience Manager Guides as a Cloud Service

I den här artikeln beskrivs de nya och förbättrade funktionerna i versionen från oktober 2023 av Adobe Experience Manager Guides (kallas senare *AEM stödlinjer as a Cloud Service*).

Mer information om uppgraderingsinstruktioner, kompatibilitetsmatris och problemen som åtgärdas i den här versionen finns i [Versionsinformation](release-notes-2023.10.0.md).


## Konfigurera en datakällanslutning från användargränssnittet

Nu finns det en **Datakällor** som hjälper dig att konfigurera färdiga anslutningar för datakällor. Du kan enkelt skapa kopplingar för databaserna JIRA, SQL (MySQL, PostgreSQL, Microsoft SQL Server, SQLite, MariaDB, H2DB), Adobe Commerce och Elasticsearch.

Du kan också enkelt redigera, återansluta, duplicera eller ta bort en datakällkoppling. Lär dig hur [enkelt konfigurera en datakällanslutning från användargränssnittet](../cs-install-guide/conf-data-source-connector-tools.md).

![datakällanslutningar som listas på datakällpanelen](assets/data-sources-create-window.png){width="550" align="left"}

*Skapa och visa datakällanslutningar från panelen för datakällor.*

## Visa loggar för ämnesgeneratorn

Nu kan du även visa loggfilen för innehållsgenerering. Loggfilen hjälper dig att kontrollera varningar, fel och undantag.  Läs mer om hur [alternativ för ämnesgenerator](../user-guide/web-editor-content-snippet.md#options-for-a-topic-generator) hjälper dig att enkelt generera och hantera ämnesgeneratorer.

## Stöd för snabbverktyg i datakällmallarna

Nu kan du använda snabbverktygen i mallarna för stödlinjer i Experience Manager. Med de här verktygen kan du använda olika funktioner för data som du hämtar från datakällorna. Du kan använda mallarna när du skapar ett innehållsutdrag eller ett ämne. Med den här funktionen kan du spara tid och arbete med att manuellt använda samma funktion för varje datauppsättning.  Det ger också korrekta resultat.
Du kan till exempel använda $mathTool för att utföra matematiska funktioner.
Läs mer om hur [använda snabbhetsverktyg i datakällmallar](../user-guide/web-editor-content-snippet.md#use-velocity-tools).


## Förbättringar av inbyggda PDF

Följande förbättringar av ursprungligt PDF har gjorts i oktober 2023-versionen:

### Återställ sidnumret för den första sidan i en layout

I utdata från PDF kan du starta om sidnumren och ange från vilket nummer numreringen börjar. Nu kan du också börja numreringen endast för den första förekomsten av ett avsnitt.
Läs mer om hur [arbeta med sidegenskaperna i en sidlayout](../native-pdf/design-page-layout.md#page-props-page-layout).


### Visa kapitel utan automatiska nummer i innehållsförteckningen

Stödlinjerna i Experience Manager visar kapitelnumren tillsammans med kapitelnamnen i innehållsförteckningen. Nu kan du välja att publicera enbart kapitelnamnen utan kapitelnumren. Visa mer information om hur du konfigurerar [avancerade PDF-inställningar för en mall](../native-pdf/components-pdf-template.md#advanced-pdf-settings).

## Hämta en karta från Web Editor

Nu kan du inte bara redigera en karta i kartvyn i Web Editor utan även hämta den. Du kan välja att hämta kartan med en viss baslinje. Du kan också förenkla hierarkin och spara alla filer och mappar i en enda mapp.

Mer information finns i **Kartvy** funktionsbeskrivning i [Vänster panel](../user-guide/web-editor-features.md#id2051EA0M0HS) -avsnitt.

![alternativmeny för en fil i databasvyn](assets/options-menu-repo-view-file-level-2310.png){width="550" align="left"}

*Välj en fil i databasvyn och välj alternativet för att utföra en åtgärd på filen.*

## Redigera en fil i syrgasanslutningens plugin

Nu kan du välja en fil i webbredigeraren och sedan välja att redigera filen i plugin-programmet för syreanslutning i Experience Manager. Det här alternativet är inte aktiverat som en del av det färdiga stödet.

Mer information finns i **Alternativ för en fil** funktionsbeskrivning i [Vänster panel](../user-guide/web-editor-features.md#id2051EA0M0HS) -avsnitt.
