---
title: Andra funktioner i Web Editor
description: Utforska andra funktioner i webbredigeraren i AEM. Lär dig hur du använder de här funktionerna för att förbättra redigeringen i AEM.
exl-id: 1833b1e3-c7f1-4f2c-be35-235b65ba2f36
source-git-commit: e8a912b0f8bc690fceade0b54bb36057a727ab33
workflow-type: tm+mt
source-wordcount: '2248'
ht-degree: 0%

---

# Andra funktioner i Web Editor {#id2056B0B0YPF}

Det finns några andra användbara funktioner i Web Editor som du kan använda:

**Snabbmenyfunktioner på en fils flik**

När du öppnar en fil i Web Editor kan du utföra olika åtgärder på snabbmenyn. Du kan se olika alternativ beroende på om du öppnar en mediefil, en DITA-fil eller flera filer.

**Mediefil**

Du får följande funktioner på snabbmenyn för en öppnad mediefils flik:

![](images/media-file-context-menu.png){width="300" align="left"}

**En enda DITA-fil**

Du får följande funktioner på snabbmenyn för en öppen fils flik:

:   ![](images/single-file-context-menu.png){width="300" align="left"}

**Flera filer**

När du har flera filer öppna får du fler alternativ på snabbmenyn:

![](images/multiple-files-context-menu.png){width="550" align="left"}

De olika alternativen på snabbmenyn förklaras nedan:

***Spara***: Du kan välja mellan följande alternativ:

- **Spara**: Om du vill spara en fil utan att skapa en ny version väljer du **Spara**. När du skapar ett nytt ämne skapas en versionslös arbetskopia av ämnet i DAM. När du sparar dokumentet uppdateras arbetskopian av dokumentet i DAM. När du sparar en version på ett enkelt sätt skapas ingen ny version av ett ämne. Om ditt ämne är under granskning kan inte dina granskare få åtkomst till det ändrade ämnesinnehållet om du sparar ett ämne.

- **Spara alla**: Om flera dokument är öppna i Web Editor kan du även välja att **Spara alla** öppna dokument.


***Spara som ny version***

Om du vill skapa en ny version av filen väljer du **Spara som ny version**. Mer information om **Spara** och **Spara som ny version**, se [Bekanta dig med Web Editors funktioner](web-editor-features.md#).

***Kopiera***: Du kan välja mellan följande alternativ:

- **Kopiera UUID**: Om du vill kopiera UUID för den aktiva filen till Urklipp väljer du **Copy \> Copy UID**.
- **Kopiera bana**: Om du vill kopiera den fullständiga sökvägen till den aktiva filen till Urklipp väljer du **Kopiera \> Kopiera bana**.


***Sök i***: Du kan välja mellan följande alternativ:

- **Karta**: Om du har öppnat en stor DITA-karta och vill hitta den exakta platsen för en fil på kartan väljer du **Hitta på kartan \>**. När du väljer alternativet Hitta i karta, placeras filen \(från vilken alternativet anropas\) och markeras i karthierarkin. Om du vill kunna använda den här funktionen måste du öppna kartfilen i Web Editor. Om Kartvyn är dold visas kartvyn när funktionen anropas och filen markeras i karthierarkin.

- **Databas**: Liknar Hitta på karta, **Sök i databasen \>** visar platsen för filen i databasen \(eller DAM\). Databasvyn öppnas och den valda filen markeras i databasen. Om filen finns i en mapp utökas den mappen så att den visar den valda filens plats i databasen.


***Lägg till***: Du kan välja mellan följande alternativ:

- **Favoriter**: Om du vill lägga till den valda filen i favoritsamlingen väljer du **Lägg till i \> Favoriter**. Mer information finns i **Favoriter** funktionsbeskrivning i [Vänster panel](web-editor-features.md#id2051EA0M0HS) -avsnitt.



- **Återanvändbart innehåll**: Om du vill kopiera den markerade filen till listan över återanvändbart innehåll väljer du **Lägg till i \> återanvändbart innehåll**. Mer information finns i **Återanvändbart innehåll** funktionsbeskrivning i [Vänster panel](web-editor-features.md#id2051EA0M0HS) -avsnitt.




***Egenskaper***

Om du vill visa AEM egenskapssida för den markerade filen väljer du **Egenskaper**.

***Dela***: Du kan välja mellan följande alternativ:

**Upp, Ned, Vänster eller Höger**

Som standard kan du visa ett avsnitt i taget i Web Editor. Det kan finnas tillfällen då du vill se två eller flera ämnen samtidigt. Genom att dela redigerarens skärm kan du visa flera ämnen samtidigt. Om du till exempel har två ämnen - A och B öppnade i redigeraren. Högerklicka på ämne B och välj **Dela \> uppåt** delar upp redigeringsfönstret i två delar. Ämne B visas i den övre halvan och ämne A visas i den nedre halvan. På samma sätt kan du dela skärmen vågrätt genom att markera **Dela \> vänster** eller **Dela \> höger**. I följande skärmbild av Web Editor visas ämnen som delas vågrätt och lodrätt. I varje delning kan du ha olika vyer. På följande skärmbild är skärm 1 i källvyläge, skärm 2 har två dokument öppna i redigeringsläge och skärm 3 är i förhandsgranskningsläge. Du kan flytta dokument från en skärm till en annan genom att dra filfliken och släppa den på skärmen där du vill placera den. På samma sätt kan du ändra ordning på filflikarna genom att dra och flytta dem som du vill.

![](images/split-editor.png){width="800" align="left"}

***Snabbgenerering***

Generera utdata för den valda filen. Utdata kan bara genereras för filer som är en del av en förinställning. Mer information finns i [Artikelbaserad publicering från webbredigeraren](web-editor-article-publishing.md#id218CK0U019I).

***Stäng***: Du kan välja mellan följande alternativ:

**Stäng**, **Stäng andra**, eller **Stäng alla**

Om du vill stänga filen som du anropade snabbmenyn från väljer du **Stäng \> Stäng**. Använd **Stäng \> Stäng andra** om du vill stänga alla andra öppna filer förutom den aktiva filen. Om du vill stänga alla öppna filer väljer du **Stäng \> Stäng alla** på snabbmenyn eller så kan du välja att stänga webbredigeraren. Om det finns filer som inte har sparats i sessionen uppmanas du att spara dessa filer.

**Stäng filer och spara scenarier**

När du försöker stänga en fil som har öppnats i Web Editor med **Stäng** på fliken eller **Stäng** på Alternativ-menyn uppmanas du av AEM att spara redigeringarna och låsa upp en låst fil.

Frågorna baseras på följande konfigurationer som valts av administratören:

- **Fråga efter incheckning vid stängning:** Du kan checka in filen \(som du har checkat ut\) när du stänger redigeraren.
- **Fråga efter ny version vid stängning**: Du kan spara filen \(som du har redigerat\) som en ny version när du stänger redigeraren.

Hur du sparar filer beror på följande tre scenarier:

- Har inte gjort några ändringar i innehållet.
- Redigerade innehållet och sparade ändringarna.
- Innehållet har redigerats men ändringarna har inte sparats.

Du kan se följande alternativ beroende på om filen är låst/olåst och har sparade eller osparade ändringar:

- **Lås upp och stäng**: Låset på filen släpps och filen stängs.

  ![](images/file-close-unlock-file.png){width="400" align="left"}

- **Spara som ny version**: Då sparas de ändringar du har gjort i innehållet och en ny version av filen skapas. Du kan också lägga till etiketter och kommentarer för den nyligen sparade versionen. Mer information om hur du sparar en ny version finns i [Spara som ny version](web-editor-features.md#save-as-new-version-id209ME400GXA).

- **Lås upp filen**: Om du låser upp en fil kommer den att låsa upp filen och ändringarna sparas i den aktuella versionen av filen.

  >[!NOTE]
  >
  > Om du avmarkerar alternativet att låsa upp filen får du också ett alternativ för att stänga filen utan att spara ändringarna.

  Till exempel visas en av uppmaningarna på följande skärmbild:

  ![](images/file-close-save-changes-unlock.png){width="400" align="left"}

**Visuella tecken för brutna referenser**

- Om ditt ämne innehåller brutna korsreferenser eller innehållsreferenser visas de i röd text.

**Smart copy-paste**

- Du kan enkelt kopiera och klistra in innehåll inom och mellan ämnen. Källelementets struktur bevaras på målet. Om det kopierade innehållet innehåller innehållsreferenser kopieras även dessa.

**Kom ihåg den senast bläddrade platsen**

- I Web Editor finns en smart dialogruta för filbläddring. Redigeraren kommer ihåg den senast använda platsen när en referens eller ett innehåll infogas. Första gången du öppnar dialogrutan för filbläddring, \(via Infoga referens eller Infoga återanvänd innehåll\), flyttas du till den plats där det aktuella dokumentet sparas. Om du under samma session försöker infoga en annan referens navigerar dialogrutan för filbläddring automatiskt till den plats där du infogade den senaste referensen.

>[!NOTE]
>
> Om det gäller en bild-, ljud- eller videofil används filens plats som standard i dialogrutan för filbläddring, inte den plats som användes senast.

**Stöd för artikelbaserad publicering**

- I webbredigeraren kan du generera utdata för ett eller flera ämnen, eller för hela DITA-kartan. Du måste skapa förinställningar för DITA-kartan och sedan enkelt generera utdata för ett eller flera ämnen. Om du har uppdaterat några avsnitt på kartan kan du även generera utdata endast för dessa ämnen från Web Editor. Mer information finns i [Artikelbaserad publicering från webbredigeraren](web-editor-article-publishing.md#id218CK0U019I).

**Stöd för markeringsdokument**

- Med Web Editor kan du använda Markdown-dokument \(.md\) tillsammans med DITA-dokument. Du kan enkelt skapa och förhandsgranska ett markeringsdokument i Web Editor och även lägga till det i kartfilen via DITA-kartredigeraren. Mer information finns i [Skapa markeringsdokument från webbredigeraren](web-editor-markdown-topic.md#).

**Stöd för DITA ordlistetema**

- Webbredigeraren stöder DITA-ordlistor som du kan infoga genom att lägga till `term` eller `abbreviated-form` -element.

**Infoga MathML-ekvationer**

- AEM Guides ger ett körklart stöd för att infoga MathML-ekvationer genom integrering med [MathType Web](https://docs.wiris.com/en/mathtype/mathtype_web/intro) program. Om du vill infoga en MathML-ekvation klickar du på **Infoga element** och skriv mathml. När du väljer matematiska element i listan visas dialogrutan Infoga MathML:

![](images/insert-mathml-equation.png){width="550" align="left"}

Skapa ekvationen med MathML-ekvationsverktygen och klicka på Infoga för att lägga till den i dokumentet. Ekvationen infogas med ljusgrå bakgrund enligt nedan:

![](images/sample-mathml-equation.PNG){width="400" align="left"}

Du kan när som helst uppdatera en ekvation genom att högerklicka på en befintlig ekvation och välja **Redigera MathML** på snabbmenyn.

**Infoga fotnoter**

- Infoga en fotnot i innehållet genom att använda `fn` -element. I redigeringsläget visas fotnotens värde i linje med innehållet. När du byter förhandsgranskningsläge eller publicerar dokumentet visas dock fotnoten i slutet av avsnittet.

**Byta namn på eller ersätta ett element**

- I webbredigeraren visas elementets synliga del högst upp i avsnittet. Om du vill byta ut eller ersätta ett element mot ett annat element kan du göra det på snabbmenyn för vägbeskrivningsfilen. Du kan till exempel byta `p` element med `note` eller något annat giltigt element i sammanhanget.

![](images/rename-element.png){width="400" align="left"}

Högerklicka på namnet på ett element som du vill ersätta på sidlisten och välj sedan Byt namn på element på snabbmenyn. I dialogrutan Byt namn på element visas alla giltiga element som är tillåtna på den aktuella platsen. I dialogrutan Ändra namn på element markerar du det element som du vill använda. Det ursprungliga elementet ersätts med det nya elementet.

Förutom snabbmenyn för den synliga sökvägen kan du även öppna dialogrutan Byt namn på element från andra platser:

- Klicka på elementnamnet på vägbeskrivningen för att markera elementets innehåll och högerklicka på det markerade innehållet för att visa snabbmenyn.

- Aktivera taggvyn, klicka på öppningstaggen för ett element och högerklicka sedan på det markerade innehållet för att visa snabbmenyn.

- Du kommer åt dialogrutan Byt namn på element genom att öppna Alternativ-menyn för ett element på panelen Kontur.



**Radbryta ett element**

- När du kapslar ett element kan du lägga till en elementtagg i den markerade texten. Du kan radbryta texten till vilket underordnat element som helst enligt DITA-standarder. Om du till exempel har text under en `note` -element kan du kapsla in texten i `p` -element.

  The **Radbryt element** är tillgängligt på snabbmenyn för ämnesraden. Om du vill kapsla in ett element högerklickar du på elementet och öppnar snabbmenyn. Välj elementet från **Radbryt element** -dialogrutan. Texten visas i det nya elementet.

  Du kan också markera texten eller elementet i innehållet och sedan markera **Radbryt element**  på snabbmenyn.

**Dela upp ett element**

- Om du tar bort ett element kan du ta bort elementtaggen från den markerade texten och sammanfoga den med det överordnade elementet. Om du till exempel har en `p` element i en `note` -element kan du bryta upp `p` element som du vill sammanfoga texten direkt i `note` -element. The **Dela upp element** är tillgängligt på snabbmenyn för ämnesraden. Om du vill dela upp ett element högerklickar du på elementet för att öppna snabbmenyn och väljer sedan **Dela upp element** om du vill ta bort elementet och sammanfoga elementets text med dess överordnade element.

**Bevara radbrytningar och indrag**

- DITA-element som innehåller radbrytningar och blanksteg stöds och återges enligt definitionen i redigeringsläge, källläge eller förhandsgranskningsläge, och även i det slutliga publicerade resultatet. På följande skärmbild visas innehållet i `msgblock` element där radbrytningar och blanksteg \(indrag\) har bevarats:

![](images/new-line-support_cs.png){width="500" align="left"}

**Generera element-ID automatiskt**

- Du kan automatiskt generera ID:n för elementen i ditt DITA-avsnitt. Dessa ID:n är unika inom ett DITA-avsnitt. Om du till exempel genererar ID:n för ett styckeelement kommer ID:n att vara p\_1, p2, p\_3 och så vidare. Du kan välja flera element och generera ID:n för varje markerat element.

Gör följande för att automatiskt generera ID för ett eller flera element:

1. Öppna ämnet i webbredigeraren.
1. Markera innehållet som du vill tilldela ID:n till.
1. Högerklicka och välj **Generera ID:n på snabbmenyn.**

   Du kan också högerklicka i vägbeskrivningsfilen och välja **Generera ID**.


**Överordnat ämne:**[ Arbeta med webbredigeraren](web-editor.md)
