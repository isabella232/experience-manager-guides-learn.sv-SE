---
title: REST API för att registrera en datakällkoppling
description: Läs mer om REST API för att registrera en datakällkoppling
source-git-commit: 8707acf3ba01b7488eea6597c434da73a901d037
workflow-type: tm+mt
source-wordcount: '81'
ht-degree: 1%

---


# REST API för att registrera en datakällkoppling {#id236LG0Y0CXA}

Med följande REST API kan du registrera en datakällkoppling.

## Registrera en datakällkoppling

En GET-metod som registrerar en datakällkoppling.

**Begär URL**:
`http://server:port/bin/guides/v1/konnect/config/register?path=<uploaded file path>`

**Parameter**: |Namn|Typ|Obligatorisk|Beskrivning| |—|—|—|—| |`path`|String|Yes|En sträng som pekar på en sökväg i AEM. Det kan vara en bana i `/content/dam or /var/dxml`.|

**Exempel**:\
`http://host:4502/bin/guides/v1/konnect/config/register?path=/var/dxml/konnect/jira.json`

