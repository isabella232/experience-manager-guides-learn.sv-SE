---
title: Versionsinformation | Adobe Experience Manager Guides as a Cloud Service, aprilversion 2023
description: Version av Adobe Experience Manager Guides as a Cloud Service, släppt i april 2023
source-git-commit: 880cd344ceb65ea339be699ebcad41c0d62e168a
workflow-type: tm+mt
source-wordcount: '381'
ht-degree: 0%

---

# Nyheter i aprilversionen 2023 av Adobe Experience Manager Guides as a Cloud Service

I den här artikeln beskrivs de nya och förbättrade funktionerna i version april 2023 av Adobe Experience Manager Guides (senare kallad *AEM stödlinjer as a Cloud Service*).

Mer information om uppgraderingsinstruktioner, kompatibilitetsmatris och problemen som åtgärdas i den här versionen finns i [Versionsinformation](release-notes-2023.4.0.md) artikel.

## Avancerat stöd för metadata vid PDF-publicering

AEM Guides har nu avancerat stöd för metadata som mappas till metadata i utdata från PDF. Metadataalternativen innehåller information om dokumentet och dess innehåll, till exempel författarens namn, dokumenttitel, nyckelord, copyrightinformation och andra datafält.

<img src="assets/pdf-metadata.png" alt=" inbyggda PDF-metadata">

Du kan importera en XMP och AEM stödlinjer kan välja information från filen. Du kan också ange metadatanamn och värden i listrutan. Du kan också lägga till anpassade metadata genom att skriva direkt i namnfältet.


## Förbättrad dispositionsvy

AEM innehåller en förbättrad panel för dispositionsvy där du kan se den hierarkiska vyn över de element som används i dokumentet.

<img src="assets/select-element-content-outline-view_cs.png" alt=" inbyggda PDF-metadata">

I dispositionsvyn finns följande förbättringar:

* Listrutan Visningsalternativ visas högst upp på panelen Dispositionsvy. Om ett element har ett ID, attribut och text kan du markera dem i listrutan för att visa dem tillsammans med elementet. De attribut som kan visas i dispositionsvyn bestäms av inställningarna för visningsattribut som har konfigurerats av administratören i **Inställningar för Redigeraren**.

* Med sökfunktionen kan du söka efter ett element efter dess namn, id, text eller attributvärde.


## Microservice-baserad publicering för AEM Guides as a Cloud Service

AEM Guides as a Cloud Service har funktioner för att köra stora publiceringsarbetsbelastningar samtidigt med mikrotjänstbaserad publicering och utnyttjar den branschledande Adobe I/O Runtime serverlösa plattform.

I aprilversionen kan du nu köra flera publiceringsbegäranden samtidigt och generera stora PDF-utdata mycket effektivt med hjälp av den inbyggda publiceringsfunktionen för mikrotjänster i PDF.
Mer information finns i [Konfigurera ny mikrotjänstbaserad publicering för AEM Guides as a Cloud Service](../knowledge-base/publishing/configure-microservices.md).
