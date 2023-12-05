---
title: Versionsinformation | Adobe Experience Manager Guides as a Cloud Service, februari 2023-versionen
description: Februariversion av Adobe Experience Manager Guides as a Cloud Service
source-git-commit: 880cd344ceb65ea339be699ebcad41c0d62e168a
workflow-type: tm+mt
source-wordcount: '870'
ht-degree: 0%

---

# Version av Adobe Experience Manager Guides as a Cloud Service från februari 2023

Den här versionsinformationen innehåller uppgraderingsinstruktioner, kompatibilitetsmatris och problem som åtgärdats i version från februari 2023 av Adobe Experience Manager-handboken (senare kallad *AEM stödlinjer as a Cloud Service*).

Mer information om de nya funktionerna och förbättringarna finns i [Nyheter i februari 2023-utgåvan av AEM Guides as a Cloud Service](whats-new-2023.2.0.md).

## Uppgradera till februari 2023-versionen

Uppgradera din nuvarande AEM Guides as a Cloud Service genom att utföra följande steg:
1. Ta en titt på Cloud Servicens Git-kod och växla till den gren som är konfigurerad i Cloud Servicens pipeline för den miljö som du vill uppgradera.
2. Uppdatera `<dox.version>` egenskap i `/dox/dox.installer/pom.xml` fil med dina Cloud Service Git-kod till 2023.2.235.
3. Genomför ändringarna och kör Cloud Servicens pipeline för att uppgradera till februari 2023-utgåvan av AEM Guides as a Cloud Service.

## Steg för att indexera det befintliga innehållet (endast om du använder en version som är tidigare än september-versionen av AEM för as a Cloud Service stödlinjer)

Utför följande steg för att indexera det befintliga innehållet och använd den nya sök- och ersätt-texten på mappningsnivå:

* Kör en POST-begäran till servern (med korrekt autentisering) - `http://<server:port>/bin/guides/map-find/indexing`.
(Valfritt: Du kan skicka specifika sökvägar för mappningarna för att indexera dem. Som standard indexeras alla mappningar || Exempel: `https://<Server:port>/bin/guides/map-find/indexing?paths=<map_path_in_repository>`)

* API:t returnerar ett jobId. Om du vill kontrollera jobbets status kan du skicka en GET-förfrågan med jobb-ID till samma slutpunkt - `http://<server:port>/bin/guides/map-find/indexing?jobId={jobId}`
(Exempel: http://&lt;_localhost:8080_>/bin/guides/map-find/indexing?jobId=2022/9/15/7/27/7dfa1271-981e-4617-b5a4-c18379f11c42_678)

* När jobbet är klart kommer ovanstående GET-förfrågan att svara och ange om några kartor misslyckades. De korrekt indexerade mappningarna kan bekräftas från serverloggarna.

## Kompatibilitetsmatris

I det här avsnittet visas kompatibilitetsmatrisen för de program som stöds av AEM Guide as a Cloud Service från februari 2023.

### FrameMaker och FrameMaker Publishing Server

| AEM stödlinjer som en Cloud-release | FMPS | FrameMaker |
| --- | --- | --- |
| 2023.02.0 | Inte kompatibel | 2022 eller senare |
| | | |

*Originalplan och villkor skapade i AEM stöds i FMPS-versioner från och med 2020.2.

### Syrgasanslutning

| AEM stödlinjer som en Cloud-release | Syrgasanslutningsfönster | Syrgasanslutning Mac | Redigera i syrgasfönster | Redigera i Syrgas Mac |
| --- | --- | --- | --- | --- |
| 2023.02.0 | 2.8-uuid-8 | 2.8-uuid-8 | 2,3 | 2,3 |
|  |  |  |  |

## Åtgärdade problem

De buggar som har åtgärdats i olika områden listas nedan:

### Redigering

* HTML-koden för Web Editor orsakar problem med `<dl>` och `<dlentry>`. (11024)
* Vissa attribut behandlas inte som villkorliga och orsakar problem. (10895)
* Tre nivåer eller fler kapslade `<indexterm>` är inte kapslade vid export i PDF. (10799)
* Innehållet försvinner i en uppgiftsdel när du växlar från redigeringsvyn till källvyn. (10735)
* Granskningskommentarer placeras inte i en granskningsuppgift. 10625
* **Ångra** eller **Gör om** fungerar inte korrekt på vissa filer. (10373)
* Anpassade metadata behålls inte vid kopiera och klistra in-åtgärd. (10367)
* Alternativet Ångra i XML-redigeraren tar användaren längst upp på sidan. (10091)
* Nodegenskaper tas bort efter att en resurs har kopierats och klistrats in. (10053)
* mimeType är hårdkodad för att skapa och uppdatera DITA-resurser. 8979
* Versionens skaparnamn i Versionshistorik är fmdita-servicuser för filer som överförts via Assets UI. 8910
* Det går inte att kopiera och klistra in innehållsfragment när AEM har installerats i molnet. (11315)
* Webbläsaren (webbredigeraren) låser sig när innehåll läses in med ett anpassat schema. (11211)

### Förvaltning

* Om du kopierar en DITA-mappningsresurs (från tillgångsgränssnittet) skapas felaktiga baslinjer i den kopierade resursen. (11218)
* Varningsmeddelande visas inte vid överföring av en fil som är större än den gräns som tillåts i AEM (2 GB som standard). (10817)
* Web Editor-Baseline | Beteendet för den senaste kolumnen skiljer sig åt i den nya baslinjepanelen i Web Editor. (10808)
* Översättning | Översättningsjobbet kommer inte igång på grund av ogiltig /libs/fmdita/i18n/ja.json. (10543)
* Översättning | Ett fel inträffar i ett omfångsöversättningsprojekt som skapats från översättningens kontrollpanel (mänsklig översättning). (10526)
* Översättning | Efterbearbetning blockeras för hela språkmappen vars resurser finns i ett aktivt översättningsprojekt. (10332)
* Flera popup-fönster visas för alla resurser om versionen ändras och sparas i Baslinjeredigeraren. (10399)
* Sessionsläckan inträffar vid `com.day.cq.search.impl.builder.QueryBuilderImpl.createResourceResolver(QueryBuilderImpl.java:210)`. (10279)

### Publicering

* Omgenerering av ämnen fungerar inte i vissa scenarier. (10635)
* Publiceringslyssnaren visar inte begärda data i informationsloggar, och den innehåller även skräppostloggar.( 10567)
* PDF | När du skapar en utdatainställning med alternativet Lägg till i mappprofil misslyckas genereringen av PDF med ett Null-pekarundantag. (10950)
* PDF | Problem uppstår när tabellrubriken roteras. (10555)
* PDF | Kapslade `<indexterm>` är inte kapslade vid export i PDF. (10521)
* PDF | Kapslade topicref i tillägg omformas alla till h1 i det temporära HTML. 10454
* Baslinjepublicering misslyckas för PDF som genereras med FrameMaker Publishing Server 2020. (10551)
* PDF | Lägger till `xref` till en bild återges inte bilden på det genererade PDF. (11346)
* PDF | Taggen Bild lägger till ett visningsinfogat attribut i alla bilder. (10653)
* PDF | Utkastkommentarer är dolda som standard i genererade utdata. (10560)
* PDF | navtitle stöds inte för topichead. (10509)
