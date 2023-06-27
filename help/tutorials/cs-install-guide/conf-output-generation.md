---
title: Konfigurera inställningar för utdatagenerering
description: Lär dig hur du konfigurerar inställningar för generering av utdata
source-git-commit: 4f15166b1b250578f07e223b0260aacf402224be
workflow-type: tm+mt
source-wordcount: '5252'
ht-degree: 0%

---


# Konfigurera inställningar för utdatagenerering {#id181AI0B0E30}

AEM Guides innehåller många konfigurationsalternativ som du kan använda för att anpassa genereringsprocessen för utdata. I det här avsnittet beskrivs alla konfigurationer och anpassningar som kan hjälpa dig att skapa utdata.

## Konfigurera fliken Baslinje på DITA-kartkontrollpanelen {#id223MD0D0YRM}

Så här döljer du fliken Baslinje på DITA-kartkontrollpanelen:

1. Använd instruktionerna i [Konfigurationsåsidosättningar](download-install-additional-config-override.md#) för att skapa konfigurationsfilen.
1. Ange följande \(egenskap\)-information i konfigurationsfilen för att konfigurera baslinjefliken på kartkontrollpanelen.

| PID | Egenskapsnyckel | Egenskapsvärde |
|---|------------|--------------|
| `com.adobe.fmdita.config.ConfigManager` | `hide.tabs.baseline` | Boolean\(`true/false`\).**Standardvärde**: `true` |

>[!NOTE]
>
> Den här konfigurationen är aktiverad som standard och fliken Baslinje är inte tillgänglig på kartkontrollpanelen.

## Konfigurera blandad publicering på en befintlig AEM {#id1691I0V0MGR}

Om du har en AEM webbplats som innehåller DITA-innehåll kan du konfigurera dina AEM webbplatsutdata så att DITA-innehåll publiceras på en fördefinierad plats på platsen. I följande skärmbild av en AEM webbplats visas `ditacontent` noden är reserverad för lagring av DITA-innehåll:

![](assets/publish-in-aem-site.png)

De återstående noderna på sidan redigeras direkt från AEM. Om du konfigurerar publiceringsinställningen för att publicera DITA-innehåll på en fördefinierad plats, säkerställs att inget av ditt befintliga icke-DITA-innehåll ändras i publiceringsprocessen för AEM.

Du måste göra följande konfigurationer på din befintliga webbplats för att tillåta publicering av DITA-innehåll till en fördefinierad nod:

- Konfigurera platsens mallegenskaper

- Lägg till noder på webbplatsen för att publicera DITA-innehåll


Utför följande steg för att konfigurera den befintliga platsens mallegenskaper:

1. Använd Package Manager för att hämta /libs/fmdita/config/templates/default-filen.

   >[!NOTE]
   >
   > Gör inga anpassningar i standardkonfigurationsfilerna tillgängliga i `libs` nod. Du måste skapa en övertäckning av `libs` noden i `apps` noda och uppdatera de nödvändiga filerna i `apps` endast nod.

1. Lägg till följande egenskaper:

   | Egenskapsnamn | Typ | Värde |
   |-------------|----|-----|
   | `topicContentNode` | Sträng | Ange det nodnamn där du vill publicera DITA-innehållet. Standardnoden där DITA-innehåll publiceras av AEM Guides är till exempel: <br> `jcr:content/contentnode` |
   | `topicHeadNode` | Sträng | Ange det nodnamn där du vill lagra metadatainformationen för DITA-innehållet. Standardnoden där metadatainformation lagras i AEM Guides är till exempel: <br> `jcr:content/headnode` |


Nästa gång du publicerar DITA-innehåll med mallkonfigurationer för din webbplats publiceras innehållet i de noder som anges i `topicContentNode` och `topicHeadNode` egenskaper.

## Anpassa AEM {#id166TG0B30WR}

AEM stödlinjer har stöd för att skapa utdatafiler i följande format:

- AEM

- PDF

- HTML5
- ePub
- Anpassade utdata via DITA-OT

För AEM platsutdata kan du tilldela olika designmallar med olika utdatauppgifter. Dessa designmallar kan återge DITA-innehållet i olika layouter. Du kan till exempel ange olika designmallar för interna och externa målgrupper.

Du kan också använda anpassade DITA Open Toolkit-plugin-program \(DITA-OT\) med AEM stödlinjer. Du kan överföra dessa anpassade DITA-OT-plugin-program för att generera utdata från PDF på ett visst sätt.

>[!TIP]
>
> Se *AEM* i guiden för bästa praxis om hur du skapar AEM webbplatsutdata.

### Anpassa designmall för generering av utdata {#customize_xml-add-on}

I AEM används en uppsättning fördefinierade designmallar för att generera AEM webbplatsutdata. Du kan anpassa designmallarna AEM Guides för att generera utdata som passar företagets grafiska profil. En designmall är en samling med olika format \(CSS\), skript \(både server- och klientsidan\), resurser \(bilder, logotyper och andra resurser\) och JCR-noder som knyter samman alla dessa resurser. En designmall kan vara så enkel som ett enda skript på servern med bara ett par JCR-noder, eller en komplex kombination av format, resurser och JCR-noder. Designmallar används av AEM Guides Publishing-undersystemet när AEM genereras och de styr strukturen, utseendet och känslan hos det genererade resultatet.

Det finns ingen begränsning för var designmallresurserna ska placeras på servern, men de är vanligtvis logiskt ordnade efter sin funktion. Standardmallen innehåller till exempel alla JavaScript- och CSS-filer som lagras under `/etc/designs/fmdita/clientlibs/siteoutput/default` mapp. Oavsett var filerna finns länkas de ihop av en samling JCR-noder. Tillsammans utgör dessa JCR-noder och filerna hela designmallen.

Med standarddesignmallen som levereras med AEM stödlinjer kan du anpassa komponenterna för landning, ämne och söksida. Du kan skapa en kopia av standarddesignen och motsvarande referensmallar och ange olika komponenter för att generera önskat utvärde.

Utför följande steg för att ange en egen designmall som ska användas för att generera utdata AEM webbplatsen:

1. Använd pakethanteraren för att hämta standarddesignmallen från följande plats:

   /libs/fmdita/config/templates

1. Skapa en kopia av de hämtade filerna på följande plats i Git-databasen för Cloud Manager:

   /apps/fmdita/config/templates

1. Du måste också hämta och kopiera mallarna som refereras från standardmallnoden. De refererade mallarna placeras under:

   /libs/fmdita/templates/default/cqtemplates

   Egenskaperna för designmallen AEM stödlinjer beskrivs i följande tabell.

   | Egenskap | Beskrivning |
   |--------|-----------|
   | `landingPageTemplate`, `searchPageTemplate`, `topicPageTemplate`, `shadowPageTemplate` | Ange `cq:Template` nod för dessa motsvarande sidor \(landning, sökning och ämne\). Som standard är `cq:Template` noden för dessa sidor finns i `/libs/fmdita/templates/default/cqtemplates` nod. Den här noden definierar strukturen och egenskaperna för landnings-, söknings- och ämnessidorna.<br> The `shadowPageTemplate` används för att optimera det segmenterade innehållet. Du måste ange värdet för den här egenskapen till: `fmdita/templates/default/cqtemplates/shadowpage` <br> **Obs!** Du måste ange ett värde för `topicPageTemplate`. The `landingPageTemplate` och `searchPageTemplate` är valfria egenskaper. Om du inte vill att sök- och landningssidorna ska genereras ska du inte ange dessa egenskaper. |
   | `title` | Ett beskrivande namn på designmallen. |
   | `topicContentNode` | Platsen för noden som ska innehålla DITA-innehållet på en ämnessida. Sökvägen är relativ till ämnessidan. |
   | `topicHeadNode` | Platsen för noden som ska innehålla huvudvärdena \(eller metadata\) som härleds från DITA-innehållet. Sökvägen är relativ till ämnessidan. |
   | `tocNode` | Platsen för noden som ska innehålla innehållsförteckningen. Sökvägen är relativ till landningssidan eller målsökvägen. |
   | `basePathProp` | Egenskapsnamnet för lagring av sökvägen till den publicerade platsens rot. |
   | `indexPathProp` | Egenskapsnamnet för lagring av sökvägen till den publicerade platsens landnings-/indexsida. |
   | `pdfPathProp` | Egenskapsnamnet för lagring av PDF-sökvägen, om generering av ämnet PDF är aktiverat. |
   | `pdfTypeProp` | Egenskapsnamnet för lagring av PDF-genereringens typ. För närvarande innehåller den här egenskapen alltid&quot;Ämne&quot;. |
   | `searchPathProp` | Egenskapsnamnet för lagring av söksidans sökväg, om mallen innehåller en söksida. |
   | `siteTitleProp` | Egenskapsnamnet för lagring av titeln för webbplatsen som publiceras. Den här titeln är vanligtvis densamma som titeln på kartan som publiceras. |
   | `sourcePathProp` | Egenskapsnamnet för lagring av sökvägen till källans DITA-ämne för den aktuella sidan. |
   | `tocPathProp` | Egenskapsnamnet för lagring av sökvägen till TOC-roten för den publicerade webbplatsen. |


>[!NOTE]
>
> När du har skapat en anpassad designmallsnod måste du uppdatera designalternativet i AEM för webbplatsutdata för att kunna använda den anpassade designmallsnoden.

Mer information finns i [Skapa din första Adobe Experience Manager-webbplats](https://experienceleague.adobe.com/docs/experience-manager-learn/getting-started-wknd-tutorial-develop/overview.html?lang=en) och [Grunderna](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/implementing/developing/full-stack/develop-wknd-tutorial.html?lang=en) att utveckla en egen webbplats på AEM.

### Använd dokumenttitel för att generera AEM webbplatsutdata

När du genererar AEM webbplatsutdata spelar det sätt på vilket URL:er genereras en viktig roll för att ditt innehåll ska kunna identifieras. Om du använder UUID-baserade filnamn är det inte sökvänligt att generera URL:er baserade på UUID för dina filer. Som administratör eller utgivare kan du styra hur du vill generera URL:er för AEM webbplatsutdata. AEM Guides ger dig en konfiguration genom vilken du kan välja att generera URL:er AEM platsutdata med hjälp av filens namn i stället för UUID-baserade filnamn. Som standard är det här alternativet aktiverat för UUID-baserade filsystem. Detta innebar att när du genererade utdata AEM platsen för UUID-baserade filsystem, används filens namn för att generera URL:er och inte UUID:n för filerna.

>[!NOTE]
>
> Du kan konfigurera regler så att endast en teckenuppsättning tillåts i URL:er för en AEM webbplatsutdata. Mer information finns i [Konfigurera filnamnssaneringsregler för att skapa ämnen och publicera AEM webbplatsutdata](#id2164D0KD0XA).

Använd instruktionerna i [Konfigurationsåsidosättningar](download-install-additional-config-override.md#) för att skapa konfigurationsfilen. Ange följande \(egenskap\)-information i konfigurationsfilen för att konfigurera URL-generering i AEM platsutdata:

| PID | Egenskapsnyckel | Egenskapsvärde |
|---|------------|--------------|
| `com.adobe.fmdita.config.ConfigManager` | `aemsite.pagetitle` | Boolean \(true/false\). Om du vill generera utdata med sidrubriken ställer du in egenskapen på true. Som standard används filnamnet.<br> **Standardvärde**: false |

### Konfigurera filnamnssaneringsregler för att skapa ämnen och publicera AEM webbplatsutdata {#id2164D0KD0XA}

Som administratör kan du definiera en lista med giltiga specialtecken som tillåts i filnamn, som till slut utgör URL:en för en AEM webbplatsutdata. I tidigare versioner tilläts användare att definiera filnamn som innehåller specialtecken som `@`, `$`, `>`, med mera. Specialtecknen resulterade i kodad URL-adress när AEM webbplatssidor genererades.

Från och med version 3.8 har konfigurationer lagts till för att definiera en lista med specialtecken som tillåts i filnamnen. Som standard innehåller den giltiga filnamnskonfigurationen &quot;`a-z A-Z 0-9 - _`&quot;. Detta innebär att när du skapar en fil kan du ha ett specialtecken i filens titel, men internt kommer det att ersättas med ett bindestreck \(`-`\) i filnamnet. Du kan t.ex. ha filens namn som Introduktion 1 eller Introduction@1, så kommer motsvarande filnamn som skapas för båda dessa fall att vara Introduktion-1.

Tänk på följande tecken när du definierar en lista med giltiga tecken:`*/:[\]|#%{}?&<>"/+`&quot; och `a space` ersätts alltid med ett bindestreck \(`-`\).

>[!NOTE]
>
> Om du inte konfigurerar den giltiga specialteckenlistan kan det hända att du får oväntade resultat när du skapar filen.

Använd instruktionerna i [Konfigurationsåsidosättningar](download-install-additional-config-override.md#) för att skapa konfigurationsfilen. Ange följande \(egenskap\)-information i konfigurationsfilen för att konfigurera giltiga specialtecken i filnamn och AEM platsutdata:

| PID | Egenskapsnyckel | Egenskapsvärde |
|---|------------|--------------|
| `com.adobe.fmdita.common.SanitizeNodeNameImpl` | `aemsite.DisallowedFileNameChars` | Kontrollera att egenskapen är inställd på ``'<>`@$``. Du kan lägga till fler specialtecken i den här listan. |

Du kan också konfigurera andra egenskaper, till exempel använda gemener i filnamn, avgränsare för att hantera ogiltiga tecken och maximalt antal tecken som tillåts i filnamnen. Om du vill konfigurera de här egenskaperna lägger du till följande nyckelvärdepar i konfigurationsfilen:

| Egenskapsnyckel | Egenskapsvärde |
|------------|--------------|
| `nodename.uselower` | Boolean \(true/false\).<br> **Standardvärde**: true |
| `nodename.separator` | Alla tecken. <br> **Standardvärde**: \_ *\(understreck\)* |
| `nodename.maxlength` | Heltalsvärde.<br> **Standardvärde**: 50 |

### Konfigurera förenkling AEM platsnodens struktur

När du genererar utdata AEM platsen skapas en nod för varje element i avsnitten internt. För en DITA-karta med tusentals ämnen kan den här nodstrukturen bli för djup. Den här typen av djupt kapslad nodstruktur kan ha prestandaproblem för större platser. I följande bild visas djupt kapslad nodstruktur för en AEM webbplatsutdata:

![](assets/deep-nested-aem-site-node-structure.png)

Observera att det finns en nod för varje `p` -element och dess efterföljande underelement och en liknande struktur skapas för alla andra element som används i ämnet.

Med AEM Guides kan du konfigurera hur nodstrukturen AEM platsutdata skapas internt. Du kan förenkla nodstrukturen vid angivna element, vilket innebär att du kan definiera ett element som ska betraktas som huvudelement och alla underelement i det sammanfogas med huvudelementet. Om du till exempel bestämmer dig för att förenkla `p` -element, därefter alla element som finns i `p` elementet kommer att sammanfogas med huvudelementet `p` -element. Ingen separat anteckning skapas för något underelement i `p` -element. Följande ögonblicksbild visar nodstrukturen förenklad vid `p` element:

![](assets/flattened-aem-site-node-structure.png)

Så här förenklar du strukturen AEM platsnoden:

1. Identifiera det eller de element som du vill förenkla nodstrukturen vid:

1. Övertäckning för `libs` noden i `apps` och öppna filen elementmapping.xml.

1. Lägg till `<flatten>true</flatten>` i definitionen av det element där du vill lägga samman nodstrukturen. Om du till exempel vill lägga samman nodstrukturen vid `p` -element och sedan lägga till attributet flatten i definitionen av `p` element enligt nedan:

   ```XML
   <ditaelement>
         <name>p</name>
         <class>- topic/p</class>
         <componentpath>fmdita/components/dita/wrapper</componentpath>
         <type>COMPOSITE</type>
         <target>para</target>
         <flatten>true</flatten>
         <wrapelement>div</wrapelement>
      </ditaelement>
   ```

   >[!NOTE]
   >
   > Som standard har egenskapen flatten node konfigurerats på `p` -element.

1. Använd instruktionerna i [Konfigurationsåsidosättningar](download-install-additional-config-override.md#) för att skapa konfigurationsfilen.
1. Ange följande \(egenskap\)-information i konfigurationsfilen:

   | PID | Egenskapsnyckel | Egenskapsvärde |
   |---|------------|--------------|
   | `com.adobe.dxml.flattening.FlatteningConfigurationService` | `flattening.enabled` | Boolean \(true/false\).<br> **Standardvärde**: `false` |


När du nu genererar AEM Site-utdata är noderna i `p` -elementet förenklas och lagras i `p` själva elementet. Du hittar de nya förenklingsegenskaperna för `p` element i CRXDE.

![](assets/flatten-aem-site-note-props-crxde.png)

**Söka efter en sträng i innehållet i AEM**

Som standard kan du bara söka efter en sträng i titlarna i AEM platsutdata. Du kan konfigurera systemet så att det söker efter en sträng både i titlarna och i innehållet eller i innehållet i AEM.

>[!NOTE]
>
> Ibland kan din sökning fungera för vissa element i innehållet, men du kan konfigurera det så att det fungerar för hela innehållet.

![](assets/flatten-aem-site-note-props-crxde-search.png)

Om du vill aktivera sökningen bör du konfigurera förenklingen AEM platsnodstrukturen.

VARNING:

Du kan söka efter upp till 1 MB förenklat innehåll. I den föregående skärmbilden kan du till exempel söka efter innehållet under &lt;p> -taggen är &lt;= 1 MB.

>[!NOTE]
>
> Sökningen fungerar bara på elementen om `<flatten>`är true. Som standard har AEM stödlinjer `<flatten>` attribute set to true för de vanligaste textelementen som &lt;p> &lt;ul> &lt;li>. Om du har skapat vissa anpassade element bör du dock ange `<flatten>` attribute to true in the elementmapping.xml file.

**Förhindra förenkling AEM platsnodens struktur**

På samma sätt som du anger vilken nod som ska förenklas AEM platsutdata kan du även ange ett element som du vill utesluta från den här konfigurationen. Om du till exempel vill lägga samman noder vid `body` -element, men du vill inte ha något `table` element inuti `body` för att förenkla kan du lägga till egenskapen exclude i `table` -elementets definition.

Exkludera `table` från förenkling, lägg till följande egenskap i `table` elementets definition:

`<preventancestorflattening>true|false</preventancestorflattening>`

### Konfigurera versionshantering för borttagna sidor i AEM webbplatsutdata

När du genererar AEM webbplatsutdata med **Ta bort och** Skapa ****som har valts för inställningen Befintliga utdatasidor skapas en version för sidan som tas bort. Du kan konfigurera systemet så att det inte längre skapas en version innan du tar bort den.

Utför följande steg för att stoppa skapandet av en version för den sida/de sidor som ska tas bort:

1. Använd instruktionerna i [Konfigurationsåsidosättningar](download-install-additional-config-override.md#) för att skapa konfigurationsfilen.
1. Ange följande \(egenskap\)-information i konfigurationsfilen för att konfigurera **Skapa inte någon version för borttagna sidor** alternativ:

   | PID | Egenskapsnyckel | Egenskapsvärde |
   |---|------------|--------------|
   | `com.adobe.fmdita.confi g.ConfigManager` | `no.version.creation.on.deletion` | Boolean \(true/false\).<br> **Standardvärde**: `true` |

   >[!NOTE]
   >
   > När det här alternativet är markerat kan användare ta bort alla sidor direkt utan att skapa någon version för dem. Om alternativet inte är markerat skapas en version innan sidan tas bort.


## Använda metadata i publicering via DITA-OT {#id191LF0U0TY4}

AEM Guides är ett sätt att skicka anpassade metadata när utdata publiceras med DITA-OT. Som administratör och utgivare måste du utföra följande uppgifter för att konfigurera och använda anpassade metadata i publicerade utdata:

- Som administratör lägger du till de metadata som krävs i systemet så att de blir tillgängliga på sidan Egenskaper på DITA-kartan.

- Som administratör lägger du till anpassade metadata i metadatalistan så att den visas i DITA-kartkonsolen.

- Som utgivare konfigurerar och lägger du till anpassade metadata med DITA-kartan och skapar önskade utdata.


Så här lägger du till de metadata som krävs i systemet:

1. Logga in i Adobe Experience Manager som administratör.

1. Klicka på länken Adobe Experience Manager överst och välj **verktyg**.

1. Välj **Resurser** i listan över verktyg.

1. Klicka på **Metadata-scheman** platta.

   Forms-sidan Metadata Schema visas.

1. Välj **standard** från listan.

   >[!NOTE]
   >
   > Egenskaperna som visas på egenskapssidan för en DITA-karta hämtas från det här formuläret.

1. Klicka **Redigera**.

1. Lägg till anpassade metadata som du vill använda i publicerade utdata. Vi lägger till exempel till målgruppsmetadata med följande steg:

   1. Från **Skapa formulär** komponentlista, dra och släppa **Enkelradstext** till formuläret.

   2. Välj det nya fältet för att öppna **Inställningar** av fältet.

   3. I **Fältetikett**, ange metadatanamnet - Målgrupp.

   4. I **Mappa till egenskap** inställning, ange ./jcr:content/metadata/&lt;name of=&quot;&quot; the=&quot;&quot; metadata=&quot;&quot;>. Vi kommer till exempel att ställa in den på ./jcr:content/metadata/audition.

   Lägg till alla metadataparametrar som krävs med dessa steg.

1. Klicka **Spara**.


Den nya parametern visas nu på sidan Egenskaper för alla DITA-kartor.

![](assets/properties-page-custom-metadata.PNG)

Därefter måste du göra anpassade metadata tillgängliga i DITA-kartkonsolen. Gör så här för att göra anpassade metadata tillgängliga på DITA-kartans dashboard:

1. Använd pakethanteraren för att komma åt den metadataList-fil som finns på följande plats i din Cloud Managers Git-databas:

   /libs/fmdita/config/metadataList

   >[!NOTE]
   >
   > Filen metadataList innehåller en lista med egenskaper som visas i **Egenskaper** nedrullningsbar lista med en DITA-karta på kartkontrollpanelen. Som standard visas fyra egenskaper i den här filen: docstate, dc:language, dc:description och dc:title.

1. Lägg till anpassade metadata som du har lagt till på Forms-sidan Metadata Schema. Lägg till exempel till målgruppsparameter i slutet av standardlistan.


Nu visas anpassade metadata i DITA-kartkonsolens **Egenskaper** nedrullningsbar lista.

Som utgivare måste du slutligen inkludera anpassade metadata i publicerade utdata. Så här bearbetar du anpassade metadata när du genererar utdata:

1. Navigera i resursgränssnittet till den DITA-karta som du vill publicera.

1. Markera DITA-schemafilen och öppna egenskapssidan.

1. Ange värdet för anpassade metadata på sidan Egenskaper. Vi har till exempel angett värdet External som målgruppsparameter.

   ![](assets/properties-page-custom-metadata-value.png)

1. Klicka **Spara och stäng**.

1. Klicka på DITA-kartfilen för att öppna DITA-kartkonsolen.

1. I **Förinställningar för utdata** väljer du den förinställning du vill använda för att generera utdata.

1. Klicka **Redigera**.

1. Från **Egenskaper** väljer du de egenskaper som du vill skicka till publiceringsprocessen.

   ![](assets/props-in-publish-output.PNG)


De valda egenskaperna/metadata skickas vidare till publiceringsprocessen och blir tillgängliga i det slutliga resultatet.

### Validera metadata som skickas till DITA-OT för bearbetning

För att validera de metadatavärden som skickas till DITA-OT kan man använda en molnklar burk. Eftersom vi inte har åtkomst till det lokala filsystemet i molnet kan vi bara validera metadatafilen via molnklar behållare.

- Filnamn: metadata.xml
- Filplats: crx-quickstart/profiles/ditamaps/&lt;ditamap-1234>

  Så här kommer du åt metadata.xml:

   - Logga in på serverplatsen där AEM körs.
   - Migrera till crx-quickstart/profiles/ditamaps/&lt;newly-created-directory-name>/metadata.xml.
- Exempelfilformat:

  **metadata.xml**

  ```XML
  <?xml version="1.0" encoding="UTF-8" standalone="no"?>
  <root>
     <Path id="/absolutePath/sampleMap.ditamap">
        <metadata>
           <meta isArray="false" key="dc:description">This is a file</meta>
           <meta isArray="false" key="dc:title">Myfile</meta>
           <meta isArray="true" key="multivalueText">One;Two;Three</meta>
        </metadata>
     </Path>
     <Path id="/absolutePath/sampleTopic.dita">
        <metadata>
           <meta isArray="false" key="dc:description">description for the accountability</meta>
           <meta isArray="false" key="dc:title">accountability title</meta>
           <meta isArray="true" key="multivalueText">value1</meta>
        </metadata>
     </Path>
  </root>
  ```


- isArray: Ett booleskt attribut som definierar om metadata är ett multivärde \(Array\) eller inte. Värdena avgränsas av ett semikolon.
- Sökväg-ID: Absolut sökväg till filen som lagras under den tillfälliga katalogen.

>[!NOTE]
>
> Om det inte finns några metadata för filen &lt;meta> -taggen med nyckeln visas inte som egenskap för filen i filen metadata.xml.

## Anpassa DITA-elementmappning med AEM {#id1679J600HEL}

DITA-element i AEM-stödlinjerna mappas till motsvarande AEM. AEM Guides använder den här mappningen i arbetsflöden, till exempel publicering och granskning, för att konvertera DITA-element till en motsvarande AEM. Mappningen definieras i `elementmapping.xml` -fil, som du kommer åt med hjälp av pakethanteraren.

>[!NOTE]
>
> Gör inga anpassningar i standardkonfigurationsfilerna tillgängliga i ``libs`` nod. Du måste skapa en övertäckning av ``libs`` noden i ``apps`` noda och uppdatera de nödvändiga filerna i ``apps`` endast nod.

Du kan använda de fördefinierade DITA-elementmappningarna eller mappa DITA-element till dina anpassade AEM. Om du vill använda dina anpassade AEM måste du förstå strukturen för `elementmapping.xml` -fil.

### elementmapping.xml-struktur

En översikt på hög nivå över `elementmapping.xml` strukturen förklaras nedan:

1. Alla DITA-element söks först efter en motsvarande komponentmappning baserat på elementnamnet. Till exempel:

   ```XML
   <ditaelement>     
      <name>**substeps**</name>  
      <class>- topic/ol task/substeps</class>  
      <componentpath>dita/components/ditaolist</componentpath>  
      <type>COMPOSITE</type>  
      <target>para</target>
   </ditaelement>
   ```

   I ovanstående exempel är alla `substeps` DITA-element återges med `dita/components/ditaolist` -komponenten.

1. Om ett DITA-element inte hittar någon matchning baserat på namnet, söker du efter en matchning baserat på `class` är klart. Till exempel:

   ```XML
   <ditaelement>  
      <name>topic</name>  
      <class>**- topic/topic**</class>  
      <componentpath>fmdita/components/dita/topic</componentpath>  
      <type>COMPOSITE</type>  
      <target>para</target>  
      <attributemap> 
         <attribute from="id" to="id" />  
      </attributemap>
   </ditaelement>
   ```

   Om ingen mappning har definierats för `task` -element, sedan `task` -elementet mappas till ovanstående komponent eftersom `task` ärvs från `topic` -komponenten.

1. När ett element har en motsvarande komponentmappning bestäms vidare bearbetning av dess underordnade element av `type`. Till exempel:

   ```XML
   <ditaelement>  
      <name>title</name>  
      <class>- topic/title</class>  
      <componentpath>foundation/components/title</componentpath>  
      <type>**STANDALONE**</type>  
      <target>para</target>  
      <textprop>jcr:title</textprop>
   </ditaelement>
   ```

   `type` använder följande värden:

   - SAMMANSATTA: element till komponent *mappningen fortsätter för underordnade element* också.

   - FRISTÅENDE: underordnade element för det aktuella elementet är *inte mappas vidare*.

   I exemplet ovan, om `<title>` -element har underordnade element, de mappas inte till någon annan komponent. Komponenten för `<title>` -elementet ansvarar för att återge alla underordnade element inuti `<title>` -element.

1. Om det finns flera komponenter som är mappade till ett enskilt DITA-element väljs den bästa matchningen för elementet. För att välja den bästa matchningskomponenten övervägs domän- och strukturexSpecialisering för DITA-element.

   Om det finns DITA-element med domänspecialisering och en komponent mappas för domänspecialisering får den komponenten hög prioritet.

   Om det finns DITA-element med strukturell specialisering och en komponent mappas för strukturell specialisering får den komponenten hög prioritet.

1. Du kan använda `<attributemap>` i elementmappning för att mappa attributvärden till motsvarande nodegenskaper.
1. `textprop` kan användas för att serialisera textinnehållet i ett DITA-element till en nodegenskap. Dessutom kan den användas flera gånger i en elementtagg för att serialisera textinnehållet på flera platser i den publicerade hierarkin. Du kan också anpassa platsen och namnet för målegenskapen. Till exempel:

   ```XML
   <ditaelement>
      <name>title</name>
      <componentpath>foundation/components/title</componentpath>
      <type>STANDALONE</type>
      <target>para</target>
       <textprop>**jcr:title**</textprop>
   </ditaelement>
   ```

   Ovanstående elementmappning anger att textinnehållet i `<title>` -elementet sparas som värdet för en egenskap med namnet `jcr:title` på utdatanoden.

1. `xmlprop` kan användas för att serialisera hela XML för ett givet element till en nodegenskap. Komponenten kan sedan läsa den här nodegenskapen och göra anpassad återgivning. Till exempel:

   ```XML
   <ditaelement>
       <name>svg-container</name>
      <class>+ topic/foreign svg-d/svg-container</class>
       <componentpath>fmdita/components/dita/svg</componentpath>
       <type>STANDALONE</type>
       <target>para</target>
      <xmlprop>**data**</xmlprop>
   </ditaelement>
   ```

   Ovanstående elementmappning anger att hela XML-koden för elementet `<svg-container>` sparas som värdet för en egenskap med namnet `data` på utdatanoden.

1. Det finns en särskild attributmappning som hanterar sökvägsupplösning i utdatagenereringsprocessen. Till exempel:

   ```XML
   <attributemap>
      <attribute from="href" to="fileReference" ispath="true" rel="source" />
      <attribute from="height" to="height" />
       <attribute from="width" to="width" />
   </attributemap>
   ```

   För ovanstående `attributemap`, `href` -attributet i DITA-elementet mappas till en nodegenskap med namnet `fileReference`. Nu sedan `ispath` är inställd på `true`, löser utdatagenereringsprocessen den här sökvägen och anger den sedan i `fileReference` node-egenskap.

   Hur den här upplösningen sker bestäms utifrån värdet på `rel` attribut i attributmappning.

   - If `rel=source`, och sedan värdet för `href` löses med avseende på DITA-källfilen som bearbetas. Värdet för `href` är löst och placerad i värdet för `fileReference` -egenskap.

   - If `rel=target`, och sedan värdet för `href` har lösts med avseende på rotpubliceringsplatsen. Värdet för `href` är löst och placerad i värdet för `fileReference` -egenskap.

   Om du inte vill att förbehandling eller upplösning ska ske för sökvägsattribut behöver du inte ange `ispath` -attribut. Värdet kopieras som det är och komponenten kan utföra den önskade upplösningen.


### DITA-elementschema

Följande är ett exempel på DITA-elementschemat i `elementmapping.xml` fil:

```XML
<ditaelement>        
    <name>element_name</name>    
    <class>element_class</class>    
    <componentpath>fmdita/components/dita/component_name</componentpath>    
    <type>COMPOSITE|STANDALONE</type>     
    <attributeprop>propname_a</attributeprop>      
    <textprop>propname_t</textprop>    
    <xmlprop>propname_x</xmlprop>     
    <xpath>xpath expression string</xpath>     
    <target>head|para</target>     
    <wrapelement>div</wrapelement>     
    <wrapclass>class_name</wrapclass>     
    <attributemap>         
        <attribute from="attrname"         to="propname"         ispath="true|false"         rel="source|target" />    
    </attributemap>    
    <skip>true|false</skip> 
</ditaelement>
```

I följande tabell beskrivs elementen i DITA-elementschemat:

| Element | Beskrivning |
|-------|-----------|
| `<ditaelement>` | Den översta noden för varje mappningselement. |
| `<class>` | Klassattributet för det DITA-målelement som du skriver komponenten för.<br> Klassattributet för DITA-ämnet är till exempel: <br> `- topic/topic` |
| `<componentpath>` | CRXDE-sökvägen för den mappade AEM. |
| `<type>` | Möjliga värden:<br> -   **SAMMANSATTA**: Bearbeta även underordnade element <br> -   **FRISTÅENDE**: Hoppar över bearbetning av underordnade element |
| `<attributeprop>` | Används för att mappa serialiserade DITA-attribut och -värden till AEM noder som egenskap. Om du till exempel har `<note type="Caution">` -elementet och komponenten som mappas för det här elementet har `<attributeprop>attr_t</ attributeprop>`, serialiseras nodens attribut och värde till `attr_t` egenskap för motsvarande AEM nod \( `attr_t->type="caution"`\). |
| `<textprop>propname_t</textprop>` | Spara `getTextContent()` output till egenskap definierad av `propname_t.` <br> **Obs!** Det här är en optimerad egenskap. |
| `<xmlprop>propname_x </xmlprop>` | Spara serialiserad XML för den här noden till egenskap som definierats av `propname_x.<br> `**Obs!** Det här är en optimerad egenskap. |
| `<xpath>` | Om XPath-elementet anges i elementmappningen ska XPath-villkoret också uppfyllas tillsammans med elementnamnet och klassen för att komponentmappningen ska användas. |
| `<target>` | Placera DITA-elementet i crx-databasen på den angivna platsen.<br> Möjliga värden: <br> - **head**: Under noden head <br> - **text**: Under styckenoden |
| `<wrapelement>` | Det HTML-element som innehållet ska radbrytas i. |
| `<wrapclass>` | Elementvärdet för egenskapen `wrapclass.` |
| `<attributemap>` | Behållarnod som innehåller en eller flera `<attribute>` noder. |
| `<attribute from="attrname" to="propname" ispath="true|false" rel="source|target" />` | Kopplar DITA-attributen till AEM egenskaper: <br> -   **`from`**: DITA-attributnamn <br> -   **`to`**: AEM komponentens egenskapsnamn <br> -   **`ispath`**: Om attributet är ett sökvägsvärde \(till exempel: *image*\) <br> -   **`rel`**: Om sökvägen är källan eller målet <br> **Obs!** If `attrname` börjar med `%`och sedan mappa `attrname minus '%'` att beskära `propname`&#39;. |

**Ytterligare information**

- Om du tänker åsidosätta standardelementmappningen rekommenderar vi att du inte gör ändringarna i standardinställningen `elementmapping.xml` -fil. Du bör skapa en ny XML-mappningsfil och placera filen på en annan plats, helst i en anpassad programmapp som du skapar.

- I `elementmapping.xml` -filen finns det många mappningsposter som refererar till komponenten fmdita/components/dita/wrapper. Wrapper är en generisk komponent som återger relativt enkla DITA-konstruktioner med hjälp av egenskaper på webbplatsnoden för att generera relevant HTML. Den använder `wrapelement` för att generera omslutande taggar och delegerar den underordnade återgivningen till motsvarande komponenter. Detta är användbart om du bara vill ha en behållarkomponent. I stället för att skapa en ny komponent som återger en viss behållartagg som `div` eller `p`kan du använda komponenten Wrapper med `wrapelement` och `wrapclass` -egenskaper för att uppnå samma effekt.

- Du bör inte spara stora mängder text i JCR-egenskaper för strängar. Beräkningen av den optimerade egenskapstypen i utdatagenereringen säkerställer att stort textinnehåll inte sparas som strängtyp. Om innehåll som är större än ett visst tröskelvärde behöver sparas, ändras egenskapstypen till binär. Som standard är det här tröskelvärdet konfigurerat till 512 byte, men det kan ändras i Configuration Manager \(*com.adobe.fmdita.config.ConfigManager*\) genom att ändra **Spara som binärt tröskelvärde** inställning.

- Om du tänker åsidosätta vissa \(och inte alla\) av elementmappningarna behöver du inte replikera hela `elementmapping.xml` -fil. Du måste skapa en ny XML-mappningsfil och definiera endast de element som du åsidosätter.

- När du har skapat XML-filen på den anpassade platsen uppdaterar du `Override Element Mapping` i `com.adobe.fmdita.config.ConfigManager` paket.


## Anpassa DITA-kartkonsolen {#id188HC08M0CZ}

AEM Guides ger dig flexibilitet att utöka funktionerna i DITA-kartkonsolen. Om du till exempel har en uppsättning rapporter som skiljer sig från vad som finns i AEM guider kan du lägga till sådana rapporter i kartkonsolen. Om du vill anpassa kartkonsolen måste du skapa ett AEM klientbibliotek \(eller ClientLib\) som innehåller koden för att utföra de funktioner du behöver.

>[!NOTE]
>
> Direktändringar av sidkomponenter rekommenderas inte eftersom de skrivs över i nya versioner av produkten.

AEM stödlinjer innehåller `apps.fmdita.dashboard-extn` -kategori för anpassning av kartkonsol. När kartkonsolen läses in skapas de funktioner som finns under `apps.fmdita.dashboard-extn` körs och läses in.

>[!NOTE]
>
> Mer information om hur du skapar AEM klientbibliotek finns i [Använda bibliotek på klientsidan](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/implementing/developing/full-stack/clientlibs.html?lang=en).

## Hantera bildåtergivning under generering av utdata {#id177BF0G0VY4}

AEM innehåller en uppsättning standardarbetsflöden och mediehandtag för att bearbeta resurser. I AEM finns fördefinierade arbetsflöden för att hantera resursbearbetning för de vanligaste MIME-typerna. För varje bild som du överför skapas vanligtvis flera återgivningar av samma bild i binärt format AEM. Dessa återgivningar kan ha olika storlek, med olika upplösning, med vattenstämpel eller någon annan förändrad egenskap. Mer information om hur AEM hanterar resurser finns i [Bearbeta resurser med mediehanterare och arbetsflöden](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/assets/asset-microservices-overview.html?lang=en) i AEM.

Med AEM Guides kan du konfigurera vilken bildåtergivning som ska användas när du genererar utdata för dina dokument. Du kan till exempel välja mellan en av standardbildåtergivningarna eller skapa en och använda samma för att publicera dina dokument. Bildrenderingsmappning för publicering av dokument lagras i `/libs/fmdita/config/ **renditionmap.xml**` -fil. Ett fragment av `renditionmap.xml` filen är som följer:

>[!NOTE]
>
> Vi rekommenderar att du skapar en kopia av `renditionmap.xml` i `apps` mapp för alla anpassningar.

```XML
<renditionmap>
   <mapelement>
      <mimetype>image/png</mimetype>
      <rendition output="AEMSITE">cq5dam.web.1280.1280.jpeg</rendition>
      <rendition output="PDF">original</rendition>
      <rendition output="HTML5">cq5dam.web.1280.1280.jpeg</rendition>
      <rendition output="EPUB">cq5dam.web.1280.1280.jpeg</rendition>
      <rendition output="CUSTOM">cq5dam.web.1280.1280.jpeg</rendition>
   </mapelement>
...
</renditionmap>
```

The `mimetype` -elementet anger filformatets MIME-typ. The `rendition output` -element anger typ av utdataformat och namnet på återgivningen \(t.ex. `cq5dam.web.1280.1280.jpeg`\) som ska användas för publicering av angivna utdata. Du kan ange bildåtergivningarna som ska användas för alla utdataformat som stöds - AEMSITE, PDF, HTML 5, EPUB och ANPASSAD.

Om den angivna återgivningen inte finns söker AEM publiceringsprocessen först efter webbåtergivningen av den angivna bilden. Om inte ens webbåtergivningen hittas används den ursprungliga återgivningen av bilden.

>[!NOTE]
>
> Dessa bildåtergivningar styr endast utdatagenereringen. En bilds webbåtergivning används när du öppnar ett dokument för förhandsgranskning.

## Konfigurera automatisk tömningsperiod för utdathistorik {#id19AAI070V8Q}

När du genererar utdata skapas utdata tillsammans med utdataloggarna. För stora DITA-kartor kan dessa loggar ta mycket plats i din databas. Som standard lagras loggarna på följande plats i databasen:

`/var/dxml/metadata/outputHistory`

Under en tidsperiod kan den sammanlagda storleken på alla loggfiler uppgå till GB. I AEM Guides kan du konfigurera en tidsperiod för att behålla dessa loggfiler i databasen. Efter den angivna tidsperioden tas loggarna och historiken för utdatagenerering bort från databasen.

>[!NOTE]
>
> Historiken för generering av utdata är loggposten i listan Genererade utdata på fliken Utdata.

Om du konfigurerar historikrensningsfunktionen påverkas utdatagenereringen för alla DITA-kartor i databasen. På fliken Utdata i en DITA-karta rensas historiken efter det angivna antalet dagar och vid den tidpunkt som anges i inställningen.

>[!NOTE]
>
> Borttagning av loggfiler och historik för generering av utdata påverkar inte de genererade utdata.

Använd instruktionerna i [Konfigurationsåsidosättningar](download-install-additional-config-override.md#) för att skapa konfigurationsfilen. Ange följande \(egenskap\)-information i konfigurationsfilen för att ange en dag och en tid för att rensa utdatahistorik och -loggar:

| PID | Egenskapsnyckel | Egenskapsvärde |
|---|------------|--------------|
| `com.adobe.fmdita.config.ConfigManager` | `output.history.purgeperiod` | Ange efter hur många dagar som utdatahistoriken och utdataloggarna ska rensas. Om du vill inaktivera den här funktionen anger du egenskapen till 0.Daglig vid den angivna tidpunkten när rensningsprocessen körs på utdata som genererats före det antal dagar som anges i den här egenskapen. <br> **Standardvärde**: 5 |
| `output.history.purgetime` | Ange den tid då rensningsprocessen initieras. <br> **Standardvärde**: 0:00 \(eller 12:00 midnatt\) |

## Ändra gränsen för den nyligen genererade utdatalistan {#id1679JH0H0O2}

Du kan ändra det maximala antalet genererade utdata som visas på fliken Utdata för en DITA-karta.

Använd instruktionerna i [Konfigurationsåsidosättningar](download-install-additional-config-override.md#) för att skapa konfigurationsfilen. Ange följande \(egenskap\)-information i konfigurationsfilen för att ändra antalet utdata som ska visas i listan:

| PID | Egenskapsnyckel | Egenskapsvärde |
|---|------------|--------------|
| `com.adobe.fmdita.config.ConfigManager` | `output.historylimit` | Heltalsvärde.<br> **Standardvärde**: 25 |

>[!TIP]
>
> Se *Utdatahistorik* i Best practices Guide för bästa praxis när det gäller att arbeta med utdatahistorik.

