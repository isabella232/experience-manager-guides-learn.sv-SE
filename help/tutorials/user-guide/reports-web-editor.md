---
title: DITA-kartrapport från Web Editor
description: Lär dig DITA-kartrapport från Web Editor
source-git-commit: 895d9bd3587c871d5223df5b71403d10bdc3d762
workflow-type: tm+mt
source-wordcount: '1608'
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

   ![](images/web-editor-topiclist-panel.png)

1. Från **Filter** Panelen du kan filtrera ämnen baserat på **Referenstyp** \(direkt eller indirekt\), **Dokumenttillstånd** \(aktuell status för dina ämnen. Om dina ämnen till exempel är i läget Redigera, Under granskning eller Granskad visas de här alternativen) eller **Upphovsman** av ämnet.
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
   > Klicka **Uppdatera** om du vill få en ny lista med ämnen och se ändringar i kartfilen eller om referenser i ämnesfilen uppdateras.

1. Klicka **Hämta CSV** om du vill hämta den aktuella ögonblicksbilden av ämnena i DITA-kartan. CSV innehåller de markerade kolumnerna och de avsnitt som filtreras i **Ämneslista** vy. Du kan sedan öppna den här ämneslistefilen i en CSV-redigerare.

**Hantera flera metadata samtidigt från metadatarapporten**

Med AEM Guides kan du tagga DITA-innehåll från webbredigeraren. Du kan lägga till taggar i ett enskilt ämne eller använda funktionen för grupptaggning för att lägga till flera taggar i flera ämnen, en DITA-karta eller på en underkarta. Du kan också ändra dokumentläget för alla markerade ämnen till nästa möjliga gemensamma dokumentläge.

## Visa metadata

Så här visar du metadata för referenserna i den aktuella DITA-kartan:

1. Öppna DITA-schemafilen i Kartvyn på databaspanelen.
1. Klicka på **Hantera** -fliken.
1. Dubbelklicka **Metadata** till vänster. Metadatalistan med alla referenser i DITA-kartan visas. Detta inkluderar även mediereferenserna.

   ![](images/web-editor-metadata-panel.png)

1. Från **Filter** kan du filtrera ämnen baserat på **Dokumenttillstånd** \(aktuell status för dina ämnen. Om dina ämnen till exempel är i redigeringsläge, granskningsläge eller granskningsläge, visas de här avsnitten\), **Referenser** \(direkt eller indirekt\), **Filtyp** \(Karta, Ämne och Bild\) för referensen.
1. Du kan även välja att bara visa **Filer utan taggar** eller också väljer du särskilda taggar i **Taggar** för att visa de filer som är associerade med dem.
   1. Du kan också använda följande alternativ för ämnesfiltrering för att välja att visa följande kolumner i metadatalistan:
      - **Titel** \(markerat som standard\) Titeln på den refererade filen anges på DITA-kartan. Du kan klicka på filen för att redigera den.Du kan också klicka på och spela upp en ljud- eller videofil i Web Editor. Du kan ändra volymen eller vyn för videon. På snabbmenyn har du också möjlighet att hämta, ändra uppspelningshastighet eller visa bild-i-bild.

         >[!NOTE]
         >
         > En utcheckningsikon visas också nära titeln på en utcheckad fil. Du kan hålla muspekaren över ikonen för att visa namnet på användaren.

      - **Filnamn** Filens namn.
      - **Filplats** Filens fullständiga sökväg.
      - **Taggar** \(markerat som standard\) Taggar som används i filen.

         >[!NOTE]
         >
         > Som standard kan du se två taggar för en fil. Om du vill visa fler taggar klickar du på **Visa fler**. Klicka **Visa mindre** för att dra ihop listan igen.

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

   ![](images/web-editor-manage-metadata.png)

1. Om du vill lägga till nya taggar väljer du nya taggar i listrutan för att använda dem i alla markerade avsnitt. Du kan också ta bort taggar genom att klicka på kryssikonen bredvid taggen.

   >[!NOTE]
   >
   > De vanliga taggarna som används för alla markerade ämnen visas.

1. Välj ett nytt dokumentläge om du vill ändra dokumentläget för alla markerade referenser. I listrutan visas det vanliga möjliga läget för alla valda ämnen. Om det aktuella läget för dina ämnen till exempel är Under granskning, kan du visa läget Utkast, Godkänt eller Granskat.
1. Klicka **Uppdatera** för att uppdatera metadata. Ett bekräftelsemeddelande visas för metadatan, oavsett om de har uppdaterats eller inte. Du kan även klicka **Hämta rapport** om du vill hämta metadata-CSV-filen från bekräftelsedialogrutan. Den här CSV-filen innehåller information om uppdateringsstatus för de valda referenserna.

## Generera en multimedierapport

The **Multimedia** rapporten innehåller detaljerad information om de multimedia som används på kartan, till exempel titel, typ \(ljud, video och bilder\), filer som multimedia används i och referenstyp för de filer som de har använts i. Du kan också visa UUID och platsen för multimedia i databasen. Du kan skapa en rapport om multimedia genom att utföra följande steg:

1. I **Databas** öppnar du DITA-schemafilen i Kartvyn.
1. Klicka på **Hantera** -fliken.
1. Dubbelklicka **Multimedia** till vänster. Listan över multimedia som finns i DITA-kartan visas.
1. Från **Filter** kan du sortera listan efter multimedia eller efter namnen som används i referenser.

   - När du beställer **Multimedia**, visas multimedias***namn i den första kolumnen och sedan visas namnen på alla referenser i vilka de har använts i en annan kolumn på samma rad. På följande skärmbild visas multimedia WarmCoolForC.gif i den första kolumnen och tre referenser som den används i visas i den tredje kolumnen på samma rad.

      ![](images/multimedia-report-file-order.png)

   - Om du beställer av **Används i** -kolumnen visas den omformade vyn där namnen på de referenser som multimedia har använts i listas i den första kolumnen medan multimedianamnen listas i en annan kolumn på separata rader. På följande skärmbild visas namnen på tre referenser \(Justera platstemperaturen, Ändra visning av platstemperatur och besättningsområde\) i den första kolumnen och multimediafilen WarmCoolForC.gif visas i den tredje kolumnen på tre separata rader.

      ![](images/multimedia-report-used-in-order.png)

1. Du kan filtrera multimedia baserat på **Multimediatyp** och **Referenstyp**. Listan med multimediefiler visas baserat på dina val i listrutan. Du kan t.ex. välja att bara visa ljudreferenserna på DITA-kartan, och en fil visar bara de ljudreferenser som används i den.

   >[!NOTE]
   >
   > Beroende på vilken typ av multimedia som används på kartan visas bild, video och ljud i **Multimediatyp** och Direkt eller Indirekt finns i **Referenstyp** listruta.

1. Du kan också använda följande filtreringsalternativ för att välja att visa följande kolumner i listan:

   - **Multimedia** \(markerat som standard\) Multimediets titel anges på DITA-kartan. Du kan klicka på multimediet för att redigera det.
   - **Multimediaplats** Multimediets fullständiga sökväg.
   - **Multimedia UUID** Filens universellt unika identifierare \(UUID\).
   - **Multimediatyp** \(markerat som standard\) Multimedietyp. De tillgängliga alternativen är Ljud, Video eller Bild.
   - **Används i** \(markerat som standard\) De referenser som multimedia har använts i. Du kan klicka på referensen för att redigera den.
   - **Referenstyp** \(markerat som standard\) Referenstypen - direkt eller indirekt.

   >[!NOTE]
   >
   > Klicka **Uppdatera** om du vill få en ny lista över multimedia och se eventuella ändringar i kartfilen eller om några multimedia på din DITA-karta har uppdaterats.
1. Du kan också klicka på och spela upp en ljud- eller videofil i Web Editor. Du kan ändra volymen eller vyn för videon. På snabbmenyn har du också möjlighet att hämta, ändra uppspelningshastighet eller visa bild-i-bild.
   ![](images/video-web-editor.png)

1. Klicka **Hämta CSV** om du vill hämta den aktuella ögonblicksbilden av multimedia på DITA-kartan. CSV innehåller de markerade kolumnerna och multimedia som filtreras i **Multimedia** vy. Du kan sedan öppna den här multimediala CSV-filen i valfri CSV-redigerare.

**Överordnat ämne:**[ Rapporter](reports-intro.md)

