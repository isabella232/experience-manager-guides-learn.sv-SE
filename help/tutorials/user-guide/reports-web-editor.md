---
title: DITA-kartrapport från Web Editor
description: Generera DITA-kartrapporter från webbredigeraren i AEM. Lär dig hur du genererar en CSV-fil för en ämneslista, multimedierapporter, metadata och brutna länkar.
source-git-commit: 880cd344ceb65ea339be699ebcad41c0d62e168a
workflow-type: tm+mt
source-wordcount: '2366'
ht-degree: 0%

---

# DITA-kartrapport från Web Editor {#id231HF0Z0NXA}

AEM Guides innehåller en funktion i Web Editor som gör att du kan kontrollera den övergripande integriteten för dina referenser och generera rapporter för dem.

Du kan visa ämneslistan, hantera metadata för alla referenser och visa multimedielistan för den aktuella kartan från **Rapporter** i Web Editor.

## Generera en CSV-fil från ämneslistvyn

The **Ämneslista** -vyn innehåller detaljerad information om ämnen, som referenstyp, dokumenttillstånd och författare.

Du kan skapa en ämnesrapport genom att utföra följande steg:

1. I **Databas** öppnar du DITA-schemafilen i Kartvyn.
1. Klicka på **Hantera** -fliken.
1. Dubbelklicka **Ämneslista** till vänster. Listan med ämnen i DITA-kartan visas.

   ![](images/web-editor-topiclist-panel.png){width="800" align="left"}

1. Från **Filter** Panelen som du kan filtrera ämnen baserat på **Referenstyp** \(direkt eller indirekt\), **Dokumenttillstånd** \(aktuell status för dina ämnen. Om dina ämnen till exempel är i läget Redigera, Under granskning eller Granskad visas de här alternativen) eller **Upphovsman** av ämnet.

1. Du kan också använda följande alternativ för ämnesfiltrering för att välja att visa följande kolumner i listan:

   - **Ämne** Ämnets namn anges på DITA-kartan. Du kan klicka på ämnet för att redigera det.
   - **Filnamn** Filens namn.
   - **UUID** Filens universellt unika identifierare \(UUID\).
   - **Filplats** Ämnets fullständiga sökväg.
   - **Referenstyp** Referenstypen - direkt eller indirekt.
   - **Dokumenttillstånd** Ämnets aktuella tillstånd.
   - **Upphovsman** Användaren som arbetade sist med ämnet.
   - **Överordnad karta** Listan med alla kartor där ämnet refereras direkt.
   >[!NOTE]
   >
   > Klicka **Uppdatera** om du vill få en ny lista med ämnen och visa ändringar i kartfilen eller om en referens i ämnesfilen uppdateras.

1. Klicka **Hämta CSV** om du vill hämta den aktuella ögonblicksbilden av ämnena i DITA-kartan. CSV innehåller de markerade kolumnerna och de avsnitt som filtreras i **Ämneslista** vy. Du kan sedan öppna den här ämneslistefilen i en CSV-redigerare.

**Hantera flera metadata samtidigt från metadatarapporten**

Med AEM Guides kan du tagga DITA-innehåll från webbredigeraren. Du kan lägga till taggar i ett enskilt ämne eller använda funktionen för grupptaggning för att lägga till flera taggar i flera ämnen, en DITA-karta eller på en underkarta. Du kan också ändra dokumentläget för alla markerade ämnen till nästa möjliga gemensamma dokumentläge.

## Visa metadata

Så här visar du metadata för referenserna i den aktuella DITA-kartan:

1. Öppna DITA-schemafilen i Kartvyn på databaspanelen.
1. Klicka på **Hantera** -fliken.
1. Dubbelklicka **Metadata** till vänster. Metadatalistan med alla referenser i DITA-kartan visas. Detta inkluderar även mediereferenserna.

   ![](images/web-editor-metadata-panel.png){width="800" align="left"}

1. Från **Filter** kan du filtrera ämnen baserat på **Dokumenttillstånd** \(aktuell status för dina ämnen. Om dina ämnen till exempel är i redigeringsläge, granskningsläge eller granskningsläge, visas de här avsnitten\), **Referenser** \(direkt eller indirekt\), **Filtyp** \(Karta, ämne och bild\) för referensen.
1. Du kan även välja att bara visa **Filer utan taggar** eller också väljer du särskilda taggar i **Taggar** för att visa de filer som är associerade med dem.
   1. Du kan också använda följande alternativ för ämnesfiltrering för att välja att visa följande kolumner i metadatalistan:
      - **Titel** \(markerat som standard\) Titeln på den refererade filen anges på DITA-kartan. Du kan klicka på filen för att redigera den.Du kan också klicka på och spela upp en ljud- eller videofil i Web Editor. Du kan ändra volymen eller vyn för videon. På snabbmenyn har du också möjlighet att hämta, ändra uppspelningshastighet eller visa bild-i-bild.

        >[!NOTE]
        >
        > En utcheckningsikon visas också nära titeln på en utcheckad fil. Du kan hålla muspekaren över ikonen för att visa namnet på användaren.

      - **Filnamn** Filens namn.
      - **Filplats** Den fullständiga sökvägen till filen.
      - **Taggar** \(markerat som standard\) Taggar som används i filen.

        >[!NOTE]
        >
        > Som standard kan du visa två taggar för en fil. Om du vill visa fler taggar klickar du på **Visa fler**. Klicka **Visa mindre** för att dra ihop listan igen.

      - **Referenstyp** Typ av referens - direkt eller indirekt
      - **Dokumenttillstånd** \(markerat som standard\) Referensfilens aktuella läge.
      - **Filtyp** \(markerat som standard\) Källfilens typ. De tillgängliga alternativen är Karta, Ämne och Bild.
      - **Utcheckad av** Den användare som har checkat ut filen.
1. Klicka **Hämta CSV** om du vill hämta den aktuella ögonblicksbilden av referenserna i DITA-kartan. CSV-filen innehåller de markerade kolumnerna och de referenser som filtreras i ämneslistvyn. Du kan sedan öppna den här CSV-metadatafilen i valfri CSV-redigerare.

**Uppdatera metadata**

1. Om du vill uppdatera metadata markerar du de filer som du vill uppdatera.

   >[!NOTE]
   >
   > Du kan inte markera några utcheckade filer. En utcheckningsikon visas också nära titeln på en utcheckad fil. Du kan hålla muspekaren över ikonen för att visa namnet på användaren.

1. Välj **Hantera** uppifrån.

   ![](images/web-editor-manage-metadata.png){width="350" align="left"}

1. Om du vill lägga till nya taggar väljer du nya taggar i listrutan för att använda dem i alla markerade avsnitt. Du kan också ta bort taggar genom att klicka på kryssikonen bredvid taggen.

   >[!NOTE]
   >
   > De vanliga taggarna som används för alla markerade ämnen visas.

1. Välj ett nytt dokumentläge om du vill ändra dokumentläget för alla markerade referenser. I listrutan visas det vanliga möjliga läget för alla valda ämnen. Om det aktuella läget för dina ämnen till exempel är Under granskning kan du visa läget Utkast, Godkänd eller Granskad.
1. Klicka **Uppdatera** för att uppdatera metadata. Ett bekräftelsemeddelande visas för metadatan, oavsett om de har uppdaterats eller inte. Du kan även klicka **Ladda ned rapport** om du vill hämta metadata-CSV-filen från bekräftelsedialogrutan. Den här CSV-filen innehåller information om uppdateringsstatus för de valda referenserna.

## Generera en multimedierapport

The **Multimedia** rapporten innehåller detaljerad information om de multimedia som används på kartan, t.ex. titel, typ \(ljud, video och bilder\), filer som multimedia används i och referenstyp för de filer som de har använts i. Du kan också visa UUID och platsen för multimedia i databasen. Du kan skapa en rapport om multimedia genom att utföra följande steg:

1. I **Databas** öppnar du DITA-schemafilen i Kartvyn.
1. Klicka på **Hantera** -fliken.
1. Dubbelklicka **Multimedia** till vänster. Listan över multimedia som finns i DITA-kartan visas.
1. Från **Filter** kan du sortera listan efter multimedia eller efter namnen som används i referenser.

   - När du beställer **Multimedia**, visas multimedias***namn i den första kolumnen och sedan visas namnen på alla referenser i vilka de har använts i en annan kolumn på samma rad. På följande skärmbild visas multimedia WarmCoolForC.gif i den första kolumnen och tre referenser som den används i visas i den tredje kolumnen på samma rad.

     ![](images/multimedia-report-file-order.png){width="650" align="left"}

   - Om du beställer av **Används i** -kolumnen visas den omformade vyn där namnen på de referenser i vilka multimedia har använts listas i den första kolumnen medan multimedienamnen listas i en annan kolumn på separata rader. På följande skärmbild visas namnen på tre referenser \(Justera platstemperaturen, Ändra visning av platstemperatur och besättningsområde\) i den första kolumnen och multimediafilen WarmCoolForC.gif visas i den tredje kolumnen på tre separata rader.

     ![](images/multimedia-report-used-in-order.png){width="650" align="left"}

1. Du kan filtrera multimedia baserat på **Multimediatyp** och **Referenstyp**. Listan med multimediefiler visas baserat på dina val i listrutan. Du kan t.ex. välja att bara visa ljudreferenserna på DITA-kartan, och en fil visar bara de ljudreferenser som används i den.

   >[!NOTE]
   >
   > Beroende på vilken typ av multimedia som används på kartan visas bild, video och ljud i **Multimediatyp** och Direkt eller Indirekt finns i **Referenstyp** nedrullningsbar meny.

1. Du kan också använda följande filtreringsalternativ för att välja att visa följande kolumner i listan:

   - **Multimedia** \(markerat som standard\) Multimediets titel anges på DITA-kartan. Du kan klicka på multimediet för att redigera det.
   - **Multimediaplats** Multimediets fullständiga sökväg.
   - **Multimedia UUID** Filens universellt unika identifierare \(UUID\).
   - **Multimediatyp** \(markerat som standard\) Multimedietyp. De tillgängliga alternativen är Ljud, Video eller Bild.
   - **Används i** \(markerat som standard\) De referenser som multimedia har använts i. Du kan klicka på referensen för att redigera den.
   - **Referenstyp** \(markerat som standard\) Referenstypen - direkt eller indirekt.
   >[!NOTE]
   >
   > Klicka **Uppdatera** om du vill få en ny lista över multimedia och visa alla ändringar i kartfilen eller om några multimedia på din DITA-karta uppdateras.

1. Du kan också klicka på och spela upp en ljud- eller videofil i Web Editor. Du kan ändra volymen eller vyn för videon. På snabbmenyn har du också möjlighet att hämta, ändra uppspelningshastighet eller visa bild-i-bild.

   ![](images/video-web-editor.png){width="800" align="left"}

1. Klicka **Hämta CSV** om du vill hämta den aktuella ögonblicksbilden av multimedia på DITA-kartan. CSV innehåller de markerade kolumnerna och multimedia som filtreras i **Multimedia** vy. Du kan sedan öppna den här multimediala CSV-filen i valfri CSV-redigerare.


## Visa och korrigera brutna länkar{#report-broken-links}

The **Brutna länkar** är en användbar rapport som ger dig information om de brutna länkar som finns på din aktuella karta. Du kan visa brutna länkar, som kan vara för DITA-avsnitt, multimediafilreferenser, innehållsnyckelreferenser och så vidare. Du kan också åtgärda dem här själv.
Rapporten innehåller detaljerad information om exempelvis den brutna länken, länktypen, filer som referensen används i och vilken typ av filer som de har använts i.
Du kan visa rapporten för brutna länkar genom att utföra följande steg:
1. I **Databas** öppnar du DITA-schemafilen i Kartvyn.
1. Klicka på **Hantera** -fliken.
1. Dubbelklicka **Brutna länkar** till vänster. Listan med brutna länkar eller referenser i DITA-kartan visas.
1. Från **Filter** kan du sortera listan efter länkar eller efter namnen som används i referenser.

   - När du beställer efter **Bruten länk**, visas sökvägarna för de brutna länkarna i den första kolumnen och sedan visas namnen på alla referenser i vilka de har använts i en annan kolumn på separata rader. Om samma brutna länk används i flera filer visas de på en rad och visas som grupperade eller underrader. På följande skärmbild visas tre brutna länkar i den första kolumnen och den referens som de används i: `TestMap.ditamap` visas i den tredje kolumnen på tre separata rader.
   ![](images/broken-link-report.png){width="800" align="left"}

   - Om du beställer via **Används i** -kolumnen visas den omformade vyn där namnen på referenserna där de brutna länkarna har använts listas i den första kolumnen medan de brutna länkarna listas i en annan kolumn på samma rad. I följande skärmbild visas referensen (i vilken den brutna länken används) `TestMap.ditamap` i första kolumnen och de brutna länkarna visas i tredje kolumnen på samma rad.
   ![](images/broken-link-filter-usedin.png){width="800" align="left"}
1. Du kan filtrera brutna länkar baserat på **Filtyp** och **Länktyp**. Listan med brutna länkar visas baserat på ditt val i listrutan. Du kan t.ex. välja att bara visa innehållsreferenserna på DITA-kartan, och en fil visar bara de innehållsreferenser som används i den.

   Beroende på vilken typ av referenser som används i kartan visas filreferens, nyckelreferens, innehållsreferens, innehållsnyckelreferens, bildreferens och multimediefilsreferens i **Länktyp** nedrullningsbara menyer, och **DITA-ämne** eller **DITA-karta** finns listade i **Filtyp** nedrullningsbar meny.
1. Du kan också använda följande filtreringsalternativ för att välja att visa följande kolumner i listan:

   - **Bruten länk** (markerat som standard) Sökvägen till den brutna länken anges i DITA-kartan.

   - **Länktyp** (markerat som standard) Länkens typ. De tillgängliga alternativen är Content Key Reference, Content Reference, DITA Topic, File Reference, Image Reference, Key reference och Multimedia File Reference.

   - **Används i** (markerat som standard) Referenserna där den brutna länken har använts. Du kan klicka på referensen för att visa den i redigeringsläge.

   - **Filtyp** (markerat som standard) Referenstypen - DITA-schema eller DITA-ämne.
Klicka **Uppdatera** om du vill få en ny lista över brutna länkar och visa ändringar i kartfilen eller om någon bruten länk i DITA-kartan uppdateras.
1. Klicka på **Åtgärda länk** ikon (![](images/fix-broken-link.svg)) för att åtgärda den brutna länken.

   >[!NOTE]
   >
   > Håll pekaren över den brutna länksökvägen under kolumnen Bruten länk för att visa länken Korrigera (![](images/fix-broken-link.svg)).

   Du kan korrigera en länk i båda vyerna - när du har beställt av **Brutna länkar** eller av **Används i**.

   >[!NOTE]
   >
   > När du åtgärdar en bruten länk medan du har sorterat efter brutna länkar, kommer länken att korrigeras i alla filer där den används (som grupperas på en rad).

1. Du måste uppdatera den nödvändiga referensinformationen i dialogrutan **Uppdatera länk** -dialogrutan. Information som krävs i **Uppdatera länk** beror på typen av referens.\
   När du har åtgärdat en länk visas den inte under listan med brutna länkar. I stället kan du visa den under Ämneslista eller Metadata.

1. Klicka **Hämta CSV** om du vill hämta den aktuella ögonblicksbilden av de brutna länkarna i DITA-kartan. CSV-filen innehåller de markerade kolumnerna och de brutna länkarna som filtreras i vyn Brutna länkar. Du kan sedan öppna och visa den här CSV-filen i valfri CSV-redigerare.


**Överordnat ämne:**[ Rapporter](reports-intro.md)
