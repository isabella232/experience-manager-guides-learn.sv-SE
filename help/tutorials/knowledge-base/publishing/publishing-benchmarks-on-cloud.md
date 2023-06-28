---
title: Guides Publishing Benchmarks on AEMaaCS
description: Förstå systembegränsningar för publicering på AEM Cloud.
exl-id: cc6e38b9-6276-4147-beda-93f66368e15d
source-git-commit: 06a55ef933f9e7941cef2337212a830413a478af
workflow-type: tm+mt
source-wordcount: '233'
ht-degree: 4%

---

# AEM Guides Publishing Benchmarks on AEMaaCS

För närvarande AEM Guides molntjänst har vissa gränser för publiceringskartor, som Guides team aktivt arbetar med att lösa.

Guides Team har introducerat en skalbar publiceringsmikrotjänst för stöd till stora kartor och flera samtidiga publiceringstillfällen. Mer information om den nya publiceringsmikrotjänsten finns i [publicera mikrotjänstarkitektur](publish-microservice-architecture-and-performance.md)

Om du vill konfigurera den nya publiceringstjänsten för valfri AEM molnmiljö, se [konfigurera ny mikrotjänstbaserad publicering](configure-microservices.md)


## Körningsmiljö

    AEM: 2023.5.11983.20230511T173830Z
    Lägg till stödlinje i utgåva: 2023.6.0
    AEM: AEM Guides OOTB-mall
    DITA-OT-version: 3.5.4
    Typ av publiceringsarbetsflöde: Dela publiceringsarbetsflöde
    Utdata som stöds av mikrotjänsten: PDF, PDF (Dita-OT)

## Genereringsnummer för utdata

| Utdatatyp | Kartstorlek (ämnesreferenser) | Körningstid (i sekunder) | Publishing Microservice |
|---------------|------------------------------|----------------------------|-----------------------|
| AEM | 3500 | 5220 | Nej |
| PDF | 3500 | 780 | Ja |
| PDF (DITA-OT) | 11000 | 960 | Ja |
| HTML5 | 3500 | 240 | Nej |
| Egen | 300 | 300 | Nej |

## Viktiga punkter att komma ihåg

- AEM Site skapar många cq:Page-noder och förenklar genom att återge dem individuellt under genereringstiden. Därför är det tillrådligt att undvika att köra flera stora parallella publiceringar AEM webbplatsen eftersom det kan belasta systemet.
- AEM tid beror på vilken mall som används. Körningstiden kan öka om komplexa mallar används.
- Anpassad publiceringstid är för ett exempel på anpassade utdata. Anpassad publiceringstid beror enbart på kundens egen omvandlingslogik.
