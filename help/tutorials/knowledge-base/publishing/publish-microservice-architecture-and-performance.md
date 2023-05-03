---
title: Cloud Publishing Microservice Architecture and Performance
description: Förstå hur den nya mikrotjänsten möjliggör skalbar publicering på AEMaaCS.
source-git-commit: 2e45f132ced5ac29118a7301f104bedc03c93253
workflow-type: tm+mt
source-wordcount: '730'
ht-degree: 0%

---


# Cloud Publishing Microservice Architecture and Performance Analysis

I den här artikeln får du information om arkitekturen och prestandanalen i den nya molnpubliceringsmikrotjänsten.

>[!NOTE]
>
> För närvarande stöder den mikrotjänstbaserade publiceringen i AEM endast utdata från PDF med hjälp av Native PDF-publicering eller via DITA-OT. AEM kommer att lägga till stöd för mikrotjänstbaserad publicering för fler utdatatyper i framtida versioner.

## Problem med befintliga publiceringsarbetsflöden i molnet

DITA Publishing är en resurskrävande process som huvudsakligen är beroende av tillgängligt systemminne och processor. Behovet av dessa resurser ökar ytterligare om utgivare publicerar stora kartor med många ämnen eller om flera parallella publiceringsbegäranden aktiveras.

Om du inte använder den nya tjänsten sker all publicering på samma Kubernetes(k8)-pod som också kör AEM molnserver. En vanlig k8-pod har en gräns för hur mycket minne och processor den kan använda. Om AEM guidade användare publicerar stora eller parallella arbetsbelastningar kan den här gränsen bryta ut snabbt. K8 startar om poder som försöker använda fler resurser än den konfigurerade gränsen, vilket kan få allvarliga konsekvenser för själva AEM molninstansen.

Resursbegränsningen var den främsta anledningen att komma på en dedikerad tjänst som gör att vi kan köra flera samtidiga och stora publiceringsarbetsbelastningar i molnet.

## Introduktion till den nya arkitekturen

Tjänsten använder Adobe branschledande molnlösningar som App Builder, IO Eventing, IMS för att skapa ett serverlöst erbjudande. Dessa tjänster bygger i sig på de allmänt vedertagna branschstandarderna Kubernetes och Docker.

Varje begäran till den nya publiceringsmikrotjänsten körs i en isolerad dockningsbehållare som endast kör en publiceringsbegäran åt gången. Flera nya behållare skapas automatiskt om nya publiceringsbegäranden tas emot. Denna konfiguration med en enda behållare per begäran gör att mikrotjänsten kan leverera bästa prestanda till kunderna utan att medföra några säkerhetsrisker. Behållarna tas bort när publiceringen är klar och frigör därmed oanvända resurser.

All kommunikation skyddas av Adobe IMS med JWT-baserad autentisering och auktorisering och körs via HTTPS.

<img src="assets/architecture.png" alt="fliken Projekt" width="600">

>[!NOTE]
>
> Publiceringsprocessen kör vissa innehållsberoende delar av begäran på själva AEM, som generering av beroendelistor. De mest omfattande delarna av publiceringsprocessen, som att köra DITA-OT eller inbyggd motor, har dock avlästs till den nya tjänsten.


## Resultatanalys

I det här avsnittet visas mikrotjänstens prestandanummer. Den jämför mikrotjänstens prestanda med AEM Guides on-prem-erbjudanden eftersom den gamla molnarkitekturen hade problem med samtidig publicering eller publicering av mycket stora kartor.

Om du publicerar en stor karta lokalt kanske du måste justera Java-heap-parametrarna, annars kan du råka ut för minnesfel. I molnet är mikrotjänsten redan profilerad och har optimala Java-heap och andra konfigurationer direkt.

### Köra en publicering i molnet jämfört med lokalt

* Cloud

   Om du utför en enstaka publicering i molnet med den nya tjänsten kan publiceringen ta lite längre tid jämfört med en enstaka publicering på plats. Den här något förhöjda tiden beror på den nya molnarkitekturens utbredning.

   <img src="assets/cloud_single_publish.png" alt="fliken Projekt" width="600">

* Lokalt

   Resultatet av en enstaka publicering är bättre på den gamla molnarkitekturen eller på plats när den fullständiga publiceringen sker på samma stativ/dator där AEM körs.

   <img src="assets/onprem_single_publish.png" alt="fliken Projekt" width="600">

### Köra flera publiceringar i molnet jämfört med lokalt

* Cloud

   Ny publiceringsmikrotjänst visas i det här scenariot. Som du ser i bilden nedan kan molnet publicera flera samtidiga publiceringsjobb utan att publiceringstiden ökar nämnvärt.

   <img src="assets/cloud_bulk_publish.png" alt="fliken Projekt" width="600">

* Lokalt

   Om samtidig publicering körs på en lokal server försämras prestandan avsevärt. Den här prestandasänkningen är allvarligare om utgivare publicerar ännu fler kartor samtidigt.

   <img src="assets/onprem_bulk_publish.png" alt="fliken Projekt" width="600">

## Ytterligare fördelar

En del av varje publiceringsbegäran måste köras på den AEM instansen för att hämta korrekt publiceringsinnehåll som ska skickas till mikrotjänsten. Den nya molnarkitekturen använder AEM jobb i stället för AEM arbetsflöden, vilket var fallet i den gamla arkitekturen. Med den här ändringen kan AEM guidade administratörer konfigurera köinställningar för molnpublicering separat utan att påverka andra AEM eller arbetsflödeskonfigurationer.

Mer information om hur du konfigurerar den nya publiceringsmikrotjänsten finns här: [Konfigurera Microservice](configure-microservices.md)