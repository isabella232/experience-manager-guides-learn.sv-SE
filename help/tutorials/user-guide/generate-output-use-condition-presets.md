---
title: Använda förinställningar för villkor
description: Lär dig hur du använder förinställda villkor i AEM. Lär dig att skapa, redigera, kopiera och ta bort förinställningar för villkor i AEM.
exl-id: f6865a34-abdd-4d23-b903-0211bebd13b7
source-git-commit: e8a912b0f8bc690fceade0b54bb36057a727ab33
workflow-type: tm+mt
source-wordcount: '1202'
ht-degree: 0%

---

# Använda förinställningar för villkor {#id1825FL004PN}

Du kan definiera attribut i dina DITA-avsnitt och använda villkorsförinställningen för att ange vad som ska hända med attributet i det slutliga resultatet. Du kan till exempel lägga till attribut som version 1.0 och version 2.0 i ditt innehåll och använda en villkorsförinställning för att inkludera version 1.0 för version 1.0 och exkludera version 2.0. På samma sätt kan du lägga till attribut som OS Windows och OS Linux i ditt innehåll och sedan inkludera eller exkludera det relevanta innehållet för dina slutliga utdata enligt operativsystemet.

Du kan skapa villkorsförinställningar på två sätt:

* Från Web Editor: Gör att du kan skapa och hantera villkorsförinställningar för en DITA-karta från Web Editor.
* Från kartkontrollpanelen: Gör att du kan skapa och hantera villkorsförinställningar för en DITA-karta från kartkontrollpanelen.


## Villkorsförinställningar från Web Editor

Med hjälp av stödlinjerna för Experience Manager kan du hantera villkorsförinställningar från Web Editor och använda dem i utdatainställningarna för att generera det slutliga resultatet.
Du kan skapa och visa villkorsförinställningar, visa attribut och hantera åtgärder för den aktuella kartan från **Förinställningar för villkor** i webbredigeraren.

<img src="images//manage-condtions-presets.png" alt= "Förinställningar för villkor i webbredigeraren" width="800" border="1px">



### Skapa en villkorsförinställning

The **Förinställningar för villkor** I finns detaljerad information om förinställningarna, t.ex. attribut, värden och åtgärder.
Du kan skapa en villkorsförinställning av ämnena genom att utföra följande steg:

1. I **Databas** öppnar du DITA-schemafilen i Kartvyn.
1. Välj **Hantera** -fliken.
1. Välj **Förinställningar för villkor** till vänster. Listan med villkorsförinställningar som definierats för DITA-kartan visas.
1. Markera +-ikonen bredvid **Förinställningar för villkor** för att öppna **Ny villkorsförinställning** -dialogrutan.
1. Ange ett unikt namn för förinställningen.

   >[!NOTE]
   >
   > Du kan visa ett fel om namnfältet är tomt eller om du anger ett ogiltigt tecken eller ett namn som är detsamma som en befintlig villkorsförinställning. Du kan använda bindestreck &#39;-&#39; eller understreck &#39;_&#39; som avgränsare.

1. Välj **Skapa**.
Den nya villkorsförinställningen läggs till i listan.
1. Dubbelklicka på en villkorsförinställning för att visa attributen och åtgärderna.
The **Attribut** På panelen visas alla attribut som lagts till i alla referenser som finns på kartan. På den högra panelen visas endast de villkor som du har lagt till i villkorsförinställningarna.
1. Gör något av följande för att lägga till attributen:
   * Markera ett eller flera attribut om du vill lägga till alla värden under dem i villkorsförinställningen. Du kan t.ex. välja `platform` för att lägga till alla dess värden.
   * Markera ett eller flera attributvärden som du vill lägga till i villkorsförinställningen. Du kan t.ex. välja `Unix` och `Win` värden för plattformsattributet
   * Markera ett attribut- och värdepar och dra det till mittpanelen. Du kan t.ex. välja `Unix` värdet för plattformsattributet och dra det.
   * **Markera alla** om du vill lägga till alla attribut och deras värden i villkorsförinställningen.
Som standard är åtgärden för ett attribut `Include`.

1. Välj **Lägg till**. Du kan upprepa det här steget om du vill lägga till fler attribut. De attribut du lägger till flyttas från den centrala till den högra panelen.
1. Välj Ta bort i åtgärdsfältet högst upp om du vill ta bort de markerade attributen på den högra panelen.
1. (Valfritt) Om det behövs kan du åsidosätta den åtgärd som har tillämpats på attributen.
Gör något av följande:
   * För alla attribut väljer du en av följande åtgärder i listrutan Åtgärd.
      * Inkludera
      * Exkludera
      * Genomströmning
      * Flagga
   * Markera flera attributrader på den högra panelen och välj en åtgärd i åtgärdsfältet högst upp. Du kan till exempel välja åtgärden Uteslut för de markerade attributen.
1. Välj **Spara** för att spara villkorsförinställningen.

   >[!NOTE]
   >
   > Du kan visa en varning om du väljer en annan förinställning eller stänger förinställningen utan att spara den.

När du har skapat en villkorsförinställning visas den under **Förinställningar för villkor** listrutan för utdataförinställningar. Läs mer om hur [Publish PDF output](../web-editor/native-pdf-web-editor.md).

### Byta namn på en villkorsförinställning

Så här byter du namn på en villkorsförinställning:

1. Håll pekaren över en villkorsförinställning från **Förinställningar för villkor** -panelen.
1. Välj **Byt namn** på Alternativ-menyn för att öppna **Byt namn på villkorsförinställning** -dialogrutan.
1. Redigera namnet på villkorsförinställningen.
1. Klicka **Byt namn**.

### Duplicera en villkorsförinställning

Så här duplicerar du en villkorsförinställning:

1. Håll pekaren över en villkorsförinställning från **Förinställningar för villkor** -panelen.
1. Välj **Duplicera** på Alternativ-menyn för att öppna **Duplicera förinställning för villkor** -dialogrutan.
   >[!NOTE]
   >
   > Förinställningens standardnamn är `<selected condition preset name>_1`. Du kan ändra namnet enligt dina önskemål.

1. Klicka **Duplicera**.

### Ta bort förinställning för villkor

Så här tar du bort villkorsförinställningar:

1. Håll pekaren över en villkorsförinställning från **Förinställningar för villkor** -panelen.
1. Välj **Ta bort** på Alternativ-menyn för att öppna **Ta bort förinställning för villkor** -dialogrutan.
1. Klicka **Ta bort**.



## Förinställningar för villkor från kartkontrollpanelen


### Skapa en villkorsförinställning

Så här skapar du en villkorsförinställning:

1. Välj **Förinställningar för villkor** i DITA-mappningskonsolen.
1. Klicka **Skapa** -knappen.
1. Ange ett namn för förinställningen i **Namnvillkor**.
1. Välj någon av följande standardåtgärder från **Ange standardåtgärd till** nedrullningsbar lista:

   * Inkludera
   * Exkludera
   * Genomströmning
   * Flagga Åtgärden anges som standardåtgärd för alla attribut oavsett om de läggs till i villkorsförinställningen eller inte.

   Du har till exempel 15 villkorsattribut i dokumentet och du har tagit med fyra av dem i villkorsförinställningen. Om du väljer **exclude** som standardåtgärd tillämpas den på alla 15 attribut.

1. Gör något av följande för att lägga till attributen:
   * Klicka **Lägg till** till ett attribut till villkorsförinställningen. Du kan upprepa det här steget om du vill lägga till fler attribut.
   * Klicka **Lägg till alla** om du vill lägga till alla attribut i villkorsförinställningen.
1. \(Valfritt\) Om det behövs kan du åsidosätta den standardåtgärd som tillämpats på attributen i steg 4. Gör något av följande:
   * Markera flera attribut, välj en åtgärd från **Ställ in åtgärden för valda villkor på** och klicka **Använd**.
   * Välj en åtgärd för ett attribut på menyn **Åtgärd** nedrullningsbar meny.
1. Klicka **Spara**.

### Redigera en villkorsförinställning

Du kan ändra en befintlig villkorsförinställning om du vill ändra de åtgärder som har tillämpats på attributen i villkorsförinställningen. Så här redigerar du en villkorsförinställning:

1. Välj **Förinställningar för villkor** i DITA-mappningskonsolen.
1. Klicka **Redigera** -knappen.
1. Gör nödvändiga ändringar för alla attribut i villkorsförinställningen.
1. Klicka **Spara**.

### Skapa en kopia av en villkorsförinställning

Du kan skapa en kopia av en villkorsförinställning och sedan ändra den efter behov. Så här skapar du en kopia av en villkorsförinställning:

1. Välj **Förinställningar för villkor** i DITA-mappningskonsolen.
1. Klicka **Duplicera** -knappen.

   >[!NOTE]
   >
   > Förinställningens standardnamn är `<selected condition preset name>_Duplicate`

   Du kan ändra namnet efter dina önskemål.

1. \(Valfritt\) Gör nödvändiga ändringar för alla attribut i villkorsförinställningen.
1. Klicka **Spara**.

### Ta bort förinställning för villkor

Du kan ta bort en eller flera villkorsförinställningar från **Förinställning för villkor** -fliken i DITA-kartkonsolen. Så här tar du bort villkorsförinställningar:

1. Välj **Förinställningar för villkor** i DITA-mappningskonsolen.
1. Markera den eller de villkorsförinställningar som du vill ta bort.
1. Klicka **Ta bort** -knappen.
1. Klicka **Ta bort** för att bekräfta åtgärden.

**Överordnat ämne:**[ Generering av utdata](generate-output.md)
