---
title: Versionsinformation | Adobe Experience Manager Guides 4.2
description: Lär dig mer om felkorrigeringarna och hur du uppgraderar till 4.2-utgåvor av Adobe Experience Manager Guides
source-git-commit: 880cd344ceb65ea339be699ebcad41c0d62e168a
workflow-type: tm+mt
source-wordcount: '1391'
ht-degree: 0%

---

# 4.2-utgåvan av Adobe Experience Manager Guides (februari 2023)

Den här versionsinformationen innehåller uppgraderingsinstruktioner, kompatibilitetsmatris och problem som har korrigerats i version 4.2 av Adobe Experience Manager Guides (senare kallat *AEM stödlinjer*).

Mer information om de nya funktionerna och förbättringarna finns i [Nyheter i version 4.2 av Adobe Experience Manager Guides](whats-new-4.2-release.md).

## Uppgradera till version 4.2 av AEM

Du kan enkelt uppgradera din nuvarande version av AEM till version 4.2. Innan du uppgraderar till version 4.2 AEM handboken måste du tänka på följande:
* Om du använder version 4.0, 4.1 eller 4.1.x kan du uppgradera direkt till version 4.2.
* Om du använder version 3.8.5 måste du uppgradera till version 4.0 innan du uppgraderar till version 4.2.
* Om du använder en version som är tidigare än 3.8.5, se *AEM* i den produktspecifika installationsguiden.

>[!NOTE]
>
>Du måste installera AEM Service Pack innan du uppgraderar AEM Guides version.

Mer information finns i [Uppgraderingsinstruktioner](assets/Adobe-Experience-Manager-Guides-Upgrade-Instructions-EN.pdf).

## Kompatibilitetsmatris

I det här avsnittet visas kompatibilitetsmatrisen för de program som stöds i AEM 4.2.

### Adobe Experience Manager

**Ej UID**
Version 6.5 Service Pack 15, 14, 13 eller 12

**UUID**
Version 6.5 Service Pack 15, 14, 13 eller 12

Mer information finns i *Tekniska krav* i guiden Installera och konfigurera Adobe Experience Manager Guides.

### FrameMaker och FrameMaker Publishing Server

| Frigör | FMPS 2022 | FMPS 2020 | Fm 2022 | Fm 2020 |
| --- | --- | --- | --- | --- |
| 4.2 (ej UUID) | 2022 eller senare | 2020.2 eller senare* | 2022 eller senare | 2020.3 eller senare |
| 4.2 (UUID) | 2022 eller senare | 2020.2 eller senare* | 2022 eller senare | 2020.4 eller senare |
| | | | |

*Originalplan och villkor skapade i AEM stöds i FMPS-versioner från och med 2020.2.

### Syrgasanslutning

| Frigör | Syrgasanslutningsfönster | Syrgasanslutning Mac | Redigera i syrgasfönster | Redigera i Syrgas Mac |
| --- | --- | --- |--- |--- |
| 4.2 (ej UUID) | 2.1-regular-4 | 2.1-regular-4 | 1,6 | 1,6 |
| 4.2 (UUID) | 2.8-uuid-8 | 2.8-uuid-8 | 2,3 | 2,3 |
|  |  |   |

## Åtgärdade problem

De buggar som har åtgärdats i olika områden listas nedan:

### Redigering

* Vänster panel bryts när en flik läggs till. (11126)
* HTML-koden för Web Editor orsakar problem med `<dl>` och `<dlentry>`. (11024)
* Vissa attribut behandlas inte som villkorliga och orsakar problem. (10895)
* Tre nivåer eller fler kapslade `<indexterm>` är inte kapslade vid export i PDF. (10799)
* Innehållet försvinner i en uppgiftsdel när du växlar från redigeringsvyn till källvyn. (10735)
* Granskningskommentarer placeras inte i en granskningsuppgift. 10625
* `<conref>` anteckning inuti en paragraftagg visas inte i förhandsgranskningsläget. (10559)
* Hela listan tas bort om du placerar backstegstangenten i slutet av ett listobjekt. (10540)
* Skärmen visas som tom i Chrome v106 när du drar och släpper ett element från gränssnittet (till exempel från panelen Villkor). (10524)
* Knappen för automatiskt indrag saknas i verktygsfältet i **Källa** vy. 10448
* Det första tecknet i ett listobjekt går förlorat ibland när listan redigeras.( 10447)
* **Ångra** eller **Gör om** fungerar inte korrekt på vissa filer. (10373)
* Anpassade metadata behålls inte vid kopiera och klistra in-åtgärd. (10367)
* Ett fel inträffar när du kopierar (Ctrl+C) och klistrar in (Ctrl+V) innehåll. (10304)
* Dispositionspanelen visar inte innehåll när den växlar från redigeringsläge till källäge. (10296)
* Submap skapas inte när den refererar till en huvudkarta i DITA-mallar. (10231)
* Navigeringsproblem uppstår i Web Editor efter 4.0-uppgraderingen. (10159)
* Alternativet Ångra i XML-redigeraren tar användaren längst upp på sidan. (10091)
* Nodegenskaper tas bort efter att en resurs har kopierats och klistrats in. (10053)
* SVG-filer som lagts till i DITA-avsnitt visas inte i redigerarens förhandsgranskningsläge. (10010)
* Sökresultaten för att söka och ersätta i Web Editor kan inte läsas i mörkt läge. (9978)
* Det finns ingen inläsare när en karta skapas från mappningsmallen. 9891
* Conref i ämnesmallen fungerar inte och det hash-id som kopieras uppdateras inte i innehållskopian. (9890)
* Inget alternativ visas för att bläddra bland ämnen eller mappningsmallar i undermapparna till ämnet eller mappningsmappen. 9889
* Det finns inget alternativ för att skapa en ny mall i undermapparna till ämnen eller kartor. 9888
* XML-redigeraren uppdaterar inte bilderna i ämnen. (9500)
* mimeType är hårdkodad för att skapa och uppdatera DITA-resurser. 8979
* Ett vanligt bindestreck infogas när du väljer Hårt bindestreck i dialogrutan **Infoga specialtecken** -dialogrutan. (8919)
* Versionens skaparnamn i Versionshistorik är fmdita-servicuser för filer som överförts via Assets UI. 8910
* Redigeringsalternativet fungerar inte för bilder när du arbetar i kolumnvyn i resursgränssnittet. 8758
* DITA-avsnittet uppdateras inte automatiskt med ändringar gjorda på **Egenskaper** sida. 8745
* När du flyttar element inom avsnittet i Web Editor skrivs de tilldelade ID:n för element över av automatiskt tilldelade ID:n. 7895

### Förvaltning

* Om du kopierar en DITA-mappningsresurs (från tillgångsgränssnittet) skapas felaktiga baslinjer i den kopierade resursen. (11218)
* Varningsmeddelande visas inte vid överföring av en fil som är större än den gräns som tillåts i AEM (2 GB som standard). (10817)
* Web Editor-Baseline | Beteendet för den senaste kolumnen skiljer sig åt i den nya baslinjepanelen i Web Editor. (10808)
* Översättning | Översättningsjobbet kommer inte igång på grund av ogiltig /libs/fmdita/i18n/ja.json. (10543)
* Översättning | Ett fel inträffar i ett omfångsöversättningsprojekt som skapats från översättningens kontrollpanel (mänsklig översättning). (10526)
* Översättning | Efterbearbetning blockeras för hela språkmappen vars resurser finns i ett aktivt översättningsprojekt. (10332)
* Översättning| Metadata och taggar sprids inte till de översatta kopiorna. 4696
* Flera popup-fönster visas för alla resurser om versionen ändras och sparas i Baslinjeredigeraren. (10399)
* Sessionsläckan inträffar på com.day.cq.search.impl.builder.QueryBuilderImpl.createResourceResolver(QueryBuilderImpl.java:210). (10279)
* Videofilen saknas från baslinjen om den överordnade mappen innehåller utrymme i namnet. (10031)

### Publicering

* Omgenerering av ämnen fungerar inte i vissa scenarier. (10635)
* Publicering i PDF misslyckas när utdata genereras för en dubblettförinställning (för en befintlig förinställning). (10584)
* Knappen Visa logg fungerar inte om genereringen av PDF misslyckas för en förinställning. (10576)
* Publiceringslyssnaren visar inte begärda data i informationsloggar, och den innehåller även skräppostloggar.( 10567)
* PDF | Det går inte att skapa PDF med ett Null-pekarundantag. (10950)
* PDF | conkeyref löses inte i genererade utdata. (10564)
* PDF | Problem uppstår med metadata för en karta som behöver refereras till i utdata från PDF.( 10556)
* PDF | Problem uppstår när tabellrubriken roteras. (10555)
* PDF | Problem uppstår vid borttagning av ämnen med processing role=&#39;resource-only&#39;. (10554)
* PDF | Tomma nyckeltal visas i utdata från PDF. (10553)
* PDF | Kapslade `<indexterm>` är inte kapslade vid export i PDF. (10521)
* PDF | Inbyggd PDF använder inline-format i stället för klassnamn för de genererade taggarna. (10498)
* PDF | Kapslade topicref i tillägg omformas alla till h1 i det temporära HTML.( 10454)
* PDF | Det går inte att dölja ämnen som ligger före varandra i innehållsförteckningen. (10355)
* PDF | Tabellens bildruteattribut sprids inte till det temporära HTML (som klass). (10353)
* PDF | Temporära HTML-filer lägger till klasserna colsep och rowsep i <td> och <th> även om deras värde är 0 i käll-DITA. (10352)
* PDF | Om du startar om sidnummer i kapitellayouten startas numreringen slumpmässigt från slutet av föregående kapitel. (10154)
* PDF | Nyckelreferenser för nyckeldefinitioner med bilder eller externa länkar tolkas inte. (10063)
* PDF | Bilaga visas som ett kapitel i genererad PDF. 9829
* Fliken Mall i xml-redigeraren visas inte för mappprofiladministratörer. (10266)
* Baslinjepublicering misslyckas för PDF som genereras med FrameMaker Publishing Server 2020. (10551)
* Ett programfel inträffar när du klickar på knappen Redigera efter att ha markerat alla förinställningar via kryssrutan Utdatainställningar i snabbgenereringsfönstret. (10388)
* Om fliken Utdata i Web Editor har fler förinställningar går det inte att rulla avsnittet med förinställningar lodrätt och inte alla tillgängliga förinställningar visas. 9787
* Det går inte att ta bort förinställningar från utdataarbetsflödet vid publicering via redigeraren. (9100)
* Peer-länken återges som normal text i stället för som en länk på den genererade sidan. 7774

## Känt fel

Adobe har identifierat följande kända problem i AEM 4.2-versionen:

* Användare kan utföra granskningsåtgärder även när granskningsuppgifterna har slutförts.
