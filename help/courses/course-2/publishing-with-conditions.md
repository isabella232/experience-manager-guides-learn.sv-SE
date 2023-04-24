---
title: Publicera med villkor
description: Publicera med villkor med Adobe Experience Manager Guides
exl-id: ea94824a-884b-447f-9562-e6c629b8133b
source-git-commit: 67ba514616a0bf4449aeda035161d1caae0c3f50
workflow-type: tm+mt
source-wordcount: '359'
ht-degree: 0%

---

# Publicera med villkor

Med villkorlig publicering kan en innehållskälla skrivas för en eller flera målgrupper, produkter eller plattformar. Den här informationen kan sedan publiceras dynamiskt och endast det innehåll som krävs i utdata.

>[!VIDEO](https://video.tv.adobe.com/v/339041?quality=12&learn=on)

## Förberedelse för övningen

Du kan hämta exempelfiler för övningen här.

[Översikt - nedladdning](assets/exercises/publishing-with-conditions.zip)

## Markera innehåll med villkorsattribut

1. Öppna det ämne som ska ändras.

1. Ange den text som ska bli villkorlig. Ett eller flera stycken, en hel tabell, en illustration eller annat innehåll.

   ![Presenting-Information](images/presenting-info.png)

1. Markera det specifika innehåll som du vill tilldela ett villkorsattribut till. Ett enstaka stycke i källan.

   ![Template-Choice](images/template-choice.png)

1. I högra rullen ser du till att Egenskaper visas.

1. Lägg till ett attribut för målgrupp, produkt eller plattform.

1. Tilldela ett värde till attributet. Innehållet visas med uppdateringar för att visa villkorlig kod.

   ![Ange mall](images/specify-template.png)

## Förhandsgranska villkorligt innehåll

1. Klicka **Förhandsgranska**.

1. Under **Filter** markerar eller avmarkerar du de villkor som ska visas eller döljas.

1. Markera eller avmarkera **Markera villkorstext**.

   ![Förhandsgranska-villkorligt-innehåll](images/preview-conditional-content.png)

## Skapa en villkorsförinställning

En villkorsförinställning är en samling egenskaper som definierar vad som ska inkluderas, exkluderas, eller på annat sätt markeras, under genereringen av utdata.

1. På kartkontrollpanelen väljer du **Förinställningar för villkor** -fliken.

1. Klicka **Skapa**.

1. Välj **Lägg till** (eller **Lägg till alla**).

1. Ge villkoret ett namn.

1. Välj en kombination av attribut, etikett och åtgärd.

   ![Create-Condition-Preset](images/create-condition-preset.png)

1. Upprepa efter behov.

1. Klicka **Spara**.

## Generera villkorliga utdata

När villkoren har tillämpats på innehållet kan de genereras som utdata. Detta kan antingen använda en villkorsförinställning eller en DITAval-fil.

## Generera villkorliga utdata med en villkorsförinställning

1. Välj **Förinställningar för utdata** -fliken.

1. Välj en förinställning för utdata.

1. Klicka **Redigera**.

1. Under **Använd villkor med** välj en villkorsförinställning.

   ![Generate-Conditional-output](images/generate-conditional-output.png)

1. Klicka **Klar**.

1. Generera förinställningen för utdata och granska innehållet.

## Generera villkorliga utdata med en DITAval-fil

DITAval-filen kan användas för att publicera villkorsstyrt innehåll. Detta kräver att en fil skapas eller överförs och sedan refereras vid publiceringen.

1. Välj **Förinställningar för utdata** -fliken.

1. Välj en förinställning för utdata.

1. Klicka **Redigera**.

1. Välj en DITAval-fil under Använd villkor med.

   ![Generate-Using-DITAval](images/generate-using-ditaval.png)

1. Klicka **Klar**.

1. Generera förinställningen för utdata och granska innehållet.
