---
title: Vyer i Web Editor
description: Lär dig hur du visar Web Editor
exl-id: 86d8abc2-1d0e-4744-91c9-848c00447971
source-git-commit: 8073716bccacbe8d6a158b44d5106b083e3a5dcd
workflow-type: tm+mt
source-wordcount: '1424'
ht-degree: 0%

---

# Vyer i Web Editor {#id204GK0D0V5Z}

AEM Guides Web Editor har stöd för att visa dokument i tre olika lägen eller vyer:

## Författare

Det här är en typisk vy som du ser i vyn What You Get \(WYSISYG\) i webbredigeraren. Du kan redigera ämnen på samma sätt som i vanliga RTF-redigerare. I redigeringsvyn har du möjlighet att spara en revision av dokumentet, söka och ersätta innehåll, infoga element, infoga hyperlänk, infoga innehållsreferens och mycket annat.

>[!NOTE]
>
> När du använder innehållsreferensen visas även det refererade innehållet i redigeringsvyn i blå färg. Det refererade innehållet går inte att redigera.

## Källa

I källvyn visas den underliggande XML-koden som avsnittet består av. Om du är van vid att arbeta med XML direkt bör du använda källvyn. Förutom att göra vanliga textredigeringar i den här vyn kan du även lägga till element och attribut med den smarta katalogen eller söka och ersätta text, element eller attribut.

- Om du vill anropa den smarta katalogen placerar du markören i slutet av en elementtagg där du vill infoga det nya elementet och skriver &quot;&lt;&quot;. Redigeraren visar en lista med alla giltiga XML-element som du kan infoga på den platsen. Använd piltangenterna för att markera det element som du vill infoga och tryck på Retur. När du anger avslutande parentes &quot;\> läggs sluttaggen för elementet till automatiskt.

   ![](images/smart-catalog-elements.png){width="400" align="left"}

- Du kan också enkelt ändra ett element från källvyn. Om du till exempel ändrar starttaggen för en `p` element till `note`och sedan stänger `p` taggen ändras automatiskt till `/note`. Om du ersätter ett element med ett felaktigt element visas valideringsfelet omedelbart.

- Om du vill lägga till ett attribut i ett element placerar du markören inuti elementtaggen och trycker på blankstegstangenten. En lista med giltiga attribut för det elementet visas i den smarta katalogen. Använd piltangenterna för att markera det önskade elementet och tryck på Retur för att infoga elementet. Om du vill ange ett värde för attributet anger du lika med-tecknet \(=\) och redigeraren anger automatiskt inledande och avslutande citattecken &quot;&quot;, där du kan ange attributets värde.

   ![](images/smart-catalog-attribute.png){width="350" align="left"}

- I källvyn finns det ett alternativ för automatiskt indrag som ordnar om XML-koden i ett presenterbart och lättläst format. Om du markerar en text och växlar från författare till källa eller från källa till författare, markeras den markerade texten även i den andra vyn.
- En annan kraftfull funktion i källvyn är XML-valideringen i dokumentet. Om du öppnar ett dokument som innehåller ogiltig XML öppnas det i källvyn med information om ogiltig XML. I följande skärmbild visas den exakta informationen om den felaktiga XML:en i popup-fönstret Tolkningsfel.

   ![](images/invalid-topic-xml.png){width="650" align="left"}

   På skärmbilden ovan används en markering som pekar på raden som innehåller felaktig XML.

- Med funktionen Sök och ersätt kan du söka efter text, element eller attribut i källvyn.
Mer information finns i **Sök och ersätt** funktionsbeskrivning i [Huvudverktygsfältet](web-editor-features.md#id#id2051EA0G05Z) -avsnitt.

- I källvyn finns många kortkommandon som du kan använda för att snabbt navigera och arbeta med dokument. I följande tabell visas vilka åtgärder som stöds och deras kortkommandon:

   | För att göra detta | Använd den här genvägen |
   |----------|-----------------|
   | Lägga till flera markörer | **Ctrl**+Vänsterklicka |
   | Flera textmarkeringar som inte följer varandra | **Ctrl**+Vänsterklicka för att dra och markera text |
   | Markera text över och mellan rader | **Alt**+Vänsterklicka för att dra och markera text |
   | Ångra flera markeringar eller avsluta helskärmsläge | **Esc** |
   | Visa automatisk komplettering | **Ctrl**+**Blanksteg** |
   | Gå till den aktuella taggens öppningstagg eller avslutande tagg | **Ctrl**+**J** |
   | Expandera eller komprimera den aktuella taggen och dess innehåll | **Ctrl**+**Q** |
   | Markera det aktuella elementet och dess innehåll | **Ctrl**+**L** |
   | Dra ut aktuellt element | **Skift**+**Tabb** |
   | Ta bort det aktuella elementet och dess innehåll | **Skift**+**Ctrl**+**K** |
   | Flytta markören ett ord åt vänster | **Alt**+**Vänsterpil** |
   | Flytta markören ett ord åt höger | **Alt**+**Högerpil** |
   | Rulla en rad uppåt utan att ändra markörens plats | **Ctrl**+**Uppåtpil** |
   | Bläddra en rad nedåt utan att ändra markörens plats | **Ctrl**+**Nedåtpil** |
   | Växla helskärm | **F11** |
   | Infoga en ny rad efter det aktuella elementet | **Ctrl**+**Retur** |
   | Infoga en ny rad före det aktuella elementet | **Skift**+**Ctrl**+**Retur** |
   | Sök efter och markera nästa förekomst av det aktuella ordet | **Ctrl**+**D** |
   | Flytta det aktuella elementet och dess innehåll ett element uppåt | **Skift**+**Ctrl**+**Uppåtpil** |
   | Flytta det aktuella elementet och dess innehåll ett element nedåt | **Skift**+**Ctrl**+**Nedåtpil** |
   | Radbryt det aktuella elementet i kommentartaggen | **Ctrl**+**/** |
   | Duplicera det aktuella elementet och dess innehåll | **Skift**+**Ctrl**+**D** |
   | Ta bort text efter markören. Om markören står före ett öppningselement tas hela elementet bort. | **Ctrl**+**K**+**K** |
   | Radera text till vänster om markören på den aktuella raden. Om markören står efter den avslutande taggen för ett element tas hela elementet bort. | **Ctrl**+**K**+**Backsteg** |
   | Konvertera den aktuella texten till versaler | **Ctrl**+**K**+**U** |
   | Konvertera den aktuella texten till gemener | **Ctrl**+**K**+**L** |
   | Bläddra det aktuella elementet till mitten av redigeraren | **Ctrl**+**K**+**C** |
   | Lägg till en markör ovanför den aktuella positionen | **Ctrl**+**Alt**+**Uppåtpil** |
   | Lägg till en markör under den aktuella positionen | **Ctrl**+**Alt**+**Nedåtpil** |
   | Hitta det aktuella ordet rekursivt \(i framåtriktning\) | **Ctrl**+**F3** |
   | Hitta det aktuella ordet rekursivt \(i bakåtriktning\) | **Skift**+**Ctrl**+**F3** |


## Förhandsgranska

När du öppnar ett ämne i förhandsgranskningsläget visas hur ett ämne kommer att visas när det visas av en användare i webbläsaren. Om det är en DITA-karta visas en förhandsvisning av kartan där ett sammansatt dokument med alla ämnen på kartan visas.

I förhandsgranskningsläget kan du använda följande funktioner:

- [Visa innehåll baserat på villkorsstyrda filter](#id2114BI00VXA)
- [Visa ändringsmarkeringar för spårning](#id2114BJ00CE8)
- [Exportera ett ämne som PDF](#id2114BL00B5U)

### Visa innehåll baserat på villkorsstyrda filter {#id2114BI00VXA}

Om du har använt villkor i ett ämne eller en karta visas dessa villkor på panelen Filter. Som standard markeras alla villkor och hela innehållet visas. Om du avmarkerar ett villkor tas innehållet med det villkoret bort från vyn. Du kan också välja att markera villkorat innehåll.

I följande bild visas ett ämne som använder två villkor: `Audience` och `Product`. Det villkorade innehållet markeras med gul bakgrund.

![](images/preview-filters.png){width="800" align="left"}

### Visa ändringsmarkeringar för spårning {#id2114BJ00CE8}

Om ett dokument innehåller spåra ändringar av markeringar \(eller visuella tecken\) kan du även förhandsgranska dokumentet med eller utan dessa markeringar. När du förhandsgranskar ett dokument innehåller den högra panelen alternativen Filter och Spärra/knip.

![](images/preview-tracking_cs.png){width="400" align="left"}

Det finns tre **Spårning** alternativ som du kan välja mellan:

- **Ingen markering**: I den här vyn accepteras alla infogningar och borttagningar och en enkel vy av dokumentet visas. I den här vyn visas inga ändringsmarkeringar för spår.
- **Original**: I den här vyn avvisas alla infogningar och alla borttagningar återställs och en förhandsvisning visas. Du får helt enkelt originalformuläret för dokumentet innan du aktiverade läget för spårändringar.
- **Visa markering**: I den här vyn får du alla markeringar för infogat och borttaget innehåll.

   I följande bild visas förhandsgranskningen av en kartfil med markeringar:

   ![](images/preview-map-with-track-changes.PNG){width="800" align="left"}


### Exportera ett ämne som PDF {#id2114BL00B5U}

PDF är ett av de vanligaste utdataformaten som används i alla möjliga steg i dokumentutvecklingscykeln. Med AEM stödlinjer kan du skapa PDF för ett enskilt ämne eller en hel kartfil. Med funktionen Exportera som PDF kan författaren, utgivaren eller en administratör enkelt generera PDF-utdata för ett enskilt ämne. Den använder DITA-OT-konfigurationer som sparats i mappnivåprofilen för att generera PDF.

Den här funktionen har stöd för följande funktioner:

- Generera PDF till den aktuella arbetskopian av ett ämne.
- Acceptera DITA-OT-omformningsnamnet och kommandoradsargumenten för att generera PDF.
- Spara genererade utdata på det lokala systemet.
- Lös de nyckel- och innehållsreferenser som används i avsnittet innan utdata genereras.

Så här exporterar du ett ämne som PDF:

1. Öppna ämnet i förhandsgranskningsläget.

1. Klicka på **Exportera som PDF** \(![](images/export-as-pdf-icon.svg)\) ikon.

   Dialogrutan Exportera som PDF visas.

   ![](images/export-as-pdf-dialog.png){width="350" align="left"}

1. *\(Valfritt\)* Ange DITA-OT-omformningsnamnet och eventuella kommandoradsargument som du vill använda.

1. Klicka **Hämta**.

   >[!NOTE]
   >
   > Kontrollera att du har aktiverat popup-fönstret i webbläsarkonfigurationen, annars hämtas inte PDF.

   PDF genereras och öppnas på en ny flik eller så visas en dialogruta där du kan spara PDF på ditt lokala system.


**Överordnat ämne:**[ Arbeta med webbredigeraren](web-editor.md)
