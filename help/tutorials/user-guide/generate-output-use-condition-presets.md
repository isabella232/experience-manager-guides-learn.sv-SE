---
title: Använda förinställningar för villkor
description: Lär dig hur du använder villkorsförinställningar
exl-id: cd8f8196-ba03-4a4b-9ce8-2651de4e5cc2
source-git-commit: 8073716bccacbe8d6a158b44d5106b083e3a5dcd
workflow-type: tm+mt
source-wordcount: '485'
ht-degree: 0%

---

# Använda förinställningar för villkor {#id1825FL004PN}

Du kan definiera attribut i dina DITA-avsnitt och använda villkorsförinställningen för att ange vad som ska hända med attributet i det slutliga resultatet. Du kan till exempel lägga till attribut som version 1.0 och version 2.0 i ditt innehåll och använda en villkorsförinställning för att inkludera version 1.0 för version 1.0 och exkludera version 2.0. På samma sätt kan du lägga till attribut som OS Windows och OS Linux i ditt innehåll och sedan inkludera eller exkludera det relevanta innehållet för dina slutliga utdata enligt operativsystemet.

## Skapa en villkorsförinställning

Så här skapar du en villkorsförinställning:

1. Klicka **Förinställningar för villkor** i DITA-mappningskonsolen.
1. Klicka **Skapa** -knappen.
1. Ange ett namn för förinställningen i **Namnvillkor**.
1. Välj någon av följande standardåtgärder från **Ange standardåtgärd till** nedrullningsbar meny:

   - Inkludera
   - Exkludera
   - Genomströmning
   - Flagga Åtgärden anges som standardåtgärd för alla attribut oavsett om de läggs till i villkorsförinställningen eller inte.

   Du har till exempel 15 villkorsattribut i dokumentet och du har tagit med fyra av dem i villkorsförinställningen. Om du väljer **exclude** som standardåtgärd tillämpas den på alla 15 attribut.

1. Gör något av följande för att lägga till attributen:
   - Klicka **Lägg till** till ett attribut till villkorsförinställningen. Du kan upprepa det här steget om du vill lägga till fler attribut.
   - Klicka **Lägg till alla** om du vill lägga till alla attribut i villkorsförinställningen.
1. \(Valfritt\) Om det behövs kan du åsidosätta den standardåtgärd som tillämpats på attributen i steg 4. Gör något av följande:
   - Markera flera attribut, välj en åtgärd från **Ställ in åtgärden för valda villkor på** och klicka **Använd**.
   - Välj en åtgärd för ett attribut på menyn **Åtgärd** nedrullningsbar meny.
1. Klicka **Spara**.

## Redigera en villkorsförinställning

Du kan ändra en befintlig villkorsförinställning om du vill ändra de åtgärder som har tillämpats på attributen i villkorsförinställningen. Så här redigerar du en villkorsförinställning:

1. Klicka **Förinställningar för villkor** i DITA-mappningskonsolen.
1. Klicka **Redigera** -knappen.
1. Gör nödvändiga ändringar för alla attribut i villkorsförinställningen.
1. Klicka **Spara**.

## Skapa en kopia av en villkorsförinställning

Du kan skapa en kopia av en villkorsförinställning och sedan ändra den efter behov. Så här skapar du en kopia av en villkorsförinställning:

1. Klicka **Förinställningar för villkor** i DITA-mappningskonsolen.
1. Klicka **Duplicera** -knappen.

   >[!NOTE]
   >
   > Förinställningens standardnamn är `<selected condition preset name>_Duplicate`

   Du kan ändra namnet efter dina önskemål.

1. \(Valfritt\) Gör nödvändiga ändringar för alla attribut i villkorsförinställningen.
1. Klicka **Spara**.

## Ta bort förinställning för villkor

Du kan ta bort en eller flera villkorsförinställningar från **Förinställning för villkor** -fliken i DITA-kartkonsolen. Så här tar du bort villkorsförinställningar:

1. Klicka **Förinställningar för villkor** i DITA-mappningskonsolen.
1. Markera den eller de villkorsförinställningar som du vill ta bort.
1. Klicka **Ta bort** -knappen.
1. Klicka **Ta bort** för att bekräfta åtgärden.

**Överordnat ämne:**[ Generering av utdata](generate-output.md)
