---
title: Java-baserat API som fungerar med utdatagenerering
description: Lär dig mer om det Java-baserade API:t för att arbeta med generering av utdata
source-git-commit: 880cd344ceb65ea339be699ebcad41c0d62e168a
workflow-type: tm+mt
source-wordcount: '160'
ht-degree: 0%

---

# Java-baserat API som fungerar med utdatagenerering {#id175UB30E05Z}

Med följande Java-baserade API kan du generera utdata för en DITA-karta. Detta API är tillgängligt i form av ett paket. Du måste inkludera det här paketet i koden för att kunna använda dessa API:er.

Paketinformation:

- Grupp-ID: **com.adobe.fmdita**

- Artefakt-ID: **api**

- Version: **3.4**

- Paket: ****com.adobe.fmdita.api.maps****

- Klassinformation:

  ```JAVA
  public class **PublishUtils** extends Object
  ```

  The **`PublishUtils`** -klassen innehåller en metod för att generera utdata för en eller flera förinställningar.


## Generera utdata

The ``generateOutput`` -metoden genererar utdata för en DITA-mappningsfil med de angivna utdataförinställningarna.

**Syntax**:

```JAVA
public static void generateOutput(Session session,
String sourcePath,
String outputName)
throws GuidesApiException
```

**Parametrar**: |Namn|Typ|Beskrivning| |—|—|—| |`session`|javax.jcr.Session|En giltig JCR-session.| |``sourcePath``|String|Sökväg \(i den AEM databasen\) för den DITA-mappningsfil som utdata ska skapas för.| |``outputName``|String|Namnet på den förinställning som ska användas för att generera utdata. Du kan ange flera förinställningar med hjälp av en pipe \(&quot;\|&quot;\)-avgränsare, till exempel `aemsite\|pdfoutput`.|

**Undantag**: Throws ``javax.jcr.RepositoryException``, `java.io.IOException`och `java.lang.Exception`.
