---
title: Skapa och anpassa inbyggda PDF-mallar
description: Lär dig hur du skapar och anpassar mallar för inbyggda PDF.
source-git-commit: 880cd344ceb65ea339be699ebcad41c0d62e168a
workflow-type: tm+mt
source-wordcount: '1154'
ht-degree: 0%

---

# PDF-mall {#PDF-template}

En mall ger en konsekvent innehållslayout och innehållsstruktur. När mallarna är fördefinierade kan du undvika att arbeta om formateringsproblem som uppstår för varje nytt projekt eller uppdateringar. Med mallar kan du utforma sidlayouter, formatera innehåll och använda olika inställningar för att anpassa PDF.

## Mallar för fabriksinstallationer och anpassade PDF

Det finns några färdiga mallar som utvecklarna kan använda som grundmallar för att skapa anpassade mallar efter organisationens behov.



## Skapa en ny PDF-mall {#create-pdf-template}

Du kan skapa anpassade PDF-mallar med särskilda sidlayouter och definiera formatering för sidlayoutskomponenter (som innehållsförteckning, index, ordlista) eller DITA-komponenter (som rubrik, stycke, lista) med hjälp av formatmallar.

Så här skapar du en ny PDF-mall:
1. Gå till webbredigeraren **Utdata** -fliken.
1. Välj **Mallar** <img src="./assets/template.svg" alt= "mallikon" width="25"> till vänster.
<img src="assets/create-pdf-template.png" alt="Skapa PDF-mall" width="400">
1. I fönstret **Mallar** väljer du ikonen **+** bredvid **Mallar** och väljer **PDF-mall**.
1. I dialogrutan **Ny PDF-mall** väljer du en standardmall som du vill använda som bas för att skapa den anpassade mallen. Du kan också använda sökrutan för att söka efter en mall.
1. Ange en rubrik för mallen.

>[!NOTE]
>
>  Du kan också förhandsgranska en miniatyrbild för mallen när du skapar och duplicerar en mall. Redigera eller ta bort miniatyrbilden med [**Egenskaper**](#properties-option) i **Alternativ** -menyn när du har skapat mallen.

1. Klicka **Skapa**.

   Den nya mallen skapas och läggs till i **Mallar** -panelen.

## Duplicera en PDF-mall {#duplicate-pdf-template}

Om du vill skapa en ny mall med samma sidlayout och formatering som en befintlig mall kan du skapa en kopia. När en mall har duplicerats kan du anpassa dess komponenter ytterligare efter behov.

Så här duplicerar du en befintlig PDF-mall:
1. Gå till webbredigeraren **Utdata** -fliken.
1. Välj **Mallar** <img src="./assets/template.svg" alt= "mallikon" width="25"> till vänster. Då öppnas **Mallar** -fönstret.
1. Håll pekaren över mallen som du vill duplicera och markera **...** *Alternativ* ikon och välj **Duplicera** på snabbmenyn.

   Då öppnas **Duplicera PDF-mall** -dialogrutan.

   <img src="assets/duplicate-template.png" alt="Mallen Duplicera PDF" width="350">

   *Välj en mall som du vill duplicera, förhandsvisa miniatyrbilden och uppdatera titeln i dialogrutan **Duplicera PDF-mall**-dialogrutan.*

1. Ange en rubrik för mallen.

   The **Titel** fältet är förifyllt som en kopia av samma titel som källmallen. Du kommer att visa ett felmeddelande om mallen med samma namn finns.



1. Om du vill ange en önskad titel tar du bort den förifyllda titeln och anger en titel.
1. Klicka **Duplicera**.

   En dubblettmall skapas och läggs till under **Mallar**.

## Andra åtgärder för mallarna

Du kan även utföra följande åtgärder på mallarna från **Alternativ** meny:

<img src="assets/PDF-template-options.png" alt="Mallen Duplicera PDF" width="350">

### Ta bort

Välj alternativet Ta bort om du vill ta bort den markerade mallen. Välj sedan Ja på bekräftelsemeddelandet.
Förinställningen tas bort från **Mallar**.

### Egenskaper{#properties-option}

Välj det här alternativet om du vill visa och redigera mallens egenskaper. Du kan förhandsgranska mallens befintliga miniatyrbild. Du kan också redigera eller ta bort miniatyrbilden. Du kan också ändra mallens rubrik och beskrivning.

### Visa i resursgränssnitt

Välj det här alternativet om du vill visa mallen i resursgränssnittet. När mallens rotplats öppnas kan du visa alla resurser i mallen.

När du har skapat den anpassade mallen kan du välja den bland sidlayouterna i PDF-förinställningen.
Lär dig hur [publicera PDF](https://experienceleague.adobe.com/docs/experience-manager-guides-learn/tutorials/user-guide/output-gen/web-editor/native-pdf-web-editor.html?lang=en).

>[!NOTE]
>
>Om mappen har en konfigurerad mappprofil visas endast de PDF-mallar som är konfigurerade i mappprofilen.

Beroende på din konfiguration kan administratören konfigurera mallarna:

<details>
<summary> Cloud Service </summary>

Mer information om hur du konfigurerar globala profiler och profiler på mappnivå finns i [Konfigurera mallar](../cs-install-guide/conf-folder-level.md#id1889D0IL0Y4) i installations- och konfigurationshandboken för Cloud Service.

</details>

<details>    
<summary>  Lokal programvara </summary>

Mer information om hur du konfigurerar globala profiler och profiler på mappnivå finns i [Konfigurera redigeringsmallar](../install-guide/conf-folder-level.md#create-custom-authoring-template-id1917d0eg0hj) i installations- och konfigureringshandboken på plats.

</details>

## Anpassa en PDF-mall {#customize-pdf-template}

Du kan anpassa mallar genom att justera mallkomponenterna och använda formatformat med hjälp av formatmallar.

Så här anpassar du en PDF-mall:
1. Gå till webbredigeraren **Utdata** -fliken.
1. Expandera den vänstra sidlisten och välj **Mallar**.

   Då öppnas **Mallar** -panelen.
1. Gör något av följande om du vill visa komponenterna i en mall:

   * Välj >-ikonen bredvid en mall eller dubbelklicka på mallnamnet.
   * Håll pekaren över en mall och välj ... (**Alternativ** ikon) och välj **Redigera** på snabbmenyn.

     Som standard öppnas **Inställningar** i mallredigeraren.
   <img src="assets/customize-pdf-template.png" alt="Anpassa PDF Teamplte" width="350">

   >[!NOTE]
   >
   >  Administratören kan hämta de senaste mallarna från följande sökväg och ersätta de befintliga:
   >
   > `/libs/fmdita/pdf`

   De olika mallkomponenter du kan anpassa är kategoriserade under följande avsnitt:
   * Sidlayouter: Ett vanligt PDF innehåller olika sidor, t.ex. ett försättsblad eller en titelsida, innehållsförteckning, kapitel, index, citat med mera. I delen Sidlayouter kan du designa utseendet på olika sidor som skulle utgöra PDF. Mer information finns i [Sidlayouter](../native-pdf/components-pdf-template.md#page-layouts).

     Förutom utseendet kan du även definiera placeringen av sidelement som sidhuvud, sidfot och innehållsområden på en sida. Mer information om hur du anpassar en sidas layout finns i [Skapa och anpassa sidlayouter](components-pdf-template.md#create-customize-page-layout).

   * Formatmallar: Med inställningarna i avsnittet Formatmallar kan du anpassa utseende och känsla för sidlayoutskomponenter som innehållsförteckning, index, ordlista, citat och mycket annat. Dessutom kan du anpassa formaten för DITA-innehållet, till exempel rubriker, stycken, listor och annat. Mer information om hur du använder formatmallar finns i [Anpassa PDF med formatmallar](components-pdf-template.md#stylesheet-customization).
   * Resurser: Lagra resursfiler som du behöver för att anpassa eller utforma PDF-mallar. Resurser som logotyper, anpassade teckensnitt, bakgrundsbilder med mera lagras i Resurser.
Du kan också använda resurser som finns på någon annan plats i databasen. Du behöver inte skapa dubblettresurser för varje mall, och du kan behålla dem i en delad mapp och använda dem i alla mallar i PDF.

     Mer information om hur du använder resurser finns i [Arbeta med resurser](components-pdf-template.md#work-with-resources).
   * Inställningar: Konfigurera utdatainställningarna för att skapa en PDF med hjälp av mallen. I det här avsnittet kan du definiera mallmappning för olika sidor på en PDF, startsida för kapitel, utskriftsmärken, citat och mycket annat.
Du kan också ordna i vilken ordning de ska visas i den slutliga utskriften för PDF.
Mer information om hur du använder inställningar finns i [Avancerade PDF-inställningar](components-pdf-template.md#advanced-pdf-settings).


1. Om du vill anpassa en mallkomponent dubbelklickar du på en mallkomponent eller väljer ikonen > före den.

   Du kan till exempel dubbelklicka *Sidlayouter* eller välj *>* ikon före *Sidlayouter* för att visa tillgängliga sidlayouter.

   >[!NOTE]
   >
   >Du kan även uppdatera en miniatyrbild och mallbeskrivningen med hjälp av [**Egenskaper**](#properties-option) i **Alternativ** -menyn.

1. När du har gjort önskade ändringar väljer du *Spara alla* (eller `Ctrl+S`).
