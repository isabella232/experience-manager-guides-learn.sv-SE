---
title: Publiceringsfunktion för PDF | Komponenter i en PDF-mall
description: Lär dig de olika komponenterna i en PDF-mall och hur du anpassar och konfigurerar dem.
hide: true
hidefromtoc: true
exl-id: 0ddb3b81-42ca-4a66-be7d-051a5175d53a
source-git-commit: e0602e325fec014fe5a9ebe231b0c62611a4e52d
workflow-type: tm+mt
source-wordcount: '2295'
ht-degree: 0%

---

# Komponenter i en PDF-mall

En PDF-mall har fyra komponenter: Sidlayouter, formatmallar, resurser och inställningar. Du kan skapa en mall genom att anpassa de här enskilda komponenterna och koppla mallen till en förinställning för utdata när du genererar utdata för PDF. I följande avsnitt beskrivs dessa komponenter och deras anpassningsprocess i detalj.


## Skapa och anpassa sidlayouter

Med inställningarna i komponenten Sidlayout kan du utforma strukturen för en sida genom att definiera sidhuvudet, sidfoten och innehållsområdet på en sida. Med layoutredigeraren i WYSIWYG kan du skapa en sidlayout för olika avsnitt i en PDF, t.ex. framsidan och baksidan av omslaget, kapitlet, innehållsförteckningen (TOC), indexet, tom sida, Lista över illustrationer (LOF), Lista över tabeller (LOT), ordlistan eller skapa en layout för en anpassad sida. I mallinställningarna för PDF kan du tilldela en sidlayout med olika avsnitt i PDF, som sedan används för att generera utdata från PDF.

### Skapa en ny sidlayout

> **Anteckning**: Det finns exempelsidlayouter som levereras utanför kartongen. Du kan anpassa dessa eller skapa nya sidlayouter.

1. Gå till webbredigeraren **Utdata** -fliken.
1. Expandera den vänstra sidlisten och klicka på **Mallar**.
1. Öppna mallen som du vill arbeta med.
   > **Anteckning**: Du kan öppna en mall genom att dubbelklicka på dess namn eller klicka på >-ikonen bredvid dess namn.
1. Om du vill skapa en ny sidlayout gör du något av följande:
   * Hovra över **Sidlayouter** och klicka på&#x200B;*Alternativ* ikon) **...** och välja **Ny sidlayout**.
   * I **Mallar** klickar du på **+** ikon bredvid **Mallar** och välja **Sidlayout** på snabbmenyn.

      Dialogrutan Lägg till layout öppnas.

      <img src="assets/add-layout-2.png" alt="Dialogrutan Lägg till layout" width="250">
1. Ange ett namn för den nya sidlayouten.
   > **Obs!** Undvik att använda specialtecken när du namnger en sidlayout. Ett blanksteg i namnet ersätts med understrecket&quot;_&quot;.
1. Klicka **Klar**.

   Den nya layouten skapas och läggs till under Sidlayouter.

### Duplicera en sidlayout

1. I **Mallar** i mallen som du vill duplicera dubbelklickar du på **Sidlayouter** eller klicka på **>** ikon före **Sidlayouter**.

   Då visas en lista med sidlayouter i mallen.

1. Håll pekaren över den sidlayout som du vill duplicera och klicka på (*Alternativ* ikon) **...** och markera **Duplicera** på snabbmenyn.

1. I _Duplicera layout_ anger du ett namn för sidlayouten.

1. Klicka **Klar**.
En kopia av den valda sidlayouten skapas och läggs till under Sidlayouter.

### Anpassa en sidlayout

1. I **Mallar** i mallen som du vill redigera dubbelklickar du på **Sidlayouter** eller klicka på **>** ikon före **Sidlayouter**.

   Då visas en lista med sidlayouter i mallen.
1. Gör något av följande om du vill anpassa en sidlayout:
   * Dubbelklicka på en sidlayout.
   * Håll pekaren över en sidlayout och klicka på (*Alternativ* ikon) **...** och markera **Redigera** på snabbmenyn.

   Då öppnas sidlayoutredigeraren för anpassning.
1. När du har gjort ändringarna klickar du på *Spara alla* (eller `Crl+S`).

   Mer information om hur du definierar enskilda layoutelement som sidhuvud, sidfot, sidnummer, rubrik med mera finns i *Arbeta med sidlayoutselement*.

## Anpassa PDF med formatmallar

Med inställningarna i formatmallskomponenten kan du formatera sidlayoutskomponenterna och DITA-innehållet med WYSIWYG-redigeraren eller arbeta direkt med CSS-filen. Du kan skapa egna format eller anpassa standardformategenskaperna. WYSIWYG-redigeraren ger dig tillgång till de flesta egenskaper som du behöver för att formatera din sidlayout eller DITA-innehåll. För avancerade anpassningar kan du arbeta direkt i källvyn.

### Skapa en ny formatmall

CSS-filer tillhandahålls för innehåll och layout, men du kan skapa en ny formatmall som använder flera anpassningar för en viss formattyp som sedan kan användas för en målkomponent. Som standard paketeras CSS-exempelfiler i produkten. Dessa CSS-filer är avsedda att hjälpa dig att ordna formatinformation för innehåll och layout. Du kan välja att sammanfoga dessa format i en eller flera CSS-filer.

När du skapar en ny sidlayout är standardinställningen `layout.css` filen inkluderas i den nya sidlayouten. Om du vill att sidlayouten ska innehålla format från en annan CSS-fil kan du helt enkelt dra och släppa önskad CSS-fil i den nya sidlayoutens innehållredigeringsområde. Om du vill verifiera om CSS-filen har bäddats in i sidlayouten växlar du till källvyn så att du hittar en länk till CSS-filen i `<head>` -element.


Så här skapar du en formatmall:
1. I **Mallar** gör du något av följande:
   * Hovra över **Formatmallar** och klicka på (*Alternativ* ikon) **...** och välja **Ny formatmall**.
   * Klicka på **+** ikon bredvid **Mallar** och välja **Formatmall** på snabbmenyn.

   Dialogrutan Lägg till formatmall öppnas.

   <img src="assets/add-stylesheet.png" alt="Lägg till formatmall" width="250">
1. Ange ett namn för den nya formatmallen.
1. Klicka **Klar**.

   En ny formatmall skapas och läggs till under formatmallsavsnittet.

### Skapa ett nytt format

Som standard innehåller CSS-filerna format för rubriker, stycken, tecken, hyperlänkar, bilder, tabeller, div, sidor och andra format. Du kan åsidosätta standardformatet eller skapa ett nytt format.

Vanligtvis skapar du ett nytt format när du vill koppla ett anpassat format för ett DITA-element. För att sådana anpassade format ska fungera måste du se till att du kopplar formatets klassnamn till DITA-elementets outputClass-attribut.


Så här skapar du ett nytt format:
1. Högerklicka på ett format och välj Nytt format på snabbmenyn.

   Dialogrutan Lägg till format öppnas.

   <img src="assets/add-style.png" alt="Lägg till nytt format" width="300"/>
1. I **Tagg** väljer du ett märkord som du vill skapa ett nytt format för.
1. Ange en **Klass** namn.

   Klassnamnet måste associeras med taggens outputClass-attribut i källinnehållet.
1. Välj en **Pseudo-klass** för bättre formatering av elementet.
1. Klicka **Klar**.

   Ett nytt format skapas och läggs till under basformatet.

### Anpassa ett fördefinierat eller nytt format

När du har skapat en ny CSS-fil med standardformat eller vill anpassa format i en befintlig CSS-fil kan du använda formatredigeraren för att göra det.

Så här anpassar du en stil:
1. Dubbelklicka på **Formatmallar** eller klicka på **>** ikon före **Formatmallar**.

   Detta visar standardfilerna (Innehåll och layout) och anpassade CSS-filer.
1. Öppna en formatmall för redigering.

   Gör något av följande om du vill öppna en formatmall för redigering:
   * Dubbelklicka på formatmallens namn.
   * Håll pekaren över formatmallens namn och klicka på (alternativikonen) ... och väljer Redigera.

   Då öppnas formatmallen för redigering och formatlistan visas på formatpanelen.

   <img src="assets/customize-style.png" alt="Anpassa stil" width="450">

1. Om du vill anpassa ett format dubbelklickar du på det eller klickar på >-ikonen före ett format för att visa och anpassa det med formatredigeraren.

## Arbeta med resurser

Detta är en behållare för alla resurser som används för att utforma en mall. Du kan tänka dig det som en mapp som innehåller resurser som bakgrundsbilder, anpassade teckensnitt, logotyper med mera. När du lägger till en resurs i mallen överförs den eller checkas in i resursmappen. Du kan sedan använda dessa resurser för att anpassa eller utforma dina PDF-mallar.

Följ stegen nedan för att lägga till en resursfil i resursmappen:
1. Håll muspekaren över fliken Resursmapp och klicka på (alternativikonen) ... och väljer Importera.

   Dialogrutan Överför resurser öppnas.

   <img src="assets/resources-import-assets.png" alt="Överför resurser" width="300">

   Sökvägen dit resursfilen ska överföras visas i **Välj resursmapp** fält.
   > **Obs!** Du kan inte ändra sökvägen för överföring av resurser. Som standard lagras alla resurser under `/content/dam/dita-templates/pdf/<PDF-template-name>` mapp.

1. Klicka **Välj filer** för att bläddra i resursfilen från din lokala dator
1. Klicka **Överför**.
Den valda filen importeras och visas under mappen Resurser.

## Avancerade PDF-inställningar

Använd avsnittet Inställningar för att konfigurera de avancerade inställningarna för PDF sidlayout, med början PDF från udda eller jämna sidor, format för korsreferenserna och aktivering av utskriftsmärken i det slutliga PDF som genereras med mallen.

Konfigurera genom att klicka på **Inställningar** i **Mallar** för att visa följande alternativ:

**Allmänt**

Ange de grundläggande konfigurationsinställningarna för att starta ett kapitel från udda eller jämn sida, innehållsförteckningsstrukturen och definiera ledarradformatet för posterna i innehållsförteckningen. Du kan definiera följande inställning:

* **Starta alltid kapitel från**: Här kan du definiera hur varje kapitel ska publiceras i den slutliga PDF. Du kan välja bland en **Ny sida**, **Udda sida**, eller **Jämn sida** alternativ. Om du väljer att starta ett nytt kapitel från en udda sida infogas en tom sida efter ett kapitel som slutar på en udda sida. Om kapitlet avslutas på sidan 15 infogas ett tomt nummer 16 i publiceringsprocessen<sup>th</sup> så att det nya kapitlet kan börja från 17<sup>th</sup> sida.

* **Starta varje ämne från en ny sida**: Om du vill att varje ämne i kapitlet ska börja på en ny sida väljer du **Starta varje ämne från en ny sida** alternativ. Om du vill att dina ämnen ska fortsätta utan sidmellanrum avmarkerar du det här alternativet.

* **Innehållsförteckningsstruktur**: Här kan du anpassa hierarkin för innehållsförteckningen. Följande ytterligare inställningar används:

   * **Använd rubriker upp till nivå**: Du kan justera antalet rubriknivåer som ska visas i innehållsförteckningsstrukturen på PDF.
   * **Visa inte sidnummer för den första nivån i innehållsförteckningen**: Välj det här alternativet om du vill dölja motsvarande sidnummer för alla kapitel som innehåller kapslade eller underordnade ämnen. Titta på följande exempel där en utdatafil skapas utan att markera det här alternativet.

   <img src="assets/page-number-in-toc.png" alt="Överför resurser" width="250">

   I ovanstående exempel är Avancerade PDF-inställningar, Bilaga och Legal ämnesrubriker på första nivån eller kapitelrubriker. Alla rubriker tilldelas ett sidnummer.

   Om du väljer det här alternativet och genererar utdata får du nu följande innehållsförteckning:
   <img src="assets/page-number-missing-in-toc.png" alt="Överför resurser" width="250">

   Här ser du att det första kapitlet Avancerade PDF-inställningar inte får något sidnummer, som det har kapslade eller underordnade avsnitt. Ett sidnummer om det tilldelas till Bilaga och Rättslig information eftersom de är fristående ämnen utan något underordnat ämne.

* **Ledarformat**: Använd listrutan för att välja prickade, heldragna eller mellanslag för att koppla rubriknivåer till motsvarande sidnummer.
Information om hur du använder rubriknivåer för innehållsförteckningens struktur och format finns i *Definiera innehållsförteckning*.

   > **Anteckning**: Om du är CSS-utvecklare kan du definiera ledarformatet direkt i CSS-filen också.
* **Använd fortsättningsmarkör för register**: Välj det här alternativet om du vill definiera markörer för långa tabeller som sprids över flera sidor. Mer information om att använda fortsättningsmarkörer för tabeller finns i Använda fortsättningsmarkörer för tabeller.

**Sidlayouter**

Inställningarna för sidlayout ger dig fullständig kontroll över hur du anger vilken sidlayout som ska användas för ett visst avsnitt i dokumentet. Om du till exempel vill välja en layout för innehållsförteckningen klickar du på listrutan under innehållsförteckningsfältet och väljer den layout som du har utformat för att generera innehållsförteckningen.

Om du inte har skapat någon layout för ett visst avsnitt i dokumentet kan du välja en layout som fungerar som standardlayout för sådana avsnitt eller avsnitt. Standardsidlayouten används sedan för alla avsnitt som inte har någon dedikerad sidlayout.

Om du vill ha en omslag och en baksida måste du ha en sidlayout som skapas och används i inställningarna. Annars kommer PDF inte att innehålla omslag och baksidor.


Mer information om sidlayouter finns i *Ange sidlayout*.

**Skriv ut**

Konfigurera utskriftsinställningarna för att tilldela skrivarmärken, välja färgmodeller och ange egenskaper för utskrift av PDF.

* **Skrivarmärken**: När du förbereder ett dokument för tryckproduktion läggs skrivarmärken till på sidgränserna för att underlätta korrekt justering, beskärning och färgval vid utskrift. Genom att välja ett skrivarmärke utökas sidgränsen så att den passar markeringen, som beskärs vid utskrift. Du kan välja att visa följande skrivarmärken i utdata från PDF:
   * **Ytmärken**: Välj alternativet att placera ett märke i varje hörn av trimningsområdet för att ange var papperet behöver beskäras efter utskrift.
   * **Utfallsmärken**: Välj det här alternativet om du vill placera ett märke i varje hörn av utfallsrutan för att ange den utökade bildens ytområde.
   * **Registreringsmärken**: Välj det här alternativet om du vill placera ett märke utanför beskärningsområdet för att justera de olika separationerna i ett färgdokument.
   * **Färgremsor**: Välj det här alternativet om du vill lägga till en rad färger utanför det beskurna området för att bibehålla färgernas enhetlighet och justera tryckfärgens densitet vid utskrift.

   Ange mått för de valda skrivarmärkena med hjälp av **Linjebredd**, **Linjefärg** och **Bredd på utfallsruta** alternativ.

* **Media Box-storlek**: Detta är den totala sidstorleken inklusive utökat område som används av skrivarmärken. Använd listrutan för att välja sidstorlek för dina utdata från PDF eller skapa en egen anpassad storlek.

* **Färgmodell**: Du kan välja mellan RGB eller CMYK-färgrymder för att skriva ut PDF-dokumentet. Välj RGB om du vill visa PDF digitalt och CMYK för fysisk utskrift. Färger som definieras i dokumentet konverteras till den valda färgrymden.
   > **Anteckning**: En ICC-färgprofil krävs för att skapa PDF/A om CMYK-färgmodellen används.

   Mer information om hur du använder de här utskriftsinställningarna finns i *Utskriftsinställningar*.

**Korsreferenser**

Använd fliken Korsreferens för att definiera hur korsreferenserna ska publiceras i PDF. Du kan formatera korsreferenserna för ämnesrubrik, tabeller, figurer och mycket annat. Mer information finns i *Formatera korsreferenser*.
