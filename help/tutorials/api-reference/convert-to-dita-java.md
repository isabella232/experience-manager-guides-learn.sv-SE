---
title: Java-baserade API:er för konverteringsarbetsflöde
description: Läs mer om Java-baserade API:er för konverteringsarbetsflöde
source-git-commit: 880cd344ceb65ea339be699ebcad41c0d62e168a
workflow-type: tm+mt
source-wordcount: '259'
ht-degree: 0%

---

# Java-baserade API:er för konverteringsarbetsflöde {#id175UB30E05Z}

Med följande Java-baserade API:er kan du konvertera HTML- och Word-dokument till DITA-format. Dessa API:er är tillgängliga i form av ett paket. Du måste inkludera det här paketet i koden för att kunna använda dessa API:er.

**Information om programpaket**:

- Grupp-ID: **com.adobe.fmdita**

- Artefakt-ID: **api**

- Version: **3.2**

- Paket: **com.adobe.fmdita.api.conversion**

- Klassinformation:

  ```JAVA
  public class ConversionUtils extends Object
  ```

  The **ConversionUtils** -klassen innehåller metoder för konvertering av HTML- och Word-dokument till DITA-format.


## Konvertera HTML-dokument

The `convertHtmlToDita` konverterar HTML-dokument till DITA-format.

**Syntax**:

```JAVA
public static void convertHtmlToDita(Session session, 
                  String inputFile, 
                  String destPath, 
                  boolean createRev) 
                  throws RepositoryException, WorkflowException
```

**Parametrar**: |Namn|Typ|Beskrivning| |—|—|—| |`session`|javax.jcr.Session|En giltig JCR-session.| |`inputFile`|String|Absolut sökväg för HTML-källfilerna i AEM.| |`destPath`|String|Absolut sökväg till målplatsen där de konverterade DITA-filerna ska sparas.| |`createRev`|Boolean|Ange om en version av filerna skapas \( `true`\) vid det angivna målet eller inte \( `false`\). Detta gäller endast när målplatsen innehåller en befintlig version av de konverterade filerna.|

**Undantag**: Throws `RepositoryException`.

## Konvertera Word-dokument

The ``convertWordToDita`` konverterar Word-dokument till DITA-format.

**Syntax**:

```JAVA
public static void convertWordToDita(Session session, 
                  String inputFile,
                  String destPath, 
                  String style2tagMap, 
                  boolean createRev) 
                  throws RepositoryException, WorkflowException
```

**Parametrar**: |Namn|Typ|Beskrivning| |—|—|—| |`session`|javax.jcr.Session|En giltig JCR-session.| |`inputFile`|String|Absolut sökväg för Word-källfilerna i AEM.| |`destPath`|String|Absolut sökväg till målplatsen där de konverterade DITA-filerna ska sparas.| |`style2tagMap`|String|Absolut sökväg till den formatmappningsfil som ska användas för konvertering.| |`createRev`|Boolean|Ange om en version av filerna skapas \( `true`\) vid det angivna målet eller inte \( `false`\). Detta gäller endast när målplatsen innehåller en befintlig version av de konverterade filerna.|

**Undantag**: Throws `RepositoryException`.
