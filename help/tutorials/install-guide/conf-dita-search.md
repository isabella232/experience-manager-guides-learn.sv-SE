---
title: Konfigurera sökning i AEM Assets UI
description: Lär dig hur du konfigurerar sökning efter AEM Assets-användargränssnitt
source-git-commit: dcd27b39b64edec83b56fe9aa4a2abdc321b95a9
workflow-type: tm+mt
source-wordcount: '1695'
ht-degree: 0%

---

# Konfigurera sökning i AEM Assets UI {#id192SC800MY4}

Som standard känner AEM inte igen DITA-innehåll, vilket innebär att det inte finns någon mekanism för att söka efter DITA-innehåll i dess databas. Med AEM Guides kan du lägga till sökfunktionen för DITA-innehåll i AEM.

Som standard känner AEM inte igen DITA-innehåll, vilket innebär att det inte finns någon mekanism för att söka efter DITA-innehåll i dess databas. Det finns heller ingen OOTB-funktion för att söka efter innehåll baserat på deras UUID. Med AEM Guides kan du lägga till funktionerna för sökning efter DITA-innehåll och UUID-baserad sökning i AEM.

När du konfigurerar innehållssökning i DITA utförs följande uppgifter:

1. [Lägg till sökkomponenten för DITA-element i resursgränssnittet](#id192SF0F50HS)
1. [Lägg till UUID-baserad sökkomponent i resursanvändargränssnittet](#id2034F04K05Z)
1. [Ge behörigheter till användare](#id192SF0G0RUI)
1. [Lägg till anpassade element eller attribut i sökningen](#id192SF0G10YK)
1. [Extrahera metadata från befintligt innehåll](#id192SF0GA0HT)

Förutom att lägga till sökfunktioner kan du även konfigurera de mappar som inte ska ingå i sökningen. Mer information finns i [Uteslut temporära filer från sökresultat](#id197AHI0035Z).

## Lägg till sökkomponenten för DITA-element i resursgränssnittet {#id192SF0F50HS}

Gör följande för att lägga till en sökkomponent för DITA-innehåll i AEM Assets-gränssnittet:

1. Logga in i Adobe Experience Manager som administratör.

1. Klicka på **Adobe Experience Manager** överst och välj **verktyg**.

1. Välj **Allmänt** i listan med verktyg och klicka på **Sök i Forms** platta.

1. I **Sök i Forms** väljer du **Resursadministratörssökväg**.

1. Klicka **Redigera**.
1. I **Välj predikat** bläddra till slutet av listan.

1. Dra och släppa **DITA-elementpredikat** på önskad plats i sökformuläret.

   ![](assets/drag-search-predicate.png){width="650" align="left"}

1. Klicka **Klar** för att spara ändringarna.

   När du öppnar alternativet Filter i resursgränssnittet får du sökfilteralternativet DITA-element.

   ![](assets/search-filter-asset-console.png){width="350" align="left"}


## Lägg till UUID-baserad sökkomponent i resursanvändargränssnittet {#id2034F04K05Z}

Gör följande för att lägga till UUID-baserad sökkomponent i AEM Assets UI:

1. Logga in i Adobe Experience Manager som administratör.

1. Klicka på **Adobe Experience Manager** överst och välj **verktyg**.

1. Välj **Allmänt** i listan med verktyg och klicka på **Sök i Forms** platta.

1. I **Sök i Forms** väljer du **Resursadministratörssökväg**.

1. Klicka **Redigera**.
1. I **Välj predikat** flik, välja **Egenskapspredikat** och dra och släpp det på önskad plats i sökformuläret.

1. I **Inställningar** kan du ange följande information för den nya tillagda **Egenskapspredikat** komponent:

   - **Fältetikett**: UUID
   - **Egenskapsnamn**: jcr:content/fmUuid
1. Klicka **Klar** för att spara ändringarna.

   När du öppnar alternativet Filter i resursgränssnittet får du det UIS-baserade sökfilteralternativet.


## Ge behörigheter till användare {#id192SF0G0RUI}

Författare och utgivare måste få explicit behörighet för att kunna komma åt sökfunktionerna från Assets UI. Om du inte ger dessa behörigheter kommer dina användare inte att kunna söka efter DITA-innehåll baserat på deras element-/attributvärden eller UUID.

Utför följande steg för att ge åtkomst till DITA-sökfunktionen:

1. Gå till sidan med användar- och gruppbehörigheter. Standardwebbadressen för åtkomst till sidan är:

   `http://<server name>:<port>/useradmin.html`

1. Sök efter användargruppen eller en enskild användare som du vill ge åtkomst till. Om du till exempel vill ge åtkomst till alla användare i gruppen författare anger du författare i **Filterfråga** fält och tryck **Retur**.

   ![](assets/authors-group-permission.png){width="350" align="left"}

1. Välj **författare** grupp.

1. I den högra rutan väljer du **Behörigheter** -fliken.

1. Navigera till följande mapplats:

   /conf/global/settings/dam/search

1. Ge **Läs** behörighet för sökmappen.

   ![](assets/read-permission-authors.png){width="650" align="left"}

1. Klicka **Spara**.


Den valda användaren eller användargruppen har nu åtkomst till funktionen för sökning av DITA-innehåll i resursgränssnittet.

## Lägg till anpassade element eller attribut i sökningen {#id192SF0G10YK}

För att DITA-sökningen ska fungera krävs viss förbearbetning av DITA-innehållet. Detta förbearbetningssteg extraherar selektivt innehåll från enskilda DITA-kartor och -ämnen så att det kan indexeras för snabbare sökning. Internt anropas processen *Serialisering*. Serialisering av DITA-filer sker under överföring av innehåll eller kan även utföras on-demand. Den använder en konfigurationsfil för att avgöra hur mycket innehåll från varje DITA-fil som ska indexeras. Standardplatsen för serialiseringsfilen är:

/libs/fmdita/config/serializationconfig.xml

Med standardsökkonfigurationen kan du söka efter alla element och attribut i DITA `prolog` -element. Om du vill söka baserat på andra element eller attribut måste du konfigurera sökserialiseringsfilen.

>[!NOTE]
>
> Om du vill använda standardsökkonfigurationen i `prolog` kan du hoppa över den här processen.

Filen innehåller två huvudavsnitt - attributuppsättning och regeluppsättning. Nedan visas ett utdrag av regeluppsättningsavsnittet:

```XML
<ruleset filetypes="xml dita"><!-- Element rules --><rule xpath="//[contains(@class, 'topic/topic')]/[contains(@class, 'topic/prolog')]//*[not(*)]" text="yes" attributeset="all-attrs" /><!-- Attribute rules --><rule xpath="//[contains(@class, 'topic/topic')]/[contains(@class, 'topic/prolog')]///@[local-name() != 'class']" /></ruleset>
```

I avsnittet Regeluppsättning kan du ange:

- Regler för att extrahera elementen

- Regler för att extrahera attribut


En regel består av följande:

xpath : Det här är XPath-frågan som hämtar element eller attribut från DITA-filer. Standardkonfigurationen för elementregeln hämtar alla `prolog` -element. Och standardkonfigurationen för attributregeln hämtar alla attribut för `prolog` -element. Du kan ange en XPath-fråga för att serialisera de element eller attribut som du vill söka efter.

XPath-frågan innehåller dokumenttypens klassnamn. The `topic/topic` -klassen används för ämnestyp DITA-dokument. Om du vill skapa en regel för andra DITA-dokument måste du använda följande klassnamn:

| Dokumenttyp | Klassnamn |
|-------------|----------|
| Ämne | - ämne |
| Uppgift | - ämne/ämne uppgift/uppgift |
| Koncept | - ämne/ämne/begrepp |
| Referens | - ämnesreferens/referens |
| Karta | - karta/karta |

text: Om du vill söka efter texten i det angivna elementet anger du yes-värdet. Om du anger nej som värde serialiseras bara attributen i elementet. Attributen som du vill söka efter måste anges i attributuppsättningsavsnittet.

attributuppsättning : Ange ID:t för den attributuppsättning som du vill associera med den här regeln. Värdet all-attributes är ett specialfall som anger att alla attribut för den här regeln måste serialiseras.

En attributuppsättning innehåller en lista med attribut som du vill söka efter i DITA-innehåll. Attributuppsättningen innehåller följande:

id : En unik identifierare för attributuppsättningen. Detta ID anges i attributuppsättningsparametern för en regeluppsättning.

attribute : En lista med attribut som du vill söka efter. För varje attribut måste du skapa en enskild post i `attribute` -element.

Utför följande steg för att lägga till anpassade DITA-element eller attribut i sökserialiseringsfilen:

1. Logga in AEM och öppna läget CRXDE Lite.

1. Navigera till serialiseringskonfigurationsfilen som finns på följande plats:

   /libs/fmdita/config/serializationconfig.xml

1. Skapa en överläggsnod på `config` i `apps` nod.

1. Navigera till konfigurationsfilen som finns i `apps` nod:

   `/apps/fmdita/config/serializationconfig.xml`

1. Lägg till nödvändiga element- eller attributregeluppsättningar.

1. Spara filen.

1. Öppna konfigurationssidan för Adobe Experience Manager Web Console. Standardwebbadressen för åtkomst till konfigurationssidan är:

   http://&lt;server name=&quot;&quot;>:&lt;port>/system/console/configMgr

1. Sök efter och klicka på *com.adobe.fmdita.config.ConfigManager* paket.

1. Klicka **Spara**.


Den nya serialiseringsinformationen lagras och aktiveras för sökning. Du måste dock extrahera metadata från ditt befintliga DITA-innehåll för att bli tillgängligt för sökning.

## Extrahera metadata från befintligt innehåll {#id192SF0GA0HT}

När du har ändrat standardfilen för sökserialisering måste du aktivera alternativet Extrahering av DITA-metadata i dialogrutan *com.adobe.fmdita.config.ConfigManager* paketera och kör sedan arbetsflödet för att extrahera metadata. Detta extraherar de metadata som krävs från de befintliga DITA-filerna och det samma görs sedan tillgängligt för sökning.

Om du skapar nya filer eller redigerar en fil efter att du har uppdaterat serialiseringsfilen, extraheras metadata automatiskt från sådana filer. Processen att extrahera metadata krävs bara för filer som redan finns i AEM.

Det finns två saker att extrahera metadata från befintliga DITA-filer:

1. Aktivera alternativet för metadataextrahering i configMgr
1. Köra arbetsflödet för metadataextrahering

Utför följande steg för att aktivera alternativet för metadataextrahering i configMgr:

1. Öppna konfigurationssidan för Adobe Experience Manager Web Console. Standardwebbadressen för åtkomst till konfigurationssidan är:

   http://&lt;server name=&quot;&quot;>:&lt;port>/system/console/configMgr

1. Sök efter och klicka på *com.adobe.fmdita.config.ConfigManager* paket.

1. Välj **Aktivera extrahering av DITA-metadata** alternativ.

1. Klicka **Spara**.


Utför följande steg för att köra arbetsflödet för metadataextrahering:

1. Logga in i Adobe Experience Manager som administratör.

1. Klicka på **Adobe Experience Manager** överst och välj **verktyg**.

1. Välj **Stödlinjer** i listan med verktyg och klicka på **DITA-metadataextrahering** platta.

1. Om du vill extrahera metadata från en enskild fil och dess beroenden klickar du på **Välj en fil** och bläddra efter en fil.

1. Om du vill hämta metadata från flera filer i en mapp klickar du på **Välj mapp** , bläddra och välj önskad mapp. Klicka på **Lägg till** om du vill lägga till mappen i listan med serialiseringsåtgärder.

   >[!NOTE]
   >
   > Du kan markera och lägga till flera mappar i en serialiseringsåtgärd.

1. Klicka **Starta**.

1. I dialogrutan Bekräfta extrahering av metadata klickar du på **OK**.


## Uteslut temporära filer från sökresultat {#id197AHI0035Z}

Som standard utförs sökningen i hela AEM. Det kan finnas platser som du vill utesluta från sökningen. När du till exempel initierar arbetsflödet för översättning av innehåll blir de ogodkända filerna kvar i en tillfällig mapp. När du utför sökningen returneras filer från den här tillfälliga platsen också i sökresultaten.

Om du inte vill att AEM stödlinjer ska söka efter den tillfälliga platsen för översättningsmappen, måste du lägga till en tillfällig mappsökväg i exkluderingslistan.

Utför följande steg för att exkludera den tillfälliga översättningsmappen från sökningen:

>[!NOTE]
>
> Du kan lägga till andra mapplatser i exkluderingslistan med den här proceduren.

1. Logga in AEM och öppna läget CRXDE Lite.

1. Navigera till noden damAssetLucene som finns på följande plats:

   /oak:index/damAssetLucene

1. Lägg till följande egenskap i noden damAssetLucene:

   | Egenskapsnamn | Typ | Värde |
   |-------------|----|-----|
   | excludePaths | Sträng\[\] | Lägg till följande värde i den här egenskapen: <br>/content/dam/projects/translation\_output |

1. Navigera till lucene-noden på följande plats:

   /oak:index/lucene

1. Lägg till följande egenskap i noden lucene:

   | Egenskapsnamn | Typ | Värde |
   |-------------|----|-----|
   | excludePaths | Sträng\[\] | Lägg till följande värden i den här egenskapen: <br><ul><li>/var/dxml</li><li>/content/dam/projects/translation\_output</li></ul> |
