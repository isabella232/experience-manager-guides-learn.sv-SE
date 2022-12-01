---
title: Versionsinformation | Adobe Experience Manager Guides as a Cloud Service, november 2022-utgåvan
description: Den senaste versionen av Adobe Experience Manager Guides as a Cloud Service
source-git-commit: 549417d6a45508d0afe98574499f1694ae32e708
workflow-type: tm+mt
source-wordcount: '1423'
ht-degree: 2%

---

# Den senaste versionen av Adobe Experience Manager Guides as a Cloud Service

## Uppgradera till den senaste versionen

Uppgradera din nuvarande Adobe Experience Manager Guides as a Cloud Service (kallas senare *AEM stödlinjer as a Cloud Service*) genom att utföra följande steg:
1. Ta en titt på Cloud Servicens Git-kod och växla till den gren som är konfigurerad i Cloud Servicens pipeline för den miljö som du vill uppgradera.
2. Uppdatera `<dox.version>` egenskap i `/dox/dox.installer/pom.xml` fil med dina Cloud Services Git-kod till 2022.11.198.
3. Genomför ändringarna och kör Cloud Servicens pipeline för att uppgradera till den senaste versionen av AEM Guides as a Cloud Service.

## Steg för att indexera det befintliga innehållet (endast om du använder en version som är tidigare än september-versionen av AEM stödlinjer as a Cloud Service)

Utför följande steg för att indexera det befintliga innehållet och använd den nya sök- och ersätt-texten på mappningsnivå:

* Kör en serverbegäran (med korrekt autentisering) - `http://<server:port>/bin/guides/map-find/indexin`.
(Valfritt: Du kan skicka specifika sökvägar för mappningarna för att indexera dem. Som standard indexeras alla mappningar || Exempel: `https://<Server:port>/bin/guides/map-find/indexing?paths=<map_path_in_repository>`)

* API:t returnerar ett jobId. Om du vill kontrollera jobbets status kan du skicka en GET-förfrågan med jobb-ID till samma slutpunkt - `http://<server:port>/bin/guides/map-find/indexing?jobId={jobId}`
(Exempel: http://&lt;
_localhost:8080_>/bin/guides/map-find/indexing?jobId=2022/9/15/7/27/7dfa1271-981e-4617-b5a4-c18379f11c42_678)

* När jobbet är klart kommer ovanstående GET-förfrågan att svara och ange om några kartor misslyckades. De korrekt indexerade mappningarna kan bekräftas från serverloggarna.

## Kompatibilitetsmatris

I det här avsnittet visas kompatibilitetsmatrisen för de program som stöds av AEM Guides as a Cloud Service från november 2022.

### FrameMaker och FrameMaker Publishing Server

| FMPS | FrameMaker |
| --- | --- |
| Inte kompatibel | 2020 uppdatering 4 och senare |
|  |  |

*Originalplan och villkor skapade i AEM stöds i FMPS-versioner från och med 2020.2.

### Syrgasanslutning

| AEM stödlinjer som en Cloud-release | Syrgasanslutningsfönster | Syrgasanslutning Mac | Redigera i syrgasfönster | Redigera i Syrgas Mac |
| --- | --- | --- | --- | --- |
| 2022.11.0 | 2.7.13 | 2.7.13 | 2.3 | 2.3 |
|  |  |  |  |


## Nya funktioner och förbättringar

AEM Guides as a Cloud Service innehåller förbättringar och nya funktioner i den senaste versionen:


### Ta bort filer från databaspanelen

Nu kan du enkelt ta bort filer (en fil i taget) från **Alternativ** menyn för den valda filen från databaspanelen.
<img src="assets/repository-delete-file.png" alt="Ta bort från databas" width="500">

En bekräftelse visas innan filen tas bort. Om det inte finns någon referens till filen från någon annan fil tas den bort och ett meddelande om att åtgärden lyckades visas.

Om den markerade filen är utcheckad kan du inte ta bort den och ett felmeddelande visas. Om den markerade filen läggs till i en favoritsamling eller refereras från någon annan fil, AEM guider kontrollerar om du fått din bekräftelse och du har möjlighet att framtvinga borttagning. Om du tar bort ett refererat ämne och har öppnat filen som innehåller referenser för redigering, visas den brutna länken för den refererade filen.

**Anteckning**: Du kan också ta bort den markerade filen med tangenten Delete på tangentbordet.


### Rensa valda versioner av filer

När du skapar och underhåller ditt innehåll kan många versioner skapas för dina DITA-filer i din databas. Med AEM Guides kan du rensa bort äldre versioner av dina DITA-filer från databasen och frigöra diskutrymme.

<img src="assets/preview-purge-report.png" alt="Förhandsgranska rensningsrapport" width="500">


AEM tar inte bort den första versionen av filen eller en version som ingår i en baslinje, eller har en etikett tillämpad på den. Rensningsåtgärden tar inte ens bort filer som ingår i en översättning eller ett granskningsarbetsflöde. Du kan välja hur många versioner som ska behållas och även välja att ta bort filer som är äldre än det angivna antalet dagar.

Innan du startar rensningsåtgärden kan du förhandsgranska rapporten och se vilka versioner som kommer att rensas. Du kan sedan välja att starta eller avbryta rensningsåtgärden.

<img src="assets/download-purge-report.png" alt="PDownload tömningsrapport" width="500">

När rensningsåtgärden är klar kan du kontrollera rensningsrapporten för att se de rensade filerna.

### Hantera förinställningar för utdata för global profil och mappprofil

I AEM Guides kan du skapa och hantera förinställningar för globala profiler och mappprofiler. Sedan kan du enkelt använda de här förinställningarna för att generera utdata för alla kartor som är relaterade till den globala profilen eller mappprofilen.

<img src="assets/add-global-output-preset.png" alt="Lägg till global profil" width="400">

**Anteckning** Endast administratörer på mappnivå kan skapa förinställningar för global profil och mappprofil.

Dessa globala förinställningar visas under **Utdata** -fliken för alla relaterade kartor. Du kan använda dem för att generera utdata för alla relaterade kartor. Du kan välja förinställningen som standardförinställning för PDF för att generera utdata från PDF. Du kan också **Redigera**, **Byt namn**, **Duplicera**, eller **Ta bort** en befintlig förinställning från **Alternativ** -menyn.

### Kolumnen Versionsetikett har lagts till på översättningsinstrumentpanelen

På översättningens kontrollpanel kan du även se kolumnen Versionsetikett. Då visas etiketten för den valda versionen av källfilen. Detta kan hjälpa dig att markera alla filer med en viss etikett och översätta dem på en gång.

<img src="assets/send-translation.png" alt="skicka för översättning" width="600">


## Förbättrad publicering i PDF

### PDF med ändringsfält som visar skillnaden mellan dokumentversioner

Nu kan du skapa en PDF som visar skillnaderna i innehåll mellan två versioner med hjälp av ändringsfältet. Du kan välja att jämföra den aktuella versionen med en baslinje från den tidigare versionen eller jämföra de två valda baslinjeversionerna.

<img src="assets/pdf-change-version.png" alt="spdf-change-version" width="600">

Ett ändringsfält visas i PDF för att ange det ändrade, infogade eller borttagna innehållet. Du kan även göra följande:
* Visa det infogade innehållet i grön färg och understruken
* Visa borttaget innehåll i röd färg och markerat med genomstrykning

### Variabelstöd för utdatasökväg och PDF-filnamn

Nu kan du även använda följande variabler för att definiera utdatasökväg och PDF-fil. Du kan definiera dessa alternativ med en eller flera variabler:
* `${map_filename}`
* `${map_title}`
* `${preset_name}`
* `${language_code}`
* `${map_parentpath}` (Endast för utdatasökväg)
* `${path_after_langfolder}` (Endast för utdatasökväg)


### Generera innehållsförteckning för DITA-kartor och ändra ordning på sidlayouter

Nu kan du även generera innehållsförteckningen i DITA-kartor med en avancerad PDF-inställning för mallen. Du kan välja att aktivera eller inaktivera visningen av de olika sidlayouterna och även ändra ordningen på deras position.

## Åtgärdade problem

De buggar som har åtgärdats i olika områden listas nedan:

* PDF | En fotnot i tabellhuvudet leder till en fet och centrerad fotnotstext i sidfoten i utdata från PDF. (10610)
* PDF | `conkeyref` löses inte i genererade utdata för PDF. (10564)
* PDF | Problem uppstår vid åtkomst av metadata för en karta i utdata från PDF. (10556)
* PDF | Infogat format används för att generera taggar i stället för klassnamn.  (10498)
* Webbredigeraren läser in tomma sidor ibland. (10678)
* Publicering i PDF misslyckas om vi skapar en förinställning genom att duplicera en befintlig förinställning. (10584)
* **Visa logg** fungerar inte när genereringen av PDF misslyckas för en förinställning. (10576)
* Anteckning inuti en paragraf som är en konref visas inte i förhandsvisningen. (10559)
* Hela listan tas bort om du placerar backstegstangenten i slutet av ett listobjekt. (10540)
* Om du använder en inbyggd PDF-export `<indexterm>` är inte kapslade i indexet. (10521)
* Använda felaktig baslinjepublicering `cq:tags` plockas (hämtas från aktuell arbetskopia i stället för versionskopia). (10494)
* **Automatiskt indrag** i verktygsfältet saknas i källvyn. (10448)
* Det första tecknet i ett listobjekt försvinner när listan redigeras. (10447)
* Flera popup-fönster visas om någon DITA-resursversion ändras och sparas i redigeringsfönstret för baslinjen. (10399)
* Programfel inträffar när användaren klickar **Redigera** när du har valt alla förinställningar för utdata på snabbgenereringspanelen. (10388)
* Anpassade metadata för DITA-avsnittet behålls inte när en inklistringsåtgärd för kopiering utförs från resursgränssnittet. (10367)
* Efterbearbetning blockeras för hela språkmappen vars resurser finns i ett aktivt översättningsprojekt. (10332)
* Fliken Mall i XML-redigeraren är inte synlig för mappprofiladministratörer. (10266)
* Navigeringsproblem uppstår i Web Editor efter 4.0-uppgraderingen. (10159)
* Det första tecknet bryts på koreanska när du redigerar i webbredigeraren. (10049)
* SVG-filer visas inte i förhandsgranskningsläget. (10010)
* Om fliken Utdata i redigeraren innehåller fler förinställningar kan avsnittet med förinställningar inte rullas och alla förinställningar visas inte. (9787)
* **Redigera** och **Anteckna** alternativen för en bild fungerar inte korrekt i kolumnvyn. (8758)
* Peer-länken är inte löst och visas som en normal text i genererade utdata. (7774)
