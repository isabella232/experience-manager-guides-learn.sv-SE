---
title: Versionsinformation | Adobe Experience Manager Guides as a Cloud Service, september 2022-versionen
description: Septemberversionen av Adobe Experience Manager Guides as a Cloud Service
source-git-commit: 28712c3f2057d7553ed2fe955db0dfe278c8a9b9
workflow-type: tm+mt
source-wordcount: '1285'
ht-degree: 3%

---

# Septemberversionen av Adobe Experience Manager Guides as a Cloud Service

## Uppgradera till september-versionen

Uppgradera din nuvarande Adobe Experience Manager Guides as a Cloud Service (kallas senare *AEM stödlinjer as a Cloud Service*) genom att utföra följande steg:
1. Ta en titt på Cloud Servicens Git-kod och växla till den gren som är konfigurerad i Cloud Servicens pipeline för den miljö som du vill uppgradera.
2. Uppdatera `<dox.version>` egenskap i `/dox/dox.installer/pom.xml` fil med dina Cloud Services Git-kod till 2022.9.178.
3. Genomför ändringarna och kör Cloud Servicens pipeline för att uppgradera till september-versionen av AEM Guides as a Cloud Service.

## Steg för indexering av befintligt innehåll

Utför följande steg för att indexera det befintliga innehållet och använd den nya sök- och ersätt-texten på mappningsnivå:
* Kör en serverbegäran (med korrekt autentisering) - `http://<server:port>/bin/guides/map-find/indexin`.
(Valfritt: Du kan skicka specifika sökvägar för mappningarna för att indexera dem. Som standard indexeras alla mappningar || Exempel:   `https://<Server:port>/bin/guides/map-find/indexing?paths=<map_path_in_repository>`)
* API:t returnerar ett jobId. Om du vill kontrollera jobbets status kan du skicka en GET-förfrågan med jobb-ID till samma slutpunkt - `http://<server:port>/bin/guides/map-find/indexing?jobId={jobId}`
(Exempel: `http://<_localhost:8080_>/bin/guides/map-find/indexing?jobId=2022/9/15/7/27/7dfa1271-981e-4617-b5a4-c18379f11c42_678)`
* När jobbet är klart kommer ovanstående GET-förfrågan att svara och ange om några kartor misslyckades. De korrekt indexerade mappningarna kan bekräftas från serverloggarna.


## Kompatibilitetsmatris

I det här avsnittet visas kompatibilitetsmatrisen för de program som stöds av AEM Guides as a Cloud Service från september 2022.

### FrameMaker och FrameMaker Publishing Server

| FMPS | FrameMaker |
| --- | --- |
| Inte kompatibel | 2020 uppdatering 4 och senare |
|  |  |

*Originalplan och villkor skapade i AEM stöds i FMPS-versioner från och med 2020.2.

### Syrgasanslutning

| AEM stödlinjer som en Cloud-release | Syrgasanslutningsfönster | Syrgasanslutning Mac | Redigera i syrgasfönster | Redigera i Syrgas Mac |
| --- | --- | --- | --- | --- |
| 2022.9.0 | 2.7.13 | 2.7.13 | 2.3 | 2.3 |
|  |  |  |  |


## Nya funktioner och förbättringar

AEM Guides as a Cloud Service innehåller många förbättringar och nya funktioner i versionen från september:


### Skapa en dynamisk baslinje baserad på etiketter

Nu kan du skapa dynamiska baslinjer baserat på etiketter med hjälp av AEM stödlinjer. Om du genererar en baslinje, hämtar en baslinje eller skapar ett översättningsprojekt med hjälp av en baslinje, hämtas filerna dynamiskt baserat på de uppdaterade etiketterna. Den här funktionen är praktisk eftersom du inte behöver ändra baslinjen när du uppdaterar etiketterna.
Du kan också exportera ögonblicksbilden av baslinjen som en CSV-fil.

![Skapa baslinjer](assets/dynamic-baseline.png)

### Söka efter och ersätta text på mappningsnivå

Nu kan du söka efter filer på en karta som innehåller viss text. Den sökta texten markeras i filerna. Du kan också ersätta det sökda ordet eller frasen med ett annat ord eller en annan fras i filerna.
Välj **Ersätt** ikonen som ersätter den aktuella förekomsten och **Ersätt alla i filen** om du vill ersätta alla förekomster i den markerade filen.

![Sök ersätt på karta](assets/map-find-replace.png)

Som standard är alternativen **Checka ut filen före ersättning** och **Skapa ny version efter ersättning** är markerade, så en fil checkas ut innan du ersätter texten och en ny version skapas när texten har ersatts.

### Visa versionsskillnad för filer som inte är synkroniserade från översättningsinstrumentpanelen

Du kan nu välja att översätta **Slut på synkronisering** filer baserat på ändringar som gjorts mellan de två versionerna av ett ämne.\
![Kontrollpanel för översättning](assets/translation-version-diff.png)
På översättningens kontrollpanel ser du enkelt skillnaderna mellan den senaste översatta versionen och den aktuella versionen av den valda filen.

![versionsdifferensdialogruta](assets/version-diff.png)

Beroende på skillnaderna kan du bestämma om du vill översätta ett ämne eller inte.

### Metadatagränssnitt för förinställningar för PDF

Du kan ställa in metadata från utdataförinställningen för en DITA-karta. Du kan ange metadata för titel, författare, ämne och nyckelord. Dessa metadata mappas till metadata i filegenskaperna för utdata-PDF.
Dessa metadata åsidosätter metadata som definierats på boknivå. Du kan definiera metadata specifikt för varje utdatainställning och skicka den vidare till PDF.

![Metadata i förinställning](assets/preset-metadata.png)


## Åtgärdade problem

De buggar som har åtgärdats i olika områden listas nedan:

* Web Editor | Om du flyttar element inom ett ämne skrivs de tilldelade ID:n för element över av automatiskt tilldelade ID:n. (7895)
* Spåra ändringar | Innehållet förloras när ett nytt element anges med Retur-tangenten. (10246)
* Delkartan som refereras till huvudkartan i Dita-mallar skapas inte. (10231)
* XML Editor | Kopiera och klistra in fungerar inte i redigeringsläget. (10309)
* Flera versionsetiketter avmarkeras inte när de har markerats. (9561)
* Automatisk navigering till sökvägen i dialogrutan Bläddra fungerar inte som filbläddring. (9920)
* Dispositionspanelen visar inte innehåll när den växlas från **Upphovsman** till **Källa** läge. (10319)
* Det går inte att definiera i ett nytt ämne som skapats med innehåll i ämnesmallen. Hash-ID:t som kopieras uppdateras inte i innehållskopian. (9890)
* Webbredigerare | Det finns ingen inläsare när en karta skapas från mappningsmallen. (9891)
* Ny kartredigerare | Fet eller kursiv text i kartans titel bevaras inte om vi byter från **Upphovsman** till **Layout** vy. (10218)
* Ny kartredigerare | Villkor som används för referenser kan inte tas bort från layoutvyn. (10213)
* Ny kartredigerare | Det går inte att använda villkorsreferenser i layoutvyn på samma sätt som i redigeringsvyn. (10198)
* Ny kartredigerare | Om du flyttar åt vänster på snabbmenyn tas referensen bort om den inte kan flyttas åt vänster. (10219)
* Ny kartredigerare |Ikonen visas felaktigt för referenser i en karta som skapats i layoutvyn. (10197)
* Databaspanel | Högerklick i databaspanelen ger ett programfel. (10123)
* Sök och ersätt | Mörkt läge kan inte läsas för sökresultat i webbredigeraren. (9978)
* Översättning | Metadata och taggar sprids inte till de översatta kopiorna. (4696)
* Kopiera inklistring (ctrl+c/ctrl+v) ger ett fel i redigeringsläget. (10304)
* PDF-mall | Om du lägger till bakgrundsbilder i en sidlayout visas bildsökvägen absolut och bilderna visas inte i PDF i utdata. (10297)
* PDF | Kapitelrubrik och kapitelrubrik fungerar inte i PDF. (9947)
* PDF | `xref` för ett koncept inte löses korrekt för ett specifikt DITA-ämne. (10229)
* PDF | Det går inte att visa bildtext för en tabell i genererade utdata för PDF. (9827)
* PDF | Referenser i bilagor visas inte som bilagor i utdata från PDF. (10182)
* PDF | Bildruteattributet för en tabell sprids inte till den temporära HTML (som klass). (10353)
* PDF | temporära HTML-filer lägger till klasserna colsep och rowsep till td och även om deras värde är 0 i käll-DITA. (10352)
* PDF | Metadata för villkor som lagts till i sidlayout respekteras inte. (10377)
* PDF | Det går inte att generera PDF för visst innehåll. (9927)
* PDF | Innehåll via conkeyref visas inte i utdata från PDF. (9836)
* PDF | Nyckelreferenser för nyckeldefinitioner med bilder eller externa länkar är inte lösta. (10063)
* I redigeringsvyn för en karta visas inte platshållartext för tabeller och illustrationer. (10330)
* När vi skapar en ny baslinje används inte det redan valda baslinjefärgfiltret. (9954)
* Videofilen saknas från baslinjen om det överordnade mappnamnet har ett blankstegstecken. 10031)
* När du skapar baslinje väljs inte den senaste versionen när användarens tidszon skiljer sig från serverns tidszon. (10190)
* Genvägen Ctrl+F öppnar inte webbläsarsökningen modal på Resurskonsolen efter att AEM Guides 4.1 på AEM 6.5.12 har installerats. (10189)


## Kända fel

Adobe har identifierat följande kända problem AEM Guides as a Cloud Service från september 2022.


* Dynamisk baslinje är inte integrerad med kunskapsbaspublicering.

* Översättning | Ikonen för versionsskillnad visas för källinnehållet på grund av ändringar i målinnehållet.
