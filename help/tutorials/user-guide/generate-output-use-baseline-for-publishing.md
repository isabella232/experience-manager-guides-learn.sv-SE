---
title: Arbeta med baslinje
description: Lär dig hur du arbetar med baslinjen
exl-id: dcafab53-c388-48c3-9455-e4251cdda17d
source-git-commit: c74badebbcb4733fb9caa79c646b1d1e5c8bfe8e
workflow-type: tm+mt
source-wordcount: '1917'
ht-degree: 0%

---

# Arbeta med baslinje {#id1825FI0J0PF}

Med funktionen Baslinje kan du skapa en version av dina ämnen och resurser som sedan kan användas för publicering eller översättning. Om din DITA-karta till exempel har `topicA` och `imageA`kan du skapa en baslinje för att använda den tredje versionen av `topicA`, men den fjärde versionen av `ImageA`. När du har en originalplan kan du publicera eller översätta ämnen från olika versioner med ett enda klick.

Det är valfritt att välja en baslinje för förinställningar och en DITA-karta kan ha mer än en baslinje. Varje förinställning i en DITA-karta kan emellertid bara kopplas till en baslinje. Om ingen baslinje har angetts vid publiceringen publiceras utdata med den senaste versionen av innehållet.

På samma sätt är det valfritt att markera en baslinje för att översätta innehåll. Om du väljer att översätta innehåll med hjälp av en baslinje, sparas innehållet i baslinjen också tillsammans med de översatta kopiorna. Du kan sedan använda den översatta baslinjen för att utföra ytterligare åtgärder som att dela den med externa utgivare eller arkivera den. Mer information om hur du exporterar en översatt baslinje finns i [Exportera översatt originalplan](#id196SE600GHS).

>[!TIP]
>
> Se *Baslinje* i guiden Bästa praxis om att arbeta med baslinjer.

Administratören kan konfigurera fliken Baslinje på kartkontrollpanelen. Mer information finns i *Fliken Konfigurera baslinje på DITA-kartkontrollpanelen* i installations- och konfigureringshandboken.

Du kommer åt baslinjefunktionen genom att utföra följande steg:

1. Navigera till och klicka på DITA-mappningsfilen i resursgränssnittet.
1. Gå till **Baslinjer** -fliken.

På fliken Baslinjer kan du utföra följande åtgärder:

- [Skapa en baslinje](#id195FI0I0MUQ)
- [Visa innehållet i en baslinje](#id195FI0I0TLN)
- [Redigera, duplicera eller ta bort baslinjer](#id195FI0I0YJL)
- [Lägga till etiketter i en baslinje](#id184KD0T305Z)

## Skapa en baslinje {#id195FI0I0MUQ}

Du kan skapa en baslinje med en specifik version av ämnen och refererat innehåll som är tillgängligt på ett visst datum och en viss tid, eller med en etikett definierad för en ämnesversion. Du kan ange versioner av markerade ämnen separat på en baslinje så att de markerade avsnitten och tillhörande versioner inkluderas för generering eller översättning varje gång du använder baslinjen i arbetsflödet för publicering eller översättning.

Så här skapar du en baslinje:

1. På sidan Baslinjer klickar du på **Skapa**.
1. Ange ett namn för baslinjen i **Baslinjenamn**.
1. I **Ange version baserad på** väljer du något av följande alternativ:

   - **Etikett**: Välj det här alternativet om du vill välja ämnen enligt den etikett som används på dem. Ange en etikett för att filtrera listan baserat på den angivna strängen. I den filtrerade listan kan du välja en etikett för att välja ämnen och andra resurser med den angivna etiketten.
   När du väljer **Etikett**, får du också ytterligare ett alternativ för att använda den senaste versionen av ämnen som inte har den angivna etiketten. Om du inte markerar det här alternativet och det finns ämnen eller mediefiler som inte har den angivna etiketten, kommer baslinjen inte att kunna skapas. Mer information om hur du lägger till etiketter finns i [Använd etiketter](web-editor-use-label.md#).

   - **Version on** &lt;*tidsstämpel*\>: Hämtar ämnesversionen som angivet datum och angiven tid. Observera att den tidpunkt som du anger här motsvarar tidszonen för AEM. Om servern befinner sig i en annan tidszon hämtas ämnen enligt serverns tidszon och inte enligt den lokala tidszonen.

   När du har markerat en etikett eller version som den är, markeras alla refererade ämnen och mediefiler på kartan därefter. Det här valet av ämnen visas inte i användargränssnittet, men sparas i serverdelen.

1. Om du vill använda en annan version för ett eller flera ämnen kan du göra det genom att manuellt markera de ämnena. Klicka **Sök ämne** väljer du det ämne som du vill använda en annan version för. I listrutan Välj en version för det valda ämnet väljer du en version av ämnet som du vill använda i baslinjen och klickar på **OK**.

   ![](images/baseline-select-version-drop-down.png){width="800" align="left"}

   Informationen om ämnet och den valda versionen lagras i serverdelen. Du kan upprepa det här steget om du vill ändra den valda versionen för flera ämnen.

1. Klicka på **Bläddra bland alla ämnen** om du vill läsa in alla ämnen och mediefiler som refereras från DITA-kartan. UUID för ämnen och mediefiler visas även under ämnesrubriken eller \(media\)-filnamnet.

   >[!NOTE]
   >
   > Om du har en mycket stor uppsättning filer på DITA-kartan, med kapslade kartor och ämnen, kan det ta ett tag att läsa in alla filer om du klickar på Bläddra bland alla avsnitt.

   Innehållet i kartan visas i tre avsnitt: kartfilen, innehållet \(ämnesreferenser\) och referensinnehållet \(kapslade ämnen, kartor och andra resurser\). När du har allt refererat innehåll tillgängligt kan du välja den version av ämnet som du vill använda i baslinjen.

   The **Version** i den nedrullningsbara listan visas tillgängliga versioner av avsnitten eller det refererade innehållet. För det refererade innehållet kan du välja en version automatiskt.

   Om du väljer **Välj automatiskt** för det refererade innehållet väljs automatiskt den version av det refererade innehållet som motsvarar den version av innehållet som det refereras till i. Låt oss till exempel säga att ett ämne A har en referens till en bild B. När version 1.5 av avsnitt A skapades var version 1.2 i databasen. Nu när en baslinje skapas med version 1.5 av ämnet A med bild B inställd på **Välj automatiskt** väljer systemet automatiskt version 1.2 av bild B.

   Om du skapar en baslinje med hjälp av etiketterna **Välj automatiskt** används på versionen av allt refererat innehåll.

   Om det refererade innehållet eller resurserna \(ämne, undermappar, bilder eller videoklipp\) inte har versionsnumret \(t.ex. nyligen överfört innehåll\), skapas en version för sådana filer när du skapar en baslinje. Om filerna har en ny version skapas dock ingen inkrementell version för dessa filer. Det här beteendet styrs av inställningen för att skapa automatiskt, som är aktiverad som standard. Detta krävs också för översättning av innehåll där alla filer förväntas ha en version i översättningsprocessen.

   >[!NOTE]
   >
   > Om du vill ange en annan version för en viss resurs kan du göra det genom att välja önskad version från **Version** nedrullningsbar lista.

1. Klicka **Spara**.

## Visa innehållet i en baslinje {#id195FI0I0TLN}

Du kan visa innehållet i en befintlig baslinje genom att klicka på fliken Baslinjer och välja önskad baslinjeversion i listan. Sidan Baslinjer är uppdelad i tre delar - DITA-kartfil, kartans innehåll eller ämnen samt det refererade innehållet. Om kartan innehåller underkartor visas även de ämnen som refereras från underkartan i innehållsavsnittet. De olika kolumnerna på sidan Baslinje beskrivs nedan:

- **Namn**: Visar DITA-kartan eller objektets rubrik eller resursens namn, t.ex. bildens filnamn.

- **Typ**: Visar typ eller typ av resurs på kartan, t.ex. DITA-karta, DITA-avsnitt eller bildformat.

- **Version**: Visar vilken version av resursen som är tillgänglig på baslinjen.

- **Datum och tid för version**: Visar datum och tid när resursen skapades för den valda versionen.

- **Senaste**: Anger om den senaste versionen av resursen används i baslinjen.

- **Överordnad karta**: Om kartfilen innehåller undermappar innehåller den här kolumnen namnet på den karta som ett ämne refereras till i.

- **Etikett**: Visar etiketten/etiketterna som används i versionen av ämnet.

- **Refererad av**: Den här kolumnen är endast tillgänglig för det refererade innehållet. Den anger det överordnade avsnittet för den refererade resursen. Om en resurs refereras av flera ämnen, separeras ämnena med kommatecken.

## Redigera, duplicera eller ta bort baslinjer {#id195FI0I0YJL}

**Redigera baslinjer**

Utför följande steg för att redigera en befintlig baslinje:

1. Markera baslinjen och klicka på **Redigera**.
1. Gör önskade ändringar i baslinjen. Du kan ändra namn och version för ämnet eller det refererade innehållet.
1. Klicka **Spara**.

**Duplicera baslinjer**

Markera baslinjen och klicka på **Duplicera** om du vill skapa en kopia av en befintlig baslinje. Ange ett annat namn för baslinjen, välj versionsnummer för avsnitten och det refererade innehållet och klicka på **Spara**.

**Ta bort baslinjer**

Välj baslinjeversionen och klicka på **Ta bort** för att ta bort en baslinje.

## Lägga till etiketter i en baslinje {#id184KD0T305Z}

Det kan vara tidskrävande att lägga till etiketter i varje enskilt ämne. Med AEM Guides kan du lägga till etiketter i flera ämnen och refererat innehåll på en DITA-karta med ett enda klick.

Utför följande steg för att lägga till en etikett i flera ämnen och refererat innehåll i en DITA-karta:

1. På sidan Baslinjer väljer du en baslinje som innehåller ämnen och refererat innehåll som du vill lägga till en etikett för.

   >[!NOTE]
   >
   > Se till att baslinjen inte har den senaste versionen av något ämne eller material. En etikett kan bara läggas till i ett versionsämne eller en resurs.

1. Klicka **Lägg till etiketter**.

   ![](images/add-label-baseline-uuid.png){width="800" align="left"}

1. I **Lägg till etikett** anger du en unik etikett som ska kopplas till baslinjen.

   Om administratören har konfigurerat fördefinierade etiketter visas dessa i en listruta. Du måste välja en etikett i listan.

1. Om du vill använda etiketten för ämnen som refereras från undermappningarna väljer du **Använd etikett på underordnade kartor och underordnade** alternativ.

   - Klicka **Lägg till**.
Den angivna etiketten läggs till på DITA-kartan och de ämnen och innehåll som refereras.

      ![](images/label-added-baseline-uuid.png){width="650" align="left"}


## Exportera översatt originalplan {#id196SE600GHS}

Du kan använda Baslinje för översättning av innehåll. Du kan till exempel skapa en baslinje för version 1.1 som är klar för översättning på franska. På fliken Översättning måste du använda Baslinje för att filtrera innehållet och sedan välja Baslinje för version 1.1 av innehållet. Genom att använda Baslinje för översättning av innehåll blir det enklare för dig att hantera ditt innehåll.

När innehållet har översatts kan du exportera den översatta baslinjen för arkivering eller dela den med olika team i organisationen. Du måste tänka på följande innan du exporterar en översatt baslinje:

- Det går bara att exportera en baslinje efter att innehållet i baslinjen har översatts. Om du försöker exportera en baslinje för vilken översättningen inte har startats eller inte är fullständig visas ett felmeddelande.
- Du kan bara överföra baslinjen för en version som redan är översatt. Om du t.ex. har skapat en baslinje för version 1.1 av ditt innehåll och samma är översatt, kan du exportera denna baslinje. Om du har skapat en baslinje för version 1.2, som inte är översatt, kan du inte exportera baslinjen.
- Om en baslinje redan har exporterats kan du skriva över den befintliga baslinjen genom att markera *Skriv över befintlig baslinje* vid export.

Utför följande steg för att exportera en översatt baslinje:

1. Öppna DITA-kartan som innehåller den översatta baslinjen.

1. I **Översättning** -fliken, expandera **Baslinje** i den vänstra listen.

   ![](images/export-baseline.png){width="800" align="left"}

1. Välj **Använd baslinje** och välj den baslinje som du vill exportera.

1. Klicka **Exportera baslinje**.

   Exportstatus visas. Om processen lyckas visas ett meddelande där du anger vilket språk baslinjen ska exporteras för. Om ett fel uppstår visas felorsaken.

   Om du försöker exportera den baslinje som redan har exporterats visas även felmeddelandet när baslinjen skapades.

1. \(Valfritt\) Om du vill exportera en baslinje som redan har exporterats väljer du **Skriv över befintlig baslinje** och sedan klicka **Exportera baslinje**.


**Överordnat ämne:**[ Generering av utdata](generate-output.md)
