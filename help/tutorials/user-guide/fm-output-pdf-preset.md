---
title: PDF
description: Generera och konfigurera PDF för FrameMaker-dokument i AEM.
exl-id: ece004ed-5233-460b-889d-94e693ceed93
source-git-commit: 8504a0a52d381044bf1f0d6e7de3585ebecf3a7b
workflow-type: tm+mt
source-wordcount: '381'
ht-degree: 0%

---

# PDF {#id205BB0T20RH}

Följande alternativ är tillgängliga för utdata från PDF:

>[!NOTE]
>
> Om du vill öppna förinställningar för PDF klickar du på en FrameMaker \(`.fm` eller `.book`\), klicka sedan på Utdataförinställningar och klicka på PDF.

| Alternativ för PDF | Beskrivning |
|-----------|-----------|
| Utdatatyp | Den typ av utdata som du vill generera. Om du vill generera utdata för PDF väljer du alternativet PDF. |
| Inställningsnamn | Ge PDF ett beskrivande namn på de utdatainställningar du skapar. Du kan till exempel ange *Resultat från interna kunder* eller *slutanvändares utdata*. |
| **Jobbinställningar** |
| Alternativ | Välj den förinställning för PDF som du vill använda för att generera utdata från PDF. |
| Generera taggad PDF | Välj det här alternativet om du vill generera taggad PDF som innehåller information om dokumentets innehåll och struktur. Den här informationen används av skärmläsare. |
| Generera PDF för varje fil i boken | Om du genererar utdata för en bokfil väljer du det här alternativet för att generera ett separat PDF för varje fil i boken. |
| Generera endast PDF för granskning | Välj det här alternativet om du vill generera PDF med kommentarsfunktionen aktiverad. |
| Skapa namngivet mål för alla element och stycken | Välj det här alternativet om du vill skapa namngivna mål baserat på element och stycken. |
| **Visningsinställningar** |
| Öppna dokument på sidan | Ange vilket sidnummer som ska visas när PDF öppnas. |
| Inledande zoomnivå | Välj dokumentets zoomnivå. |
| Registreringsmärke | Om du vill skriva ut ett dokument med skärmärken och passmärken väljer du ett alternativ i listrutan Registreringsmärken. |
| Sidbredd och sidhöjd | Ange sidans bredd och höjd. |
| Sidintervall | Välj om du vill publicera alla sidor i boken eller ett sidintervall. Om du väljer Intervall måste du ange sidintervallet Från och Till. |
| Konvertera CYMK till RGB | Välj det här alternativet om du vill konvertera CMYK-färger till RGB i det genererade PDF. |
| Generera bokmärken i PDF | Skapa tillgänglig PDF som innehåller bokmärken. |
| Målsökväg | Den sökväg i AEM där utdata från PDF lagras. |
| Kör arbetsflöde efter generering | När du väljer det här alternativet visas en ny arbetsflödeslista som innehåller alla arbetsflöden som är konfigurerade i AEM. Du måste välja ett arbetsflöde som du vill köra när arbetsflödet för generering av utdata har slutförts. |

**Överordnat ämne:**[ Generera utdata av FrameMaker dokument](fm-output-generatation.md)
