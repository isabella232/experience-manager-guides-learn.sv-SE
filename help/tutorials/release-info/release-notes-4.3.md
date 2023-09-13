---
title: Versionsinformation | Uppgraderingsinstruktioner och åtgärdade fel i Adobe Experience Manager Guides 4.3.0
description: Lär dig mer om felkorrigeringarna och hur du uppgraderar till 4.3.0-utgåvor av Adobe Experience Manager Guides
source-git-commit: b53f76c2f0234c1ef6c65d954311e3f8c980ffe2
workflow-type: tm+mt
source-wordcount: '998'
ht-degree: 4%

---

# 4.3.0-utgåvan av Adobe Experience Manager Guides (juli 2023)

Den här versionsinformationen innehåller uppgraderingsinstruktioner, kompatibilitetsmatris och problem som har korrigerats i version 4.3.0 av Adobe Experience Manager Guides (senare kallat *AEM stödlinjer*).

Mer information om de nya funktionerna och förbättringarna finns i [Nyheter i version 4.3.0 av Adobe Experience Manager Guides](./whats-new-4.3-release.md).

## Uppgradera till version 4.3.0 av AEM


Du kan enkelt uppgradera din nuvarande version av AEM till version 4.3.0. Innan du uppgraderar till version 4.3.0 av AEM Guides måste du tänka på följande: Du kan uppgradera din nuvarande version av AEM Guides till version 4.3.0

- Om du använder version 4.2 eller 4.2.x kan du uppgradera direkt till version 4.3.0.
- Om du använder version 4.1 eller 4.1.x måste du uppgradera till version 4.2 eller 4.2.x innan du uppgraderar till version 4.3.0.
- Om du använder version 4.0 måste du uppgradera till version 4.2 innan du uppgraderar till version 4.3.0.
- Om du använder version 3.8.5 måste du uppgradera till version 4.0 innan du uppgraderar till version 4.2.
- Om du har en version som är äldre än 3.8.5, se avsnittet om AEM i den produktspecifika installationshandboken.



>[!NOTE]
>
>Du måste installera AEM Service Pack innan du uppgraderar AEM Guides version.

Mer information finns i [Uppgraderingsinstruktioner](../install-guide/upgrade-xml-documentation.md).

## Kompatibilitetsmatris

I det här avsnittet visas kompatibilitetsmatrisen för de program som stöds i AEM 4.3.0.

### Adobe Experience Manager

**4.3.0 Ej UUID**
Version 6.5 Service Pack 18, 17, 16, 15 eller 14

**4.3.0 UUID**
Version 6.5 Service Pack 18, 17, 16, 15 eller 14

Mer information finns i *Tekniska krav* i guiden Installera och konfigurera Adobe Experience Manager Guides.

### FrameMaker och FrameMaker Publishing Server

| Frigör | FMPS 2022 | FMPS 2020 | Fm 2022 | Fm 2020 |
| --- | --- | --- | --- | --- |
| 4.3.0 (ej UUID) | 2022 eller senare | 2020.2 eller senare* | 2022 eller senare | 2020.3 eller senare |
| 4.3.0 (UID) | 2022 eller senare | 2020.2 eller senare* | 2022 eller senare | 2020.4 eller senare |
| | | | |

*Originalplan och villkor skapade i AEM stöds i FMPS-versioner från och med 2020.2.

### Syrgasanslutning

| Frigör | Syrgasanslutningsfönster | Syrgasanslutning Mac | Redigera i syrgasfönster | Redigera i Syrgas Mac |
| --- | --- | --- |--- |--- |
| 4.3.0 (ej UUID) | 2.3-regular-5 | 2.3-regular-5 | 1.6 | 1.6 |
| 4.3.0 (UID) | 3.0-uuid-4 | 3.0-uuid-3 | 2.3 | 2.3 |
|  |  |   |

## Åtgärdade problem

De buggar som har åtgärdats i olika områden listas nedan:

### Redigering

- Ämnesfilen är inte olåst i Web Editor, även om alternativet Lås upp fil och alternativet Spara inte är markerat. (12558)
- Det går inte att checka ut en fil i webbredigeraren, trots att du har valt alternativet NEJ för att ignorera ändringarna före incheckning. (12557)
- Verktygstipsen för filikonerna Lås och lås upp i huvudverktygsfältet i Web Editor är inte konsekventa med de ikoner som visas i databasvyn.(12555)
- Alternativet Avbryt utcheckning och Lås upp visas för en fil i Web Editor som ännu inte är utcheckad i Kartvyn. (12556)
- Det går inte att markera PDF-resurserna i de befintliga topicref-länkarna. (12477).
- När du sammanfogar och delar i tabeller genererar AEM 4.2 ytterligare tabellceller. (11793)
- I databasvyn kan du inte dra ämnen eller bilder efter att du har använt funktionerna Sök/Filter. (12396)
- Sökresultaten inaktiveras på panelen Sök och ersätt när du har öppnat en sökad fil. (12142)
- Siffertangenten&quot;8&quot; på sidotangentbordet fungerar inte i redigeraren AEM stödlinjer. (12106)
- Textbundna attribut/visningsattribut visas inte i layoutvyn i Web Editor. (12498)
- Konfigurationen för det globala profilanvändargränssnittet matchar inte mappprofilen. (11970)
- Innehållsreferenser bryts när DITA-filer kopieras och klistras in. (11959)
- Det går inte att redigera innehållsfragment i kolumnvyn med AEM stödlinjer installerade. (7342)
- Innehållet förloras när en unwrapped xref finns under en underordnad elementtagg. (12532)
- Arbetsflödet för godkännande fungerar inte när dokumentläget ändras till slutläge från filegenskaperna på den högra panelen. (11026)
- Resursgränssnitt | I listvyn går det inte att sammanfoga de överlagrade kolumnerna. (11528)
- Keyref är inte löst i kartvyn. (11490)
- Den övre menyn visas inte när du navigerar i XML-redigeraren. (10868)
- `conref` in ph-tagg | Den visade bläddringsdialogrutan är felaktig. (9481)
- Lokala länkar till andra element kan inte lösas i Web Editor. (8790)
- Funktionen Matches() fungerar inte i funktionen Schematron. (11224)



### Förvaltning

- Fältet &quot;title&quot; i DITA-mappningens metadataegenskaper skrivs över av `<title>` kartelementet. (10702)
- När du försöker öppna eller uppdatera versionen av ämnen i baslinjen körs inläsaren &quot;Hämtning av information från servern&quot; oavbrutet.(12478)


### Granska

- Nytt gränssnitt för granskning | Villkoren markeras och visas och fungerar annorlunda än de fungerar i Web Editor. (11628)

### Publicering

- Publiceringen misslyckas när namnet på en förinställning för inbyggda PDF ändras. (12564)
- När du duplicerar en inbyggd PDF-mall dupliceras den till standardmallplatsen i stället för den angivna anpassade mallplatsen. (12563)
- PDF | Språkmetadata kan inte anges i det genererade PDF för att uppfylla kraven i WCAG 2.0. (12407)
- Publicering till AEM misslyckas när temporära filer från pod som kan ha uppdaterats eller startats om läses. (12113)
- PDF | Anpassade attribut sprids inte till motorn för temporära HTML eller PDF. (DXML-12005)
- PDF | Java OutOfMemoryError inträffar vid publicering av stort innehåll. (11789)
- PDF | Xref skriver ut innehållet i href-ämnesrubriken i stället för Xref-etiketten. (11322)
- PDF | Det går inte att spara mallinställningarna för PDF. (10751)
- PDF | Texten sträcker sig utanför kolumnbredden och inkluderar flera xrefs. (10876)
- PDF | `<note>``</note>` -elementet genererar ingen extra intervalltitel av sin typ. (10549)
- JSON-utdata | De `fmUuid` -egenskapen i jcr:content-noden i JSON skiljer sig från&quot;id&quot; i JSON. (11564)
- JSON-utdata | Om det finns en karta och ett ämne med samma filnamn tas JSON bort för kartan. (11524)

## Känt fel

Adobe har identifierat följande kända problem i AEM 4.3.0-versionen:

- En gemensam sidlayout som definieras i den grundläggande mallen används inte som standardmall.

  Tillfällig lösning: Lägg till gemensam sidlayout som fram- och baksida så börjar det gälla för varje sida.
- Ett problem uppstår i Webbplatssökning när du söker på AEM webbplats utdatasida AEM Service Pack 16 eller 17.

  Lösning:

   1. Öppna filen med sökvägen: `/libs/foundation/components/search/search.jsp` in `crx/de`
   1. Ersätt radnummer 234 med följande kod:

      ```
      <a href="<c:url value="${hit.URL}" context="/"/>" onclick="trackSelectedResult(this, ${status.index + 1})"><%= xssAPI.filterHTML(((Search.Hit) pageContext.getAttribute("hit")).getTitle()) %></a>
      
      *(Add the missing closing anchor tag at the end).
      ```

   1. Spara filen.