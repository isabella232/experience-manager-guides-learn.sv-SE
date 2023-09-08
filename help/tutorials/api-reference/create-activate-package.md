---
title: REST API för att skapa och aktivera paket
description: Läs mer om REST API för att skapa och aktivera paket
source-git-commit: fad5049962f258bbe59c7d172436d82b3d6cd68f
workflow-type: tm+mt
source-wordcount: '118'
ht-degree: 0%

---


# REST API för att skapa och aktivera paket {#id198CF0260Y4}

Med följande REST API kan du skapa och aktivera CRX-paket.

## Skapa och aktivera paket

En POST-metod som skapar och aktiverar CRX-paket.

**Begär URL**: http://*&lt;aem-guides-server>*: *&lt;port-number>*/bin/fmdita/activate

**Parametrar**: Begäran-frågan består av JSON-regelsträngen. Innehållstypen för begäran om POST måste anges till `application/json; charset=UTF-8`.

**Exempel**: I följande exempel visas API-anropet med kommandot curl:

    &quot;
    curl -u &lt;*username*>:&lt;*password*> -H &quot;Content-Type: application/json; charset=UTF-8&quot; -k -X POST -d &quot;{[JSON rules string](create-activate-package-java.md#example-create-activate-package-id198JH0B905Z)}&quot; http://&lt;*aau em-guides-server*>:&lt;*port-number*>/bin/fmdita/activate
    &quot;
