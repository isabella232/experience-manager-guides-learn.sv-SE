---
title: Versionsinformation för [!DNL AEM Guides], januari 2022-versionen
description: Januariversion av [!DNL Adobe Experience Manager Guides] as a Cloud Service
source-git-commit: 880cd344ceb65ea339be699ebcad41c0d62e168a
workflow-type: tm+mt
source-wordcount: '2441'
ht-degree: 0%

---

# Januariversion av [!DNL Adobe Experience Manager Guides] as a Cloud Service

## Uppgradera till januariversionen

Uppgradera din nuvarande [!DNL Adobe Experience Manager Guides] as a Cloud Service (kallas senare [!DNL AEM Guides] as a Cloud Service) konfigurera genom att utföra följande steg:
1. Ta en titt på Cloud Servicens Git-kod och växla till den gren som är konfigurerad i Cloud Servicens pipeline för den miljö du vill uppgradera.
1. Uppdatera `<dox.version>` egenskap i `/dox/dox.installer/pom.xml` fil med dina Cloud Service Git-kod till 2022.1.78.
1. Genomför ändringarna och kör Cloud Servicens pipeline för att uppgradera till januariversionen av [!DNL AEM Guides] as a Cloud Service.

## Kompatibilitetsmatris

I det här avsnittet visas kompatibilitetsmatrisen för de program som stöds av [!DNL AEM Guides] as a Cloud Service januariversion 2022.

### FrameMaker och FrameMaker Publishing Server

| FMPS | FrameMaker |
| --- | --- |
| Inte kompatibel | 2020 uppdatering 4 och senare |
| | |


### Syrgasanslutning

| [!DNL AEM Guides] Cloud-utgåva | Syrgasanslutningsfönster | Syrgasanslutning Mac | Redigera i syrgasfönster | Redigera i Syrgas Mac |
| --- | --- | --- | --- | --- |
| 2022.1.0 | 2.4.0 | 2.4.0 | 2,2 | 2,2 |
|  |  |  |  |  |


## Nya funktioner och förbättringar

### Artikelbaserad publicering

I januariversionen har vi introducerat en artikelbaserad publiceringsfunktion som är integrerad i Web Editor. Du kan använda den artikelbaserade publiceringsfunktionen för att stegvis generera utdata för ett eller flera ämnen eller publicera innehållet på en kunskapsbaserad plattform.

Med den här funktionen kan användarna skapa DITA-kartan på ett additivt sätt och publicera ämnen när de är klara. När du har publicerat kartan använder du den artikelbaserade publiceringsfunktionen för att få stegvis publicering endast för de uppdaterade artiklarna.

![Artikelbaserad publicering](assets/article-based-publishing.png)

Förutom AEM kan du använda den här unika funktionen för att publicera dina artiklar till alla kunskapsbasportaler, som Salesforce. Den här funktionen innehåller också en OOTB-innehållsmall, som bygger på AEM kärnkomponenter, med vilken du kan skapa en kunskapsbaserad databas med det tekniska innehållet. Det som är bra med den här mallen är att den är helt anpassningsbar för att passa organisationens behov och kan även stödja användningsfall som intranätsportaler.
Du kan också filtrera artiklarna baserat på deras dokumenttillstånd och ändringsdatum.

Denna välbehövliga artikelpublicering i farten ger dig inte bara fullständig kontroll över innehållspubliceringen utan minskar även den totala tiden för publicering av uppdaterat innehåll.
När du publicerar artiklar med den här mallen kan även metadata skickas till dina publicerade sidor.
Mer information finns i *Artikelbaserad publicering från webbredigeraren* i användarhandboken.

### Förbättrad webbredigerare

Det finns många förbättringar och nya funktioner i Web Editor:

* Stöd för ämnesschemat har också lagts till i Web Editor. Du kan nu skapa och använda ämnesschemat med hjälp av ämnesschemapanelen. Med det nya ämnesschemat kan du nu använda egna metadata och taxonomi för företag.

![Ämnesschema](assets/subject-scheme-panel.png)

* Ett nytt ordlisteverktyg har introducerats i den här versionen för att hantera flera ordlistor samtidigt. Med det här verktyget kan du snabbt konvertera text till ordlista och ordlista till termer i grupp för en markerad karta eller öppna ämnen.

![Ordlistehotspot](assets/glossary-hotspot-tool.png)

* Ny uppdateringsfunktion i panelen Återanvändbart innehåll som gör att du snabbt kan uppdatera återanvändbart innehåll i referensfiler.
* En ny indikator visar om din aktuella (arbetskopia) av filen är synkroniserad med den sparade versionen eller inte.

![Versionsindikator](assets/version-update-indicator.png)

* Sökfiltret i databaspanelen och dialogrutan för filbläddring har förbättrats så att fler filtreringsalternativ kan anpassas ytterligare.

![Sökfilter i databasen](assets/repository-filter-search.png)

* Nu kan du överföra .docx-filer från Web Editor.

### Skapa med FrameMaker

Nu kan du skapa och publicera dina dokument i FrameMaker. FrameMakerna levereras med en färdig anslutning till Adobe Experience Manager. I FrameMaker får du ett lättanvänt gränssnitt där du kan underhålla dokumentversioner i en distribuerad och samarbetsorienterad miljö.

När du har skapat ditt innehåll kan du med FrameMaker publicera dina dokument i olika format - PDF, HTML5, EPUB och DITA. Du kan också utföra olika filhanteringsåtgärder som utcheckning, utcheckning med beroende personer, incheckning, uppdatering och så vidare.
Om du vill skriva med FrameMaker in [!DNL AEM Guides] FrameMaker för as a Cloud Service användning version 2020.4 och senare.

### Ny översättningsinstrumentpanel

En ny kontrollpanel för översättning har lagts till i Web Editor med följande funktioner:

* Sortera, söka och filtrera ämneslistan.
* Filtrera innehåll efter referenstyp - direkta eller indirekta referenser.
* Enkel navigering för att hitta ett befintligt projekt när du initierar en översättningsbegäran.
* En flerspråkig översättningsmekanism har introducerats för att undvika att skapa flera projekt för varje språk när översättningsbegäran initieras för mer än ett språk.
* En konfiguration som döljer översättningsfliken i kartkontrollpanelen introducerades. Som standard är den synlig. Du kan välja att översätta innehåll antingen med kartpanelen eller webbredigeraren.

![Kontrollpanel för översättning](assets/translation-from-web-editor.png)

### Förbättrad publicering

* Författare kan nu skicka metadata på mapps- och ämnesnivå till DITA-OT-publicering. Detta är praktiskt när anpassade PDF-mallar är utformade för att använda egenskaper för filmetadata som taggar, författare, dokumenttillstånd med mera.

![DITA-OT-metadata](assets/custom-meta-data-output-preset.png)

* En ny konfiguration har lagts till som tillåter användare att behålla eller ta bort de versioner av ämnen som tas bort när **Ta bort och skapa** används för att generera AEM för webbplatsen.

### Förbättrad filhantering

Följande förbättringar visas nu när du arbetar med filer i AEM Assets:
* En ny upplevelse vid filöverföring och en ny dialogruta för att välja en strategi för konfliktlösning har lagts till.

![Konflikt vid filöverföring](assets/file-upload-name-conflict.png)

* Möjlighet att skapa en ny version av den överförda filen med möjlighet att förhindra att en utcheckad fil skrivs över.
* Nu kan du se en förhandsvisning av bilder direkt från vyn Versionshistorik. Versionshistorik visar även den aktuella versionsinformationen separat för DITA-filer och andra filer.

![Miniatyr av versionshistorik](assets/version-history-preview-image.png)

* När användaren skapar en DITA-fil visas standardfilnamnet med ett litet skiftläge så att det är textbundet när AEM skapas.

### Ny rapportexportfunktion

Rapporter är mycket användbara när det gäller att identifiera innehållets hälsa. [!DNL AEM Guides] as a Cloud Service innehåller olika rapporter som tar kontroll över ditt innehåll. Nu kan du inte bara visa rapporterna, utan även exportera rapportdata i en CSV-fil för att visa och dela dem med det större teamet. Rapportdata kan ge dig en snabb överblick över eventuella brutna länkar eller saknade bilder.

![Rapportexport](assets/export-report.png)

### Förbättrad DAM-uppdatering av syre

När du uppdaterar filer från AEM Server i Syrgas visas ett varningsmeddelande om du har osparade filer i den aktuella Syrgassessionen. Du kan välja att avbryta uppdateringsåtgärden för att spara osparade filer. Utan den här funktionen förlorade användare osparad information i sina dokument.


### Andra funktionsförbättringar

* Nu kan du skapa en ny **Dita Project** mall under **/apps/projects/templates** bana.
* Hämta nu standardinställningen **ui_config.json** från dina mappprofiler. Detta kan användas för att sammanfoga anpassade ändringar från befintliga **ui_config.json** när du uppgraderar.
* Du behöver inte rensa webbläsarens cache även när det finns nya versioner av JS-filer.

## Åtgärdade problem

De buggar som har åtgärdats i olika områden listas nedan:

### Web Editor

* Färgkonturer visas i röd färg även om de inte är brutna. 8239
* Värdet för villkorsattribut fylls inte i automatiskt när Lägg till alla egenskaper är markerat i DITAVAL-redigeraren. 8234
* Författare kan inte infoga en bild i ett ämne med hjälp av en relativ sökväg. (8112)
* Granska uppgiftssidan som inte visar multimediefilerna om det finns mellanslag i filnamnet. (8111)
* Ph conref som lagts till i tabellcellen visas i röd färg. 8083
* Länkar i granskningsprocessen uppdateras inte när de granskade filerna flyttas. (8080)
* Webbredigeraren återger inte bilder som har skalningsegenskapen inställd på 75 % eller högre korrekt. 8073
* GIF-bilder återges som statiska bilder i Web Editor. 8024
* En conkeyref i ett anteckningselement visas inte i webbredigerarens förhandsgranskning eller i utdata. 8006
* xref till ett element som själv är en conref tolkas inte i redigeraren. 7933
* Titel som har en nyckel återges inte korrekt i redigerarens förhandsgranskning och på databaspanelen. 7909
* Fragment med specialtecken lagras inte korrekt. 7908
* Om du sparar ett ämne efter formatering av MathML-ekvationer uppstår ett fel. 7954
* Tm (keydef having) återges inte korrekt i redigeraren och AEM platsutdata innehöll duplicerade TM-symboler. 7859
* Det går inte att dra och släppa ett fragment enligt DTD-dokumenten. 7758
* HTML ignorerar anpassade definierade dimensioner för grafik. 7718
* conrefend-attributet uppdateras inte när källfilen flyttas. 7698
* Arbetet med typdokument för referensämnen leder till flera problem med användargränssnittet. 7656
* DITAVAL-filer visas inte när författaren lägger till ditavalref i en karta. 7594
* Oväntat utrymme hittades i varje tomt `<entry>` element när attributet outputClass läggs till i `<tgroup>` -element. 7532
* Källknappen fungerar inte för ämnen som öppnas via kartpanelen. 7465
* Kort utskrift infogar tomma rader och blanksteg som syns när filen öppnas i FrameMaker eller syrgas. 7408
* Kartor med href=&quot;/&quot; i något av ämnena publiceras inte AEM webbplatser. 7405
* Prestandaproblem som hittas i redigeraren när rotkartan har ett stort antal nyckeldefinitioner. (7400)
* Dokumenttillståndet för en karta med en anpassad mall ärvs inte från sin motsvarande lägesprofil. 7359
* `<tm>` felaktigt återgivet element som ett blockelement. 7286
* Duplicerade mallar visas i panelen för redigeringsmallar när en ny mall skapas. 5814
* Mallar som definieras i ui_config för bilder för inställning av ytterligare attribut kan inte användas för dra/släpp-fall. (5713)
* Felaktigt standardutseende för uicontrol på menucascade. 5483
* Anpassade mallar för Ämne/Karta visar inte ett nytt namn i användargränssnittet. Det visar namnet som&quot;Ämne&quot;/&quot;Karta&quot; i stället för det konfigurerade namnet. 4958
* Möjlighet att ta bort en rotmapp från inställningarna för användarinställningar. 8534
* En nyligen skapad kartsamling visas inte, inte ens efter att sidan har uppdaterats.8603
* Olåst ämne kan inte stängas. 8545
* Om du växlar mellan käll- och författarläge markeras ämnet som smutsigt och innehållet måste sparas igen.8524
* Återanvänd innehållspanelen kraschar vid sökning efter specialtecken `[` eller `*` .8279
* Markören visas inte i sökfältet när dialogrutan Infoga element öppnas med kortkommandot Alt+Retur.7912
* Sökalternativet söker bara i filnamn och inte i innehåll. 7784


### Syrgasanslutning

* Filer vars överordnade mapp har specialtecken ger fel vid inläsning i Syrgas. 8054
* När ett nyligen skapat dokument öppnas i Syrgas visas felet&quot;Det går inte att hitta GUID&quot;. 7856
* Incheckningsalternativet är inaktiverat när filen har checkats ut från AEM med Redigera i syrgas. 7471


### Granska

* Synkronisering i realtid fungerar inte för kommentarer. 7661

### Kartkontrollpanel

* Det går inte att se generiskt innehåll i titeln för ett ämne på fliken med ämnen eller rapporter på kontrollpanelen för kartor. 8263
* AEM Sites Output | jcr:titeln för den genererade webbplatssidan uppdateras inte när DITA-avsnittsrubriken uppdateras. (8131)
* Ladda ned MAP hämtar inte de videofiler som används i avsnitten. 8070
* Mediefiler laddas inte ned när object-taggen används via hämtningsbokmapps-API:t. 8057
* Felaktig rapport visas på fliken Rapporter om något ämne har konverterats till en fil vars titel börjar med conref. (4698)
* Dialogrutan Använd etiketter på fliken Baslinje visar inte etiketter i listrutan. 8455

### Publicering

* Det går inte att skapa PDF för första gången när Aktivera versionshantering är markerat. (8053, 8294)
* Blanksteg läggs automatiskt till efter taggen tm; AEM Site-utdata. 7964
* Det går inte att visa YouTube-videor i AEM. 7401
* Filtrera efter etikett misslyckas för refererat innehåll efter att användaren har klickat på Bläddra i alla ämnen på baslinjefliken på kartkontrollpanelen. 7388
* Publicera ämne med element `<tm>` med egenskapsvärdet SM eller reg visas felaktigt i genererade utdata. 7239
* Vid baslinjepublicering med bild väljs inte bildens senaste version i publicerade utdata. 7231
* Relaterbara ämnen som refereras visas på fliken Baslinje. 5424
* Stegvis publicering för ett ämne med conkeyref i titeln fungerar inte som förväntat. 4474
* Sidtitel används inte för generering av utdata-URL trots att inställningen är markerad. 8257
* Vid baslinjepublicering väljs den aktuella versionen av bilderna i stället för den frysta noden. Detta visas även om en bild har blanksteg eller specialtecken i filnamnet. 8274, 8322
* Inkrementell publicering misslyckas för DITA-kartan med ett typämnesschema som har mapref. (8218)
* Null läggs till när en karta läggs till på kontrollpanelen för masspublicering. 8695
* Om du använder baslinjepublicering med bilden som conref i avsnittet publiceras inte bilden i utdata. 8564
* Publiceringen misslyckas med ett undantag om den baslinje som används AEM webbplatspubliceringen tas bort. 8572
* Omgenerering av ämnen fungerar inte. 8091
* Det finns problem med att publicera fotnoter i tabeller. (4709)

### AEM Assets

* Prestandaproblem påträffades vid markering/borttagning av omfattande innehåll i resursgränssnittet. 8238
* Sparad sökfunktion (smart samling) avbryts om DITA Predicate läggs till i sökfiltren. 8048
* Det går inte att återställa en bild till en äldre version. (DXML-7903)
* Alternativet Ta bort är också synligt för författare som inte har behörighet att ta bort. 7322
* CCMS-övertäckning för Resursredigeraren avbryter återgivningen av alternativet Ta bort. 8093
* Dokumentprofilen tas inte bort. 8604
* Referenser bryts när du väljer Markera allt och flyttar multimedia/Dita_Content till en annan mapp. 8621
* Felaktiga referenser inträffar i källan när resurserna flyttas. 8627
* Den fasta listvyn läses inte in. 8542

### Innehållsimport

* Konvertering från HTML till DITA | Tabell med tr med tomma td-poster orsakar ytterligare rader i utdata. 8132
* Konvertering från HTML till DITA | HTML som har en tabell med flera förekomster misslyckas med ett undantag. (7940)
* Konvertering från HTML till DITA | fel om HTML har kommentarer. 7937
* Om du importerar DITA 1.3 DITA-filer omvandlas en del href till felformaterade länkar. (8019)

## Kända fel

Adobe har identifierat följande kända problem för [!DNL AEM Guides] as a Cloud Service januariversion 2022.


### Kända problem med lösningar

Använd den angivna lösningen för följande kända problem:

* Webbautentiseringen fungerar inte för syreanslutningen på Mac.
  **Tillfällig lösning**: Använd syrekontakten i Windows tills vidare.

* I Firefox-webbläsaren går det inte att importera granskningskommentarerna utan att öppna sida vid sida-vyn.
  **Tillfällig lösning**: Använd Chrome-webbläsaren för tillfället.

* Referenser bryts när bilder eller multimediefiler som har plats(er) flyttas i filnamnen.
  **Tillfällig lösning**: Byt namn på filen och ta bort blankstegen från filnamnet innan du flyttar dem.

* Kontrollpanelen för kartan läses inte in regelbundet i den senaste versionen av Chrome-webbläsaren.
  **Tillfällig lösning**: Uppdatera sidan på kartpanelen.

### Andra kända fel

* Om syre är ansluten med [!DNL AEM Guides] lösning med webbautentisering misslyckas utloggningen.
* Granskningsuppgifter kan inte tilldelas om till användarna.
* Det finns problem i kartuppsättningens användargränssnitt, till exempel att texten är förvrängd och **Markera alla** funktionen fungerar inte som den ska.
