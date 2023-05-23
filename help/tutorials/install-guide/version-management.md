---
title: Versionshantering
description: Läs om hur versionshantering fungerar
source-git-commit: 5ac066bb8db32944abd046f64da11eeb1bdbe467
workflow-type: tm+mt
source-wordcount: '1657'
ht-degree: 0%

---


# Versionshantering {#id181GB000XY4}

Versionshantering är en viktig aspekt i alla innehållshanteringssystem. Du kan skapa en ögonblicksbild av din digitala resurs vid en viss tidpunkt. När du har en version av en digital resurs på plats kan du återställa den version av resursen som krävs och uppdatera den. När du skapar en version av en resurs checkar du ofta ut och checkar in den önskade resursen.

Som administratör kan du tillämpa regler som hindrar användare från att redigera en fil utan att checka ut den. På samma sätt kan du se till att alla utcheckade filer checkas in igen för att undvika dataförluster.

I fleranvändningsmiljöer är det också viktigt att se till att användarna inte tar bort filer från systemet. Detta krav är mer kritiskt för filer som har checkats ut av andra användare.Du kan tillåta eller förhindra användare från att skriva över filer som har checkats ut av andra användare. För att förhindra att användare råkar ta bort utcheckade filer från systemet innehåller AEM stödlinjer en konfiguration som du kan använda. Förutom utcheckade filer kan du även styra borttagningen av filer som innehåller referenser eller som refereras från andra filer. Dessutom kan du skapa en ny version för överförda filer.

## Skapa ny version för överförd fil

>[!NOTE]
>
> Den här konfigurationen kan bara användas när filer överförs.

Så här skapar du en ny version av den överförda filen:

1. Öppna konfigurationssidan för Adobe Experience Manager Web Console.

   Standardwebbadressen för åtkomst till konfigurationssidan är:

   ```http
   http://<server name>:<port>/system/console/configMgr
   ```

1. Sök efter och klicka på **com.adobe.fmdita.config.ConfigManager** paket.

1. Välj **Skapa ny version för överförd fil** alternativ.

   Som standard är det här alternativet inaktiverat.

   När alternativet är markerat utförs en ny versionshanteringsmekanism och åsidosätter standardbeteendet för överföring, som är för alla efterföljande överföringar, så sparas innehållet i den överförda filen som en ny version. Om alternativet är avmarkerat använder AEM stödlinjer AEM standardmekanism för versionshantering.

1. Klicka **Spara**.


>[!NOTE]
>
> Du kan överföra filer i grupper om 70 eller mindre om du aktiverar egenskapen **Skapa ny version för överförd fil** \(create.ver.new.content\) och använd **Resurser, användargränssnitt** för att överföra resurser i grupp.

## Konfigurera inställningar som tillåter redigering av utcheckade filer

Med AEM Guides Web Editor kan du skapa och uppdatera DITA-avsnitt. Du kan konfigurera Web Editor så att endast de dokument som har checkats ut från databasen kan redigeras. Detta säkerställer att ingen annan skribent av misstag skriver över ett ämne som har öppnats för redigering av en annan skribent. När ett ämne öppnas för redigering kan författaren checka in filen när filen stängs.

En annan viktig regel är att se till att filer som har checkats ut checkas in i systemet igen. Detta förhindrar att användare av misstag stänger filerna utan att checka in dem igen.

Gör så här för att aktivera de här funktionerna:

1. Öppna konfigurationssidan för Adobe Experience Manager Web Console.

   Standardwebbadressen för åtkomst till konfigurationssidan är:

   ```http
   http://<server name>:<port>/system/console/configMgr
   ```

1. Sök efter och klicka på **com.adobe.fmdita.xmleditor.config.XmlEditorConfig** paket.

1. Välj **Inaktivera redigering utan utcheckning** alternativ.

   ![](assets/xml-editor-config.png){width="650" align="left"}

   Med det här alternativet kommer användare inte att se alternativet Redigera i verktygsfältet förrän de checkar ut en fil.

1. Välj **Fråga efter incheckning vid stängning** om du vill visa ett varningsmeddelande när en utcheckad fil stängs utan att spara eller checka in den i databasen igen.

1. Klicka **Spara**.


>[!NOTE]
>
> Oavsett om du aktiverar eller inaktiverar den här funktionen är alternativen Checka ut och Checka in alltid tillgängliga i en ämnesförhandsvisning.

## Skriv över utcheckad fil vid överföring

>[!NOTE]
>
> Den här konfigurationen används bara när du skapar filer från resursgränssnittet och inte när du överför filer med WebDAV-verktyget.

Gör så här om du vill tillåta användare att skriva över filen vid överföring som har checkats ut av dem eller någon annan användare:

1. Öppna konfigurationssidan för Adobe Experience Manager Web Console.

   Standardwebbadressen för åtkomst till konfigurationssidan är:

   ```http
   http://<server name>:<port>/system/console/configMgr
   ```

1. Sök efter och klicka på **com.adobe.fmdita.config.ConfigManager** paket.

1. Välj **Skriv över utcheckad fil vid överföring** alternativ.

   Som standard är det här alternativet PÅ. När det här alternativet är markerat kan användare skriva över utcheckade filer. Om alternativet inte är markerat går det inte att skriva över filen om den är utcheckad av någon annan användare.

1. Klicka **Spara**.


## Förhindra borttagning av utcheckade filer

Så här förhindrar du att användare av misstag tar bort filer som har checkats ut av dem eller någon annan användare:

1. Öppna konfigurationssidan för Adobe Experience Manager Web Console.

   Standardwebbadressen för åtkomst till konfigurationssidan är:

   ```http
   http://<server name>:<port>/system/console/configMgr
   ```

1. Sök efter och klicka på **com.adobe.fmdita.xmleditor.config.XmlEditorConfig** paket.

1. Välj **Förhindra borttagning av utcheckat innehåll** alternativ.

   Som standard är det här alternativet PÅ. När det här alternativet är markerat kan användare inte ta bort utcheckade filer.

1. Klicka **Spara**.


En ny indexegenskap som stöd för den här funktionen `drivelock` läggs till i `oak:index`:

`/oak:index/damAssetLucene/indexRules/dam:Asset/properties/drivelock`

![](assets/index-property-oak-index-drivelock.png){width="800" align="left"}

Förutom den nya indexegenskapen ser du till att följande egenskaper är inställda på `/oak:index/damAssetLucene`:

- `jcr:primaryType`=`"oak:QueryIndexDefinition"`
- `async`=`"async"`
- `compatVersion`=`"{Long}2"`
- `evaluatePathRestrictions`=`"{Boolean}true"`
- `reindex`=`"{Boolean}false"`
- `reindexCount`=`"{Long}3"` *\(detta är antalet gånger som omindexering görs, det ersätts med installationen av vårt paket\)*
- `type`=`"lucene"`

>[!NOTE]
>
> Du kan ändra värdet för `reindex` till `"{Boolean}true"`. Detta ger snabbare sökresultat för de utcheckade filerna i en hierarki av mappar.

## Förhindra borttagning av refererade filer

Som administratör kan du styra vem som kan ta bort filer från AEM. I synnerhet om en fil innehåller referenser eller refereras av någon annan fil, kan du definiera vem som kan ta bort sådana filer.

Med den här konfigurationen kan du tillåta eller neka alla användare att ta bort filer eller tillåta att endast en viss användargrupp tar bort filer. Om det är tillåtet att ta bort filer följer du följande process:

- Om du tar bort en mapp som innehåller alla refererade och refererade filer, tas alla filer bort. Processen tar först bort alla filer som inte innehåller några referenser, följt av filerna som innehåller referenser eller refereras.

- Om du tar bort en mapp, och en fil i mappen refereras till av en fil utanför den mappen, uppmanas du att ta bort referensen innan du tar bort filen.


Så här definierar du vem som kan ta bort en fil som innehåller referenser eller som refereras av andra filer:

1. Öppna konfigurationssidan för Adobe Experience Manager Web Console.

   Standardwebbadressen för åtkomst till konfigurationssidan är:

   ```http
   http://<server name>:<port>/system/console/configMgr
   ```

1. Sök efter och klicka på **com.adobe.fmdita.config.ConfigManager** paket.

1. Leta reda på **Blockborttagning för refererade resurser** alternativ.

1. Beroende på vem du vill ge åtkomst för borttagning anger du en av följande konstanter:

   - allow\_unsafe\_delete\_for\_all: Ge alla användare behörighet att ta bort filer. Om filen innehåller referenser eller refereras av andra filer kan du även ta bort sådana filer. Innan du tar bort filen visas ett meddelande med referenserna, du kan avbryta borttagningsåtgärden, ta bort referenserna och slutligen ta bort filen. Du kan också framtvinga borttagning av filen utan att ta bort referenserna.

      ![](assets/allow_unsafe_delete-force-delete.PNG){width="550" align="left"}

   - allow\_unsafe\_delete\_for\_delete\_assets\_group: En administratör eller en användare som tillhör *delete-assets* grupp kan ta bort filer. Om någon annan användare försöker ta bort filer med referenser, kommer de inte att kunna ta bort sådana filer förrän alla referenser tas bort. Följande skärmbild visas när en användare som inte har behörighet försöker ta bort filer.

      ![](assets/allow_unsafe_delete_for_delete_assets_group.PNG){width="550" align="left"}

   - block\_unsafe\_delete\_for\_all: Tillåt inte alla användare \(inklusive administratörer\) att ta bort filer förrän referenser till och från filen\(erna\) tas bort.

1. Klicka **Spara**.


## Rensa äldre versioner av DITA-filer

När du uppdaterar innehåll och skapar nya versioner bevaras de tidigare versionerna av DITA-filerna i databasen. Många versioner kan skapas för dina DITA-filer under en period och kan tillsammans ta upp mycket utrymme i din databas. I AEM kan du konfigurera de äldre versionerna som ska tas bort från databasen.

Om du har administratörsbehörighet kan du komma åt det här verktyget via den angivna URL:en:

`<server folder path> /libs/fmdita/clientlibs/xmleditor_version_purge/page.html`

Den version av en DITA-fil som uppfyller något av de angivna villkoren bevaras och rensas inte:

- Är den första versionen av en fil
- Ingår i en baslinje
- Ingår i arbetsflödet för översättning och granskning
- Har en etikett tillämpat
- Uppfyller definierad ålder eller angivet antal versionskriterier

Utför följande steg för att rensa de äldre versionerna:

1. Ange följande information om de filer du vill rensa:

   ![](assets/preview-purge-report.png){width="350" align="left"}

1. 
   - **Antal versioner att behålla från den senaste versionen**: Ange antalet versioner som ska behållas och inte rensas. Om vi till exempel anger 5 behålls de senaste 5 versionerna och de tidigare versionerna är kvalificerade att rensas om andra rensningsvillkor uppfylls.
- **Behåll versioner som skapats inom tidsintervallet \(i dagar\)**: Ange högsta ålder för en version i dagar. Versioner som är äldre än det angivna antalet dagar kan rensas om andra rensningsvillkor uppfylls. Om vi till exempel anger 100 kvalificeras alla versioner som skapats före 100 dagar att rensas om andra rensningsvillkor uppfylls.
- **Bana**: Välj sökvägen till filen eller mappen vars filer du vill rensa.

   >[!NOTE]
   >
   > Du kan bara rensa DITA-filer.

1. Klicka **Förhandsgranska rensningsrapport**.

   >[!NOTE]
   >
   > Det kan bara finnas en rensningsåtgärd åt gången. Du kan inte initiera en annan versionsrensningsåtgärd om en sådan pågår.

   Rapporten för versionsrensning genereras.

1. Ladda ned versionsrensningsrapport och kontrollera vilka filer och versioner som ska rensas.
1. Du kan välja att **Avbryt tömning** eller **Starta tömning**.

   ![](assets/download-purge-report.png){width="350" align="left"}

   Tömningsstatusen visas.

   Klicka **Hämta versionsrensningsrapport** för att visa de rensade versionerna. Den här rapporten innehåller rensningsstatus för alla versioner tillsammans med orsaker till varför en viss version kvarstod eller varför den rensades.


>[!NOTE]
>
> Rapporten hämtas på följande plats: /var/dxml/versionpurge

