---
title: Versionsinformation | Adobe Experience Manager Guides as a Cloud Service, majversionen 2022
description: majversionen av Adobe Experience Manager Guides as a Cloud Service
source-git-commit: 880cd344ceb65ea339be699ebcad41c0d62e168a
workflow-type: tm+mt
source-wordcount: '1887'
ht-degree: 0%

---

# majversionen av Adobe Experience Manager Guides as a Cloud Service

## Uppgradera till majversionen

Uppgradera din nuvarande Adobe Experience Manager Guides as a Cloud Service (kallas senare *AEM stödlinjer as a Cloud Service*) genom att utföra följande steg:
1. Ta en titt på Cloud Servicens Git-kod och växla till den gren som är konfigurerad i Cloud Servicens pipeline för den miljö du vill uppgradera.
1. Uppdatera `<dox.version>` egenskap i `/dox/dox.installer/pom.xml` fil med dina Cloud Service Git-kod till 2022.5.144.
1. Genomför ändringarna och kör Cloud Servicens pipeline för att uppgradera till majversionen av AEM Guides as a Cloud Service.

## Kompatibilitetsmatris

I det här avsnittet visas kompatibilitetsmatrisen för de program som stöds av AEM Guide as a Cloud Service från maj 2022.

### FrameMaker och FrameMaker Publishing Server

| FMPS | FrameMaker |
| --- | --- |
| Inte kompatibel | 2020 uppdatering 4 och senare |
| | |

*Originalplan och villkor skapade i AEM stöds i FMPS-versioner från och med 2020.2.

### Syrgasanslutning

| AEM stödlinjer som en Cloud-release | Syrgasanslutningsfönster | Syrgasanslutning Mac |
| --- | --- | --- |
| 2022.5.0 | 2.6.9 | 2.6.9 |
|  |  |  |


## Nya funktioner och förbättringar

AEM Guides as a Cloud Service innehåller många förbättringar och nya funktioner i majversionen:

### Förbättrad webbredigerare

* **Skapa kartor baserade på anpassade mallar**

Nu får du den kraftfulla funktionen för att skapa anpassade kartmallar. Du kan använda dem för att skapa DITA-kartor tillsammans med ämnesmallarna och mappningsmallarna som refereras i kartmallen.

![dita-mallar](assets/dita-templates.png)

Du kan även referera till andra mappningsmallar och ämnesmallar från den anpassade mappningsmallen. De refererade mappningsmallarna kan hänvisa till olika mappningsmallar, ämnesmallar, ämnen, kartor, bilder, videor och andra resurser.

![skapa datamallar](assets/create-dita-template.png)

Den anpassade mappningsmallen kan hjälpa dig att enkelt replikera mappningsmallarna och hela den refererade mappstrukturen. Dessa anpassade mallar är särskilt användbara när du vill skapa och återskapa flera kartor med rekursiva strukturer och referenser.

* The **Infoga nyckelord** har förbättrats. Nu är det enklare att hitta ett nyckelord som ska infogas eftersom nyckelorden visas i alfabetisk ordning. Du kan också söka efter nyckelord genom att skriva en söksträng i sökrutan.

![infoga nyckelord](assets/insert-keyword.png)

* I databasvyn läses filerna in i grupper. 75 filer läses in samtidigt. Gruppinläsningen är effektiv och du kan komma åt filerna snabbare än att läsa in alla filer som finns i en mapp.

![läsa in fler filer](assets/load-more-files.png)

* Du kan återge bilder i SVG som innehåller inbäddade data eller länkar i alla XML-redigeringsskärmar, inklusive men inte begränsat till förhandsgransknings- och redigeringsvyn.

* XSD/DTD kan uppdateras till den senaste versionen

### Förbättrad översättningsprocess

* **Möjlighet att skapa ett omfångsöversättningsprojekt**
Om du bara behöver skapa omfånget för ett projekt som ska översättas kan du välja **Skapa ett nytt omfångsöversättningsprojekt**. Kopiorna skickas inte för översättning och den ursprungliga översättningsstatusen för filerna behålls.

![omfångsöversättningsprojekt](assets/scoping-translation-project.png)

* Om du avvisar översättningen för ett eller flera ämnen i ett översättningsjobb återställs statusen Pågående översättning för alla avvisade ämnen till den ursprungliga statusen.

* The **Språk** visas språkmapparna tillsammans med deras språkkoder. Till exempel franska (fr) och tyska (de).

* Översättningsfunktionen har nu även stöd för språkkoden som innehåller både land och språk. Till exempel: `fr-fr`, `en-us`.

![översättningsspråk](assets/translation-languages.png)

* När du läser in en DITA-karta som ligger utanför språkmappen loggas inget undantag i serverdelen.

Mer information om översättning finns i *Översätta dokument från Web Editor* i Använda Adobe Experience Manager Guides as a Cloud Service.


### Förbättrad publicering

* Du kan även komma åt **Publish Dashboard** på fliken Utdata när du genererar utdata från kartkontrollpanelen. En lista över alla aktiva publiceringsåtgärder finns på Publish Dashboard.

![utdata i kö](assets/queued-output.png)

* På kartkontrollpanelen kan du välja flera DITAVAL-filer för att generera villkorat innehåll. Du kan behålla filordningen genom att lägga till eller ta bort filer. Du kan också hovra över filnamnet för att se sökvägen i den AEM databasen där filen lagras.

* **Inaktuell funktion**
AEM as a Cloud Service stöder inte längre generering av DITA-utdataformat för FrameMaker-dokument. Det här DITA-alternativet har också tagits bort från förinställningarna för utdata på kontrollpanelen för kartor.

### Förbättrad artikelbaserad publicering

Med XML-redigeraren kan du mappa mer än en produktkategori till en artikel när du publicerar till en Salesforce-profil.

### Andra funktionsförbättringar

* Förhandsgranskningsläget har även stöd för `deliveryTarget` villkorsstyrt bearbetningsattribut i DITA. Det finns som ett alternativ i listrutan tillsammans med **publik**, **plattform**, **produkt**, proppar, **andra proppar**.
* Det finns ett alternativ för att synkronisera mellan AEM server i Syrgas och det lokala systemet.

## Åtgärdade problem

De buggar som har åtgärdats i olika områden listas nedan:

* På Web Editors granskningspanel kan användaren inte svara på granskningskommentarerna. 9667
* Programmet blir tomt när du klickar på en tom mapp efter att ha uppdaterat den via Alternativ-menyn. 9639
* En ny version skapas när vi **Spara och stäng** den incheckade filen. 9638
* Knappen Stäng visas inte när **Spara som ny version** är aktiverad. 9637
* Korrekt PDF publiceras inte om det först publiceras via ett separat PDF för varje kapitel och sedan en enda PDF-fil (Skapa separata PDF-filer avmarkeras). 9632
* Kartpanelen genererar metadataproblem för icke-adminanvändare. (9620)
* När en baslinje har skapats, ställs statusen in på Misslyckad i användargränssnittet (det går inte att hämta statusanropet) om servern har fler än 10000 filer. (9608)
* Lagring av stora data i egenskaper resulterar i ett publiceringsfel eftersom ett delat publiceringsarbetsflöde misslyckas. 9586
* Tillståndet för villkorsstyrda attributfilter bevaras inte när du växlar mellan Förhandsgranska till källa och Förhandsgranska igen. 9553
* Bokmappsnamnet kommer att bli tomt i databasvyn om inget namn anges via `mainbooktitle` -tagg. 9538
* HTTP 400-fel inträffar när en fil som har överförts med Syrgas öppnas. 9535
* Förinställningarna för en tidigare öppnad karta visas på fliken Utdata när du öppnar en karta utan definierade förinställningar. 9523
* Sökfunktionen för taggar och attribut fungerar inte på dispositionspanelen. 9506
* Samlingen som skapades nyligen visas inte förrän webbläsaren har uppdaterats i webbläsaren. 9505
* Villkorliga attributetiketter (inte värdena) visas i källäge när du lägger till alla villkor med alternativet Lägg till alla utkast. (9501)
* Filerna checkas ut automatiskt när de återställs till valfri version. 9482
* Felaktiga tidsstämpelskillnader visas i resursgränssnittet när en filversion återställs. 9480)
* Flera objekt från sökresultat läggs till när objekt infogas i elementet topicref i DITA-kartan. 9474
* Om inställningen **Skapa ny version för överförd fil** är PÅ, skapas en ny version när du återställer och sparar en fryst nod. 9473
* Visningstexten i Key Reference och Content Key Reference bevaras inte när link URL ändras, om visningstexten inte läggs till när nyckelreferensen definieras. 9458
* I Versionshistorik visas inte versionsnummer och etikett för den aktuella versionen. 9446
* Redigeraren låser sig när vissa innehållsfiler öppnas i redigeraren. 9443
* Om du söker på panelen Databas och dialogrutan för att bläddra i utseendet på utseendet låses skärmen när innehållet är stort. 9432
* Metadata som skickas AEM webbplatsens utdata följer inte innehållets baslinje. 9416
* Syrgas kontrollerar en felaktig version av ett ämne efter en versionsåterställning i AEM. 9411
* Om det inte går att använda baslinjen inaktiveras redigering på fliken Förinställning på kartkontrollpanelen. 9403
* Fel loggas alltid när nytt innehåll skapas. 9388
* Nyligen skapade DITA-resurser checkas alltid ut av en annan användare. 9387
* Byt namn på element fungerar inte korrekt när topicref konverteras till glossref. 9380)
* Versionsetiketten visas inte som listruta i **Spara som ny version** -dialogrutan. 9379
* Villkoren tillämpas inte vid växling mellan olika versioner från **Visa differens** nedrullningsbar meny. 9366
* Det kan uppstå flera problem när du använder förhandsgranskningsfilter. 9365
* Det går inte att infoga icke-DITA- och DITAVAL-resurser i topicref. 9363
* Godkänd översättning kan inte integreras med målspråket när målspråkskoden innehåller fem tecken som `fr_ca`. 9357
* Det går inte att söka efter filer med **Sök efter filer i mappen** från **Fler alternativ** och appen slutar svara. 9337
* Dialogrutan Bläddra låses om det finns ett stort antal tangenter. 9332
* DITAVAL-filer fungerar inte vid artikelbaserad publicering. 9330
* Fotnoternas ordning är felaktig i AEM. 9327
* Sökningen utförs inte automatiskt när markeringssökvägen ändras. 9323
* När översättningen är klar skapas ytterligare en version för den översatta resursen. 9310
* Det går inte att ta bort administratörsanvändarna i mappprofilen. 9306
* Rotmappningen som uppdateras från innehållsnyckelreferensen ställs inte in förrän sidan uppdateras. 9302
* Webbautentisering fungerar inte i syre. 9296
* Webblänkar med kodade tecken fungerar inte korrekt. 9227
* Filen checkas inte ut när den öppnas i syrgas. 9217
* Det går inte att uppdatera utcheckade filer vid loggning med webbautentisering i Syrgas. (9179)
* Flikarna Översättning och Baslinje visas en tid på kontrollpanelen Karta. (9146)
* Problem med upplevelsen eller funktionen uppstår när mappprofilen läses in igen. (9103)
* Om du tar bort sidlayoutredigeraren stängs den inte från mittpanelen i redigeringsvyn. 9087
* Valideringsfel inträffar i Web Editor när en bild tas bort och sedan sparas den nya versionen av dokumentet. 8985
* Det går inte att visa alla `glossrefs` i ordlistepanelen (innehållsspecifik). 8886
* `xref` utan text inte visas i artikelbaserade publiceringsutdata. 8764
* Referenser bryts vid rörliga bilder eller multimediefiler som har ett blanksteg i filnamnen. 8624
* Referenser bryts vid val `Select All` och flytta multimediafilerna eller DITA-innehållet till en annan mapp. (8622)
* Utdatafält med status Väntar eller Körning rensas inte på kontrollpanelen Publicera.  8569
* Funktionen för rensning av utdata fungerar inte om det finns ett stort antal noder för historik över utgående utdata. 8568
* DITA Add on package förhindrar DAM-dubblettidentifiering av resurser. 8417
* Knappen Skapa granskningsåtgärd har aktiverats för andra filer än DITA. 8401
* Dialogrutan Infoga referenser öppnas när du lägger till subjekten på en karta med hjälp av användargränssnittet. 8212
* Oväntat utrymme hittades i varje tomt `entry` element när attributet outputClass läggs till i `tgroup` -element. 7532
* Databaspanelen visar inte in- eller utcheckade fillås-ikoner så fort åtgärden har slutförts. 5817
* Låsikonen visas i databasvyn även när filen har checkats in från redigeraren.  5756
* Platser saknas i AEM förinställningar på fliken Utdata. 9567
* XML-redigeraren hänger sig vid försök att redigera vissa DITA-filer. 9537
* Om du gör en sökning i XML-redigeraren fryser sidan. 9452
* Hämta kartan med baslinjen fungerar inte om innehållet flyttas till en annan mapp. 9331
* Återuppladdningen misslyckas i syre när filen/filerna redan finns i AEM på samma plats. 9328
* Markeringens position är felaktig i vyn Sida vid sida. 9305
* Efter incheckning av ett dokument från Syrgas till AEM ersätts japanskt innehåll i dokumentet med frågetecken (???). 9276
* Det går inte att överföra filer från Syrgas till AEM. (9157)
* E-postmeddelanden skickas inte när en granskningsuppgift omtilldelas i Inkorgen. 8376

## Kända fel

Tom sida visas då och då när redigeraren öppnas.
