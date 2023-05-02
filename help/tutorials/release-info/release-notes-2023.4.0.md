---
title: Versionsinformation | Adobe Experience Manager Guides as a Cloud Service, aprilversion 2023
description: Den senaste versionen av Adobe Experience Manager Guides as a Cloud Service
exl-id: 3b09f0b3-cfa4-422d-91b7-733ab1c1896c
source-git-commit: cf612da41f79b0bf9da4c4d7454a0e3c86af7a4c
workflow-type: tm+mt
source-wordcount: '852'
ht-degree: 1%

---

# aprilversion av Adobe Experience Manager Guides as a Cloud Service

## Uppgradera till den senaste versionen

Uppgradera din nuvarande Adobe Experience Manager Guides as a Cloud Service (kallas senare *AEM stödlinjer as a Cloud Service*) genom att utföra följande steg:

1. Ta en titt på Cloud Servicens Git-kod och växla till den gren som är konfigurerad i Cloud Servicens pipeline för den miljö som du vill uppgradera.
2. Uppdatera `<dox.version>` egenskap i `/dox/dox.installer/pom.xml` fil med dina Cloud Services Git-kod till 2023.4.249.
3. Genomför ändringarna och kör Cloud Servicens pipeline för att uppgradera till den senaste versionen av AEM Guides as a Cloud Service.

## Steg för att indexera det befintliga innehållet (endast om du använder en version som är tidigare än september-versionen av AEM stödlinjer as a Cloud Service)

Utför följande steg för att indexera det befintliga innehållet och använda den nya texten för att söka och ersätta på mappnivå:

* Kör en serverbegäran (med korrekt autentisering) - `http://<server:port>/bin/guides/map-find/indexing`.
(Valfritt: Du kan skicka specifika sökvägar för mappningarna för att indexera dem. Som standard indexeras alla mappningar || Exempel: `https://<Server:port>/bin/guides/map-find/indexing?paths=<map_path_in_repository>`)

* API:t returnerar ett jobId. Om du vill kontrollera jobbets status kan du skicka en GET-förfrågan med jobb-ID till samma slutpunkt - `http://<server:port>/bin/guides/map-find/indexing?jobId={jobId}`
(Exempel: http://&lt;
_localhost:8080_>/bin/guides/map-find/indexing?jobId=2022/9/15/7/27/7dfa1271-981e-4617-b5a4-c18379f11c42_678)

* När jobbet är klart kommer ovanstående GET-förfrågan att svara och ange om några kartor misslyckades. De korrekt indexerade mappningarna kan bekräftas från serverloggarna.

## Kompatibilitetsmatris

I det här avsnittet visas kompatibilitetsmatrisen för de program som stöds av AEM Guide as a Cloud Service April 2023.

### FrameMaker och FrameMaker Publishing Server

| AEM stödlinjer som en Cloud-release | FMPS | FrameMaker |
| --- | --- | --- |
| 2023.04.0 | Inte kompatibel | 2022 eller senare |
|  |  |  |


### Syrgasanslutning

| AEM stödlinjer som en Cloud-release | Syrgasanslutningsfönster | Syrgasanslutning Mac | Redigera i syrgasfönster | Redigera i Syrgas Mac |
| --- | --- | --- | --- | --- |
| 2023.04.0 | 2.9-uuid-2 | 2.9-uuid-2 | 2.3 | 2.3 |
|  |  |  |  |


## Nya funktioner och förbättringar

AEM Guides as a Cloud Service innehåller förbättringar och nya funktioner i den senaste versionen:

### Avancerat stöd för metadata vid PDF-publicering

AEM Guides har nu avancerat stöd för metadata som mappas till metadata i utdata från PDF. Metadataalternativen innehåller information om dokumentet och dess innehåll, till exempel författarens namn, dokumenttitel, nyckelord, copyrightinformation och andra datafält.

<img src="assets/pdf-metadata.png" alt=" inbyggda PDF-metadata">

Du kan importera en XMP och AEM stödlinjer kan välja information från filen. Du kan också ange metadatanamn och värden i listrutan. Du kan också lägga till anpassade metadata genom att skriva direkt i namnfältet.


### Förbättrad dispositionsvy

AEM innehåller en förbättrad panel för dispositionsvy där du kan se den hierarkiska vyn över de element som används i dokumentet.

<img src="assets/select-element-content-outline-view_cs.png" alt=" inbyggda PDF-metadata">

I dispositionsvyn finns följande förbättringar:

* Listrutan Visningsalternativ visas högst upp på panelen Dispositionsvy. Om ett element har ett ID, attribut och text kan du markera dem i listrutan för att visa dem tillsammans med elementet. De attribut som kan visas i dispositionsvyn bestäms av inställningarna för visningsattribut som har konfigurerats av administratören i **Inställningar för Redigeraren**.

* Med sökfunktionen kan du söka efter ett element efter dess namn, id, text eller attributvärde.


### Microservice-baserad publicering för AEM Guides as a Cloud Service

AEM Guides as a Cloud Service har funktioner för att köra stora publiceringsarbetsbelastningar samtidigt med mikrotjänstbaserad publicering och utnyttjar den branschledande serverlösa Adobe I/O Runtime-plattformen.

I aprilversionen kan du nu köra flera publiceringsbegäranden samtidigt och generera stora PDF-utdata mycket effektivt med hjälp av den inbyggda publiceringsfunktionen för mikrotjänster i PDF.
Mer information finns i [Konfigurera ny mikrotjänstbaserad publicering för AEM Guides as a Cloud Service](../knowledge-base/publishing/configure-microservices.md).


## Åtgärdade problem

De buggar som har åtgärdats i olika områden listas nedan:

* PDF | Publicering av innehåll som har en utdataklass med hakparenteser() resulterar i en publiceringsfrysning. (11596)
* Problem uppstår när du flyttar (drar och släpper) i stället för ett befintligt listobjekt med Spåra ändringar aktiverat. (11570)
* Problem uppstår när du flyttar (drar och släpper) som ett nytt listobjekt med Spåra ändringar aktiverat. (11569)
* Indrag eller indrag i listobjekt fungerar inte som väntat med Spåra ändringar. (11568)
* Om du lägger till innehåll på en linje med Spåra ändringar aktiverat och sedan stänger av Spåra ändringar inaktiveras det inte. (11567)
* Det är svårt att dra och släppa ett listobjekt. Texten flyttas istället för listobjektet. (11566)
* Den slutförda granskningen öppnas inte i skrivskyddat läge. (11387)
* Problem uppstår AEM webbplatssökningen (fungerar inte längre än 2-3 nivånoder). (11352)
* Vid redigering i det element som visas i grönt (Spåra ändringar) visas det nya innehållet som spåra ändringar även om spårändringen är inaktiverad. (7021)

### Känt problem med tillfälliga lösningar

Adobe har identifierat följande kända fel i AEM Guide as a Cloud Service April 2023.

* PDF | Gamla metadata fylls inte i förrän förinställningen för utdata öppnas explicit.
