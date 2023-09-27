---
title: Använd HTML5
description: Lär dig hur du skapar en förinställning för HTML5 från webbredigeraren och kartpanelen. Konfigurera förinställningen för HTML5 i AEM.
exl-id: c484289b-92aa-4790-b62b-650ecbe1b86b
source-git-commit: 8504a0a52d381044bf1f0d6e7de3585ebecf3a7b
workflow-type: tm+mt
source-wordcount: '1157'
ht-degree: 0%

---

# HTML5 {#id205BE700XO1}

HTML5-utdata genereras i en hierarki med platta mappar. Detta innebär att mappstrukturen som används av innehållet i databasen inte replikeras i utdata från HTML5. Hela innehållet publiceras i utdataformat för HTML5 och sparas i en enda mapp. Filnamnen ersätts också med UUID:n för filerna i de genererade utdata. Den enda fil som inte har något UUID-baserat filnamn är filen index.html.

Du kan skapa förinställningen HTML på två sätt:

**Från webbredigeraren:** Öppna DITA-schemafilen i Kartvyn på panelen Databas, välj ikonen + på fliken Utdata för att skapa en förinställning och välj sedan HTML5 i listrutan i dialogrutan Lägg till förinställning.

>[!NOTE]
>
> Du kan välja vilken metod som ska användas för att generera HTML5 med DITA-OT eller FMPS \(om systemadministratören har konfigurerat det\).

I webbredigeraren har konfigurationerna ordnats under flikarna Allmänt och Avancerat:

**Allmänt**

The **Allmänt** -fliken innehåller följande konfigurationer:

- Utdatasökväg
- Kommandoradsargument för DITA-OT
- Filnamn
- Använd villkor med \(Om villkoren är definierade för en karta\)
- Använd baslinje \(Om en baslinje skapas för en karta\)
- Arbetsflöde efter generering

**Avancerat**

Fliken Avancerat innehåller följande konfigurationer:

- Transformeringsnamn
- Rensa tillfälliga DITA-OT-filer
- Egenskaper

Mer information finns i [HTML5-konfiguration](#id231KJA00REJ).

**Från kartpanelen**

Om du vill öppna förinställningar för utdata för PDF klickar du på en DITA-kartfil i användargränssnittet för resurser, klickar på Utdatainställningar och sedan på alternativet HTML 5. Klicka på **Redigera** överst för att uppdatera de olika konfigurationerna och sedan klicka på **Spara**.

**HTML5-konfiguration**

Följande alternativ är tillgängliga för utdata från HTML5:

| HTML5-alternativ | Beskrivning |
| --- | --- |
| Utdatatyp | Den typ av utdata som du vill generera. Om du vill generera utdata för HTML5 väljer du HTML 5. |
| Inställningsnamn | Ange ett beskrivande namn för de utdatainställningar för HTML5 som du skapar. Du kan till exempel ange _Resultat från interna kunder_ eller _slutanvändares utdata_. |
| Kommandoradsargument för DITA-OT | Ange de ytterligare argument som du vill att DITA-OT ska behandla när du genererar utdata. Mer information om de kommandoradsargument som stöds i DITA-OT finns i [DITA-OT-dokumentation](https://www.dita-ot.org/). |
| Generera responsiv med | Välj DITA-OT för att generera utdata från HTML5. |
| Använd villkor med | Välj något av följande alternativ:<br><br>* **Ingen används**: Välj det här alternativet om du inte vill använda något villkor i publicerade utdata.<br>* **DITAVal-fil**: Välj DITAVal-filer för att generera anpassat innehåll. Du kan markera flera DITAVal-filer i dialogrutan Bläddra eller genom att skriva filsökvägen. Använd kryssikonen bredvid filnamnet för att ta bort den. DITAVal-filer utvärderas i den ordning som anges, så de villkor som anges i den första filen har företräde framför de matchande villkor som anges i senare filer. Du kan behålla filordningen genom att lägga till eller ta bort filer. Om DITAVal-filen flyttas till en annan plats eller tas bort, tas den inte automatiskt bort från kartkontrollpanelen. Du måste uppdatera platsen om filerna flyttas eller tas bort. Du kan hovra över filnamnet för att se sökvägen i AEM databas där filen lagras. Du kan bara välja DITAVal-filer och ett fel visas om du har valt någon annan filtyp. FrameMakra Publishing Servern stöder inte flera DITAVAL-filer.<br>* **Förinställning för villkor**: Välj en villkorsförinställning i listrutan om du vill använda ett villkor när du publicerar utdata. Alternativet är synligt om du har lagt till ett villkor på fliken Villkorsförinställningar i DITA-kartkonsolen. Mer information om förinställda villkor finns i [Använda förinställningar för villkor](generate-output-use-condition-presets.md#id1825FL004PN).<br><br>Du kan markera flera DITAVAL-filer i dialogrutan Bläddra eller genom att skriva filsökvägen. Använd kryssikonen bredvid filnamnet för att ta bort den. DITAVAL-filer utvärderas i den ordning som anges, så de villkor som anges i den första filen har företräde framför de matchningsvillkor som anges i senare filer. Du kan behålla filordningen genom att lägga till eller ta bort filer. Du måste uppdatera platsen om filerna flyttas eller tas bort. Du kan hovra över filnamnet för att se sökvägen i AEM databas där filen lagras. Du kan bara spara DITAVAL-filer. Ett fel visas om du har valt en annan fil.<br><br>**Anteckning**: FrameMakra Publishing Servern stöder inte flera DITAVAL-filer. |
| Transformeringsnamn | Ange vilken typ av utdata du vill generera. Detta är nödvändigt om du vill generera utdata med ett eget anpassat plugin-program, som är integrerat i DITA-OT-plugin-programmet. Om du till exempel vill generera XHTML-utdata anger du `xhtml`. En lista över omformningar i DITA-OT finns på [DITA-OT-omformningar (utdataformat)](http://www.dita-ot.org/2.3/user-guide/AvailableTransforms.html) i OASIS DITA-OT User Guide. |
| Filnamn | Ange det filnamn som du vill spara HTML5-utdata med.<br><br>**Anteckning**:Om du inte anger något filnamn används DITA-kartans titel för att generera det slutliga HTML5-utdatafilnamnet. Om kartan inte har någon titel används DITA-kartans filnamn för att namnge det slutliga HTML5-resultatet. Filnamnet sanaliseras med de regler som konfigurerats i systemet för att hantera ogiltiga tecken. |
| Kör arbetsflöde efter generering | När du väljer det här alternativet visas en ny arbetsflödeslista som innehåller alla arbetsflöden som är konfigurerade i AEM. Du måste välja ett arbetsflöde som du vill köra när arbetsflödet för generering av utdata har slutförts.<br><br>**Anteckning**:Mer information om hur du skapar ett anpassat arbetsflöde för efterhandsgenerering finns i _Anpassa arbetsflödet för efterhandsproduktion_ i Installera och konfigurera Adobe Experience Manager Guides as a Cloud Service. |
| Målsökväg | Den sökväg i AEM där HTML5-utdata lagras. |
| Rensa tillfälliga DITA-OT-filer | Välj det här alternativet om du vill rensa de temporära filer som genererats av DITA-OT. Platsen där tillfälliga filer lagras i DITA-OT finns i loggen för generering av utdata.<br><br>Om du får problem när du genererar utdata via DITA-OT kan du avmarkera det här alternativet om du vill behålla de tillfälliga filerna. Du kan sedan använda dessa filer för att felsöka fel vid generering av utdata. |
| Använd baslinje | Om du har skapat en baslinje för den valda DITA-kartan väljer du det här alternativet för att ange vilken version du vill publicera.<br><br>Se [Arbeta med baslinje](generate-output-use-baseline-for-publishing.md#id1825FI0J0PF) för mer information. |
| Egenskaper | Välj de egenskaper som du vill bearbeta som metadata. Dessa egenskaper ställs in från sidan Egenskaper i DITA-kartan eller bokmappningsfilen. Egenskaperna som du väljer i listrutan visas under fältet Egenskaper och tas bort från listrutan. När de har angetts kopieras även dessa egenskaper till avsnitten på kartan.<br><br>**Anteckning**: Du kan också skicka metadata till utdata med DITA-OT-publicering. Mer information finns i [Skicka metadata till utdata med DITA-OT](pass-metadata-dita-ot.md#id21BJ00QD0XA). |

**Överordnat ämne:**[ Förinställningar för utdata](generate-output-understand-presets.md)
