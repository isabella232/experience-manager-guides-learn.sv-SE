---
title: Konfigurera inställningar för utdatagenerering
description: Lär dig hur du konfigurerar inställningar för generering av utdata
source-git-commit: 5ac066bb8db32944abd046f64da11eeb1bdbe467
workflow-type: tm+mt
source-wordcount: '5761'
ht-degree: 0%

---

# Konfigurera inställningar för utdatagenerering {#id181AI0B0E30}

AEM Guides innehåller många konfigurationsalternativ som du kan använda för att anpassa genereringsprocessen för utdata. I det här avsnittet beskrivs alla konfigurationer och anpassningar som kan hjälpa dig att skapa utdata.

## Konfigurera fliken Baslinje på DITA-kartkontrollpanelen {#id223MD0D0YRM}

Du kan konfigurera och dölja fliken Baslinje som finns på kartkontrollpanelen.

The **Dölj fliken Baslinje** är inte aktiverat som standard och du måste aktivera det från configMgr. Följ de här stegen för att aktivera alternativet som standard i Web Editor:

1. Öppna konfigurationssidan för Adobe Experience Manager Web Console.

   Standardwebbadressen för åtkomst till konfigurationssidan är:

   ```http
   http://<server name>:<port>/system/console/configMgr
   ```

1. Sök efter och klicka på **com.adobe.fmdita.config.ConfigManager** paket.

1. Välj **Dölj fliken Baslinje** alternativ.

1. Klicka **Spara**.

   >[!NOTE]
   >
   > Den här konfigurationen är inaktiverad som standard och fliken Baslinje är tillgänglig på kartkontrollpanelen.


## Konfigurera FrameMaker Publishing Server {#id1678G0Z0TN6}

Du kan använda FrameMaker Publishing Server \(FMPS\) för att generera utdata för DITA-innehåll. Om du konfigurerar FMPS kan du generera utdata i flera format som stöds av FMPS.

>[!NOTE]
>
> Om du vill generera utdata med FMPS måste du ha FMPS-servern konfigurerad. Installations- och konfigurationsinformation finns i användarhandboken för FrameMaker Publishing Server.

Om du vill konfigurera AEM stödlinjer så att de använder FMPS uppdaterar du följande egenskaper i `com.adobe.fmdita.config.ConfigManager` i webbkonsolen.

>[!NOTE]
>
> Öppna http://&lt;server name=&quot;&quot;>:&lt;port>/system/console/configMgr URL för att öppna webbkonsolen.

| Egenskap | Beskrivning |
|--------|-----------|
| Inloggningsdomän för FrameMaker Publishing Server | Ange domännamnet eller namnet på arbetsgruppen där FrameMaker Publishing Server finns. Baserat på FMPS-versionen anger du domännamnet som:-   **FMPS 2020**: IP-adress som 192.168.1.101 <br>- **FMPS 2019 och tidigare**: IP-adress eller domännamn |
| FrameMaker Publishing Server URL | Ange URL:en för FrameMaker Publishing Server. Baserat på FMPS-versionen anger du URL:en för FMPS enligt följande:<br>- **FMPS 2020**: `http://<fmps_ip>:<port>` \(http://192.168.1.101:7000\) <br> - **FMPS 2019 och tidigare**: `http://<fmps_ip>:<port>/fmserver/v1/` |
| FMPS-version | Ange versionsnumret för FrameMaker Publishing Server. Baserat på FMPS-versionen anger du versionsinformationen som: <br>- **FMPS 2020**: 2020 <br> - **FMPS 2019 och tidigare**: 2019 eller 2017 |
| Användarnamn och lösenord för FrameMaker Publishing Server | Ange användarnamn och lösenord för att komma åt FrameMaker Publishing Server. |
| FMPS-timeout | \(*Valfritt*\) Ange tiden \(i sekunder\) för vilken AEM väntar på ett svar från FrameMaker Publishing Server. Om inget svar tas emot under den angivna tiden avbryts publiceringsaktiviteten och aktiviteten flaggas som misslyckad. <br> Standardvärde: 300 sekunder \(5 minuter\) |
| Extern AEM-URL | *\(Valfritt\)* Den AEM URL där FrameMaker Publishing Server placerar de genererade utdatafilerna. Till exempel, `http://<server-name>:<port>/`. |
| AEM administratörens användarnamn och lösenord | *\(Valfritt\)* Användarnamn och lösenord för en administratör för AEM. Det används av FrameMaker Publishing Server för att kommunicera med AEM. |
| Timeout för väntan på körning av FMPS-aktivitet | Den här inställningen gäller endast för FMPS 2020. Ange tiden \(i sekunder\) efter vilken FMPS slutar vänta på att den här processen ska köras. |

## Konfigurera blandad publicering på en befintlig AEM {#id1691I0V0MGR}

Om du har en AEM webbplats som innehåller DITA-innehåll kan du konfigurera dina AEM webbplatsutdata så att DITA-innehåll publiceras på en fördefinierad plats på platsen. I följande skärmbild av en AEM webbplats visas `ditacontent` noden är reserverad för lagring av DITA-innehåll:

![](assets/publish-in-aem-site.png){width="300" align="left"}

De återstående noderna på sidan redigeras direkt från AEM. Om du konfigurerar publiceringsinställningen för att publicera DITA-innehåll på en fördefinierad plats, säkerställs att inget av ditt befintliga icke-DITA-innehåll ändras i publiceringsprocessen för AEM.

Du måste göra följande konfigurationer på din befintliga webbplats för att tillåta publicering av DITA-innehåll till en fördefinierad nod:

- Konfigurera platsens mallegenskaper

- Lägg till noder på webbplatsen för att publicera DITA-innehåll


Utför följande steg för att konfigurera den befintliga platsens mallegenskaper:

1. Logga in AEM och öppna läget CRXDE Lite.

1. Navigera till platsens mallkonfigurationsnod. I AEM sparas standardmallkonfigurationerna i följande nod:

   `/libs/fmdita/config/templates/default`

   >[!NOTE]
   >
   > Gör inga anpassningar i standardkonfigurationsfilerna tillgängliga i `libs` nod. Du måste skapa en övertäckning av `libs` noden i `apps` noda och uppdatera de nödvändiga filerna i `apps` endast nod.

1. Lägg till följande egenskaper:

   | Egenskapsnamn | Typ | Värde |
   |-------------|----|-----|
   | `topicContentNode` | Sträng | Ange det nodnamn där du vill publicera DITA-innehållet. Standardnoden där DITA-innehåll publiceras av AEM Guides är till exempel: <br>`jcr:content/contentnode` |
   | `topicHeadNode` | Sträng | Ange det nodnamn där du vill lagra metadatainformationen för DITA-innehållet. Standardnoden där metadatainformation lagras i AEM Guides är till exempel: <br>`jcr:content/headnode` |


På följande skärmbild visas de egenskaper som lagts till i standardmallnoden för AEM stödlinjer:

![](assets/add-content-node.png){width="800" align="left"}

Nästa gång du publicerar DITA-innehåll med mallkonfigurationer för din webbplats publiceras innehållet i de noder som anges i `topicContentNode` och `topicHeadNode` egenskaper.

För befintliga webbplatser måste du dock lägga till `topicContentNode` och `topicHeadNode` noder.

Utför följande steg för att lägga till de nödvändiga noderna på din befintliga plats:

1. Logga in AEM och öppna läget CRXDE Lite.

1. Sök `jcr:content` i platsnoden.

1. Lägg till `topicContentNode` och `topicHeadNode` noder med samma namn som du angav i platsens mallkonfigurationer.


## Anpassa AEM {#id166TG0B30WR}

AEM har stöd för att skapa utdata i följande format:

- AEM

- PDF

- HTML5
- ePub
- Anpassade utdata via DITA-OT

För AEM platsutdata kan du tilldela olika designmallar med olika utdatauppgifter. Dessa designmallar kan återge DITA-innehållet i olika layouter. Du kan till exempel ange olika designmallar för interna och externa målgrupper.

Du kan också använda anpassade DITA Open Toolkit-plugin-program \(DITA-OT\) med AEM Guides. Du kan överföra dessa anpassade DITA-OT-plugin-program för att generera utdata från PDF på ett visst sätt.

>[!TIP]
>
> Se *AEM* i Best practices Guide[appendix.md\#](appendix.md#) om du vill ha de bästa sätten att skapa AEM webbplatsutdata.

### Anpassa designmall för generering av utdata {#customize_xml-add-on}

AEM Guides använder en uppsättning fördefinierade designmallar för att generera AEM webbplatsutdata. Du kan anpassa designmallarna i AEM Guides för att skapa utdata som passar företagets grafiska profil. En designmall är en samling med olika format \(CSS\), skript \(både server- och klientsidan\), resurser \(bilder, logotyper och andra resurser\) och JCR-noder som knyter samman alla dessa resurser. En designmall kan vara så enkel som ett enda skript på servern med bara ett par JCR-noder, eller en komplex kombination av format, resurser och JCR-noder. Designmallar används av AEM Guides Publishing-undersystemet när AEM genereras och de styr strukturen, utseendet och känslan hos det genererade resultatet.

Det finns ingen begränsning för var designmallresurserna ska placeras på servern, men de är vanligtvis logiskt ordnade efter sin funktion. Standardmallen innehåller till exempel alla JavaScript- och CSS-filer som lagras under `/etc/designs/fmdita/clientlibs/siteoutput/default` mapp. Oavsett var filerna finns länkas de ihop av en samling JCR-noder. Tillsammans utgör dessa JCR-noder och filerna hela designmallen.

Med standarddesignmallen som levereras med AEM stödlinjer kan du anpassa komponenterna för landning, ämne och söksida. Du kan skapa en kopia av standarddesignen och motsvarande referensmallar och ange olika komponenter för att generera önskat utvärde.

Utför följande steg för att ange en egen designmall som ska användas för att generera utdata AEM webbplatsen:

1. Logga in AEM och öppna läget CRXDE Lite.

1. Navigera till standarddesignmallsnoden. Platsen för standarddesignmallsnoden är:

   `/libs/fmdita/config/templates/`

   ![](assets/templates-node.png){width="300" align="left"}

   >[!NOTE]
   >
   > Skapa en kopia av standarddesignmallarna från `libs` mapp till `apps` och gör ändringar i `apps` mapp. Du måste också göra ändringar i mallarna som refereras från standardmallnoden. De refererade mallarna placeras under `/libs/fmdita/templates/default/cqtemplates` nod. Skapa en kopia av de refererade mallarna i `apps` innan du gör några ändringar.

1. Klicka på *standard* i *mallar* för att komma åt dess egenskaper.

   Egenskaper för designmallar AEM stödlinjer beskrivs i följande tabell.

   | Egenskap | Beskrivning |
   |--------|-----------|
   | `landingPageTemplate`, `searchPageTemplate`, `topicPageTemplate`, `shadowPageTemplate` | Ange `cq:Template` nod för dessa motsvarande sidor \(landning, sökning och ämne\). Som standard är `cq:Template` noden för dessa sidor finns i `/libs/fmdita/templates/default/cqtemplates` nod. Den här noden definierar strukturen och egenskaperna för landnings-, söknings- och ämnessidorna. <br>The `shadowPageTemplate` används för att optimera det segmenterade innehållet. Du måste ange värdet för den här egenskapen till: <br> `fmdita/templates/default/cqtemplates/shadowpage` <br> **Anteckning** Du måste ange ett värde för `topicPageTemplate`. The `landingPageTemplate` och `searchPageTemplate` är valfria egenskaper. Om du inte vill att sök- och landningssidorna ska genereras ska du inte ange dessa egenskaper. |
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

Mer information finns i [Skapa din första Adobe Experience Manager 6.3-webbplats](https://helpx.adobe.com/experience-manager/using/first_aem63_website.html) och [Grunderna](https://helpx.adobe.com/experience-manager/6-3/sites/developing/using/the-basics.html) att utveckla en egen webbplats på AEM.

### Använd dokumenttitel för att generera AEM webbplatsutdata

När du genererar AEM webbplatsutdata spelar det sätt på vilket URL:er genereras en viktig roll för att ditt innehåll ska kunna identifieras. Om du använder UUID-baserade filnamn är det inte sökvänligt att generera URL:er baserade på UUID för dina filer. Som administratör eller utgivare kan du styra hur du vill generera URL:er för AEM webbplatsutdata. AEM Guides ger dig en konfiguration genom vilken du kan välja att generera URL:er AEM platsutdata med hjälp av filens namn i stället för UUID-baserade filnamn. Som standard är det här alternativet aktiverat för UUID-baserade filsystem. Detta innebar att när du genererade utdata AEM platsen för UUID-baserade filsystem, används filens namn för att generera URL:er och inte UUID:n för filerna.

När du genererar AEM webbplatsutdata spelar det sätt på vilket URL:er genereras en viktig roll för att ditt innehåll ska kunna identifieras. Om det inte finns UUID-baserade filsystem genereras AEM platsutdata med filnamnen och inte filens titlar. Som administratör eller utgivare kan du styra hur du vill generera URL:er för AEM webbplatsutdata. AEM Guides ger dig en konfiguration genom vilken du kan välja att generera URL:er AEM webbplatsens utdata med hjälp av filens rubrik i stället för filnamnen. Som standard är det här alternativet inaktiverat. Detta innebar att när du genererade AEM Site-utdata används filnamnen för att generera URL:er och inte filens titel. Du kan välja att generera URL:er baserat på filens namn genom att aktivera det här alternativet.

>[!NOTE]
>
> Du kan konfigurera regler så att endast en teckenuppsättning tillåts i URL:er för en AEM webbplatsutdata. Mer information finns i [Konfigurera filnamnssaneringsregler för att skapa ämnen och publicera AEM webbplatsutdata](#id2164D0KD0XA).

Så här konfigurerar du URL-generering AEM platsutdata:

1. Öppna konfigurationssidan för Adobe Experience Manager Web Console.

   Standardwebbadressen för åtkomst till konfigurationssidan är:

   ```http
   http://<server name>:<port>/system/console/configMgr
   ```

1. Sök efter och klicka på **com.adobe.fmdita.config.ConfigManager** paket.

1. Välj **Använd rubrik AEM webbplatsens sidnamn** alternativ.

   >[!NOTE]
   >
   > Om du vill generera utdata med hjälp av filnamnen avmarkerar du det här alternativet.

1. Klicka **Spara**.


### Konfigurera filnamnssaneringsregler för att skapa ämnen och publicera AEM webbplatsutdata {#id2164D0KD0XA}

Som administratör kan du definiera en lista med giltiga specialtecken som tillåts i filnamn, som till slut utgör URL:en för en AEM webbplatsutdata. I tidigare versioner tilläts användare att definiera filnamn som innehåller specialtecken som `@`, `$`, `>`, med mera. Specialtecknen resulterade i kodad URL-adress när AEM webbplatssidor genererades.

Från och med version 3.8 har konfigurationer lagts till för att definiera en lista med specialtecken som tillåts i filnamnen. Som standard innehåller den giltiga filnamnskonfigurationen &quot;`a-z A-Z 0-9 - _`&quot;. Detta innebär att när du skapar en fil kan du ha ett specialtecken i filens titel, men internt kommer det att ersättas med ett bindestreck \(`-`\) i filnamnet. Du kan t.ex. ha filens namn som Introduktion 1 eller Introduction@1, så kommer motsvarande filnamn som skapas för båda dessa fall att vara Introduktion-1.

Tänk på följande tecken när du definierar en lista med giltiga tecken:`*/:[\]|#%{}?&<>"/+`&quot; och `a space` ersätts alltid med ett bindestreck \(`-`\).

>[!NOTE]
>
> Om du inte konfigurerar den giltiga specialteckenlistan kan det hända att du får oväntade resultat när du skapar filen.

Så här konfigurerar du giltiga specialtecken i filnamn och AEM platsutdata:

1. Öppna konfigurationssidan för Adobe Experience Manager Web Console.

   Standardwebbadressen för åtkomst till konfigurationssidan är:

   ```http
   http://<server name>:<port>/system/console/configMgr
   ```

1. Sök efter och klicka på *com.adobe.fmdita.common.SanitizeNodeNameImpl* paket.

1. I **Otillåten teckenuppsättning för publicering till AEM Sites** egenskap, kontrollera att egenskapen är inställd på ```'<>`@$```. Du kan lägga till fler specialtecken i den här listan, men det måste innehålla dessa specialtecken.

   >[!NOTE]
   >
   > Du kan också konfigurera andra egenskaper som **Använd gemener** i filnamn, **Avgränsare** för att hantera ogiltiga tecken, och **Maximalt antal tecken** tillåtna i filnamn.

1. Klicka **Spara**.

1. Sök efter och klicka på **com.adobe.fmdita.config.ConfigManager** paket.

1. I **Regex för giltiga tecken** egenskap, kontrollera att egenskapen är inställd på `[-a-zA-Z0-9_]`. Du kan lägga till fler tecken i den här listan, men den måste innehålla dessa grundläggande tecken och listan måste börja med ett bindestreck \(`-`\).

   >[!NOTE]
   >
   > This property define the list of valid character used to create a new file.

1. Klicka **Spara**.


### Konfigurera förenkling AEM platsnodens struktur

När du genererar utdata AEM platsen skapas en nod för varje element i avsnitten internt. För en DITA-karta med tusentals ämnen kan den här nodstrukturen bli för djup. Den här typen av djupt kapslad nodstruktur kan ha prestandaproblem för större platser. I följande bild visas djupt kapslad nodstruktur för en AEM webbplatsutdata:

![](assets/deep-nested-aem-site-node-structure.png){width="300" align="left"}

Observera att det finns en nod för varje `p` -element och dess efterföljande underelement och en liknande struktur skapas för alla andra element som används i ämnet.

Med AEM Guides kan du konfigurera hur nodstrukturen AEM platsutdata skapas internt. Du kan förenkla nodstrukturen vid angivna element, vilket innebär att du kan definiera ett element som ska betraktas som huvudelement och alla underelement i det sammanfogas med huvudelementet. Om du till exempel bestämmer dig för att förenkla `p` -element, därefter alla element som finns i `p` elementet kommer att sammanfogas med huvudelementet `p` -element. Ingen separat anteckning skapas för något underelement i `p` -element. Följande ögonblicksbild visar nodstrukturen förenklad vid `p` element:

![](assets/flattened-aem-site-node-structure.png){width="300" align="left"}

Så här förenklar du strukturen AEM platsnoden:

1. Ange det element som du vill lägga samman nodstrukturen i.

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

1. Aktivera platsnodens förenklingskonfiguration i configMgr.

   1. Öppna konfigurationssidan för Adobe Experience Manager Web Console.

      Standardwebbadressen för åtkomst till konfigurationssidan är:

      ```http
      http://<server name>:<port>/system/console/configMgr
      ```

   1. Sök efter och klicka på *com.adobe.dxml.flattening.FlatteningConfigurationService* paket.

   1. Välj **Förenkling av egenskap.enabled** alternativ.

   1. Klicka **Spara**.


>[!IMPORTANT]
>
> Om du har gjort några ändringar i elementmapping.xml-filen måste du öppna configMgr och spara eventuella paket så att ändringarna börjar gälla.

När du nu genererar AEM Site-utdata är noderna i `p` -elementet förenklas och lagras i `p` själva elementet. Du hittar de nya förenklingsegenskaperna för `p` element i CRXDE.

![](assets/flatten-aem-site-note-props-crxde.png){width="650" align="left"}

**Förhindra förenkling AEM platsnotsstrukturen**

På samma sätt som du anger vilken nod som ska förenklas AEM platsutdata kan du även ange ett element som du vill utesluta från den här konfigurationen. Om du till exempel vill lägga samman noder vid `body` -element, men du vill inte ha något `table` element inuti `body` för att förenkla kan du lägga till egenskapen exclude i `table` -elementets definition.

Exkludera `table` från förenkling, lägg till följande egenskap i `table` elementets definition:

`<preventancestorflattening>true|false</preventancestorflattening>`

### Konfigurera versionshantering för borttagna sidor i AEM webbplatsutdata

När du genererar AEM webbplatsutdata med **Ta bort och** Skapa ****som har valts för inställningen Befintliga utdatasidor skapas en version för sidan som tas bort. Du kan konfigurera systemet så att det inte längre skapas en version innan du tar bort den.

Utför följande steg för att stoppa skapandet av en version för den sida/de sidor som ska tas bort:

1. Öppna konfigurationssidan för Adobe Experience Manager Web Console.

   Standardwebbadressen för åtkomst till konfigurationssidan är:

   ```http
   http://<server name>:<port>/system/console/configMgr
   ```

1. Sök efter och klicka på *com.adobe.fmdita.config.ConfigManager* paket.

1. Välj **Skapa inte någon version för borttagna sidor** alternativ.

   >[!NOTE]
   >
   > När det här alternativet är markerat kan användare ta bort alla sidor direkt utan att skapa någon version för dem. Om alternativet inte är markerat skapas en version innan sidan tas bort.

1. Klicka **Spara**.

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

   1. Välj det nya fältet för att öppna **Inställningar** av fältet.

   1. I **Fältetikett**, ange metadatanamnet - Målgrupp.

   1. I **Mappa till egenskap** inställning, ange ./jcr:content/metadata/&lt;name of=&quot;&quot; the=&quot;&quot; metadata=&quot;&quot;>. Vi kommer till exempel att ställa in den på ./jcr:content/metadata/audition.

   Lägg till alla metadataparametrar som krävs med dessa steg.

1. Klicka **Spara**.


Den nya parametern visas nu på sidan Egenskaper för alla DITA-kartor.

![](assets/properties-page-custom-metadata.PNG){width="650" align="left"}

Därefter måste du göra anpassade metadata tillgängliga i DITA-kartkonsolen. Gör så här för att göra anpassade metadata tillgängliga på DITA-kartans dashboard:

1. Logga in AEM och öppna läget CRXDE Lite.

1. Gå till filen metadataList som finns på följande plats:

   /libs/fmdita/config/metadataList

   >[!NOTE]
   >
   > Filen metadataList innehåller en lista med egenskaper som visas i **Egenskaper** nedrullningsbar lista med en DITA-karta på kartkontrollpanelen. Som standard visas fyra egenskaper i den här filen: docstate, dc:language, dc:description och dc:title.

1. Lägg till anpassade metadata som du har lagt till på Forms-sidan Metadata Schema. Lägg till exempel till målgruppsparameter i slutet av standardlistan.

1. Klicka **Spara alla**.


Nu visas anpassade metadata i DITA-kartkonsolens **Egenskaper** nedrullningsbar lista.

Som utgivare måste du slutligen inkludera anpassade metadata i publicerade utdata. Så här bearbetar du anpassade metadata när du genererar utdata:

1. Navigera i resursgränssnittet till den DITA-karta som du vill publicera.

1. Markera DITA-schemafilen och öppna egenskapssidan.

1. Ange värdet för anpassade metadata på sidan Egenskaper. Vi har till exempel angett värdet External som målgruppsparameter.

   ![](assets/properties-page-custom-metadata-value.png){width="650" align="left"}

1. Klicka **Spara och stäng**.

1. Klicka på DITA-kartfilen för att öppna DITA-kartkonsolen.

1. I **Förinställningar för utdata** väljer du den förinställning du vill använda för att generera utdata.

1. Klicka **Redigera**.

1. Från **Egenskaper** väljer du de egenskaper som du vill skicka till publiceringsprocessen.

   ![](assets/props-in-publish-output.PNG){width="650" align="left"}


De valda egenskaperna/metadata skickas vidare till publiceringsprocessen och blir tillgängliga i det slutliga resultatet.

## Anpassa DITA-elementmappning med AEM {#id1679J600HEL}

DITA-element AEM stödlinjer mappas till motsvarande AEM. AEM Guides använder den här mappningen i arbetsflöden, till exempel publicering och granskning, för att konvertera DITA-element till en motsvarande AEM. Mappningen definieras i `elementmapping.xml` -fil, som du kommer åt i läget CRXDE Lite. Öppna följande URL i läget CRXDE Lite:

`/libs/fmdita/config/elementmapping.xml`

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
       <class>- topic/title</class> 
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
    <attribute from="attrname" to="propname" ispath="true|false" rel="source|target" />     
    </attributemap>     
    <skip>true|false</skip> 
</ditaelement>
```

I följande tabell beskrivs elementen i DITA-elementschemat:

| Element | Beskrivning |
|-------|-----------|
| `<ditaelement>` | Den översta noden för varje mappningselement. |
| `<class>` | Klassattributet för det DITA-målelement som du skriver komponenten för. <br>Klassattributet för DITA-ämnet är till exempel: <br>`topic/topic` |
| `<componentpath>` | CRXDE-sökvägen för den mappade AEM. |
| `<type>` | Möjliga värden: <br>- **SAMMANSATTA**: Bearbeta även underordnade element <br>- **FRISTÅENDE**: Hoppar över bearbetning av underordnade element |
| `<attributeprop>` | Används för att mappa serialiserade DITA-attribut och -värden till AEM noder som egenskap. Om du till exempel har `<note type="Caution">` -elementet och komponenten som mappas för det här elementet har `<attributeprop>attr_t</ attributeprop>`, serialiseras nodens attribut och värde till `attr_t` egenskap för motsvarande AEM nod \( `attr_t->type="caution"`\). |
| `<textprop>propname_t</textprop>` | Spara `getTextContent()` output till egenskap definierad av `propname_t.` **Obs!**  Det här är en optimerad egenskap. |
| `<xmlprop>propname_x </xmlprop>` | Spara serialiserad XML för den här noden till egenskap som definierats av `propname_x.` **Obs!** Det här är en optimerad egenskap. |
| `<xpath>` | Om XPath-elementet anges i elementmappningen ska XPath-villkoret också uppfyllas tillsammans med elementnamnet och klassen för att komponentmappningen ska användas. |
| `<target>` | Placera DITA-elementet i crx-databasen på den angivna platsen. <br>Möjliga värden:<br>- **head**: Under noden head <br>- **text**: Under styckenoden |
| `<wrapelement>` | Det HTML-element som innehållet ska radbrytas i. |
| `<wrapclass>` | Elementvärdet för egenskapen `wrapclass.` |
| `<attributemap>` | Behållarnod som innehåller en eller flera `<attribute>` noder. |
| `<attribute from="attrname" to="propname" ispath="true|false" rel="source|target" />` | Kopplar DITA-attributen till AEM egenskaper:<br>- **`from`**: DITA-attributnamn<br>- **`to`**: AEM komponentens egenskapsnamn <br>- **`ispath`**: Om attributet är ett sökvägsvärde \(till exempel: *image*\)<br>- **`rel`**: Om sökvägen är källan eller målet <br>**Obs!** If `attrname` börjar med `%`och sedan mappa `attrname minus '%'` att beskära `propname`&#39;. |

**Ytterligare information**

- Om du tänker åsidosätta standardelementmappningen rekommenderar vi att du inte gör ändringarna i standardinställningen `elementmapping.xml` -fil. Du bör skapa en ny XML-mappningsfil och placera filen på en annan plats, helst i en anpassad programmapp som du skapar.

- I `elementmapping.xml` -filen finns det många mappningsposter som refererar till komponenten fmdita/components/dita/wrapper. Wrapper är en generisk komponent som återger relativt enkla DITA-konstruktioner med hjälp av egenskaper på webbplatsnoden för att generera relevant HTML. Den använder `wrapelement` för att generera omslutande taggar och delegerar den underordnade återgivningen till motsvarande komponenter. Detta är användbart om du bara vill ha en behållarkomponent. I stället för att skapa en ny komponent som återger en viss behållartagg som `div` eller `p`kan du använda komponenten Wrapper med `wrapelement` och `wrapclass` -egenskaper för att uppnå samma effekt.

- Du bör inte spara stora mängder text i JCR-egenskaper för strängar. Beräkningen av den optimerade egenskapstypen i utdatagenereringen säkerställer att stort textinnehåll inte sparas som strängtyp. Om innehåll som är större än ett visst tröskelvärde behöver sparas, ändras egenskapstypen till binär. Som standard är det här tröskelvärdet konfigurerat till 512 byte, men det kan ändras i Configuration Manager \(*com.adobe.fmdita.config.ConfigManager*\) genom att ändra **Spara som binärt tröskelvärde** inställning.

- Om du tänker åsidosätta vissa \(och inte alla\) av elementmappningarna behöver du inte replikera hela `elementmapping.xml` -fil. Du måste skapa en ny XML-mappningsfil och definiera endast de element som du åsidosätter.

- När du har skapat XML-filen på den anpassade platsen uppdaterar du `Override Element Mapping` i `com.adobe.fmdita.config.ConfigManager` paket.


## Anpassa DITA-kartkonsolen {#id188HC08M0CZ}

AEM Guides ger dig flexibilitet att utöka funktionerna i DITA-kartkonsolen. Om du till exempel har en uppsättning rapporter som skiljer sig från vad som finns i AEM guider, kan du lägga till sådana rapporter i kartkonsolen. Om du vill anpassa kartkonsolen måste du skapa ett AEM klientbibliotek \(eller ClientLib\) som innehåller koden för att utföra de funktioner du behöver.

>[!NOTE]
>
> Direktändringar av sidkomponenter rekommenderas inte eftersom de skrivs över i nya versioner av produkten.

AEM stödlinjer innehåller `apps.fmdita.dashboard-extn` -kategori för anpassning av kartkonsol. När kartkonsolen läses in skapas de funktioner som finns under `apps.fmdita.dashboard-extn` körs och läses in.

>[!NOTE]
>
> Mer information om hur du skapar AEM klientbibliotek finns i [Använda bibliotek på klientsidan](https://helpx.adobe.com/experience-manager/6-4/sites/developing/using/clientlibs.html).

## Hantera bildåtergivning under generering av utdata {#id177BF0G0VY4}

AEM innehåller en uppsättning standardarbetsflöden och mediehandtag för att bearbeta resurser. I AEM finns fördefinierade arbetsflöden för att hantera resursbearbetning för de vanligaste MIME-typerna. För varje bild som du överför skapas vanligtvis flera återgivningar av samma bild i binärt format AEM. Dessa återgivningar kan ha olika storlek, med olika upplösning, med vattenstämpel eller någon annan förändrad egenskap. Mer information om hur AEM hanterar resurser finns i [Bearbeta resurser med mediehanterare och arbetsflöden](https://helpx.adobe.com/experience-manager/6-5/assets/using/media-handlers.html) i AEM.

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

/var/dxml/metadata/outputHistory/

Under en tidsperiod kan den sammanlagda storleken på alla loggfiler uppgå till GB. I AEM Guides kan du konfigurera en tidsperiod för att behålla dessa loggfiler i databasen. Efter den angivna tidsperioden tas loggarna och historiken för utdatagenerering bort från databasen.

>[!NOTE]
>
> Historiken för generering av utdata är loggposten i listan Genererade utdata på fliken Utdata.

Om du konfigurerar historikrensningsfunktionen påverkas utdatagenereringen för alla DITA-kartor i databasen. På fliken Utdata i en DITA-karta rensas historiken efter det angivna antalet dagar och vid den tidpunkt som anges i inställningen.

>[!NOTE]
>
> Borttagning av loggfiler och historik för generering av utdata påverkar inte de genererade utdata.

Utför följande steg för att ställa in en dag och en tid för att rensa utdatahistorik och -loggar:

1. Öppna konfigurationssidan för Adobe Experience Manager Web Console.

   Standardwebbadressen för åtkomst till konfigurationssidan är:

   ```http
   http://<server name>:<port>/system/console/configMgr
   ```

1. Sök efter och klicka på **com.adobe.fmdita.config.ConfigManager** paket.

1. I **Rensningsperiod för utdatahistorik** anger du efter hur många dagar som utdatahistoriken och utdataloggarna ska rensas. Som standard är den inställd på 5 dagar. Om du vill inaktivera den här funktionen anger du egenskapen till 0.

1. I **Tömningstid för utdatahistorik** anger du den tidpunkt då rensningsprocessen initieras. Som standard är det 0:00 \(eller 12:00 midnatt\). Rensningsprocessen utförs dagligen på utdata som genereras före det antal dagar som anges i **Rensningsperiod för utdatahistorik** -egenskap.

   >[!NOTE]
   >
   > Som standard utförs rensningsfunktionen varje midnatt på utdata som är äldre än 5 dagar.

1. Klicka **Spara**.


## Ändra gränsen för den nyligen genererade utdatalistan {#id1679JH0H0O2}

Du kan ändra det maximala antalet genererade utdata som visas på fliken Utdata för en DITA-karta. Som standard visas en lista med de senaste 25 genererade utdatafilerna. Om du vill ändra antalet utdata som ska visas i listan uppdaterar du **Gräns för utdatalista** i `com.adobe.fmdita.config.ConfigManager` paket.

>[!TIP]
>
> Se *Utdatahistorik* i Best practices Guide[appendix.md\#](appendix.md#) för bästa praxis när det gäller att arbeta med utdatahistorik.

## Prestandaoptimering för utdatagenerering {#id176LB050VUI}

Med AEM Guides kan du konfigurera poolstorleken för utdatagenereringsprocesser som styr antalet processer för generering av utdata som körs samtidigt. Som standard är processpoolens storlek inställd på antalet processorkärnor som är tillgängliga i systemet plus ett. Du kan ändra värdet till 1 om du vill ha sekventiell publicering. I det här fallet körs den första publiceringsaktiviteten och nästa publiceringsåtgärd lagras i publiceringskön.

Om du vill ändra storleken på bearbetningspoolen för utdatagenerering uppdaterar du **Storlek på genereringspool** i `com.adobe.fmdita.publish.manager.PublishThreadManagerImpl` paket.

