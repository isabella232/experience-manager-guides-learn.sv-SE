---
title: Java-baserade API:er som fungerar med baslinje och etiketter
description: Lär dig mer om Java-baserade API:er som fungerar med baslinjer och etiketter
source-git-commit: 880cd344ceb65ea339be699ebcad41c0d62e168a
workflow-type: tm+mt
source-wordcount: '890'
ht-degree: 0%

---

# Java-baserade API:er som fungerar med baslinje och etiketter {#id175UB30E05Z}

Med följande Java-baserade API:er kan du skapa baslinjer och lägga till etiketter i filer i en baslinje. Dessa API:er är tillgängliga i form av ett paket. Du måste inkludera det här paketet i koden för att kunna använda dessa API:er.

Paketinformation:

- Grupp-ID: **com.adobe.fmdita**

- Artefakt-ID: **api**

- Version: **3.5**

- Paket: **com.adobe.fmdita.api.baselines**

- Klassinformation:

  ```JAVA
  public class BaselineUtils extends Object
  ```

  The **BaslinjeVerktyg** -klassen innehåller metoder för att skapa baslinjer och använda etiketter på filer i en baslinje.


## Skapa en baslinje

Metoden för att skapa baslinje har två versioner - en för XML Documentation-lösning version 3.5 och en för tidigare versioner än 3.5 \(som innehåller version 3.4, 3.3 och 3.2\). API:t för version 3.5 gör det möjligt att skapa baslinjen med hjälp av en etikett, direkta referenser och indirekta referenser i en mappningsfil.

I den andra versionen av API används datum och tid för att skapa en baslinje. Detta API bevaras för bakåtkompatibilitet med system som använder XML Documentation 3.4, 3.3 eller 3.2.

**Syntax \(för version 3.5\)**:

```JAVA
public static String createBaseline(Session session, 
String sourcePath, 
String baselineTitle, 
String label, 
LinkedHashMap directContext, 
LinkedHashMap indirectContext) 
throws GuidesApiException
```

**Parametrar**: |Namn|Typ|Beskrivning| |—|—|—| |`session`|javax.jcr.Session|En giltig JCR-session. Användarsessionen måste ha både läs- och skrivbehörighet för DITA-kartan och läsbehörighet för alla referensfiler som ingår i baslinjen.| |`sourcePath`|String|Absolut sökväg för DITA-mappningsfilen i AEM.| |`baselineTitle`|String|En unik rubrik för baslinjen.| |`label`|String|Markera den version av ett ämne som har den angivna etiketten.| |`directContext`|LinkedHashMap&lt;string object=&quot;&quot;>|De konfigurationer på grundval av vilka det direkt refererade ämnet \(innehåll\) väljs följs ordningen som anges på kartan för att lösa en version. <br> Om ingen version hittas efter upprepning på alla tangenter på kartan, misslyckas skapandet av baslinjen. <br> Om HashMap är tom \(skicka tom och inte null-mappning som standard\) fylls den som standard i som: <br>`directContext.put("label", label);` <br> `directContext.put("latest", true);` <br> Om du vill att baslinjen bara ska välja version av en viss etikett och misslyckas om det inte finns någon sådan version, ställer du in `label` och etiketten som du vill skapa baslinjen på.| |`indirectContext`|LinkedHashMap&lt;string object=&quot;&quot;>|De konfigurationer som indirekt refererar till ämnet \(refererat innehåll\) väljs utifrån följs ordningen som anges på kartan för att matcha en version. <br> Om ingen version hittas efter upprepning på alla tangenter på kartan, misslyckas skapandet av baslinjen. <br> Om HashMap är tom \(skicka tom och inte null-mappning som standard\) fylls den som standard i som: <br>`indirectContext.put("label", label);` <br>`indirectContext.put "pickAutomatically", null);` <br> Om du vill att den ska vara den senaste versionen istället för att hämta en version automatiskt ersätter du den: <br>`indirectContext.put("pickAutomatically", null);` <br> _med:_ <br>`indirectContext.put("latest", true)`|

**Returnerar**: Baslinjens namn, som är baslinjens nodnamn i JCR-databasen. Titeln på den nyskapade baslinjen visas för användaren på sidan Baslinje för DITA-kartan.

**Undantag**: Throws ``ItemExistExceptiom`` om det redan finns en baslinje med samma titel.

**Syntax \(för version 3.4, 3.3 och 3.2\)**

```JAVA
public static String createBaseline
(Session session, 
String sourcePath, 
String baselineTitle, 
Date versionDate) throws GuidesApiException
```

**Parametrar**: |Namn|Typ|Beskrivning| |—|—|—| |`session`|javax.jcr.Session|En giltig JCR-session. Användarsessionen måste ha både läs- och skrivbehörighet för DITA-kartan och läsbehörighet för alla referensfiler som ingår i baslinjen.| |``sourcePath``|String|Absolut sökväg för DITA-mappningsfilen i AEM.| |`baselineTitle`|String|En unik rubrik för baslinjen.| |`versionDate`|Datum|Baslinjen skapas med hjälp av de versioner av ämnen\(som refereras direkt från DITA-kartan\) som på detta datum. Ange datumet i `d-MM-yyyy H:mm` format.|

**Returnerar**: Baslinjens namn, som är baslinjens nodnamn i JCR-databasen. Titeln på den nyskapade baslinjen visas för användaren på sidan Baslinje för DITA-kartan.

**Undantag**: Throws ``RepositoryException.``

## Använd etiketter

The ``applyLabel`` använder du en eller flera etiketter på filerna i en baslinje.

**Syntax**:

```JAVA
public static void applyLabel(Session session,
                  String sourcePath,
                  String baselineName,
                  String label)
                  throws RepositoryException, WorkflowException, Exception
```

**Parametrar**: |Namn|Typ|Beskrivning| |—|—|—| |`session`|javax.jcr.Session|En giltig JCR-session.| |`sourcePath`|String|Absolut sökväg för DITA-mappningsfilen i AEM.| |``baselineName``|String|Namnet på baslinjenoden som etiketten ska användas på. Om du vill hämta namnet på baslinjenoden kan du använda [\#id185NFF0085Z](#id185NFF0085Z) eller kontrollera baslinjenoden för DITA-kartan i CRXDE.<br> **Obs!** Etikett används på versioner av filer som är direkt refererade från kartfilen i baslinjen.| |`label`|String|En etikett som används på filer i baslinjen. Se till att etiketten inte innehåller följande tecken: &amp;sol; &amp;komma; &amp;kolon; komma; &amp;komma; brack; komma; &amp;rack; komma; &amp;komma; &amp;vertera; &amp;komma; &amp;ast; <br> Om du vill ange flera etiketter avgränsar du dem med kommatecken, till exempel Label1, Label2.|

**Undantag**: Throws `RepositoryException`.

## Ta bort etiketter

The ``deleteLabel`` tar bort en eller flera etiketter från filerna i en baslinje.

**Syntax**:

```JAVA
public static Map
<String, String> deleteLabel(Session session, 
String sourcePath, 
String baselineName, 
String label) throws GuidesApiException
```

**Parametrar**: |Namn|Typ|Beskrivning| |—|—|—| |`session`|javax.jcr.Session|En giltig JCR-session.| |`sourcePath`|String|Absolut sökväg för DITA-mappningsfilen i AEM.| |`baselineName`|String|Namnet på baslinjen som etiketten ska tas bort från. <br> **Obs!** Etikett tas bort från den version av filer som är direkt refererade från kartfilen i baslinjen.| |`label`|String|En etikett som ska tas bort från filer i baslinjen. <br> Om du vill ta bort flera etiketter avgränsar du dem med kommatecken, till exempel Label1, Label2.|

**Returnerar**: Kartan med *nyckel:värde* par av `path:deletedlabels` för alla filer i baslinjen.

**Undantag**: Throws ``RepositoryException`, `VersionException`, `Exception``.
