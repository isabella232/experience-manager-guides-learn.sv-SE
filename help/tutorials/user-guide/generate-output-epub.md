---
title: EPUB-förinställning
description: Lär dig hur du skapar en förinställning för EPUB från kartpanelen. Konfigurera förinställningen för EPUB-utdata i AEM.
exl-id: 19425ed2-fd7e-49c2-8f84-fc559a1db81b
source-git-commit: 8504a0a52d381044bf1f0d6e7de3585ebecf3a7b
workflow-type: tm+mt
source-wordcount: '814'
ht-degree: 0%

---

# EPUB {#id205BED020YT}

Du kan skapa förinställningen EPUB från kartkontrollpanelen.

>[!NOTE]
>
> Du kan välja vilken metod som ska användas för att generera HTML5 med DITA-OT eller FMPS \(om systemadministratören har konfigurerat det\).

Om du vill öppna förinställningar för EPUB klickar du på en DITA-kartfil, sedan på Utdatainställningar och sedan på alternativet EPUB. Följande alternativ är tillgängliga för EPUB Output:

| Alternativ för ePub | Beskrivning |
| --- | --- |
| Utdatatyp | Den typ av utdata som du vill generera. Om du vill generera utdata för EPUB väljer du alternativet EPUB. |
| Inställningsnamn | Ge EPUBEN ett beskrivande namn för de utdatainställningar du skapar. Du kan till exempel ange _Resultat från interna kunder_ eller _slutanvändares utdata_. |
| Kommandoradsargument för DITA-OT | Ange de ytterligare argument som du vill att DITA-OT ska behandla när du genererar utdata. Mer information om de kommandoradsargument som stöds i DITA-OT finns i [DITA-OT-dokumentation](https://www.dita-ot.org/). |
| Generera EPUB med | Välj DITA-OT för att generera EPUBEN. |
| Använd villkor med | Välj något av följande alternativ:<br><br>* **Ingen används**: Välj det här alternativet om du inte vill använda något villkor i publicerade utdata.<br>* **DITAVal-fil**: Välj DITAVal-filer för att generera anpassat innehåll. Du kan markera flera DITAVal-filer i dialogrutan Bläddra eller genom att skriva filsökvägen. Använd kryssikonen bredvid filnamnet för att ta bort den. DITAVal-filer utvärderas i den ordning som anges, så de villkor som anges i den första filen har företräde framför de matchande villkor som anges i senare filer. Du kan behålla filordningen genom att lägga till eller ta bort filer. Om DITAVal-filen flyttas till en annan plats eller tas bort, tas den inte automatiskt bort från kartkontrollpanelen. Du måste uppdatera platsen om filerna flyttas eller tas bort. Du kan hovra över filnamnet för att se sökvägen i AEM databas där filen lagras. Du kan bara välja DITAVal-filer och ett fel visas om du har valt någon annan filtyp. FrameMakra Publishing Servern stöder inte flera DITAVAL-filer.<br>* **Förinställning för villkor**: Välj en villkorsförinställning i listrutan om du vill använda ett villkor när du publicerar utdata. Alternativet är synligt om du har lagt till ett villkor på fliken Villkorsförinställningar i DITA-kartkonsolen. Mer information om förinställda villkor finns i [Använda förinställningar för villkor](generate-output-use-condition-presets.md#id1825FL004PN). |
| Målsökväg | Den sökväg i AEM där EPUB-utdata lagras. |
| Filnamn | Ange det filnamn som du vill spara EPUBEN med.<br><br>**Anteckning**: Om du inte anger något filnamn används DITA-kartans titel för att generera det slutliga EPUBENS utdatafilnamn. Om kartan inte har någon titel används DITA-kartans filnamn som namn på den slutliga EPUBEN. Filnamnet sanaliseras med de regler som konfigurerats i systemet för att hantera ogiltiga tecken. |
| Transformeringsnamn | Ange vilken typ av utdata du vill generera. Detta är nödvändigt om du vill generera utdata med ett eget anpassat plugin-program, som är integrerat i DITA-OT-plugin-programmet. Om du till exempel vill generera XHTML-utdata anger du `xhtml`. En lista över omformningar i DITA-OT finns på [DITA-OT-omformningar (utdataformat)](http://www.dita-ot.org/2.3/user-guide/AvailableTransforms.md) i OASIS DITA-OT User Guide. |
| Rensa tillfälliga DITA-OT-filer | Välj det här alternativet om du vill rensa de temporära filer som genererats av DITA-OT. Platsen där tillfälliga filer lagras i DITA-OT finns i loggen för generering av utdata.<br><br>Om du får problem när du genererar utdata via DITA-OT kan du avmarkera det här alternativet om du vill behålla de tillfälliga filerna. Du kan sedan använda dessa filer för att felsöka fel vid generering av utdata. |
| Kör arbetsflöde efter generering | När du väljer det här alternativet visas en ny arbetsflödeslista som innehåller alla arbetsflöden som är konfigurerade i AEM. Du måste välja ett arbetsflöde som du vill köra när arbetsflödet för generering av utdata har slutförts.<br><br>**Anteckning**: Mer information om hur du skapar ett anpassat arbetsflöde för efterhandsgenerering finns i _Anpassa arbetsflödet för efterhandsproduktion_ i Installera och konfigurera Adobe Experience Manager Guides as a Cloud Service. |
| Använd baslinje | Om du har skapat en baslinje för den valda DITA-kartan väljer du det här alternativet för att ange vilken version du vill publicera.<br><br>Se [Arbeta med baslinje](generate-output-use-baseline-for-publishing.md#id1825FI0J0PF) för mer information. |
| Egenskaper | Välj de egenskaper som du vill bearbeta som metadata. Dessa egenskaper ställs in från sidan Egenskaper i DITA-kartan eller bokmappningsfilen. Egenskaperna som du väljer i listrutan visas under fältet Egenskaper och tas bort från listrutan. När de har angetts kopieras även dessa egenskaper till avsnitten på kartan.<br><br>**Anteckning**: Du kan också skicka metadata till utdata med DITA-OT-publicering. Mer information finns i [Skicka metadata till utdata med DITA-OT](pass-metadata-dita-ot.md#id21BJ00QD0XA). |

**Överordnat ämne:**[ Förinställningar för utdata](generate-output-understand-presets.md)
