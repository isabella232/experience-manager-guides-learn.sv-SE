---
title: Konfigurera en datakällanslutning med verktyg
description: Lär dig hur du konfigurerar en datakällanslutning med verktygen.
exl-id: b73ceb8d-caf0-4752-a6d9-07985cdf741e
source-git-commit: e8503e1441b7bc365d37c76ab9cf7b5f50374f10
workflow-type: tm+mt
source-wordcount: '522'
ht-degree: 0%

---



# Konfigurera en datakällanslutning från användargränssnittet

Experience Manager Guides har **Datakällor** som hjälper dig att konfigurera färdiga anslutningar för datakällor. Du kan konfigurera anslutningar för databaserna JIRA, SQL (MySQL, PostgreSQL, Microsoft SQL Server, SQLite, MariaDB, H2DB), Adobe Commerce och Elasticsearch.

Så här konfigurerar du en koppling:

1. Välj **Adobe Experience Manager** överst och välj Verktyg.
1. Välj **Stödlinjer** i listan över verktyg.
1. Välj **Datakällor** platta. The **Datakällor** visas. Du kan visa de anslutna datakällorna.

   Du kan växla mellan **Listvy** eller **Panelvy** för att visa de olika anslutna datakällorna som en lista eller som rutor.

   <img src="./assets/data-sources-create-window.png" alt= "datakällor som listas på sidan med datakällor" width="800">

   *Visa eller skapa en datakällkoppling.*
1. Klicka **Skapa**.
1. Välj den databas som du vill skapa kopplingen för. Exempel: Elasticsearch-kopplingen.
   >[!NOTE]
   >
   >Alla tillgängliga färdiga databaser visas.

1. Klicka på **Nästa**.
1. Ange konfigurations- och anslutningsinformation enligt databasen.

   >[!TIP]
   >* Hovring <img src="./assets/info-details.svg" alt= "informationsikon" width="25"> i närheten av fältet för att visa mer information om det.
   > * Fält med * är obligatoriska. Du kan till exempel ange följande information för Elasticsearch-kopplingen.

   * **Namn**: Ange namnet på datakällan.
   * Autentiseringstyp: Välj autentiseringstyp i listrutan. Grundläggande autentisering av användarnamn och lösenord
   * **Användarnamn**: Ange ditt användarnamn.
   * **Lösenord**: Ange ditt användarnamn och lösenord.
   * **URL**: Lägg till API-URL:en.

1. Välj **Testanslutning**. Du kan visa **Testanslutning** bara aktiverad när du har lagt till den obligatoriska informationen. Visa ett meddelande om att anslutningen är korrekt. Annars kan du visa ett felmeddelande.



1. Välj **Spara** längst upp för att spara kopplingen.     Visa **Spara** när du fyllt i alla detaljer och anslutningen lyckades.


   Om anslutningen har sparats kan du visa den anslutna datakällan på sidan.

## Tillgängliga funktioner för en koppling

* Växla mellan **Listvy** eller **Panelvy**  för att visa de olika anslutna datakällorna som en lista eller som rutor.
* Markera kryssrutan för en enskild koppling. Klicka **Markera alla** för att välja alla anslutningar. Klicka **Avmarkera allt** när alla kopplingar är markerade.

<img src="./assets/data-sources-features.png" alt= "funktioner för datakällorna på sidan med datakällor" width="800">

*Redigera, återansluta, duplicera eller ta bort en datakällkoppling.*

Du kan använda följande funktioner för kontakten på **Datakällor** sida:

* **Redigera**: Redigera konfigurationsinformationen för den valda kopplingen.

* **Återanslut**: Återanslut till en frånkopplad koppling.

* **Duplicera**: Skapa en ny dubblettkoppling med den aktuella kopplingen som bas. Den duplicerade kopplingen skapas som standard med ett suffix (som connectorname_1). Exempel: elastic-search_1.
Du kan visa ett fel om det finns en koppling med samma namn.

* **Ta bort**: Ta bort den markerade kopplingen.


När du har konfigurerat datakällan visas anslutningen under **Panelen Datakällor** i webbredigeraren. Sedan kan du ansluta till datakällan och infoga ett innehållskuvert i dina ämnen. Mer information finns i [Infoga ett innehållssfragment från datakällan](../user-guide/web-editor-content-snippet.md).
