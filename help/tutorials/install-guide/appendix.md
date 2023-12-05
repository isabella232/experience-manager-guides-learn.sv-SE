---
title: Bilaga
description: Lär dig hur du förbereder InDesigner för konvertering
source-git-commit: 880cd344ceb65ea339be699ebcad41c0d62e168a
workflow-type: tm+mt
source-wordcount: '2851'
ht-degree: 0%

---

# Bilaga {#id195AD0L60Y4}

## Förbered InDesign-filer för konvertering {#id195DBF0045Z}

InDesign ger författarna en mängd funktioner för att skapa attraktiva och komplexa dokument. Det innebär ofta att de olika delarna av ett dokument placeras visuellt på sidan, men att inget försök görs att skapa något flöde mellan dessa textramar. När *läsordning*&#39; of the text frames is not defined, the IDML file will contain stories that may not follow any purpose order. Slutresultatet blir ett eller flera DITA-avsnitt med stycken, tabeller och bilder i slumpmässig ordning.

Även om det går att redigera DITA-innehåll i en vettig ordning i en DITA-redigerare är det mycket enklare att åtgärda InDesignen innan du skapar IDML-filen. Detta kan du göra utan att ändra utseendet på källdokumentet. Det har också fördelen att göra källdokumentet tillgängligt genom att rätt definiera läsordningen.

***Koppla textramar***

InDesignen använder termen *&#39;threading&#39;* för att länka en ram till en annan. Mer information om att koppla textramar finns i *[Koppla text](https://helpx.adobe.com/in/indesign/using/threading-text.html)* i InDesignens dokumentation.

***Överlappande bildrutor***

I vissa InDesigner används icke-kopplade överlappande bildrutor av layoutskäl. Det kan vara mycket svårt att sammanfoga det här innehållet i huvudtråden. Det bästa alternativet kan vara att redigera resultatet i DITA-miljön.

***InDesigner***

Varje kopplat innehållsflöde i ett InDesign-dokument kallas *artikel*&#39;. För bästa resultat rekommenderar vi att du begränsar antalet artiklar. Det finns dock vissa delar av dokumentet som kanske inte behövs i DITA-utdata. Sidfötter behövs till exempel sällan, men de kan visas mitt i ett avsnitt om de inte hanteras försiktigt.

Det enklaste sättet att exkludera text som inte behövs i dokumentet är att ge den ett särskilt sätt *Stycke* som bara används för det oönskade innehållet. I stället för att återanvända en *\[Allmänt stycke\]* för sidfoten, skapa en dedikerad *Sidfot* -tagg. I filen MapStyle anger du sedan bara *Sidfot* stycken som ska tas bort så här:

```XML
<paraRule style="Footer" local="0" refactor="drop">
   <attributeRules createID="false"/>
</paraRule>
```

***Mappa till DITA-dokumenttyper***

Det är viktigt att källdokumentet har minst ett styckeformat eller -element som kan markera början av ett ämne. Det är vanligt att dokument används *Rubrik1* som namnet på de översta rubrikerna i dokumentet. Du kan sedan skapa en koppling från det formatet till en viss DITA-dokumenttyp. Om ditt dokument är välorganiserat och om du använder *Rubrik1* är konstant hela tiden, så får du bra resultat.

***Flera DITA-dokumenttyper***

Om en del av *Rubrik1* stycken måste konverteras till olika DITA-dokumenttyper och sedan dupliceras styckeformatet i InDesign. Ge dessa format ett enkelt namn som *Rubrik1\_genAktivitet* eller *Rubrik1\_felsökning* i tillämpliga fall. Konfigurera sedan filen mapStyle enligt nedan:

```XML
<doctypes>
   <doctypeParaRule style="Heading1" local="0" mapToDoctype="concept">
      <attributeRules createID="true"/>
   </doctypeParaRule>
   <doctypeParaRule style="Heading1_genTask" local="0" mapToDoctype=" generalTask">
      <attributeRules createID="true"/>
   </doctypeParaRule>
   <doctypeParaRule style="Heading1_troubleshooting" local="0"mapToDoctype=" troubleshooting">
      <attributeRules createID="true"/>
   </doctypeParaRule>
</doctypes>
```

***Dokument med strukturerad InDesign***

InDesignen har ett löst förhållande till XML. Även om ett dokument kan innehålla en DTD för XML och huvudartikeln kan vara giltig mot DTD-filen, går det också att skapa hybriddokument där en del av innehållet är XML, men inget DTD-dokument inkluderas. Detta är de oönskade fallen vid en lyckad konvertering till DITA. Om ett dokument innehåller XML-delar kan du försöka spara utdata i XML-format och se om resultaten är godtagbara. Annars kommer DITA-innehållet också att innehålla ogiltigt innehåll eller misslyckas helt.

***Tabellformatering***

Konverteringen från tabellformateringsregler för InDesign till motsvarande tabellformatering i DITA är en komplex process. Detta beror på de omfattande formateringsfunktioner som finns i källfilerna jämfört med de grundläggande alternativen i Oasis \(CALS\)-tabellmodellen som används i DITA. Lodrät och vågrät textjustering tillhandahålls och ger liknande resultat, även om Justerad text alltid justeras enligt textriktningen, medan InDesign tillåter Vänsterjusterad och Högerjusterad.

InDesignens hantering av kolumn- och radavgränsare är nu ännu mer användbar än tabellmodellens grundläggande alternativ i Oasis. InDesign har fyra cellkanter - Kantlinjetyp \(heldragen eller mönster\), Kantbredd, Kantfärg, Kantfärg, Kantmellanrumsfärg och Kantmellanrumston. Alla dessa måste mappas nedåt till kantlinjer till höger och nederst i varje cell \(entry element\) där de enda alternativen är 0 eller 1 - dölj kantlinjen eller visa kantlinjen.

Kantlinjering i InDesign kan användas på följande nivåer:

- Tabellformat
- Cellformat
- Lokala åsidosättningar i varje cell

InDesignen till DITA-konverteringsprocessen tillämpar kantlinjalen enligt följande:

- Tabellformat kopplas till `colspec/@colsep` för lodräta regler. Vågräta linjer mappas till `row/@rowsep` -attribut. I båda fallen skapas inte attributet om kantlinjen inte är definierad.
- Cellformat kopplas till `entry/@colsep` och `entry/@rowsep` attribut. Dessa värden åsidosätter alla härledda kanter i tabellformat.
- Med lokala åsidosättningar används formateringen direkt i cellen och tabellformat och cellformat åsidosätts.

***Alternerande mönster***

Med tabellformat för InDesigner kan stapel- och cellinjer följa ett alternerande mönster. Den här funktionen stöds för konvertering, men resultatet blir bara tydligt när en mönstergrupp mappas till reglaget \(1\) och den andra mönstergruppen mappar till att dölja reglaget \(0\).

## Förbered mappningsfilen för InDesign till DITA-migrering {#id194AF0003HT}

För korrekt DITA-konvertering krävs en mappningsfil som matchar innehållet i källdokumentet. För dokument med ostrukturerad InDesign innebär detta att alla tillgängliga styckeformat och teckenformat måste kopplas. För dokument med XML-strukturerad InDesign måste alla element i tillhörande DTD mappas.

Mappningsfilerna för ostrukturerade och strukturerade InDesigner är olika. Detta beror på de mer komplexa bearbetningskrav som ställs för att konvertera ostrukturerat källinnehåll till DITA.

Nedan visas ett exempel på mappningsfilen:

```XML
<?xml version="1.0" encoding="UTF-8"?>
<!DOCTYPE styleMap SYSTEM "mapStyle.dtd">
<styleMap xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" xsi:noNamespaceSchemaLocation="mapStyle.xsd" >
   <doctypes>
      <mapDoctypeParaRule root="itpx:stories" mapToDoctype="map">
         <attributeRules createID="true">
            <addNew name="outputclass" value="map"/>
         </attributeRules>
      </mapDoctypeParaRule>
      <doctypeParaRule style="Heading 1" local="0" mapToDoctype="concept">
         <attributeRules createID="true"/>
      </doctypeParaRule>
      <doctypeParaRule style="Heading A" local="0" mapToDoctype="topic">
         <attributeRules createID="true"/>
      </doctypeParaRule>
   </doctypes>
   <wrappingRules>
      <wrap elements="li+" context="number" wrapper="ol">
         <attributeRules createID="true"/>
      </wrap>
      <wrap elements="li+" context="bullet" wrapper="ul">
         <attributeRules createID="true"/>
      </wrap>
   </wrappingRules>
   <paragraphStyleRules>
      <paraRule style="Heading 2" local="0"  mapTo="p">
         <attributeRules createID="true"/>
      </paraRule>
      <paraRule style="Heading 3" local="0"  mapTo="p">
         <attributeRules createID="true"/>
      </paraRule>
      <paraRule style="List Paragraph" local="p[-|-|-|-|-|b|-|-]" context="bullet" mapTo="li">
         <attributeRules createID="true"/>
      </paraRule>
      <paraRule style="List Paragraph" local="p[-|-|-|-|-|n|-|-]" context="number" mapTo="li">
         <attributeRules createID="true"/>
      </paraRule>
      <paraRule style="List Paragraph" local="0" context="bullet" mapTo="li">
         <attributeRules createID="true"/>
      </paraRule>
      <paraRule style="Normal" local="0"  mapTo="p">
         <attributeRules createID="true"/>
      </paraRule>
      <paraRule style="Normal" local="p[-|-|-|-|-|b|-|-]" context="bullet" mapTo="li">
         <attributeRules createID="true"/>
      </paraRule>
      <paraRule style="Title" local="0"  mapTo="p">
         <attributeRules createID="true"/>
      </paraRule>
   </paragraphStyleRules>
   <characterStyleRules>
      <charRule style="Bold" local="0" mapTo="b">
         <attributeRules createID="false"/>
      </charRule>
      <charRule style="Code" local="0" mapTo="codeph">
         <attributeRules createID="false"/>
      </charRule>
      <charRule style="[No character style]" local="c[Bold|-|-|-|-|-|-|-]" mapTo="b">
         <attributeRules createID="false"/>
      </charRule>
      <charRule style="[No character style]" local="c[Italic|-|-|-|-|-|-|-]" mapTo="i">
         <attributeRules createID="false"/>
      </charRule>
   </characterStyleRules>
</styleMap>
```

Kopplingsfilen är en XML-fil med en enkel struktur som visar alla källstyckeformat och teckenformatkoder. Filinnehållet förklaras nedan:

**Koppla format**

I `styleMap` -element kan du ange två valfria attribut - `@map_date` och `@map_version` för att spela in mappningsfilens version.

**Dokumenttyp**

The `doctypes` -elementet listar DITA-kartor och ämnesmappningar som stöds.

**Koppla styckelinjer för dokumenttyp**

The `mapDoctypeParaRule` -element är obligatoriskt. Elementets attribut får inte redigeras eftersom käll-XML:ens rotelement alltid är mappat till DITA-mappningens rot `map` -element.

**Styckelinje för dokumenttyp**

The `doctypeParaRule` -element är obligatoriskt. Detta ger konverteringsprocessen ett sätt att identifiera början på ett nytt ämne. Normalt visas `@style` -attributet används ensamt med `@local` -attributet har värdet 0. Om det alltid finns lokala formateringsåsidosättningar i det valda formatet måste du lägga till en regel för varje format plus lokala åsidosättningar. Detta är enkelt att känna igen i den genererade mappningsfilen där det är möjligt att hitta detta eller liknande:

```XML
<paraRule style="Heading 1" local="0" mapTo="p">
   <attributeRules createID="true"/>
</paraRule>
<paraRule style="Heading 1" local="p[Italic|-|-|-|-|-|-|-]" mapTo="p">
   <attributeRules createID="true"/>
</paraRule>
```

I exemplet ovan finns två `paraRule` element för `@style` = &quot;Rubrik1&quot;. Skapa en motsvarighet `doctypeParaRule` -element med `@mapToDoctype` attributet har angetts som obligatoriskt.

Attributen som används i `doctypeParaRule` förklaras nedan:

- `@style`: Namnet på ett format i källdokumentet för InDesign.
- `@local`: Se [\#id194CG0V005Z](#id194CG0V005Z).
- `@mapToDoctype`: Namnet på en DITA-ämnestyp från en numrerad lista med alla giltiga `doctypes`.

**Regler för elementomslutning**

Reglerna för elementomslutning definierar hur element i det inkommande dokumentet ska radbrytas eller flyttas till ett fördefinierat element enligt en uppsättning attributvärden.

***`wrap`element***

Detta är ett valfritt element. The `wrap` -elementet visar de element som kommer att kapslas eller flyttas. Figursättning används vanligtvis när en serie element måste tilldelas ett gemensamt överordnat element. Till exempel flera `li` element som radbryts i en `ol` -element. Dessutom `wrap` kan användas för rörliga element som rubriker för figurer och tabeller.

Attributen som används i `wrap` förklaras nedan:

- `@element`: Ett plustecken efter ett elementnamn visar att alla intilliggande element med samma namn kommer att kapslas in i elementet som namnges i `@wrapper`-attribut.
- `@wrapper`: Namnet på figursättningselementet.
- `@context`: Innehåller ett sätt att ytterligare förfina hur ett visst element radbryts. I följande exempel visas ett sätt att mappa en serie `li` element i antingen en ordnad lista `ol` eller en osorterad lista `ul` enligt `@context` värdet \(kontexten definieras på `paraRule` element\):

  ```XML
  <wrap elements="li+" context="number" wrapper="ol">
     <attributeRules createID="true"/>
  </wrap>
  <wrap elements="li+" context="bullet" wrapper="ul">
     <attributeRules createID="true"/>
  </wrap>
  ```


I följande exempel visas hur du skapar en `fig` element från `title` och `image` element:

- `@elements`: Elementen som anges och avgränsas med kommatecken radbryts i elementet som namnges i `@wrapper` -attribut. På grund av det vanliga sättet att ta med bildtitlar under bilden blir titeln `title` element omedelbart efter `image`.

  Följande radbrytningsregel:

  ```XML
  <wrap elements="title, image" context="FigTitle" wrapper="fig">
     <attributeRules createID="true"/>
  </wrap>
  ```

  Konverterar följande mellanliggande XML:

  ```XML
  <image href="Links/myImage.png" scale="59">
     <title>IDML2DITA workflow</title>
  ```

  I följande giltiga DITA-figurstruktur:

  ```XML
  <fig id="id397504">
     <title>IDML2DITA workflow</title>
     <image href="Links/myImage.png" scale="59">
  </fig>
  ```

- `@wrapper`: Namnet på figursättningselementet.
- `@context`: Innehåller ett sätt att ytterligare förfina hur ett visst element bryts \(sammanhanget definieras på `paraRule` element\).

I följande exempel visas hur du flyttar en `title` till en `table`:

- `@elements`: `title` element som finns omedelbart före eller omedelbart efter `table` kommer att kapslas in i elementet som namnges i `@wrapper` -attribut. Ett XPath-liknande predikat kan identifiera positionen för title-elementet som `[before]` eller `[after]`.

  Exempel: Följande radbrytningsregel:

  ```XML
  <wrap elements="title[before]" context="TableTitle" wrapper="table">
     <attributeRules createID="true"/>
  </wrap>
  ```

  Konverterar följande mellanliggande XML:

  ```XML
  <title>IDML2DITA workflow</title>
  <table id="id289742" outputclass="BasicTable">
     <tgroup cols="2">
        <colspec colname="0" colwidth="0.7*">
           <colspec colname="1" colwidth="0.3*">
  ```

  I den här giltiga DITA-figurstrukturen:

  ```XML
  <table id="id289742" outputclass="BasicTable">
     <title>IDML2DITA workflow</title>
     <tgroup cols="2">
        <colspec colname="0" colwidth="0.7*">
           <colspec colname="1" colwidth="0.3*">
  ```

- `@wrapper`: Namnet på figursättningselementet.

- `@context`: Innehåller ett sätt att ytterligare förfina hur ett visst element bryts \(sammanhanget definieras på `paraRule` element\).


**Regler för styckeformat**

The `<paragraphStyleRule>` beskrivs nedan:

***`paraRule`element***

The `paraRule` -element är obligatoriskt. Detta anger mappningsreglerna för alla styckeformat. I ett textdokument finns all InDesign i en understruktur till styckeformatmallar, även stycken utan format namnges `[No paragraph style]`. De här hakparenteserna anger ett inbyggt namn på InDesignen.

>[!NOTE]
>
> Hakparenteserna anger ett inbyggt namn på InDesignen.

Attributen som används i `paraRule` förklaras nedan:

- `@style`: Namnet på ett format i källdokumentet för InDesign.
- `@local`: Se [\#id194CG0V005Z](#id194CG0V005Z).
- `@mapTo`: Namnet på ett DITA-målelement.

- `@context`: Det här attributet används för att länka till ett specifikt **bryt** -regel när mer än ett radbrytningsalternativ är tillgängligt. Exempel: `li` -element kan kapslas i antingen en `ol`, eller en `ul` -element. Om du vill identifiera de olika listtyperna kan du använda ett specifikt formatnamn eller `@local` som kan visa följande:
   - `local="p[-|-|-|-|-|b|-|-]"` Där &#39;`b`&#39; i fält 6 anger ett punktlisteobjekt. I det här fallet `@context` till &#39;`bullet`&#39;.
   - `local="p[-|-|-|-|-|n|-|-]"` Där &#39;`n`&#39; i fält 6 anger ett numrerat listobjekt. I det här fallet `@context` till &#39;`number`&#39;.

- `@commentOut`: Det här attributet aktiverar kapsling av målelementet i XML-kommentarer så att informationen inte går förlorad utan kan hanteras manuellt av användaren. Detta är användbart om källinnehållet inte kan tvingas att följa DITA-strukturregler.

- `@refactor`: Det här valfria attributet kan ha två värden:

- `unwrap`: Det matchande elementet tas bort samtidigt som innehållet behålls.

- `drop`: Det matchande elementet och allt dess innehåll tas bort.


**Teckenformatregler**

The `charRule` beskrivs nedan:

>[!NOTE]
>
> Det kommer inte att finnas någon mappning för det inbyggda teckenformatet `[No character style]` när `local="0"`, eftersom de tas bort under förbearbetningen.

***`charRule`element***

Detta är ett valfritt element.

Detta är mappningsreglerna för alla teckenformat. I ett textdokument finns all InDesign i underordnade element till teckenformat.

Attributen som används i `charRule` förklaras nedan:

- `@style`: Namnet på ett format i källdokumentet för InDesign.
- `@local`: Se [\#id194CG0V005Z](#id194CG0V005Z).
- `@mapTo`: Namnet på ett DITA-målelement.
- `@refactor`: Det här valfria attributet kan ha två värden:
   - `unwrap`: Det matchande elementet tas bort samtidigt som innehållet behålls.

   - `drop`: Det matchande elementet och allt dess innehåll tas bort.


**Attributregler**

Det här elementet kan vara underordnat följande elementkontexter:

- `mapDoctypeParaRule`
- `mapDoctypeElemRule`
- `doctypeParaRule`
- `doctypeElemRule`
- `paraRule`
- `charRule`
- `elementRule`

Syftet med attributregler är att hantera attributen för de matchade elementen.

Beroende på sammanhanget är följande attribut tillgängliga för `attributeRules` element:

- `@createID`: Skapar ett unikt ID för matchande element. Tillåtna värden `true` eller `false`. Finns i alla sammanhang.
- `@copyAll`: Kopierar endast alla attribut från XML-källinnehållet för strukturerade källfiler. Tillåtna värden är `true` eller `false`. Tillgängligt för kontexter `mapDoctypeParaRule`, `mapDoctypeElemRule`, `doctypeElemRule` och `elementRule`.


Attributen som används i `attributeRules` förklaras nedan:

>[!NOTE]
>
> Det här elementet kan innehålla flera underordnade element.

- `addNew`: Lägger till ett nytt attribut i det matchande elementet. Tillgängligt för alla kontexter. Den har två attribut:
   - `@name`: Måste vara ett giltigt XML-namn, helst giltigt för DITA-kontexten.
   - `@value`: Kan vara literal text eller ett enkelt XPath-uttryck.
- `copyAtt`: Kopierar ett enskilt attribut till målet och kan även byta namn på det i processen. Värdet ändras inte. Tillgängligt för kontexter `mapDoctypeParaRule`, `mapDoctypeElemRule`, `doctypeElemRule` och `elementRule`. När det här elementet finns visas `@copyAllAtts` värdet antas `false`. Den har två attribut:
   - `@name`: Måste vara namnet på ett attribut som finns i käll-XML-elementet.
   - `@mapTo`: Måste vara ett giltigt XML-namn, helst giltigt för DITA-kontexten.

**Lokala formateringskoder**

I alla slags InDesigner kan det finnas flera hundra olika formatåsidosättningar för styckeformat och teckenformat. De flesta av dessa egenskaper har ingen användbar roll i konverteringsprocessen. Vi har dock identifierat en viktig uppsättning formateringsfunktioner som påverkar dokumentets semantik och som måste påverka konverteringsprocessen.

The `@local` attribut anges som ett särskilt avgränsat format där åtta fält anges tillsammans med ett prefix som visar typen av formateringsåsidosättning. Formateringskodfälten visas nedan:

- Prefix **p** lokal åsidosättning eller **c** för lokal åsidosättning av teckenformat.
- **Teckensnittsformat** som är familjenamnet och egenskaper som &#39;***Fet kondenserad kursiv***&#39;.
- **Teckenstorlek** i punkter.
- **Teckenposition** för upphöjd eller nedsänkt text.
- **Under** för understreck.
- **Genomstrykning** för genomstrykning.
- **Listkod** för att identifiera listtyp som punktlistor eller numrerade - används inte alltid som InDesign.
- **Punktkod** listar alla definierade punkttyper i dokumentet.
- **Nummerkod** visar alla definierade numreringsformat i dokumentet.

Om du använder den här funktionen noggrant kan du spara lokal formatering vilket kan förbättra kvaliteten på en överföring från formaterat innehåll till DITA. Det här exemplet kan tolkas som kursiv, 16pt text i en punktlista: `p[Italic|16|-|-|-|b|-|-]`.

**Strukturmappning**

Strukturmappningsfilen liknar formatmappningsfilen med en enkel struktur som listar alla källelement och relevanta attributtyper. Två attribut: `@map_date` och `@map_version` finns för att spela in den version av mappningsfilen som ska användas.

**Dokumenttyp**

The `doctypes` -elementet listar DITA-kartor och ämnesmappningar som stöds.

**Koppla elementregler för dokumenttyp**

The `mapDoctypeElemRule` -element är obligatoriskt. Elementets attribut får inte redigeras eftersom käll-XML:ens rotelement alltid är mappat till DITA-mappningens rot `map` -element.

**Regler för elementomslutning**

**`elementRules`element** Här listas alla element.

**`elementRule`element** The `elementRule` -element är obligatoriskt. Detta är mappningsreglerna för alla källelement. Ett dokument innehåller ostrukturerade formatelement, men de ignoreras för strukturerat innehåll såvida inte &#39;***hybridläge*** Bearbetning är aktiverat.

Attributen som används i `elementRule` förklaras nedan:

- `@elementName`: Namnet på ett element i källdokumentet för InDesign.

- `@local`: Se [\#id194CG0V005Z](#id194CG0V005Z). \(Endast användbart för hybrid-dokument\).

- `@mapTo`: Namnet på ett DITA-målelement.

- `@refactor`: Det här valfria attributet kan ha två värden:

   - `unwrap`: Det matchande elementet tas bort samtidigt som innehållet behålls.

   - `drop`: Det matchande elementet och allt dess innehåll tas bort.

- `@context`: Det här attributet används för att länka till en viss radbrytningsregel när mer än ett radbrytningsalternativ är tillgängligt. Exempel: `li` -element kan kapslas i antingen en `ol`, eller en `ul` -element.

- `@commentOut`: Det här attributet aktiverar kapsling av målelementet i XML-kommentarer så att informationen inte går förlorad utan kan hanteras manuellt av användaren. Detta är användbart om källinnehållet inte kan tvingas att följa DITA-strukturregler.


## Felsökning AEM guider

När du har installerat och konfigurerat AEM kan du felsöka problemen.

## Validera referenser

Du kan köra de angivna skripten för att validera referenserna. Dessa skript kan hjälpa dig att identifiera de brutna referenserna och sedan korrigera eller åtgärda dem.

- `/bin/fmdita/validatebtree?operation=validate` - rapporterar eventuella brutna innehållsreferenser, men korrigerar dem inte.
- `/bin/fmdita/validatebtree?operation=patch`- visar brutna innehållsreferenser och korrigerar dem.

**Validera skript**

Gör så här för att kontrollera referenserna med det valideringsskript som finns i produktpaketet:

1. Kör valideringsskriptet \[`/bin/fmdita/validatebtree?operation=validate`\] för att kontrollera om det finns några nya brutna referenser.
1. Om valideringsskriptet rapporterar fel kan du åtgärda det med hjälp av korrigeringsskriptet.
1. Registrera nedanstående uppgifter och dela dem vid behov med kundens framgångsgrupp:
1. 
   - Loggar som skrivs ut med valideringsskript
- Paketet med`/content/fmdita/references`&quot;
- Övriga obligatoriska uppgifter beroende på scenario som rapporteras

**Lappa skript**

Utför följande steg för att korrigera eventuella brutna referenser med hjälp av det korrigeringsskript som finns i produktpaketet:

1. Kör korrigeringsskriptet `[/bin/fmdita/validatebtree?operation=patch]` för att korrigera brutna referenser. Skriptkörningen tar några minuter och skriver ut loggarna medan den fortsätter. När exekveringen är klar skrivs den ut`Done`&quot; i slutet.

   **Obs!* Vi rekommenderar att du kopierar och sparar loggarna i referenssyfte.

1. När korrigeringsskriptet har körts kan du utföra följande kontroller:
1. 
   - Kontrollera en ny nod &quot;`references_backup_<timestamp>"` har skapats under `/content/fmdita`
- Kontrollera att referenserna har åtgärdats

**Logger**

Du kan också skapa en separat loggare för den här skriptkörningen enligt informationen nedan:

- Lägg till en loggare för klassen`adobe.fmdita.common.BTreeReferenceValidator`&quot;
- Ställ in den på `DEBUG`

Den skapade loggfilen registrerar all information som är relaterad till skriptkörning och är användbar om webbläsarens sessionstimeout skulle inträffa medan skriptet utlöses från webbläsaren.
