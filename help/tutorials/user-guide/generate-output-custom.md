---
title: Egen
description: Lär dig hur du använder anpassade förinställningar för utdata
source-git-commit: 8b6294425c6e60d1c5b37d98e99114014a104ee6
workflow-type: tm+mt
source-wordcount: '935'
ht-degree: 0%

---


# Egen {#id205BEF00PX0}

Förinställningarna för anpassade utdata är tillgängliga för anpassade DITA-OT-plugin-program. Du kan skapa en anpassad DITA-OT-utdataförinställning för publicering av utdata med ditt anpassade DITA-OT-plugin-program.

Du kan skapa den anpassade förinställningen på två sätt:

**Från webbredigeraren:** Öppna DITA-schemafilen i Kartvyn på panelen Databas, välj ikonen + på fliken Utdata för att skapa en förinställning och välj sedan Anpassad i listrutan Typ i dialogrutan Lägg till förinställning.

I webbredigeraren har konfigurationerna ordnats under flikarna Allmänt och Avancerat:

**Allmänt**

The **Allmänt** -fliken innehåller följande konfigurationer:

- Kommandoradsargument för DITA-OT
- Transformeringsnamn
- Filnamn
- Utdatasökväg
- Använd villkor med \(Om villkoren är definierade för en karta\)
- Använd baslinje \(Om en baslinje skapas för en karta\)
- Arbetsflöde efter generering

**Avancerat**

Fliken Avancerat innehåller följande konfigurationer:

- Rensa tillfälliga DITA-OT-filer
- Egenskaper

Mer information finns i [Anpassad konfiguration](#id231KJA00REJ).

**Från kartpanelen**

Om du vill öppna förinställningar för utdata för PDF klickar du på en DITA-kartfil i användargränssnittet för resurser, klickar på Utdatainställningar och sedan på alternativet HTML 5. Klicka på **Redigera** överst för att uppdatera de olika konfigurationerna och sedan klicka på **Spara**.

**Anpassad konfiguration**

Följande alternativ är tillgängliga för förinställningen Egna utdata:

| Anpassade utdataalternativ | Beskrivning |
| --- | --- |
| Utdatatyp | Den typ av utdata som du vill generera. Om du vill generera utdata med ett anpassat DITA-OT-plugin-program väljer du alternativet Egen. |
| Inställningsnamn | Ge utdatainställningarna ett beskrivande namn. Du kan till exempel ange _Resultat från interna kunder_ eller _slutanvändares utdata_. |
| Kommandoradsargument för DITA-OT | Ange de ytterligare argument som du vill att DITA-OT ska behandla när du genererar utdata. Mer information om de kommandoradsargument som stöds i DITA-OT finns i [DITA-OT-dokumentation](https://www.dita-ot.org/). |
| Transformeringsnamn | Ange vilken typ av utdata du vill generera. Detta är nödvändigt om du vill generera utdata med ett eget anpassat plugin-program, som är integrerat i DITA-OT-plugin-programmet. Om du till exempel vill generera XHTML-utdata anger du `xhtml`. En lista över omformningar i DITA-OT finns på [DITA-OT-omformningar (utdataformat)](http://www.dita-ot.org/2.3/user-guide/AvailableTransforms.html) i OASIS DITA-OT User Guide. |
| Filnamn | Ange det filnamn som du vill spara utdata med.<br><br>**Anteckning**: Om du inte anger något filnamn används DITA-kartans titel för att generera det slutliga utdatafilnamnet. Om kartan inte har någon titel används DITA-kartans filnamn för att namnge det slutliga resultatet. Filnamnet sanaliseras med de regler som konfigurerats i systemet för att hantera ogiltiga tecken. |
| Använd villkor med | Välj något av följande alternativ:<br><br>* **Ingen används**: Välj det här alternativet om du inte vill använda något villkor i publicerade utdata.<br>* **DITAVal-fil**: Välj DITAVal-filer för att generera anpassat innehåll. Du kan markera flera DITAVal-filer i dialogrutan Bläddra eller genom att skriva filsökvägen. Använd kryssikonen bredvid filnamnet för att ta bort den. DITAVal-filer utvärderas i den ordning som anges, så de villkor som anges i den första filen har företräde framför de matchande villkor som anges i senare filer. Du kan behålla filordningen genom att lägga till eller ta bort filer. Om DITAVal-filen flyttas till en annan plats eller tas bort, tas den inte automatiskt bort från kartkontrollpanelen. Du måste uppdatera platsen om filerna flyttas eller tas bort. Du kan hovra över filnamnet för att se sökvägen i AEM databas där filen lagras. Du kan bara välja DITAVal-filer och ett fel visas om du har valt någon annan filtyp.<br>* **Förinställning för villkor**: Välj en villkorsförinställning i listrutan om du vill använda ett villkor när du publicerar utdata. Alternativet är synligt om du har lagt till ett villkor på fliken Villkorsförinställningar i DITA-kartkonsolen. Mer information om förinställda villkor finns i [Använda förinställningar för villkor](generate-output-use-condition-presets.md#id1825FL004PN). |
| Målsökväg | Den sökväg i AEM där EPUB-utdata lagras. |
| Rensa tillfälliga DITA-OT-filer | Välj det här alternativet om du vill rensa de temporära filer som genererats av DITA-OT. Platsen där tillfälliga filer lagras i DITA-OT finns i loggen för generering av utdata.<br><br>Om du får problem när du genererar utdata via DITA-OT kan du avmarkera det här alternativet om du vill behålla de tillfälliga filerna. Du kan sedan använda dessa filer för att felsöka fel vid generering av utdata. |
| Kör arbetsflöde efter generering | När du väljer det här alternativet visas en ny arbetsflödeslista som innehåller alla arbetsflöden som är konfigurerade i AEM. Du måste välja ett arbetsflöde som du vill köra när arbetsflödet för generering av utdata har slutförts.<br><br>**Anteckning**: Mer information om hur du skapar ett anpassat arbetsflöde för efterhandsgenerering finns i _Anpassa arbetsflödet för efterhandsproduktion_ i Installera och konfigurera Adobe Experience Manager Guides as a Cloud Service. |
| Använd baslinje | Om du har skapat en baslinje för den valda DITA-kartan väljer du det här alternativet för att ange vilken version du vill publicera.<br><br>Se [Arbeta med baslinje](generate-output-use-baseline-for-publishing.md#id1825FI0J0PF) för mer information. |
| Egenskaper | Välj de egenskaper som du vill bearbeta som metadata. Dessa egenskaper ställs in från sidan Egenskaper i DITA-kartan eller bokmappningsfilen. Egenskaperna som du väljer i listrutan visas under fältet Egenskaper och tas bort från listrutan. När de har angetts kopieras även dessa egenskaper till avsnitten på kartan.<br><br>**Anteckning**: Du kan också skicka metadata till utdata med DITA-OT-publicering. Mer information finns i [Skicka metadata till utdata med DITA-OT](pass-metadata-dita-ot.md#id21BJ00QD0XA). |

**Överordnat ämne:**[ Förinställningar för utdata](generate-output-understand-presets.md)

