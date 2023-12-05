---
title: JSON
description: Lär dig hur du skapar JSON-förinställningar från webbredigeraren och kartkontrollpanelen. Konfigurera förinställningen för JSON-utdata i AEM.
source-git-commit: 880cd344ceb65ea339be699ebcad41c0d62e168a
workflow-type: tm+mt
source-wordcount: '676'
ht-degree: 0%

---

# JSON {#id231KK0180T4}

Du kan skapa JSON-förinställningen från Web Editor:

Öppna DITA-schemafilen i Kartvyn på panelen Databas, välj ikonen + på fliken Utdata för att skapa en förinställning och välj sedan JSON i listrutan typ i dialogrutan Lägg till förinställning.

I webbredigeraren har följande konfigurationer ordnats under **Allmänt** tab:

- Utdatasökväg
- Indexfil
- Använd villkor med \(Om villkoren är definierade för en karta\)
- Använd baslinje \(Om en baslinje skapas för en karta\)
- Egenskaper att sprida i utdata
- Arbetsflöde efter generering

Mer information finns i [JSON-konfiguration](#id231KJA00REJ).

**Från kartpanelen**

Om du vill öppna förinställningar för utdata för PDF klickar du på en DITA-kartfil i användargränssnittet för resurser, klickar på Utdatainställningar och sedan på alternativet HTML 5. Klicka på **Redigera** överst för att uppdatera de olika konfigurationerna och sedan klicka på **Spara**.

**JSON-konfiguration**

Följande alternativ är tillgängliga för JSON-förinställningen:

>[!NOTE]
>
> Du kan också redigera JSON-filen i Web Editor.

| JSON-alternativ | Beskrivning |
| --- | --- |
| Utdatasökväg | Den sökväg i AEM där JSON-utdata lagras. |
| Indexfil | Du kan ge indexfilen ett namn som du skapar för JSON-utdata. Som standard väljs filnamnet på DITA-kartan och ett suffix läggs till (som `map_filename_index.json`).<br><br>Du kan också använda variabler när du ställer in indexfilen. Mer information om hur du använder variabler finns i [Använd variabler för att ange alternativen Målsökväg, Platsnamn eller Filnamn](generate-output-use-variables.md#id18BUG70K05Z). |
| Använd villkor med | Välj något av följande alternativ:<br><br>* **Ingen används**: Välj det här alternativet om du inte vill använda något villkor i publicerade utdata.<br>* **DITAVAL**: Välj DITAVAL-fil(er) för att generera anpassat innehåll. Du kan markera flera DITAVAL-filer i dialogrutan Bläddra eller genom att skriva filsökvägen. Använd kryssikonen bredvid filnamnet för att ta bort den. DITAVAL-filer utvärderas i den ordning som anges, så de villkor som anges i den första filen har företräde framför de matchningsvillkor som anges i senare filer. Du kan behålla filordningen genom att lägga till eller ta bort filer. Om DITAVAL-filen flyttas till en annan plats eller tas bort, tas den inte automatiskt bort från kartkontrollpanelen. Du måste uppdatera platsen om filerna flyttas eller tas bort. Du kan hovra över filnamnet för att se sökvägen i AEM databas där filen lagras. Du kan bara välja DITAVAL-filer och ett fel visas om du har valt någon annan filtyp.<br>* **Förinställning för villkor**: Välj en villkorsförinställning i listrutan om du vill använda ett villkor när du publicerar utdata. Alternativet är synligt om du har lagt till ett villkor på fliken Villkorsförinställningar i DITA-kartkonsolen. Mer information om förinställda villkor finns i [Använda förinställningar för villkor](generate-output-use-condition-presets.md#id1825FL004PN). |
| Använd baslinje | Om du har skapat en baslinje för den valda DITA-kartan väljer du det här alternativet för att ange vilken version du vill publicera.<br><br>Se [Arbeta med baslinje](generate-output-use-baseline-for-publishing.md#id1825FI0J0PF) för mer information. |
| Egenskaper att sprida i utdata | Välj de egenskaper som du vill bearbeta som metadata. Dessa egenskaper ställs in från sidan Egenskaper i DITA-kartan eller bokmappningsfilen. Egenskaperna som du väljer i listrutan visas under fältet Egenskaper.<br><br>**Anteckning**: Du kan också definiera egna egenskaper och skicka metadata till utdata med DITA-OT-publicering. Mer information finns i [Arbeta med metadata](metadata-dita.md#id21BJ00QD0XA). |
| Arbetsflöde efter generering | När du väljer det här alternativet visas en ny arbetsflödeslista som innehåller alla arbetsflöden som är konfigurerade i AEM. Du måste välja ett arbetsflöde som du vill köra när arbetsflödet för generering av utdata har slutförts.<br><br>**Anteckning**: Mer information om hur du skapar ett anpassat arbetsflöde för efterhandsgenerering finns i _Anpassa arbetsflödet för efterhandsproduktion_ i den as a Cloud Service guiden Installera och konfigurera Adobe Experience Manager Guides. |

**Överordnat ämne:**[ Förinställningar för utdata](generate-output-understand-presets.md)
