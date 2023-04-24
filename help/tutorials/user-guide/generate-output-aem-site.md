---
title: AEM
description: Lär dig AEM
source-git-commit: 23d6c87b525f0763990166e46f4bd4ac2d6e7cd5
workflow-type: tm+mt
source-wordcount: '2545'
ht-degree: 0%

---


# AEM {#id205BE3008SW}

Följande alternativ är tillgängliga för AEM platsutdata:

Du kan skapa AEM platsförinställning på två sätt:

**Från webbredigeraren:** Öppna DITA-schemafilen i Kartvyn på panelen Databas, välj ikonen + på fliken Utdata för att skapa en utdatainställning och välj sedan AEM Plats i listrutan i dialogrutan Lägg till förinställning.I webbredigeraren har konfigurationerna ordnats under flikarna Allmänt och Avancerat:

**Allmänt**

The **Allmänt** -fliken innehåller följande konfigurationer:

- Platsnamn
- Utdatasökväg
- Befintliga utdatasidor
- Ta bort enstaka webbplatssidor
- Använd villkor med \(Om villkoren är definierade för en karta\)
- Använd baslinje \(Om en baslinje skapas för en karta\)
- Arbetsflöde efter generering

**Avancerat**

Fliken Avancerat innehåller följande konfigurationer:

- Rensa tillfälliga DITA-OT-filer
- Generera separat PDF för varje ämne
- Använd kartegenskaper som standard

Mer information finns i [Konfiguration av AEM](#id231KIM004X1).

**Från kartpanelen**

Om du vill öppna förinställningar för AEM webbplats klickar du på en DITA-kartfil i resursgränssnittet, sedan på Utdatainställningar och sedan på AEM Utdataläge.Klicka på panelen Karta. **Redigera** överst för att uppdatera de olika konfigurationerna och sedan klicka på **Spara**.

>[!TIP]
>
> Se *AEM* i guiden för bästa praxis om hur du skapar AEM webbplatsutdata.

## Konfiguration av AEM {#id_aem_site_config}

Följande alternativ är tillgängliga för AEM platsutdata:

| Alternativ för AEM | Beskrivning |
| --- | --- |
| Utdatatyp | Den typ av utdata som du vill generera. Om du vill generera responsiva AEM platsutdata väljer du alternativet AEM plats. |
| Inställningsnamn | Ange ett beskrivande namn för de AEM platsinställningar som du skapar. Du kan till exempel ange *Resultat från interna kunder* eller *slutanvändares utdata*. |
| Platsnamn | Ett platsnamn där utdata lagras i AEM.<br><br>En nod i AEM skapas med det namn som anges här. Om du inte anger platsnamnet skapas platsnoden med DITA-mappningsfilens namn.<br><br>Det platsnamn du anger här används också som rubrik på fliken Webbläsare.<br><br>Du kan också använda variabler när du anger platsnamn. Mer information om hur du använder variabler finns i [Använd variabler för att ange alternativen Målsökväg, Platsnamn eller Filnamn](generate-output-use-variables.md#id18BUG70K05Z). |
| Design | Välj den designmall som du vill använda för att generera utdata.<br><br>Kontakta din publiceringsadministratör om du vill ha mer information om hur du använder anpassade designmallar för att generera utdata. |
| Målsökväg | Den sökväg i AEM där utdata lagras. När du genererar det slutliga resultatet kombineras platsnamnet och målsökvägen. Om du till exempel anger platsnamnet som `user-guide` och målsökvägen som `/content/output/aem-guides`, genereras slutresultatet under `/content/output/aem-guides/user-guide` nod.<br><br>Du kan också använda variabler när du anger målsökvägen. Mer information om hur du använder variabler finns i [Använd variabler för att ange alternativen Målsökväg, Platsnamn eller Filnamn](generate-output-use-variables.md#id18BUG70K05Z). |
| Använd villkor med | Välj något av följande alternativ:<br><br>**Ingen används**: Välj det här alternativet om du inte vill använda något villkor i publicerade utdata.<br>**DITAVal-fil**: Välj DITAVal-filer för att generera villkorat innehåll. Du kan markera flera DITAVal-filer i dialogrutan Bläddra eller genom att skriva filsökvägen. Använd kryssikonen bredvid filnamnet för att ta bort den. DITAVal-filer utvärderas i den ordning som anges, så de villkor som anges i den första filen har företräde framför de matchande villkor som anges i senare filer. Du kan behålla filordningen genom att lägga till eller ta bort filer. Om DITAVal-filen flyttas till en annan plats eller tas bort, tas den inte automatiskt bort från kartkontrollpanelen. Du måste uppdatera platsen om filerna flyttas eller tas bort. Du kan hovra över filnamnet för att se sökvägen i AEM databas där filen lagras. Du kan bara välja DITAVal-filer och ett fel visas om du väljer någon annan filtyp.<br>**Förinställning för villkor**: Välj en villkorsförinställning i listrutan om du vill använda ett villkor när du publicerar utdata. Det här alternativet är synligt om du har lagt till ett villkor för DITA-kartfilen. De villkorliga inställningarna finns på fliken Villkorsförinställningar i DITA-kartkonsolen. Mer information om förinställda villkor finns i [Använda förinställningar för villkor](generate-output-use-condition-presets.md#id1825FL004PN). |
| Befintliga utdatasidor | Välj **Skriv över innehåll** om du vill skriva över innehåll på befintliga sidor. Det här alternativet skriver bara över innehåll som finns under sidans innehåll och head-noder. Det här alternativet möjliggör blandad publicering av innehåll. Om du väljer det här alternativet kan du välja att ta bort överblivna sidor från publicerade utdata. Detta är också *standard* för att skapa AEM för webbplatsutdata.<br><br>Välj **Ta bort och skapa** om du vill framtvinga borttagning av befintliga sidor vid publicering. Med det här alternativet tas sidnoden bort tillsammans med innehållet och alla underordnade sidor under den. Använd det här alternativet om du har ändrat designmallen för förinställningen för utdata eller om du vill att eventuella extra sidor som redan finns i målet ska tas bort. |
| Ta bort enstaka webbplatssidor | Markera **Skriv över innehåll** i **Befintliga utdatasidor** inställningen visar det här alternativet. Om du väljer det här alternativet tas alla sidor som är överblivna bort från den publicerade AEM. För att den här funktionen ska fungera måste du publicera hela DITA-kartan och inte använda den inkrementella publiceringen.<br><br>Säg att du har publicerat en DITA-karta som innehåller avsnitten a.dita, b.dita och c.dita. Innan du publicerade kartan igen tog du bort b.dita-ämnet från kartan. Om du har valt det här alternativet tas nu allt innehåll som är relaterat till b.dita bort från AEM och bara a.dita och c.dita publiceras.<br><br>Den här funktionen tar inte bort någon publicerad underordnad karta. Om den överordnade kartan till exempel innehåller en underordnad karta och du tar bort hela den underordnade kartan tas inte innehållet bort från den publicerade utdata. Om du däremot tar bort ett ämne från en underordnad karta och publicerar om, tas innehållet i det borttagna ämnet bort från webbplatsens utdata.<br><br>Om det finns något refererat innehåll, och det innehållet tas bort innan det publiceras igen, tas det refererade innehållets data inte bort.<br><br>**Anteckning**: Information om borttagna överblivna sidor finns också i loggarna för generering av utdata. Mer information om åtkomst till loggfilerna finns i [Visa och kontrollera loggfilen](generate-output-basic-troubleshooting.md#id1821I0Y0G0A__id1822G0P0CHS). |
| Rensa tillfälliga DITA-OT-filer | Välj det här alternativet om du vill rensa de temporära filer som genererats av DITA-OT. Platsen där tillfälliga filer lagras i DITA-OT finns i loggen för generering av utdata.<br><br>Om du får problem när du genererar utdata via DITA-OT kan du avmarkera det här alternativet om du vill behålla de tillfälliga filerna. Du kan sedan använda dessa filer för att felsöka fel vid generering av utdata. |
| Generera separata PDF för varje ämne | Om du väljer det här alternativet skapas även ett PDF för varje avsnitt på DITA-kartan. När du väljer det här alternativet visas ett nytt alternativ för Delad PDF-bana.<br><br>I fältet Delad PDF-sökväg anger du sökvägen för att lagra PDF som genereras för varje ämne.<br><br>**Anteckning**: AEM Guides använder DITA-OT-pluginen pdfx för att generera PDF för varje ämne. Denna plugin medföljer DITA-OT-paketet som levereras i kartong. Du kan anpassa det här plugin-programmet för att skapa PDF efter dina behov. Om du använder en anpassad DITA-OT-plugin måste du integrera pdfx-pluginen för att kunna skapa PDF på ämnesnivå. |
| Kör arbetsflöde efter generering | När du väljer det här alternativet visas en ny arbetsflödeslista som innehåller alla arbetsflöden som är konfigurerade i AEM. Du måste välja ett arbetsflöde som du vill köra när arbetsflödet för generering av utdata har slutförts. |
| Använd baslinje | Om du har skapat en baslinje för den valda DITA-kartan väljer du det här alternativet för att ange vilken version du vill publicera.<br><br>**Viktigt**: När du genererar inkrementella utdata för den AEM platsen skapas utdata med den aktuella versionen av filerna och inte med den kopplade baslinjen.<br><br>Se [Arbeta med baslinje](generate-output-use-baseline-for-publishing.md#id1825FI0J0PF) för mer information. |
| Egenskaper | Välj de egenskaper som du vill bearbeta som metadata. Dessa egenskaper ställs in från sidan Egenskaper i DITA-kartan eller bokmappningsfilen. Egenskaperna som du väljer i listrutan visas under fältet Egenskaper och tas bort från listrutan.<br><br>**Anteckning**: Metadataegenskaperna är skiftlägeskänsliga.<br><br>*Om du har valt en baslinje baseras värdena för egenskaperna på versionen av den valda baslinjen.<br>* Om du inte har valt en baslinje baseras värdena för egenskaperna på den senaste versionen.<br><br>Du kan också skicka metadata till utdata med DITA-OT-publicering. Mer information finns i [Skicka metadata till utdata med DITA-OT](pass-metadata-dita-ot.md#id21BJ00QD0XA).<br><br>**Anteckning**: Om du inte har definierat `cq:tags` i alternativet Egenskaper, sedan värdena för `cq:tags` väljs från den aktuella arbetskopian även om du har valt en baslinje för publicering. |
| Använd kartegenskaper om de saknas i ämne | Om du väljer det här alternativet kopieras även de egenskaper som definierats för kartfilen till de avsnitt där sådana egenskaper inte har definierats. Tänk på följande när du använder det här alternativet:<br><br>*Endast egenskaperna String, Date och Long (en och flera värden) kan skickas till AEM Site-sidor.<br>* Metadatavärdena för en String-typegenskap stöder inte några specialtecken (till exempel `@, #, " "`).<br>* Det här alternativet bör användas tillsammans med `Properties` alternativ. |

## Ytterligare information om AEM

### Generera artikelbaserade utdata från Web Editor

Du kan generera AEM för ett eller flera ämnen eller hela DITA-kartan från Web Editor. Du måste skapa förinställningar för DITA-kartan och sedan enkelt generera AEM för din karta. Om du har uppdaterat några avsnitt på kartan kan du även generera AEM webbplatsutdata endast för dessa ämnen från Web Editor. Mer information finns i [Artikelbaserad publicering från webbredigeraren](web-editor-article-publishing.md#id218CK0U019I).

### Generera utdata som länkar ämnen från andra kartor

Det är ett mycket vanligt scenario att ha en stor uppsättning dokumentation spridda över flera mappar och DITA-kartor. Det blir extremt komplext att publicera innehåll som är länkat från olika platser. Som standard är alla länkar `<xref>` skapas med `local` `@scope`. Publicering av sådana ämnen innebär inga utmaningar eftersom den använder direktlänk till ämnet. Om ämnet ligger utanför den aktuella DITA-kartan visas inte det länkade innehållet i länken.

Ett annat sätt att länka innehåll är att skapa en länk med `peer` `@scope`. För sådant innehåll löses länken vid körning genom att det konfigurerade sammanhanget för det länkade ämnet väljs från DITA-kartans publiceringskontext. På följande skärmbild visas egenskapspanelen för en länk med `peer` `@scope`:

![](images/peer-link-scope-link.png){width="800" align="left"}

För att förenkla publiceringen av komplexa kartor och ämnen som länkar till andra ämnen i andra kartor AEM du använda stödlinjerna för att ange publiceringskontext för varje förinställning.

I publiceringssammanhanget kan du ange vilket ämne som ska användas för att publicera ett visst utdataavsnitt. Låt oss förstå detta med hjälp av ett exempel - låt oss säga att du har fyra mappar: sampla a, exempel b, prov c och exempel d. Varje mapp innehåller en DITA-karta - DITA-karta A, DITA-karta B, DITA-karta C och DITA-karta D. Länkning av tvärscheman sker när ett avsnitt i DITA-kartan A länkar till ett ämne på DITA-kartan B, C eller D. I skärmbilden nedan innehåller exempelavsnittet länkar \(eller referenser\) till filer som är en del av andra DITA-kartor.

![](images/sample-concept-link-to-other.png){width="450" align="left"}

När du nu konfigurerar publiceringsinställningarna för AEM webbplats för kartfilen som innehåller det här avsnittet kan du välja vilken publiceringskontext för det länkade innehållet som ska användas vid publiceringen. En publiceringskontext är en kombination av DITA-kartan och dess förinställning för utdata. Utdataförinställningen innehåller i sin tur en specifik version av innehållet och villkorliga förinställningar. Hela den här kombinationen av DITA-kartan, förinställningen, versionen \(filer\) och villkoren definierar publiceringskontexten för en länkad karta.

Gör så här för att ange publiceringskontext för korslänkade filer:

1. Öppna **Förinställningar för utdata** -fliken i den DITA-karta som du vill publicera.

1. Välj **AEM** förinställning för utdata.

   Du kan hämta AEM förinställningar och publiceringskontextflikterna.

   ![](images/aem-site-publish-settings.png){width="800" align="left"}

1. Öppna **Publicera kontext** -fliken.

   Du visas en lista med beroende ämnen. Det här är ämnen som är länkade från något ämne i den aktuella kartan, men de är tillgängliga i vissa andra DITA-kartor.

   >[!NOTE]
   >
   > På fliken Publiceringskontext visas ämnen som är länkade med `peer` `@scope` endast. För länkar med `local` `@scope`behöver du inte ange publiceringskontext.

   Som standard är alla länkade ämnen markerade med sin senaste förinställning och karta för utdata.

   ![](images/default-publish-context.png){width="800" align="left"}

1. Om du vill ändra standardvalet för DITA-kartan och förinställningen klickar du på **Redigera** \(i huvudverktygsfältet\).

1. Om du vill använda de senast publicerade utdata för varje beroende fil på kartan väljer du **Använd den senast genererade publiceringskontexten för alla beroende ämnen**.

1. I **Överordnad karta** i den nedrullningsbara listan markerar du den kartfil vars utdata du vill länka den aktuella kartans utdata.

   När du väljer en kartfil visas kartans UUID i kolumnen Överordnad karta. De förinställningar för utdata som är associerade med den valda kartan visas i listan Förinställningar för överordnad karta.

1. I **Förinställning för överordnad karta** väljer du den förinställning som du vill länka den aktuella kartans utdata till.

1. Välj önskad karta och dess förinställning för alla beroende ämnen och klicka på **Klar**.

   Kontexten för de beroende ämnena ställs nu in. Du kan generera utdata för den aktuella kartan. Mer information om hur du genererar utdata finns i [Generera utdata för en DITA-karta från kartkonsolen](generate-output-for-a-dita-map.md#).

### Blandad publicering

AEM Guides har stöd för publicering av DITA-innehåll på din befintliga AEM. Om du till exempel har en befintlig plats kan du använda AEM webbplatsutdata för att publicera endast DITA-innehållet på den platsen. I den här processen ändras inte det befintliga icke-DITA-innehållet i publiceringsprocessen. Kontakta din publiceringsadministratör om du vill ha mer information om hur du konfigurerar webbplatsen så att endast DITA-innehåll publiceras.

### Publicering `conref`

Om du använder `conref` i innehållet publiceras det som normalt eller inbäddat innehåll tillsammans med innehållet i källämnet \(eller refererande\). The `conref` innehållet återges tillsammans med huvudinnehållet och ingen separat webbplatssida skapas för det. När du söker efter innehållet som refereras i `conref`, och sedan bara huvudavsnittet eller huvudsidan som innehåller `conref` innehållet visas i sökresultaten.

>[!NOTE]
>
>Om du har skapat separata sidor för `conref` innehåll med hjälp av AEM Guides version 3.5 eller tidigare rekommenderar vi att du rensar/tar bort dessa sidor med [Ta bort enstaka webbplatssidor](#delete-orphan-page-aem-site) alternativ.


### Söka efter en sträng i innehållet

Du kan söka efter en sträng i AEM. Som standard kan du bara söka efter strängen i rubrikerna. Om du vill söka efter strängen i innehållet eller innehållet i AEM webbplatsutdata kontaktar du systemadministratören för att aktivera egenskapen flattening.enabled.


<img src="images/aem-output-search.png" alt="Sök AEM webbplatsutdata" width="800">

Mer information finns i *Konfigurera förenkling AEM platsnodens struktur* i guiden Installera och konfigurera Adobe Experience Manager Guides.

**Överordnat ämne:**[ Förinställningar för utdata](generate-output-understand-presets.md)