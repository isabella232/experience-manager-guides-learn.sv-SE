---
title: Versionsinformation | Uppgraderingsinstruktioner och åtgärdade fel i Adobe Experience Manager Guides 4.3.1
description: Lär dig mer om felkorrigeringarna och hur du uppgraderar till 4.3.1-utgåvor av Adobe Experience Manager Guides
source-git-commit: 880cd344ceb65ea339be699ebcad41c0d62e168a
workflow-type: tm+mt
source-wordcount: '1306'
ht-degree: 0%

---

# 4.3.1-utgåvan av Adobe Experience Manager Guides (oktober 2023)

Den här versionsinformationen innehåller uppgraderingsinstruktioner, kompatibilitetsmatris och problem som har korrigerats i version 4.3.1 av Adobe Experience Manager Guides (senare kallat *Stödlinjer för Experience Manager*).

Mer information om de nya funktionerna och förbättringarna finns i [Nyheter i version 4.3.1 av Adobe Experience Manager Guides](./whats-new-4.3.1-release.md).

## Uppgradera till version 4.3.1 av Experience Manager Guides


Du kan enkelt uppgradera din nuvarande version av Guides till version 4.3.1. Innan du uppgraderar till version 4.3.1 av handboken för Experience Manager måste du tänka på följande: Du kan uppgradera din nuvarande version av handboken för Experience Manager till version 4.3.1


- Om du använder version 4.3.0, 4.2 eller 4.2.1 kan du uppgradera direkt till version 4.3.1.
- Om du använder version 4.1 eller 4.1.x måste du uppgradera till version 4.3.0, 4.2 eller 4.2.x innan du uppgraderar till version 4.3.1.
- Om du använder version 4.0 måste du uppgradera till version 4.2 innan du uppgraderar till version 4.3.1.
- Om du använder version 3.8.5 måste du uppgradera till version 4.0 innan du uppgraderar till version 4.2.
- Om du har en tidigare version än 3.8.5 kan du läsa mer i avsnittet Upgrade Experience Manager Guides i den produktspecifika installationsguiden.


>[!NOTE]
>
>Du måste installera AEM Service Pack innan du uppgraderar Experience Manager Guides-versionen.

Mer information finns i [Uppgraderingsinstruktioner](../install-guide/upgrade-xml-documentation.md).

## Kompatibilitetsmatris

I det här avsnittet listas kompatibilitetsmatrisen för de program som stöds i version 4.3.1 av Experience Manager Guides.

### Adobe Experience Manager

**4.3.1 Ej UUID**
Version 6.5 Service Pack 18, 17, 16, 15 eller 14

**4.3.1 UUID**
Version 6.5 Service Pack 18, 17, 16, 15 eller 14

Mer information finns i *Tekniska krav* i guiden Installera och konfigurera Adobe Experience Manager Guides.

### FrameMaker och FrameMaker Publishing Server

| Frigör | FMPS 2022 | FMPS 2020 | Fm 2022 | Fm 2020 |
| --- | --- | --- | --- | --- |
| 4.3.1 (ej UUID) | 2022 eller senare | 2020.2 eller senare* | 2022 eller senare | 2020.3 eller senare |
| 4.3.1 (UID) | 2022 eller senare | 2020.2 eller senare* | 2022 eller senare | 2020.4 eller senare |
| | | | |

*Originalplan och villkor skapade i AEM stöds i FMPS-versioner från och med 2020.2.

### Syrgasanslutning

| Frigör | Syrgasanslutningsfönster | Syrgasanslutning Mac | Redigera i syrgasfönster | Redigera i Syrgas Mac |
| --- | --- | --- |--- |--- |
| 4.3.1 (ej UUID) | 2.3-regular-5 | 2.3-regular-5 | 1,6 | 1,6 |
| 4.3.1 (UID) | 3.2-uuid-5 | 3.2-uuid-5 | 2,3 | 2,3 |
|  |  |   |



### Kunskapsbasmallens version

| Komponentpaketets namn | Komponentversion | Mallversion |
|---|---|---|
| Innehållspaket för komponenter i Experience Manager-stödlinjer för Cloud Service | dxml-components.all-1.2.2 | aem-site-template-dxml.all-1.0.15 |

## Åtgärdade problem

De buggar som har åtgärdats i olika områden listas nedan:

### Redigering

- Eftermiddagstid anges inte i **Datum** för att skapa baslinjer. (12712)
- Det går inte att klistra in JSON-koden i `<codeblock>` i Web Editor. 12326
- Versionsändringar som inte har sparats och indikatorerna för dem visas inte för stora filer. 11784
- När du redigerar på koreanska ändras det första tecknet till standardvärdet. (10049)

- Prefixet dupliceras i förhandsgranskningsläget i Web Editor. 13133
- `Choicetable` rader visas inte eller kan inte markeras. 12616
- Webbredigeraren genererar valideringsfel i specifika scenarier när du skapar ett ämne med ett anpassat schema. 12576
- Mallreferenser för dynamiska ämnen skapar inte någon kopia i innehållsmappen när en karta från mappningsmallen skapas. (12150)

- Sökrutan i DITA-kartor har ingen stängningsknapp. (11867)
- När du sparar långa filer i Web Editor `DirtyChecker` genererar ett undantag med en lång stackspårning och fyller i loggfilerna. (11860)
- För att skapa DITA-avsnitt krävs behörigheten Ta bort på motsvarande mappnod, men kartan kan skapas med skrivbehörighet. 11706
- I webbredigeraren visas en felaktig titel när det finns ett snedstreck. (10949)

- Om titeln för ett ämne innehåller ett snedstreck &quot;/&quot;, visar fliken i redigeraren bara de bokstäver som kommer efter det. 13455
- Förhandsvisningen av bilden försvinner inte när du har visat förhandsvisningen i redigeraren. 13454
- Vissa av de befintliga versionerna eller deras etiketter visas inte i versionshistoriken efter uppgraderingen till 4.x. 13247
- Versionshistorikpanelen i resursgränssnittet visar en felaktig tidsstämpel för **Aktuell** fält. 12624
- Ämnet med conref-titel löses inte i databasvyn eller kartvyn.(13304)


### Publicering

- PDF | Ordningen på ämnena är inte fast när utdata från PDF skapas. 13157
- Inbyggd PDF| Det finns ingen standardformattagg för `<p>`-element. (12559)
- PDF | Infogade format som används i innehållsområdet används inte för ämnen som skrivs framför och under. (13510)
- The `DeliveryTarget` attribut sprids inte när AEM genereras.  13132
- The **Publicera** arbetsflödet fastnar när AEM genereras för innehåll med vissa fel. (12000)

- PDF | Om du tar med flera xrefs, utvidgas texten utanför kolumnbredden. 13004
- PDF | När ämnet och titeln har samma ID leder det till en felaktig generering av PDF-utdata. 12644
- PDF | Lägga till en utdataklass till en överordnad `<topicref>` -elementet i en DITA-karta och använder en anpassad stil på klassen Output. Formateringen används på element i ämnesbrödtexten, inklusive avsnittsrubriker. (12166)
- Inkrementell publicering fungerar inte om en DITA-karta har flera diavalrefs. (12117)
- AEM | När du skapar en karta med nyckelord som pekar på ett ämne som en variabel och lägger till processing-role=resource-only skapas en del oväntade sidor. (12099)
- Om resurser från AEM DAM används i andra utdata än den AEM platsen, återspeglar inte metadata&quot;jcr:createdBy&quot; utgivarens namn eller namnet på den användare som senast ändrade DITA-kartan eller -avsnittet. (12090)
- AEM Sites | DITA-kartan med topichad i navigeringsrubriken (med tecken som inte stöds) leder till felaktiga sidadresser. (11978)
- PDF | Problem inträffar med stöd för topichead/topicmeta/navtitle i Frontmatter och Backmatter. (11969)
- PDF | Det tar tid att generera PDF för stora dokument. (11955)
- PDF | Om du byter namn på en förinställning genereras ett NullPointerException-fel när du genererar utdata i PDF. 11889
- The `<conref>` -innehåll visas inte i utdata från PDF. (11131)
- Ett extra blanksteg läggs till i `<div>` element vid växling mellan redigeringsvyn för författare och källa i sidlayoutredigeraren. 10750)
- Innehållet som replikeras i AEM Cloud Manager visas inte i Publish-instansen. 9564


### Förvaltning

- Versionshistorik visas inte även om `dc:format` egenskapen finns inte för en resurs. 10463
- Innehållsreferens är bruten kopiering och inklistring av DITA-filer när ämnets ID inte är detsamma som GUID. 12614
- I dynamiska baslinjer hämtas inte listan med etiketter från de direkta referenserna för arbetskopian av en DITA-karta. (11917)
- Baslinjen visar det felaktiga antalet filer på Map Dashboard när du använder funktionen Bläddra i alla ämnen. 13265
- Baslinjen i Web Editor visar titeln för den föregående versionen i stället för den valda versionen av DITA-filen. 13444)

### Granska

- Granskningen av ett ämne visar felaktiga kommentarer. 13453
- Knappen Stäng på sidan Granska i Experience Manager-guiderna tar användarna till AEM hemsida. 13535
- Bifogade filer visas inte på redigerarens högra panel för ett ämne som ska granskas. (13011)



### Översättning

- Baslinjen exporterad från **Översättning** Kontrollpanelen misslyckas och öppnas inte på målspråket. 13466)

- Nya översättningsprojekt skapas i stället för att nya jobb läggs till i de valda befintliga översättningsprojekten.  (10214)
- Den översatta filens namn visas i stället för källfilens namn. (11630)
- Automatisk godkännande fungerar ibland inte, och undantag uppstår om ett felaktigt värde har angetts för Översättningsstatus. 13607
- Baslinjen som exporteras från översättningsinstrumentpanelen misslyckas och öppnas inte på målspråket. (12993)
- Vissa filer saknas när baslinjer används i översättning. 13021
