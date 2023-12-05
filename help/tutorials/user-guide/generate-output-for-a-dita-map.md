---
title: Generera utdata för en DITA-karta från kartkonsolen
description: Generera utdata för en DITA-karta från kartkonsolen i AEM. Lär dig mer om inkrementell generering av utdata och hur du visar status, avbryter och tar bort en utdataåtgärd.
source-git-commit: 880cd344ceb65ea339be699ebcad41c0d62e168a
workflow-type: tm+mt
source-wordcount: '1418'
ht-degree: 0%

---

# Generera utdata för en DITA-karta från kartkonsolen {#id1825FG00UHT}

Utför följande steg för att generera utdata för en DITA-karta:

1. I resursgränssnittet navigerar du till och klickar på den DITA-kartfil som du vill publicera.

   DITA-kartkonsolen visas med en lista över tillgängliga utdatapresentationer för att generera utdata.

1. Välj en eller flera förinställningar som du vill använda för att generera utdata.

   ![](images/generate-multiple-outputs-uuid.png){width="800" align="left"}

   >[!NOTE]
   >
   > Om du genererar AEM platsutdata används den struktur som definierats i `.ditamap` för att skapa AEM platsstruktur.

1. Klicka på ikonen Generera för att starta genereringsprocessen för utdata.


Du kan visa aktuell status för begäran om generering av utdata genom att klicka på Utdata. Mer information finns i [Visa status för utdatagenereringsaktiviteten](#viewing_output_history)

>[!IMPORTANT]
>
> Om en utdatagenereringsprocess för en förinställning antingen finns i kön eller pågår kan du inte initiera en annan utdatagenereringsåtgärd för samma förinställning.

Du kan generera utdata från PDF för en eller flera förinställningar som skapats för en DITA-karta från webbredigeraren. Mer information finns i [Använd snabbgenereringspanelen för att generera och visa utdata för förinställningarna](web-editor-quick-generate-panel.md#).

Du kan också generera AEM för ett eller flera avsnitt eller hela DITA-kartan från Web Editor. Mer information finns i [Artikelbaserad publicering från webbredigeraren](web-editor-article-publishing.md#id218CK0U019I).

## Inkrementell utdatagenerering {#generating_standalone_topic}

>[!NOTE]
>
> Inkrementell utdatagenerering gäller endast för AEM. Du kan också endast återskapa DITA-avsnitt \(.dita/.xml\) från en DITA-karta eller underkartor. Om du väljer en DITA-karta, delkarta, ämnesgrupp eller ett ämne med `@processing-role="resource-only"`är alternativet för att återskapa inte tillgängligt.

Det kan finnas ett antal tillfällen då du bara uppdaterar ett fåtal ämnen på din DITA-karta och bara överför dessa uppdaterade ämnen live. Om du vill hantera sådana scenarier kan du skapa inkrementella utdata med hjälp av AEM. Om du har uppdaterat några avsnitt behöver du inte generera om hela DITA-kartan. Du kan bara välja de uppdaterade avsnitten och återskapa dem.

Om kartan är hackad och du har uppdaterat ett enskilt ämne på kartan, måste du generera om hela kartan för det uppdaterade ämnet eller innehållet så att det återspeglas i utdata. Du får inte alternativet för omgenerering av utdata på ämnesnivå, det är bara tillgängligt på mappningsnivån \(chunked\). Detta gäller för den överordnade kartan och alla underkartor.

Så här återskapar du utdata för ett visst ämne eller en grupp ämnen:

>[!IMPORTANT]
>
> När du återskapar AEM platsutdata skapas utdata med den aktuella versionen av filerna och inte med den kopplade baslinjen.

1. Navigera till och klicka på DITA-mappningsfilen i resursgränssnittet.

   DITA-kartkonsolen visas med en lista över tillgängliga utdatapresentationer för att generera utdata.

1. Välj **Ämnen** -fliken.

   En lista med ämnen som är tillgängliga på DITA-kartan visas.

1. Markera de ämnen som du vill återskapa.

   >[!NOTE]
   >
   > Om du har lagt till nya ämnen i DITA-kartan kan du inte generera dessa nya ämnen härifrån. Du måste först publicera de nya ämnena med DITA-kartpubliceringsfunktionen.

   ![](images/regenerate-topics.png){width="800" align="left"}

1. Klicka **Återskapa**.

   Sidan Återskapa markerade ämnen visas.

1. Välj den förinställning för utdata som du vill använda för att återskapa de valda ämnena.

1. Klicka **Återskapa** för att starta processen för generering av utdata.


>[!IMPORTANT]
>
> Om du byter namn på ett ämne och genererar om ämnet, återspeglas inte den uppdaterade ämnestiteln i DITA-schemats innehållsförteckning. Om du vill uppdatera ämnestiteln i innehållsförteckningen måste du generera hela DITA-kartan.

Du kan visa aktuell status för begäran om generering av utdata genom att klicka på Utdata. Mer information finns i [Visa status för utdatagenereringsaktiviteten](#viewing_output_history).

## Visa status för utdatagenereringsaktiviteten {#viewing_output_history}

När du initierar genereringsuppgiften för utdata för en karta eller återskapar valda ämnen, skickar AEM den här uppgiften till kön för utdatagenerering. Den här kön uppdateras i realtid och visar statusen för varje utdatagenereringsuppgift i kön.

Utför följande steg för att visa kön för generering av utdata:

1. I resursgränssnittet navigerar du till och klickar på den kartfil som du vill kontrollera utdatagenereringsstatusen för.

1. Klicka **Utdata**.

   ![](images/output-queued.png){width="800" align="left"}

   Sidan Utdata är uppdelad i två delar:

   - **Utdata i kö:**

     Visar utdata som väntar på att skapas eller som håller på att genereras. De köade eller pågående uppgifterna visas med en blå färgikon före förinställningens namn. Du kan också hitta den inställning eller förinställning för generering av utdata som används för uppgiften som står i kö, typ, användare som initierade uppgiften, tid sedan uppgiften placerades i kö samt aktuell status.

     Klicka på länken för att komma åt **Publish Dashboard** och visa aktuell körningsstatus. En lista över alla aktiva publiceringsåtgärder finns på Publish Dashboard. The **Utdata i kö** och **Publish Dashboard**-länken visas bara när det finns utdata som antingen väntar på att genereras eller som håller på att genereras. De visas inte när utdataåtgärderna har slutförts.Mer information om Publish Dashboard finns i [Hantera publiceringsuppgifter med Publish Dashboard](generate-output-publish-dashboard.md#).

   - **Genererade utdata**

     Visar en lista över utdataaktiviteter som har slutförts. Informationen som visas här liknar den i avsnittet Utdata i kö med några skillnader. Du har en ny uppsättning information i form av ikoner för utdataresultat och tiden för generering av utdata.

     I den här listan kan du ha uppgifter som har körts, uppgifter som har körts med meddelande eller misslyckade uppgifter. De slutförda åtgärderna visas med en grön färgikon, uppgifterna med ett meddelande har en orange färgikon och de misslyckade åtgärderna visas med en röd färgikon.

     Publiceringsprocessen skapar en loggfil, \(logs.txt\), som du kommer åt genom att klicka på länken i kolumnen Genererad vid. För uppgifter som har misslyckats eller innehåller meddelanden kan du kontrollera loggfilen, som förklaras i avsnittet [Visa och kontrollera loggfilen](generate-output-basic-troubleshooting.md#id1822G0P0CHS).

     >[!NOTE]
     >
     > När du klickar på en länk till det genererade PDF-utdata blir du ombedd att hämta PDF. Detta är standardbeteendet i AEM 6.5 och 6.4.


## Avbryt en utdatagenereringsaktivitet {#id2061H100T5Z}

AEM Guides är ett enkelt och enkelt sätt att avbryta pågående publiceringsuppgifter. Som utgivare kan du avbryta en pågående publiceringsåtgärd från DITA-kartkonsolen eller [Publish Dashboard](generate-output-publish-dashboard.md#).

Utför följande steg för att avbryta en utdatagenereringsaktivitet från DITA-kartkonsolen:

1. I resursgränssnittet navigerar du till och klickar på kartfilen som du vill avbryta en pågående utdatagenereringsåtgärd för.

1. Klicka **Utdata**.

1. Håll pekaren över en uppgift som du vill avbryta i listan Köade utdata.

1. Klicka på *Avbryt det här jobbet* -ikon.

   ![](images/cancel-publish-task-map-console.png){width="800" align="left"}

1. Klicka **Ja** i meddelandet Bekräfta annullering.

   ![](images/confirm-cancel-output-map-condole.png){width="800" align="left"}

   Om aktiviteten inte har startats ännu körs kommandot cancel för uppgiften. För en uppgift som avbryts ställs statusen in på Avbryta.

   När aktiviteten har avbrutits flyttas den till **Genererade utdata** lista med **Avbruten** status. När du hovrar över den avbrutna uppgiften visas namnet på den användare som avbrutit uppgiften. På följande skärmbild visas *HTML5* aktiviteten avbryts.

   ![](images/cancelled-output-task.png){width="800" align="left"}


## Ta bort en utdataåtgärd från DITA-kartkonsolen

När du genererar flera utdata för en DITA-karta, blir listan Genererade utdata för en sådan karta mycket lång under en tidsperiod. Som utgivare kan du rensa utdatahistoriken för alla mappningsfiler genom att ta bort inaktuella uppgifter från *Genererade utdata* lista. Observera att utdata inte tas bort från systemet, endast posten för genererade utdata tas bort från *Genererade utdata* lista.

Så här tar du bort en utdatauppgift från listan Genererade utdata:

1. I resursgränssnittet navigerar du till och klickar på den kartfil som du vill ta bort uppgifterna från.

1. Klicka **Utdata**.

1. Håll pekaren över en uppgift som du vill ta bort i listan Genererade utdata.

1. Klicka på ikonen Ta bort.

   ![](images/delete-output-task.png){width="800" align="left"}

1. Klicka **Ja** i meddelandet Bekräfta borttagning.

   Uppgiften tas bort från listan Genererade utdata.


**Överordnat ämne:**[ Generering av utdata](generate-output.md)
