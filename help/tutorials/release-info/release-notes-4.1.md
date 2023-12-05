---
title: Versionsinformation | Adobe Experience Manager Guides 4.1
description: Senaste utgåvan av Adobe Experience Manager Guides
source-git-commit: 880cd344ceb65ea339be699ebcad41c0d62e168a
workflow-type: tm+mt
source-wordcount: '3644'
ht-degree: 0%

---

# 4.1.x-versionen av Adobe Experience Manager Guides

Den här versionsinformationen innehåller uppgraderingsinstruktioner, nya funktioner och förbättringar i version 4.1.x av Adobe Experience Manager Guides (kallas senare *AEM stödlinjer*).

## Uppgradera till den senaste versionen

Du kan enkelt uppgradera din nuvarande version av AEM till version 4.1.3. Innan du uppgraderar till version 4.1.3 AEM handboken måste du tänka på följande:
* Om du använder version 4.1 eller 4.1.x kan du uppgradera direkt till version 4.1.3.
* Om du använder version 4.0.x måste du uppgradera till version 4.1 eller 4.1.x innan du uppgraderar till 4.1.3.
* Om du använder version 3.8.5 måste du uppgradera till version 4.0.x innan du uppgraderar till 4.1.
* Om du har en tidigare version än 3.8.5, se uppgraderingsavsnittet i den produktspecifika installationsguiden.

Mer information finns i [Uppgraderingsinstruktioner](assets/Adobe-Experience-Manager-Guides-Upgrade-Instructions-EN.pdf).

## 4.1.3 | Versionsinformation

## Kompatibilitetsmatris

I det här avsnittet visas kompatibilitetsmatrisen för de program som stöds av AEM 4.1.3.

### ADOBE EXPERIENCE MANAGER

**Ej UID**
Version 6.5 Service Pack 13, 12, 11 eller 10

**UUID**
Version 6.5 Service Pack 13, 12, 11 eller 10

Mer information finns i avsnittet Tekniska krav i guiden Installera och konfigurera Adobe Experience Manager-guider.


### FrameMaker och FrameMaker Publishing Server

| Frigör | FMPS 2020 | FMPS 2019 | Fm 2020 | Fm 2019 |
| --- | --- | --- | --- | --- |
| 4.1.3 (ej UUID) | 2020.2 eller senare* | 2019 | 2020.3 eller senare | 2019.8 (senaste uppdateringen) |
| 4.1.3 (UID) | 2020.2 eller senare* | Inte kompatibel | 2020.4 eller senare | Inte kompatibel |
| | | | |

*Originalplan och villkor skapade i AEM stöds i FMPS-versioner från och med 2020.2.

### Syrgasanslutning

| Frigör | Syrgasanslutningsfönster | Syrgasanslutning Mac | Redigera i syrgasfönster | Redigera i Syrgas Mac |
| --- | --- | --- |--- |--- |
| 4.1.3 (ej UUID) | 2,0 | 2,0 | 1,6 | 1,6 |
| 4.1.3 (UID) | 2,7 | 2,7 | 2,3 | 2,3 |
|  |  |   |


## Åtgärdade problem

Felet som har åtgärdats listas nedan:

* Webbredigeraren läser in tomma sidor ibland. (10678)


## 4.1.2 | Versionsinformation

## Kompatibilitetsmatris

I det här avsnittet visas kompatibilitetsmatrisen för de program som stöds av AEM 4.1.2.

### ADOBE EXPERIENCE MANAGER

**Ej UID**
Version 6.5 Service Pack 13, 12, 11 eller 10

**UUID**
Version 6.5 Service Pack 13, 12, 11 eller 10

Mer information finns i avsnittet Tekniska krav i guiden Installera och konfigurera Adobe Experience Manager-guider.


### FrameMaker och FrameMaker Publishing Server

| Frigör | FMPS 2020 | FMPS 2019 | Fm 2020 | Fm 2019 |
| --- | --- | --- | --- | --- |
| 4.1.2 (ej UUID) | 2020.2 eller senare* | 2019 | 2020.3 eller senare | 2019.8 (senaste uppdateringen) |
| 4.1.2 (UID) | 2020.2 eller senare* | Inte kompatibel | 2020.4 eller senare | Inte kompatibel |
| | | | |

*Originalplan och villkor skapade i AEM stöds i FMPS-versioner från och med 2020.2.

### Syrgasanslutning

| Frigör | Syrgasanslutningsfönster | Syrgasanslutning Mac | Redigera i syrgasfönster | Redigera i Syrgas Mac |
| --- | --- | --- |--- |--- |
| 4.1.2 (ej UUID) | 2,0 | 2,0 | 1,6 | 1,6 |
| 4.1.2 (UID) | 2,7 | 2,7 | 2,3 | 2,3 |
|  |  |   |


## Åtgärdade problem

De buggar som har åtgärdats i olika områden listas nedan:

* När du väljer alla mappprofiler visas en osynlig mappprofil (som är felaktig). (10393)
* När du skapar baslinjen väljs inte den senaste versionen, när användarens tidszon skiljer sig från serverns tidszon. (10336)
* Kortkommandot Ctrl+F öppnar inte webbläsarsökningen modal på Resurskonsolen efter installationen av AEM 4.1. (10339)
* Fel vid skapande av baslinje inträffar för det ämne som har referensen till en mapp. (10383)
* Fliken Utdatainställningar visar ibland en tom skärm och i vissa fall visas icke-redigerbara förinställningar. (10390)
* Hantering av nyckelrutor leder till undantag och fel. 10449)

### Kända problem med lösningar

* Baslinje som exporteras under översättning läses inte in på baslinjefliken i redigeraren.

  **Tillfällig lösning**: Använd baslinjefliken på DITA-kartkontrollpanelen.

## 4.1 | Versionsinformation

Den här versionsinformationen innehåller uppgraderingsinstruktioner, nya funktioner och förbättringar i version 4.1.x av Adobe Experience Manager Guides (kallas senare *AEM stödlinjer*).

## Kompatibilitetsmatris

I det här avsnittet visas kompatibilitetsmatrisen för de program som stöds i AEM 4.1.

### ADOBE EXPERIENCE MANAGER

**Ej UID**
Version 6.5 Service Pack 13, 12, 10 eller 11

**UUID**
Version 6.5 Service Pack 13, 12, 10 eller 11

Mer information finns i avsnittet Tekniska krav i guiden Installera och konfigurera Adobe Experience Manager-guider.




### FrameMaker och FrameMaker Publishing Server

| Frigör | FMPS 2020 | FMPS 2019 | Fm 2020 | Fm 2019 |
| --- | --- | --- | --- | --- |
| 4.1 (ej UUID) | 2020.2 eller senare* | 2019 | 2020.3 eller senare | 2019.8 (senaste uppdateringen) |
| 4.1 (UUID) | 2020.2 eller senare* | Inte kompatibel | 2020.4 eller senare | Inte kompatibel |
| | | | |

*Originalplan och villkor skapade i AEM stöds i FMPS-versioner från och med 2020.2.

### Syrgasanslutning

| Frigör | Syrgasanslutningsfönster | Syrgasanslutning Mac | Redigera i syrgasfönster | Redigera i Syrgas Mac |
| --- | --- | --- |--- |--- |
| 4.1 (ej UUID) | 2,0 | 2,0 | 1,6 | 1,6 |
| 4.1 (UUID) | 2,7 | 2,7 | 2,3 | 2,3 |
|  |  |  |


## Nya funktioner och förbättringar

AEM innehåller många förbättringar och nya funktioner i version 4.1:

### PDF

Stöd för att skapa ett inbyggt PDF har också lagts till i version 4.1 av AEM. En ny publiceringsmotor har lagts till med följande funktioner:
* Skapa en CSS-mall
* Skapa olika sidmallar
* Designa PDF-mallar med CSS och sidmallar
* Publicera karta och ämnesinnehåll i PDF-format

### Stöd för kunskapsbasens webbplatssökväg vid artikelbaserad publicering

AEM Guides innehåller den artikelbaserade publiceringsfunktionen för att stegvis generera utdata från ett eller flera ämnen eller publicera innehållet på en kunskapsbaserad plattform. I version 4.1 har du ytterligare ett alternativ för att välja den platssökväg i kunskapsbasen till vilken ämnet/kartan ska publiceras. När du har valt sökvägen genereras utdata på den angivna sökvägen.

### Förbättrad webbredigerare

* **Förbättrad tangentupplösning**

En DITA-innehållsnyckelreferens infogar en del av innehållet från ett ämne i ett annat. Den använder en nyckel för att hitta innehållet. De nyckelreferenser som är associerade med ett DITA-avsnitt måste lösas. Den markerade rotkartan har högsta prioritet för att lösa nyckelreferenser.

![dialogruta för användarinställningar](assets/user-preferences.png)

Nu löses nyckelreferenserna utifrån rotmappningen som angetts i följande prioritetsordning:

1. Användarinställningar
1. Kartvyn, panel
1. Mappprofil

Mer information finns i *Lös nyckelreferenser* i guiden Använda Adobe Experience Manager-stödlinjer.

* **Lägga till en anpassad panel i den vänstra panelen**

Nu kan du lägga till en anpassad panel i den vänstra panelen i Web Editor. Du kan använda en anpassad panel för olika syften, som att ge hjälp eller utföra testningen för ett projekt. Om en anpassad panel har konfigurerats visas den också i listan med paneler i **Inställningar för Redigeraren**. Du kan växla om du vill visa eller dölja den anpassade panelen.

* **Möjlighet att ändra dokumentstatus för ämnen i en DITA-karta**

Nu kan du enkelt ändra dokumentstatus för valda ämnen i en DITA-karta. Du kan också öppna och redigera egenskaperna för markerade ämnen i en DITA-karta från **Fler alternativ** längst ned på panelen Kartvy.

![valda ämnesegenskaper](assets/map-view-properties.png)

* **Versionsinformation som visas i förhandsgranskningsläget**

Webbredigeraren hjälper dig att hantera dina versioner. Nu kan du även se versionen av det aktiva ämnet eller DITA-kartan i det övre högra hörnet av ämnesfliken i förhandsgranskningsläget för ett ämne.

![förhandsgranskningsversion](assets/preview-version.png)


* **Förbättrat uppdateringsbeteende för webbredigeraren**

Följande förbättringar är nu tillgängliga vid uppdatering av webbläsaren i Web Editor:

* Nu har du stöd för att uppdatera webbläsaren medan du redigerar innehållet i Web Editor. Om du trycker på ikonen för uppdatering av webbläsaren när en eller flera filer med osparade ändringar öppnas för redigering, uppmanas du att spara filerna eller avbryta uppdateringsåtgärden.

* Även när du uppdaterar webbläsaren behålls vyerna från den vänstra panelen och den högra panelen.

* Det aktiva ämnet eller DITA-kartan öppnas på nytt i området för innehållsredigering.

* **Skapa kartor baserade på anpassade mallar**

Nu får du den kraftfulla funktionen för att skapa anpassade kartmallar. Du kan använda dem för att skapa DITA-kartor tillsammans med ämnesmallarna och mappningsmallarna som refereras i kartmallen.

![dita-mallar](assets/dita-templates.png)

Du kan även referera till andra mappningsmallar och ämnesmallar från den anpassade mappningsmallen. De refererade mappningsmallarna kan hänvisa till olika mappningsmallar, ämnesmallar, ämnen, kartor, bilder, videor och andra resurser.

![skapa datamallar](assets/create-dita-template.png)

Den anpassade mappningsmallen kan hjälpa dig att enkelt replikera mappningsmallarna och hela den refererade mappstrukturen. Dessa anpassade mallar är särskilt användbara när du vill skapa och återskapa flera kartor med rekursiva strukturer och referenser.

* **Stöd för Schematron**
&quot;Schematron&quot; avser ett regelbaserat valideringsspråk som används för att definiera tester för en XML-fil. Med en Schematron-fil kan du definiera vissa regler och sedan validera dem för ett DITA-avsnitt eller en karta. Webbredigeraren stöder Schematron-filer. Du kan importera schemafilerna och redigera dem i Web Editor. Stödet för Schematron i Web Editor hjälper dig att validera filerna mot en uppsättning regler och bibehålla konsekvens och korrekthet i alla ämnen.

![validera schematron](assets/schematron-validate.png)

* **Förbättrad dialogruta vid filstängning**

AEM Guides uppmanar dig att spara ändringarna och låsa upp låsta filer när du försöker stänga en fil som har öppnats i Web Editor. Frågorna visas baserat på **Fråga efter incheckning vid stängning** och **Fråga efter ny version vid stängning** inställningar som konfigureras av administratören.

Beroende på konfigurationen kan du välja att spara ändringarna och skapa en ny version av dokumentet. Du kan också checka in filen och spara ändringarna i den aktuella versionen.

![Stäng fil](assets/file-close-save-changes-unlock.png)

Mer information finns i *Stäng filer och spara scenarier* i guiden Använda Adobe Experience Manager-stödlinjer.* **Infoga nyckelord** har förbättrats. Nu är det enklare att hitta ett nyckelord som ska infogas eftersom nyckelorden visas i alfabetisk ordning. Du kan också söka efter nyckelord genom att skriva en söksträng i sökrutan.

![infoga nyckelord](assets/insert-keyword.png)

* **Stöd för markeringsdokument**
Markering är ett lättviktigt markeringsspråk som du kan använda för att lägga till formateringselement i vanliga textdokument. Med Web Editor kan du använda Markdown-dokument (.md) tillsammans med DITA-dokument. Du kan enkelt skapa och förhandsgranska ett markeringsdokument i Web Editor och även lägga till det i kartfilen via DITA-kartredigeraren.  Mer information finns i *Skapa markeringsdokument från webbredigeraren* i Använda guiden för Adobe Experience Manager-stödlinjer.

![supportmarkering](assets/create-markdown-dita-topic.png)

* **Möjlighet att konfigurera en standardvy för taggar**
Om en användare aktiverar taggvyn från Web Editor är den fortfarande aktiverad även i alla sessioner.  Det innebär att du inte behöver aktivera taggvyn igen för att komma åt den senare. Administratören kan konfigurera standardläget för taggvyn i Web Editor. Standardvärdet för taggvyn för en ny användarsession bestäms av egenskapen tagsView i filen ui_config.json.

* I databasvyn läses filerna in i grupper. Alla filer som finns i huvudfilen eller `/content/dam folder` visas. Men från nästa nivå eller den sekundära mappen läses 75 filer in samtidigt. Gruppinläsningen är effektiv och du kan komma åt filerna snabbare än att läsa in alla filer som finns i en mapp.

![läsa in fler filer](assets/load-more-files.png)

### Ny kontrollpanel för baslinje

AEM 4.1 innehåller baslinjefunktionen som är integrerad i Web Editor. Nu kan du skapa baslinjer från Web Editor och använda dem för att publicera eller översätta ämnen från olika versioner.

**Anteckning**: För uppgraderade system, uppdatera **ui_config.json** för mappprofil.

Använd den här funktionen om du vill skapa en baslinje med en specifik version av de ämnen som är tillgängliga ett visst datum och en viss tid. Du får även API-stöd för att skapa eller uppdatera en baslinje med en etikett som definierats för en ämnesversion.

![fliken hantera baslinje](assets/baseline-manage.png)

Du kan söka efter filer baserat på filnamn eller filplats. Du kan också filtrera ämnen som ska visas i redigeringsfönstret för baslinjen och sortera dem baserat på specifika kolumner.

![fliken hantera baslinje](assets/baseline-filter.png)

Prestandan för skapandet av baslinjen har förbättrats ytterligare. Processen att skapa baslinjer är asynkron, så du kan fortsätta redigera andra filer i Web Editor medan baslinjen skapas. Mer information finns i *Skapa och hantera baslinjer från Web Editor* i guiden Använda Adobe Experience Manager-stödlinjer.

Obs! Fliken Baslinje på kartkontrollpanelen är dold som standard. Administratören kan aktivera fliken Baslinje på kartkontrollpanelen.

* Baslinjeparametern i API:erna för nedladdning av karta använder nu baslinjens rubrik för att hämta versionsinnehållet.

### Förbättrad översättningsprocess

* **Möjlighet att skapa ett omfångsöversättningsprojekt**
Om du bara behöver skapa omfånget för ett projekt som ska översättas kan du välja **Skapa ett nytt omfångsöversättningsprojekt**. Kopiorna skickas inte för översättning och den ursprungliga översättningsstatusen för filerna behålls.

![omfångsöversättningsprojekt](assets/scoping-translation-project.png)

* The **Språk** visas språkmapparna tillsammans med deras språkkoder. Till exempel franska (fr) och tyska (de).

![översättningsspråk](assets/translation-languages.png)

Mer information om översättning finns i *Översätta dokument från Web Editor* i Använda guiden för Adobe Experience Manager-stödlinjer.


### Förbättrad publicering

* Du kan även komma åt **Publish Dashboard** på fliken Utdata när du genererar utdata från kartkontrollpanelen. En lista över alla aktiva publiceringsåtgärder finns på Publish Dashboard.

![utdata i kö](assets/queued-output.png)

* På kartkontrollpanelen kan du välja flera DITAVAL-filer för att generera villkorat innehåll. Du kan behålla filordningen genom att lägga till eller ta bort filer. Du kan också hovra över filnamnet för att se sökvägen i den AEM databasen där filen lagras.

* Baslinjer har använts för metadata AEM webbplatsens utdata. Du kan också bearbeta egenskaperna för en baslinjeversion som metadata. Om ingen baslinje har definierats bearbetas egenskaperna för den senaste versionen som metadata.

* The **Filnamn** och **Kommandoradsargument för DITA-OT** alternativ har lagts till för HTML 5, EPUB och anpassade förinställningar. Nu kan du ange filnamnet som du vill spara utdata med. Du kan också ange ytterligare argument som du vill att DITA-OT ska behandla när du genererar utdata.

### Kartkontrollpanel

När du väljer att hämta DITA-kartan köas begäran och du får ett meddelande när kartan är klar att hämtas. Du kan välja att ladda ned kartfilen direkt eller ladda ned den senare via länken i Inkorgen för AEM.

![Hämta karta](assets/download-map-prompt.png)

### Andra funktionsförbättringar

* AEM Guides har nu stöd för Oxygen XML Author version 24.1.
* Baslinjeparametern i API:erna för nedladdning av karta använder nu baslinjens rubrik för att hämta versionsinnehållet.

### Inaktuell funktion

AEM Guides stöder inte längre generering av DITA-utdataformat för FrameMaker-dokument. Det här DITA-alternativet har också tagits bort från förinställningarna för utdata på kontrollpanelen för kartor.

## Åtgärdade problem

De buggar som har åtgärdats i olika områden listas nedan:

* Redigeringsstöd är inte tillgängligt som alternativ för filsökvägsbaserad referens för publicering. 8076
* DITA Add on package förhindrar DAM-dubblettidentifiering av resurser. 8417
* Efter incheckning av ett dokument från Syrgas till AEM ersätts japanskt innehåll i dokumentet med frågetecken (???). (9124)
* Det går inte att uppdatera utcheckade filer vid loggning med webbautentisering i Syrgas. (9179)
* Filen checkas inte ut när den öppnas i syrgas. (9192)
* Efter incheckning av ett dokument från Syrgas till AEM ersätts japanskt innehåll i dokumentet med frågetecken (???). 9276
* Webbautentisering fungerar inte i syre. 9296
* Återuppladdningen misslyckas i syre när filen/filerna redan finns i AEM på samma plats. 9328
* Det går inte att synkronisera innehåll mellan AEM och det lokala systemet. 9439
* ID genereras inte automatiskt för element som lagts till med **Infoga återanvändbart innehåll** från det sekundära verktygsfältet. 5826
* Ingen bekräftelsedialogruta visas när en bild med samma namn som en befintlig fil överförs via redigeraren. (6011)
* Ett hårt blanksteg är inte tillgängligt i teckenlastpallen. 7523
* Elementlistan (Alt+Retur) visas nedtonad i det mörka/mörkaste temat. 7913
* Versionen uppdateras inte när ändringen av ett ämne sparas i verktygsfältet på panelen Karta. (8228)
* xref kan inte infogas även på giltiga platser. 8354
* getversionlabels-åtgärden har begränsningar och ger inte förväntad prestanda. 8513
* Problem uppstår med bekräftelsedialogrutan när en låst eller redigerad fil som inte är öppen i redigeraren stängs. 8692
* Ett fel inträffar när en användare läggs till som administratör i mappprofilen när användar-ID:t är numeriskt. 8908
* Översättningspanelen visas även när DITA-kartan öppnas i kartredigeraren. 9053
* Språkkoden visas inte med språket på översättningspanelen. (9108)
* Flikarna Översättning och Baslinje visas en tid på kontrollpanelen Karta. (9146)
* När översättningen är klar skapas ytterligare en version för den översatta resursen. 9310
* Godkänd översättning kan inte integreras med målspråket när målspråkskoden innehåller fem tecken som `fr_ca`. 9357
* Översatt innehåll bryts när målspråkskoden som skapas omnämns som `fr-fr, `, `en-us`. 9527
* När en DITA-karta som ligger utanför mappen language läses in loggas ett undantag i backend-objektet.9543
* Det går inte att skapa DITA-filen med den anpassade DITA-mallen från redigeraren. 7262
* DITA-kartan förloras när en UUID DITA-karta publiceras via FMPS. 7278
* AEM stödlinjer kopierar inte en resurs icke-unika egenskaper när en resurs kopieras och klistras in. 8241
* DITA-kartfilens namn konverteras inte till gemener när det skapas. 8383
* Beskrivningen av granskningsaktiviteten visas inte i det e-postmeddelande som skickas när en ny granskningsaktivitet tilldelas. 8507
* Hämta mappnings-API | Temporära mappar rensas inte bort om hämtningsprocessfel skulle försvinna. 8523
* `columnpreview.jsp` är beroende av SP.  8543
* Utdatafält med status Väntar eller Körning rensas inte på kontrollpanelen Publicera.  8569
* Standardikonen väljs när en rapport genereras med knappen Generera, även när ikonegenskapen är definierad. 8573
* Problem uppstår under granskningsprocessen när du uppgraderar från 3.8.X till 4.0. 8788
* Om ett användarnamn är långt visas inte ikonerna för att acceptera/avvisa på panelen Granska i Web Editor tydligt. 8793
* Referensträdet bryts när ett ämne har tagits bort och en flyttningsåtgärd har utförts. 8804
* Anpassad DTD som definieras av användaren har inte högre prioritet än standard-DITA DTD som är inbäddad i DITA-OT. (9104)
* Markeringens position är felaktig i vyn Sida vid sida. 9305
* Fotnoter som kan användas som referenser rullar inte till fotnotsavsnittet i AEM. 9061
* Fotnoternas ordning är felaktig i AEM. 9327
* Nyligen skapade DITA-resurser checkas alltid ut av en annan användare. 9387
* Fel loggas alltid när nytt innehåll skapas. 9388
* Den tredje skärmen i processen för att skapa granskningsåtgärder visar inte listan med ordlistor. (4558)
* Felaktiga UUID-referenser som tilldelats vid överföring av flera filer från FrameMaker-/syrekopplingen. 8269
* E-postmeddelanden skickas inte när en granskningsuppgift omtilldelas i Inkorgen. 8376
* Den andra administratörsanvändaren kan inte läggas till som den första administratörsanvändaren i en mapp. 8430
* **Använd etiketter** på fliken Baslinje visas inte etiketter i listrutan. 8455
* Om du använder baslinjepublicering med bilden som conref i avsnittet publiceras inte bilden i utdata. 8564
* Funktionen för rensning av utdata fungerar inte om det finns ett stort antal noder för historik över utgående utdata. 8568
* I panelen för versionshistorik visas en felaktig tidsstämpel i det aktuella versionsavsnittet och informationen ändras. 8765
* Baslinjen har inte uppdaterats baserat på den etikett som definierats. 8799
* Ett fel inträffar när filer vars överordnade mapp har specialtecken i filnamnet öppnas i Syrgas (med **Redigera i syrgas** -knapp). (8918)
* Det går inte att överföra filer från Syrgas till AEM. (9157)
* Hämta kartan med baslinjen fungerar inte om innehållet flyttas till en annan mapp. 9331
* Syrgas kontrollerar en felaktig version av ett ämne efter en versionsåterställning i AEM. 9411
* Om du söker på panelen Databas och dialogrutan för att bläddra i utseendet på utseendet låses skärmen när innehållet är stort. 9432
* Om inställningen **Skapa ny version för överförd fil** är PÅ, skapas en ny version när du återställer och sparar en fryst nod. 9473
* Felaktiga tidsstämpelskillnader visas i resursgränssnittet när en filversion återställs. 9480)
* Filerna checkas ut automatiskt när de återställs till valfri version. 9482
* Låsikonen visas i databasvyn även när filen har checkats in från redigeraren.  5756
* Det går inte att lägga till förgrundselement, bakgrundselement i en bokmapp med hjälp av redigerarens redigeringsvy. 7652
* Förhandsvisningsläget stöder inte `deliveryTarget` villkorsstyrt bearbetningsattribut i DITA. 7685
* När du öppnar ett ordlisteämne i XML-redigeraren måste AEM spara det även om det inte har ändrats. 8105
* Dialogrutan Infoga referenser öppnas när du lägger till subjekten på en karta med hjälp av användargränssnittet. 8212
* Återanvänd innehållspanelen kraschar vid sökning efter specialtecken `[` eller `*` .8279
* Vid redigering av Glossentry visas innehållet i webbredigeraren som en anteckning. 8384
* XML-redigeraren tar bort radmatningar i kodlås. (8522)
* Om du växlar mellan käll- och författarläge markeras ämnet som smutsigt och innehållet måste sparas igen.8524
* Det går inte att stänga ett olåst ämne. 8545
* Det finns inget alternativ för att välja kunskapsbassökvägen i artikelbaserade publiceringsförinställningar. 8636
* Attribut saknas när du lägger till ett kapitel i bokmappen med dra och släpp från favoritvyn. 8746
* Dialogrutan Infoga nyckelord saknar sökfunktion och nyckelorden visas inte i sorterad ordning. (9094)
* Om du gör en sökning i XML-redigeraren fryser sidan. 9452
* Platser saknas i AEM förinställningar på fliken Utdata. 9567
* SVG-bilder som inte återges korrekt i redigeringsläge i XML-redigeraren. 9426
* Baslinjen respekteras inte vid publicering via Salesforce. 8953
* Det finns inte möjlighet att rensa rotkartan från användarinställningarna. 8534
