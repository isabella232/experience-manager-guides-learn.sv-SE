---
title: Publiceringsfunktion för PDF | Anpassa och konfigurera funktionen för inbyggda PDF
description: Lär dig hur du anpassar och konfigurerar de olika komponenterna i funktionen PDF.
hide: true
hidefromtoc: true
source-git-commit: 0f18d9f7d7967b6f25c5d05b54a22f65e9fc20f7
workflow-type: tm+mt
source-wordcount: '764'
ht-degree: 0%

---

# PDF-mall

En mall ger en konsekvent innehållslayout och innehållsstruktur. När mallarna är fördefinierade kan du undvika att arbeta om formateringsproblem som uppstår för varje nytt projekt eller uppdateringar. Med mallar kan du utforma sidlayouter, formatera innehåll och använda olika inställningar för att anpassa PDF.

Utvecklare kan använda förinställningarna för PDF för att generera utdata, men de kan skapa egna mallar. Det finns exempelmallar som levereras ut ur kartongen och som kan anpassas ytterligare eller dupliceras av utvecklarna enligt deras organisatoriska krav.


## Skapa en ny PDF-mall {#create-pdf-template}

Du kan skapa anpassade PDF-mallar med särskilda sidlayouter och definiera formatering för sidlayoutskomponenter (som innehållsförteckning, index, ordlista) eller DITA-komponenter (som rubrik, stycke, lista) med hjälp av formatmallar. Du kan skapa en ny mall från grunden eller skapa den med en exempelmall.

Så här skapar du en ny PDF-mall:
1. Gå till webbredigeraren **Utdata** -fliken.
1. Expandera den vänstra sidlisten och klicka på **Mallar**.
<img src="assets/create-pdf-template.png" alt="Skapa PDF-mall" width="400">
1. I panelen **Mallar** klickar du på ikonen **+** bredvid **Mallar** och väljer **PDF-mall**.
1. Ange ett namn för mallen i dialogrutan **Ny mall**.
1. Klicka på **Klar**.

Den nya mallen skapas och läggs till i *Mallar* -panelen.

## Duplicera en PDF-mall

Om du vill skapa en ny mall med samma sidlayout och formatering som en befintlig mall kan du skapa en kopia. När en mall har duplicerats kan du anpassa dess komponenter ytterligare efter behov.

Så här duplicerar du en befintlig PDF-mall:
1. Gå till webbredigeraren **Utdata** -fliken.
1. Expandera den vänstra sidlisten och klicka på **Mallar**.

   Mallpanelen öppnas.
1. Håll pekaren över mallen som du vill duplicera och välj (*Alternativ* ikon) **...** och välja **Duplicera** på snabbmenyn.

   Dialogrutan Duplicera mall öppnas.\
   <img src="assets/duplicate-template.png" alt="Mallen Duplicera PDF" width="250">
1. Ange ett namn för teamplet.

   The **Namn** fältet är förifyllt som en kopia av samma namn som källmallen.

1. Om du vill ange ett önskat namn tar du bort det förifyllda namnet och anger ett namn.
1. Klicka **Klar**.

   En dubblettmall skapas och läggs till under Mallar.

## Anpassa en PDF-mall

Du kan anpassa mallar genom att justera mallkomponenterna och använda formatformat med hjälp av formatmallar.

Så här anpassar du en PDF-mall:
1. Gå till fliken Utdata i Web Editor.
1. Expandera den vänstra sidlisten och klicka på Mallar.

   Mallpanelen öppnas.
1. Gör något av följande om du vill visa komponenterna i en mall:

   * Klicka på ikonen > bredvid en mall eller dubbelklicka på mallnamnet.
   * Håll muspekaren över en mall och klicka på ... (Alternativikon) och välj Redigera på snabbmenyn.

      Som standard öppnas inställningspanelen i mallredigeraren.
   <img src="assets/customize-pdf-template.png" alt="Anpassa PDF Teamplte" width="350">

   De olika mallkomponenter du kan anpassa är kategoriserade under följande avsnitt:
   * Sidlayouter: En vanlig PDF innehåller olika sidor, t.ex. ett försättsblad eller en titelsida, innehållsförteckning, kapitel, index med mera. I delen Sidlayouter kan du designa utseendet på olika sidor som skulle utgöra PDF. Förutom utseendet kan du även definiera placeringen av sidelement som sidhuvud, sidfot och innehållsområden på en sida. Mer information om hur du anpassar en sidas layout finns i ***Skapa och anpassa sidlayouter***.
   * Formatmallar: Med inställningarna i avsnittet Formatmallar kan du anpassa utseendet och känslan hos sidlayoutskomponenterna som innehållsförteckning, index, ordlista med mera. Dessutom kan du anpassa formaten för DITA-innehållet, till exempel rubriker, stycken, listor och annat. Mer information om hur du använder formatmallar finns i ***Anpassa PDF med formatmallar***.
   * Resurser: Lagra resursfiler som du behöver för att anpassa eller designa PDF-mallar. Resurser som logotyper, anpassade teckensnitt, bakgrundsbilder med mera lagras i Resurser. Mer information om hur du använder resurser finns i ***Arbeta med resurser***.
   * Inställningar: Konfigurera utdatainställningarna för generering av PDF med hjälp av mallen. I det här avsnittet kan du definiera mallmappning för olika sidor på en PDF, startsida för kapitel, utskriftsmärken och mycket annat. Mer information om hur du använder inställningar finns i ***Avancerade PDF-inställningar***.
1. Om du vill anpassa en mallkomponent dubbelklickar du på en mallkomponent eller klickar på ikonen > före den.

   Du kan till exempel dubbelklicka på *Sidlayouter* eller klicka på *>* ikon före *Sidlayouter* för att visa tillgängliga sidlayouter.
1. När du har gjort ändringarna klickar du på *Spara alla* (eller `Ctrl+S`).

