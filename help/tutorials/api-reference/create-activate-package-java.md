---
title: Java-baserat API för att skapa och aktivera paket
description: Läs mer om det Java-baserade API:t för att skapa och aktivera paket
source-git-commit: 880cd344ceb65ea339be699ebcad41c0d62e168a
workflow-type: tm+mt
source-wordcount: '471'
ht-degree: 0%

---

# Java-baserat API för att skapa och aktivera paket {#id175UB30E05Z}

Med följande Java-baserade API kan du skapa och aktivera CRX-paket. Detta API är tillgängligt i form av ett paket. Du måste inkludera det här paketet i koden för att kunna använda dessa API:er.

Paketinformation:

- Grupp-ID: **com.adobe.fmdita**

- Artefakt-ID: **api**

- Version: **3.3**

- Paket: **com.adobe.fmdita.api.crxactivate**

- Klassinformation:

  ```JAVA
  public class CRXActivator
  ```

  The **`CRXActivator`** -klassen innehåller en metod för att skapa CRX-paket och replikera dem på publiceringsinstansen.


## Skapa och aktivera paket

The `activate` skapar ett CRX-paket på författarinstansen och replikerar det vid behov på publiceringsinstansen. AEM replikeringsparametrar har redan konfigurerats för författarinstansen. Den här metoden skapar CRX-paketet baserat på en lista med regler som tillhandahålls som indataparametrar i en JSON-sträng.
>[!NOTE]
>
> Fel som uppstod när programmet skapades eller aktiverades skrivs till `outputstream`.

**Syntax**:

```JAVA
public static void activate
(
  String json, 
  OutputStream outputstream, 
  Session session
) 
throws GuidesApiException
```

**Parametrar**: |Namn|Typ|Beskrivning| |—|—|—| |`json`|String|JSON-sträng som bestämmer vilket CRX-paket som ska skapas. Använd följande format för att skapa JSON-strängen: <br>- `activate`: Är av typen Boolean \(`true`/`false`\). Avgör om det CRX-paket som skapas i författarinstansen replikeras till publiceringsinstansen. <br> - `rules`: Är av typen JSON Array. En array med JSON-regler som bearbetas sekventiellt för att skapa CRX-paketet. <br> - `rootPath`: Är av typen String. Bassökvägen som nod-/egenskapsfrågorna körs på. Om det inte finns några nod-/egenskapsfrågor inkluderas rotsökvägen och alla noder som finns under rotsökvägen i CRX-paketet. <br> - `nodeQueries`: Är av typen Regex Array. En array med reguljära uttryck som används för att inkludera specifika filer under rotsökvägen. <br> - `propertyQueries`: Är av typen JSON Array. En array med JSON-objekt med varje JSON-objekt som består av en XPath-fråga som ska köras på rotsökvägen och namnet på en egenskap som finns i varje JCR-nod efter att frågan har körts. Värdet för egenskapen i varje JCR-nod ska vara en sökväg eller en array med sökvägar. Sökvägarna i den här egenskapen läggs till i CRX-paketet.| |`outputstream`|java.io.OutputStream|Detta används för att skriva resultatet av olika faser, t.ex. frågekörning, filinkludering, skapande av CRX-paket eller aktivering. Alla fel som uppstår under skapande eller aktivering skrivs till `outputstream`. Detta är användbart vid felsökning.| |`session`|String|En giltig JCR-session med aktiveringsbehörighet.|

**Undantag**: Throws ``java.io.IOException``.

**Exempel**: I följande exempel visas hur du skapar en JSON-fråga:

```JSON
{
  "activate": true,
  "rules": [
    {
      "rootPath": "/content/dam/nested",
      "nodeQueries": [
        ".*\\.jpg",
        ".*\\.png",
        ".*\\.gif"        
      ]
    },
    {
      "rootPath": "/content/output/sites/hierarchy_ditamap"
    },
    {
      "rootPath": "/content/output/sites/hierarchy_ditamap",
      "propertyQueries": [
        {
          "query": "//*[@fileReference]",
          "property": "fileReference"
        }
      ]
    }
  ]
}
```

Exempelfrågan för JSON består av följande regler:

- Endast PNG-, JPG- och GIF-bilder under /content/dam/nested path inkluderas i paketet.
- Alla noder under /content/output/sites/archy\_ditamap inkluderas i paketet.
- Banorna i `fileReference` för noder under /content/output/sites/hierarki\_ditamap ingår i paketet.
