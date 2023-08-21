---
title: Bekanta dig med Web Editors funktioner
description: Lär dig hur du känner till Web Editor-funktionerna
exl-id: 38b378ff-da24-4560-a17f-a2c547aea1b8
source-git-commit: 48845ffcc530baad6689c8bca8847c57bbe9bf5d
workflow-type: tm+mt
source-wordcount: '15744'
ht-degree: 0%

---

# Bekanta dig med Web Editors funktioner {#id176NC500V5Z}

I det här avsnittet går du igenom de olika funktioner som är tillgängliga i Web Editor. Vi kan dela in Web Editor i följande avsnitt eller områden:

- [Huvudverktygsfältet](#id2051EA0G05Z)
- [Sekundärt verktygsfält](#id2051EA0J0Y4)
- [Vänster panel](#id2051EA0M0HS)
- [Innehållsredigeringsområde](#id2051EB000UI)
- [Höger panel](#id2051EB003YK)

Följande underavsnitt beskriver de olika avsnitten i Web Editor.

## Huvudverktygsfältet {#id2051EA0G05Z}

Huvudverktygsfältet finns längst upp i Web Editor och innehåller funktioner på filnivå och olika redigeringslägen som är tillgängliga i Web Editor. De funktioner som finns i det övre verktygsfältet förklaras på följande sätt:

**Spara alla** - ![](images/SaveFloppy_icon.svg)

Sparar de ändringar du har gjort i alla öppna ämnen. Om du har flera ämnen öppna i Web Editor klickar du på **Spara alla** eller med **Ctrl**+**S** kortkommandon sparar alla dokument med ett klick. Du behöver inte spara varje enskilt dokument.

>[!NOTE]
>
> Funktionen Spara skapar inte en ny version av dina ämnen. Om du vill skapa en ny version väljer du Spara som ny version.

**Spara som ny version** - ![](images/save-revision-icon.png)

Sparar de ändringar du har gjort i ämnet och skapar även en ny version av ämnet. Om du arbetar med ett nyligen skapat ämne visas versionsinformationen som **ingen**.

![](images/save-all-first-version-none_cs.png){width="800" align="left"}

Versionsnumret ändras för varje ny version som skapas för ämne- eller mappfilen.

När du väljer att spara ett ämne eller en karta med **Spara som ny version** visas följande dialogruta:

![](images/save-as-new-version-dialog.PNG){width="300" align="left"}

Ange kommentarer och versionsetiketter för att identifiera ändringarna och klicka på **Spara** för att skapa en ny version av filen.

När du väljer *Spara som ny version*, skapas den första versionen av ämnet i DAM, som också blir den aktiva versionen av ditt ämne. Om du senare återgår till en äldre version av ämnet blir det den aktuella aktiva versionen av ämnet.

Om administratören har förkonfigurerade versionsetiketter visas dessa i en listruta. Du kan välja en etikett i listan med tillgängliga etiketter och spara dokumentet.

![](images/web-editor-pre-defined-labels.PNG){width="300" align="left"}

När du sparar ett ämne kan du lägga till en kommentar som anger vilka ändringar du har gjort i ämnet. Den här kommentaren visas i ämnets Tidigare versioner.

Om ditt ämne är under granskning får granskarna ett meddelande om att det finns en nyare version av ämnet. De kan enkelt komma åt den senaste versionen av ditt dokument och fortsätta att granska den senaste versionen av ditt ämne.

När du håller pekaren över ett temats titel visas filsökvägen och versionsnumret.

![](images/mouse-hover-on-title_cs.png){width="800" align="left"}

>[!NOTE]
>
> När en version av ämnet är tillgänglig kan du även lägga till etiketter till ämnet. Dessa etiketter kan sedan användas för att skapa en baslinje för publicering av en viss version av dokumentet. Mer information om hur du använder etiketter i dina ämnen finns i [Använd etiketter](web-editor-use-label.md#).

**Ångra och Gör om** - ![](images/Undo_icon.svg) / ![](images/Redo_icon.svg)

Ångra eller Gör om den senaste åtgärden.

**Ta bort element** - ![](images/Delete_icon.svg)

Tar bort det markerade elementet eller elementet där markören är placerad.

**Sök och ersätt** - ![](images/FindAndReplace_icon.svg)

Funktionen Sök och ersätt är tillgänglig i redigerings- och källvyläge. Textfältet Sök och ersätt visas längst ned i ämnesredigeringsområdet. Du kan använda kortkommandona **CTRL**+**F** om du vill öppna fältet Sök och ersätt.

![](images/find-replace-bar.png){width="800" align="left"}

Använda inställningsikonen \(![](images/settings-find-replace-icon.svg)\) kan du växla **Ignorera skiftläge** och **Endast hela ord** sökalternativ. Om du vill utföra en skiftlägesokänslig sökning aktiverar du \(eller väljer\) **Ignorera skiftläge** alternativ. Annars, om du vill utföra den skiftlägeskänsliga sökningen, stänger du av \(eller avmarkerar\) **Ignorera skiftläge** alternativ. Du kan också söka efter ett helt ord.

Sökningen är omedelbar, vilket betyder att när du skriver sökfrasen eller ordet i **Sök** -fältet söks termen omedelbart igenom och markeras i ämnet. Om du vill ersätta en text i ett ämne anger du söktermen och ersätter den i respektive fält och klickar på **Ersätt** eller **Ersätt alla** -knappen.

I källvyn är Sök och ersätt mycket användbart när du söker efter ett visst element eller attribut. Om du till exempel vill ersätta värdet för `@product` kan du enkelt göra det från källvyn. I redigeringsvyn kan du inte söka baserat på ett attribut eller element. Du måste dock vara försiktig när du använder **Ersätt alla** -funktionen eftersom den kan skriva över XML-koden.

**Inställningar för Redigeraren** - ![](images/editor_settings_icon.svg)

Redigeringsinställningarna är bara tillgängliga för administrativa användare. Med hjälp av inställningarna kan en administratör konfigurera följande inställningar:

>[!NOTE]
>
> Om du uppdaterar några standardinställningar bör du öppna dokumenten på nytt för att ändringarna ska börja gälla.

- **Allmänt**: Med de allmänna inställningarna kan du konfigurera det lexikon som ska användas med Web Editor. Den här fliken innehåller tre avsnitt: **Stavningskontroll**, **Villkor** och **Redigering**.

  ![](images/editor-setting-general.png){width="650" align="left"}

   - **Stavningskontroll**: Det finns två alternativ — **AEM stavningskontroll** och **Stavningskontroll för webbläsare**. Som standard använder redigeraren funktionen Stavningskontroll i webbläsaren, där stavningskontrollen utförs med webbläsarens inbyggda ordlista. Du kan växla till AEM Stavningskontroll om du vill använda AEM ordlista, som också kan anpassas för att lägga till din egen ordlista. Mer information om hur du anpassar AEM lexikon finns i *Anpassa AEM standardordlista* i avsnittet Installera och konfigurera Adobe Experience Manager Guides as a Cloud Service.


   - **Villkor**

      - **Markera villkorlig text i redigeringsvyn**: Välj det här alternativet om du vill markera den villkorliga texten i författarvyn. Villkorsinnehållet markeras med den färg som är definierad för villkoret.

      - **Validera med villkorsattribut**: Välj det här om du vill tillåta validering av de värden som definierats för attributen. Detta förhindrar att du lägger till felaktiga värden.

      - **Visa nyckeln med titeln i ämnesschemapanelen**: Välj det här om du vill visa nycklarna tillsammans med rubrikerna i ämnesschemat. Om du inte väljer det här alternativet visas bara rubrikerna. Här visas till exempel nycklarna &#39;os&#39;, &#39;målgrupp&#39; och &#39;other&#39; tillsammans med titlarna.

        ![](images/subject-scheme-title.png){width="550" align="left"}

      - **Visa ämnesschema på villkorspanelen**: Välj det här om du vill visa ett ämnesschema på villkorspanelen. Om du avmarkerar detta visas de definierade villkoren på villkorspanelen.

   - **Redigering**

      - **Aktivera Ersätt alla**: Välj det här om du vill se ikonen Ersätt alla på panelen Sök och ersätt.


   - **Citat**
Ändra format på citat. Välj den källstil i listrutan som du vill använda i ditt projekt. Mer information finns i [Ändra format för citattecken](./web-editor-apply-citations.md#change-citation-style).


**Panel**: Den här inställningen styr panelerna som visas på den vänstra panelen i redigeraren. Du kan växla om du vill visa eller dölja den önskade panelen.

![](images/editor-setting-panel.png){width="650" align="left"}

>[!NOTE]
>
> Om en anpassad panel har konfigurerats visas den också i listan med paneler. Du kan växla om du vill visa eller dölja den anpassade panelen. Mer information om konfigurationen finns i *Konfigurera en anpassad panel i den vänstra panelen* i avsnittet Installera och konfigurera Adobe Experience Manager Guides as a Cloud Service.

- **Elementlista**: Som administratör kan du styra listan med element som en författare kan infoga med [Infoga element](#id204SG30105Z) och också ange elementets visningsnamn. Med inställningen Elements List kan du ange elementets namn enligt DITA-specifikationerna och en etikett som du vill använda i stället för det DITA-definierade elementnamnet:

  ![](images/editor-setting-element-list.png){width="650" align="left"}

På skärmbilden ovan visas `b` elementet har fått etiketten Fet, `codeblock` får en etikett av kodblocket tillsammans med några andra element. Om du väljer **Använd endast ovanför element** så visas endast de giltiga elementen \(vid den aktuella insättningspunkten\) i den här listan i popup-fönstret Infoga element.

I skärmbilden nedan visas endast 3 av 4 konfigurerade element från den föregående skärmbilden i det aktuella sammanhanget:

![](images/editor-setting-insert-element-list.PNG){width="300" align="left"}

- **Attributlista**: På liknande sätt som Elements-listan kan du styra listan med attribut och deras visningsnamn som ska visas i attributlistan för ett element. På följande skärmbild har bara tre attribut konfigurerats för att visas i ett elements attributlista:

![](images/editor-setting-attributes-list.png){width="650" align="left"}

När du försöker lägga till ett attribut i ett element med den här inställningen visas bara listan med attribut som konfigurerats i listan.

![](images/editor-setting-add-attributes-list.png-to-element.PNG){width="300" align="left"}

- **Visa attribut**: Precis som attributlistan kan du styra listan med attribut som ska visas i attributlistan för ett element. Som standard är fyra **Visa attribut** — målgrupp, plattform, produkt och props har konfigurerats för att visas i ett elements attributlista. Du kan också lägga till ett visningsattribut med **Lägg till** överst. Du kan även ta bort alla visningsattribut med **Ta bort** -ikon.

De attribut som är definierade för ett element visas i layoutvyn och dispositionsvyn.

![](images/editor-settings-display-attributes.png){width="550" align="left"}

- **Översättning**: Den här fliken innehåller ett alternativ för att sprida källetiketterna till målversionen.

   - **Sprid källversionsetiketter till målversionen**: Välj det här alternativet om du vill skicka etiketten för källfilsversionen till den översatta filen. Som standard är detta inaktiverat.

  ![](images/editor-setting-translation.png){width="550" align="left"}


**Användarinställningar** - ![](images/user_preference_editor_icon.svg)

Användarinställningarna är tillgängliga för alla författare. Med hjälp av inställningarna kan en författare konfigurera följande inställningar:

![](images/user_preference_editor.PNG){width="550" align="left"}

- **Använd enhetstema**: Markera den här kryssrutan om du vill att AEM stödlinjer automatiskt ska växla mellan ljusa och mörka teman baserat på temat på enheten.
- **Tema**: Du kan välja bland temana Ljus, Ljusast, Mörk eller Mörkast för redigeraren. När det gäller det ljusaste temat använder verktygsfälten och panelerna en ljusare grå bakgrund. När det gäller ljustemat använder verktygsfälten och panelerna ljusgrå bakgrund. När det gäller det mörkaste temat använder verktygsfälten och panelerna en mörkare svart bakgrund. När det gäller mörkt tema använder verktygsfälten och panelerna svart färgbakgrund. I alla teman visas området för innehållsredigering med vit färgbakgrund.

- **Mappprofiler**: Mappprofilen styr olika konfigurationer av villkorsattribut, redigeringsmallar, utdatainställningar och Web Editor-konfigurationer. Den globala profilen visas som standard. Om administratören dessutom har konfigurerat mappprofiler i systemet visas även dessa mappprofiler i listan Mappprofiler.

  De konfigurationer som en administratör kan definiera i mappprofilen är bland annat: anpassa användargränssnittet, bland annat verktygsfältsikonerna, Web Editor-layouten, kodavsnitten och rotkartan. Mer information finns i *Konfigurera globala profiler eller profiler på mappnivå* i as a Cloud Service Installera och konfigurera Adobe Experience Manager Guides.

  >[!NOTE]
  >
  > Namnet på den aktuella mappprofilen visas som etikett för ikonen för användarinställningar i huvudverktygsfältet.

- **Grundsökväg**: Som standard visas resurser från /content/dam-platsen när du öppnar AEM från Web Editor. Arbetsmappen finns förmodligen i mappen /content/dam/. Det krävs några klick för att komma till arbetsmappen varje gång. Du kan ange grundsökvägen till din arbetsmapp och i databasvyn visas sedan innehållet från den platsen direkt. Detta minskar tiden för åtkomst till din arbetsmapp. När du infogar en referens- eller mediefil i ditt ämne börjar filbläddringsplatsen med mappen inställd i bassökvägen.

- **Välj rotkarta**: Välj en DITA-kartfil för att lösa nyckelreferenser eller ordlisteposter. Den markerade rotkartan har högsta prioritet för att lösa nyckelreferenser. Mer information finns i [Lös nyckelreferenser](map-editor-other-features.md#id176GD01H05Z).


>[!NOTE]
>
> Om du inte vill använda något rotschema kontrollerar du att **Välj rotkarta** fältet är tomt.

**Författare, Källa och Förhandsgranska**

Mer information om de olika redigerings- och dokumentvisningslägena finns i [Vyer i Web Editor](web-editor-views.md#).

## Sekundärt verktygsfält {#id2051EA0J0Y4}

Det sekundära verktygsfältet visas när du öppnar ett ämne för redigering i webbredigeraren. De funktioner som är tillgängliga i det sekundära verktygsfältet förklaras på följande sätt:

**Infoga element** - ![](images/Add_icon.svg)

Infogar ett giltigt element på den aktuella eller nästa giltiga plats. Om du arbetar inuti ett blockelement som ett `note`använder du sedan ikonen Infoga element för att infoga ett nytt element efter `note` -element. I följande skärmbild har ett anteckningselement infogats i elementet p \(stycke\):

![](images/note-in-para-insert-element_cs.png){width="800" align="left"}

Om du trycker på Retur i anteckningselementet skapas ett nytt stycke i själva anteckningselementet. Om du vill infoga ett nytt element utanför anteckningen klickar du på p-elementet \(markerat i skärmbild\) i elementets vägbeskrivning och klickar på ikonen Infoga element eller trycker på ***Alt***+***Retur*** för att öppna popup-fönstret Infoga element. Markera sedan det önskade elementet och tryck på Retur för att infoga det markerade elementet efter anteckningselementet.

Du kan också lägga till ett element mellan två element när en blinkande blockmarkör visas.

![](images/Block-cursor.png){width="300" align="left"}

Om du till exempel arbetar med ett DITA-avsnitt och blockmarkören blinkar mellan den korta beskrivningen och brödtexten kan du lägga till `prolog` och lägg sedan till copyright, författare och annan information.

Ett annat sätt att ange nya element är att använda snabbmenyn. Högerklicka var som helst i dokumentet för att öppna snabbmenyn. På den här menyn väljer du Infoga element för att visa dialogrutan Infoga element och väljer det element som du vill infoga.

![](images/insert-element-before-after.png){width="300" align="left"}

**Infoga stycke** - ![](images/Paragraph_icon.svg)

Infoga styckeelement på den aktuella eller nästa giltiga plats.

**Infoga/ta bort numrerad lista** - ![](images/TextNumbered_icon.svg)

Skapar en numrerad lista på den aktuella eller nästa giltiga plats. Om du befinner dig i en numrerad lista och klickar på den här ikonen konverteras objektet till ett normalt stycke.

**Infoga/ta bort punktlista** - ![](images/BulletList_icon.svg)

Skapar en punktlista på den aktuella eller nästa giltiga plats. Om du befinner dig i en punktlista och klickar på den här ikonen konverteras objektet till ett normalt stycke.

**Infoga tabell** - ![](images/Table_icon.svg)

Infogar en tabell vid den aktuella eller nästa giltiga plats. Klicka på ikonen Infoga tabell för att öppna dialogrutan Infoga tabell:

![](images/table-properties.png){width="550" align="left"}

Du kan ange antalet rader och kolumner som krävs i tabellen. Om du vill behålla den första raden som tabellrubrik markerar du alternativet Ange första raden som rubrik. Om du vill lägga till en rubrik i tabellen anger du den i fältet Titel.

När en tabell har infogats kan du ändra den via snabbmenyn.

![](images/table-context-menu_cs.png){width="550" align="left"}

Med tabellens snabbmeny kan du:

- Infoga celler, rader eller kolumner

- Sammanfoga celler åt höger och nedåt

- Dela celler vågrätt eller lodrätt

- Ta bort celler, rader eller kolumner

- Skapa ett fragment från tabellen

- Generera ID


Du kan också definiera attribut för flera celler, hela rader eller kolumner i en tabell. Om du till exempel vill justera tabellcellen drar och markerar du önskad cell. Egenskapen i panelen Innehållsegenskaper \(till höger\) **Typ** ändringar i **Flera poster**. I avsnittet Andra attribut väljer du `@valign` attribut från attributlistrutan. Välj den textjustering du vill använda i de markerade tabellcellerna i den nedrullningsbara listan med värden.

![](images/align-table-cell_cs.png){width="800" align="left"}

**Infoga bild** - ![](images/Image_icon.svg)

Infogar en bild vid den aktuella eller nästa giltiga plats. Klicka på ikonen Infoga bild för att öppna dialogrutan Infoga bild, sök efter och markera den bild som du vill infoga.

>[!NOTE]
>
> Du kan också lägga till en bild genom att dra och släppa den från det lokala systemet i artikeln. I det här fallet läggs bildfilen till med **Överför resurser** arbetsflöde.  Mer information finns i **Överför resurser** i [Vänster panel](web-editor-features.md#id2051EA0M0HS) -avsnitt.


![](images/insert-image.png){width="650" align="left"}

Du kan lägga till bild-/figurtitel och alternativ text för bilden i dialogrutan Infoga bild.

Du kan söka efter den önskade bildfilen genom att ange filnamnet i fältet Typ till sökning längst upp och även filtrera sökresultaten efter Sökväg \(för att söka i\), Samlingar, Filtyp och Taggar. När du har hittat den önskade bildfilen markerar du filen och klickar på Välj för att infoga bilden i dokumentet. Du kan infoga olika format för bildfiler, till exempel `.png`, `.svg`, `.gif`, `.jpg`, `.eps`, `.ai`, `.psd`, med mera.

När du har infogat en bild kan du ändra höjd, bredd, placering och attribut på panelen Innehållsegenskaper. Klicka på en bildfil och gör sedan ändringarna på panelen Innehållsegenskaper i den högra listen.

![](images/image-properties.png){width="800" align="left"}

I fältet Källa visas UUID för den infogade bildfilen. Du kan hitta hela sökvägen till den infogade bildfilen genom att hålla muspekaren över källfältet. Sökvägen visas i verktygstipset.

Du kan ändra storlek på en bild genom att ange ett värde för höjd eller bredd för bildfilen. Bildens proportioner bibehålls automatiskt. Om du vill kan du även välja att inte behålla bildfilens proportioner genom att klicka på låsikonen \(i Behåll proportioner\) och ange värden för höjd och bredd.

Du kan också ange placeringsinställningen för bilden som Textbunden eller Bryt. Om du väljer att använda alternativet Brytningsplacering kan du sedan välja var bilden ska justeras \(Vänster, Centrera eller Höger\).

Du kan också lägga till andra egenskaper för en bildfil genom att välja de nödvändiga egenskaperna i dialogrutan **Attribut** fält.

>[!NOTE]
>
>Du kan också definiera klickbara områden i bilden \(bildschema\). Mer information finns i **Infoga/redigera bildschema** funktionsbeskrivning i [Vänster panel](web-editor-features.md#id2051EA0M0HS) -avsnitt.

**Snabbmeny för bild- eller mediefiler**

Du kan också utföra vissa vanliga åtgärder för bilder och mediefiler med hjälp av snabbmenyn. Högerklicka var som helst på bilden för att öppna snabbmenyn.

Snabbmenyn innehåller alternativ för att klippa ut, kopiera eller klistra in bilden eller mediet. Du kan infoga ett element före eller efter det markerade elementet. Du kan också ändra namn på eller dela upp ett element. Du kan hitta den valda bilden eller mediet i databasen eller visa förhandsgranskningen av filen i resursgränssnittet.

Med de andra alternativen på snabbmenyn kan du kopiera banor, redigera ett bildschema, skapa ett fragment eller generera ID:n för det markerade elementet.

**Infoga multimedia** - ![](images/insert-multimedia-icon.svg)

Infogar olika typer av multimediefiler. Klicka på ikonen Infoga multimedia och välj den filtyp som du vill infoga. De multimedieformat som stöds är:

- Ljudfil
- Videofil
- YouTube
- Vimeo

När du väljer alternativet Ljud- eller videofil visas databasvyn där du kan bläddra och välja önskad fil. Om du väljer YouTube eller Vimeo visas dialogrutan Infoga multimedia. Klistra in länken till videofilen i fältet Webblänk och klicka på Infoga för att lägga till videon på den aktuella eller nästa giltiga platsen i dokumentet.

>[!NOTE]
>
> När du lägger till en YouTube-videolänk måste du ersätta strängen `watch?v=` med `embed` i webbadressen. Så här lägger du till en YouTube-videolänk: `https://www.youtube.com/**watch?v**=WlIKQOrmZcs`måste du lägga till den som: `https://www.youtube.com/**embed/**WlIKQOrmZcs`. Ändringen säkerställer att videon bäddas in i AEM och PDF.

Du kan också lägga till ljud- eller videofilen från dialogrutan Infoga multimedia. Välj alternativet Ljud-/videofil och klicka på bläddringsikonen för att öppna databasvyn. Markera ljud- eller videofilen från databasen och klicka på Välj för att lägga till länken för filen i fältet Ljud-/videofil. Om du väljer en videofil visas även en förhandsgranskning av filen i förhandsvisningsområdet. Du kan spela upp videofilen för att se dess förhandsvisning.

![](images/insert-multimedia.png){width="650" align="left"}

**Infoga korsreferens** - ![](images/Reference_icon.svg)

Infoga referenser av typen - Innehållsreferens, Nyckelreferens, Filreferens, Webblänk eller E-postlänk.

Klicka på **Välj fil** ikon \(för innehållsreferens och filreferens\) eller **Välj karta** -ikonen \(för referens till innehållsnyckel och nyckelreferens\) och välj önskad fil eller önskat innehåll att länka till.

![](images/insert-references.png){width="650" align="left"}

En länk till den valda referensen läggs till i dokumentet. På länkens snabbmeny finns alternativen:

- **Infoga element**: Visar en lista med giltiga element som du kan infoga i den angivna kontexten.
- **Kopiera UUID**: Kopierar UUID för den infogade referensen.
- **Kopiera bana**: Kopierar den fullständiga sökvägen för den infogade referensen.
- **Skapa fragment**: Skapar ett återanvändningsbart fragment av den infogade referensen.
- **Generera ID**: Skapar ett unikt ID för den infogade referensen.

Du kan också söka med UUID för filen som du vill referera till. För länkarna Innehåll och Nyckelreferens anger du UUID för filen som du vill länka till. Filen söks automatiskt och visas i avsnittet Förhandsgranska. När du anger filens UUID behöver du inte uttryckligen ange filtillägget för XML-filer. XML-tillägget läggs automatiskt till i UUID.

![](images/insert-content-using-uuid-search.png){width="650" align="left"}

Om administratören har aktiverat alternativet UUID i *XMLEditorConfig* så ser du UUID för det refererade innehållet i **Länk** -egenskap.

![](images/ref-link-uuid_cs.png){width="800" align="left"}

>[!NOTE]
>
> Om **Aktivera UUID** är inte aktiverat visas den relativa sökvägen för det refererade innehållet.

>[!IMPORTANT]
>
> Även om den relativa sökvägen för det refererade innehållet visas i **Länk** egenskapen, internt skapas länken med UUID för det refererade innehållet.

>[!TIP]
>
> Mer information om hur du refererar till innehåll finns i avsnittet Referenser i guiden Bästa metoder.

**Filtersökning**

Du kan söka efter viss text i de filer som finns på den valda sökvägen i AEM. Till exempel genomsöks&quot;general&quot; i skärmbilden nedan. Du kan även begränsa sökningen med hjälp av förbättrade filter. Du kan söka efter alla DITA-filer som DITA-avsnitt och DITA-kartor som finns på den valda sökvägen.

Du kan söka efter icke-DITA-filer som bildfiler, multimedia och dokument i den valda sökvägen. Du kan också söka efter specifika värden i attributen för DITA-element. Du kan också söka efter filer som har checkats ut av den angivna användaren.

![](images/reference-search-filters.png){width="650" align="left"}

>[!NOTE]
>
> Systemadministratören kan också konfigurera textfiltren och visa eller dölja andra filter. Mer information finns i avsnittet Konfigurera textfilter i as a Cloud Service Installera och konfigurera Adobe Experience Manager Guides.

Listan med filtrerade filer som innehåller den sökta texten visas. På skärmbilden ovan visas t.ex. filerna som innehåller texten &quot;general&quot;. Du kan också förhandsgranska filens innehåll.

**Infoga återanvändbart innehåll** - ![](images/content-reuse-icon.svg)

Återanvänd innehåll som finns i andra dokument i projektet. Du kan infoga innehåll genom att länka direkt till innehållet i en fil eller genom att använda en nyckelreferens, se [Lös nyckelreferenser](map-editor-other-features.md#id176GD01H05Z). När du klickar på ikonen Infoga återanvändbart innehåll visas dialogrutan Återanvänd innehåll:

![](images/reuse-content-dialog.png){width="650" align="left"}

I dialogrutan Återanvänd innehåll väljer du DITA-fil för filreferenser eller den DITA-kartfil som innehåller nyckelreferenserna. När du har valt det här alternativet visas ämnet eller nyckelreferenserna i dialogrutan. Du kan välja ID/nyckel för ämnet som du vill infoga och klicka på Klar för att infoga innehållet i ämnet.

När du infogar en innehållsreferens kan du även ange filens UUID och det återanvändbara innehållet från den filen visas i förhandsvisningsavsnittet.

Baserat på inställningen för infogning av länkar kan du antingen se UUID för det infogade innehållet eller den relativa sökvägen på egenskapspanelen eller i källkodsvyn. Länken skapas alltid med UUID för det refererade innehållet. Se Konfigurera UUID-baserade länkar i as a Cloud Service Installera och konfigurera Adobe Experience Manager Guides.

>[!NOTE]
>
> Om du vill lägga till innehåll före eller efter det refererade innehållet använder du *Alt*+*Vänster* Pil eller Alt+*Höger* Piltangenter för att flytta markören till önskad plats.

Du kan även bädda in det refererade innehållet i ämnet genom att högerklicka på det refererade innehållet och välja **Ersätt referens med innehåll** på snabbmenyn.

**Infoga specialtecken** -  ![](images/insert-special-chars-icon.svg)

Infogar specialtecken i ditt ämne. Klicka på ikonen Infoga specialtecken för att öppna dialogrutan Infoga specialtecken.

>[!NOTE]
>
> AEM innehåller rörliga och storleksändringsbara dialogrutor. Storleken på dialogrutor som har två tvärsnitt längst ned till höger kan ändras. Korslinjerna i dialogrutan Specialtecken visas nedan.

![](images/insert-special-char.png){width="550" align="left"}

I dialogrutan Infoga specialtecken kan du söka efter ett specialtecken med hjälp av dess namn. Alla specialtecken lagras i olika kategorier. Använd listrutan Välj kategori och välj en kategori. De specialtecken som finns i den valda kategorin visas. Du kan navigera i listan med specialtecken med piltangenterna eller klicka på det tecken du vill infoga. Namnet och hexadecimala koden för det valda specialtecknet visas under listan. Klicka på Infoga för att infoga det markerade tecknet i dokumentet.

**Infoga nyckelord** - ![](images/Keyword_icon.svg)

Infoga nyckelord som definieras i DITA-kartan. Klicka på ikonen Infoga nyckelord för att öppna dialogrutan Nyckelreferens.

![](images/insert-keyword.png){width="550" align="left"}

Nyckelorden visas i alfabetisk ordning och du kan även söka efter nyckelord genom att skriva en söksträng i sökrutan. Sökresultatet returnerar nyckelorden som innehåller strängen i ID eller Value. De nyckelord som definieras i DITA-kartan visas i den här dialogrutan. Välj det nyckelord som du vill infoga och klicka på **Infoga**.

Du kan också ändra attributen för det infogade nyckelordet genom att högerklicka på nyckelordet och välja alternativet Attribut. Attributen för nyckelordsdialogrutan öppnas:

![](images/attributes-for-keyword.png){width="550" align="left"}

Du kan ändra nyckelordets attribut eller lägga till ett nytt attribut till nyckelordet.

**Infoga fragment** - ![](images/insert-snippet-icon.svg)

Infoga ett fragment på aktuell eller nästa giltiga plats. För att den här funktionen ska fungera måste du ha definierat fragment i systemet. Mer information om hur du lägger till ett fragment finns i **Fragment** funktionsbeskrivning i [Vänster panel](web-editor-features.md#id2051EA0M0HS) -avsnitt.

När du klickar på ikonen Infoga fragment visas katalogen Infoga fragment. Katalogen är sammanhangsberoende, vilket innebär att kodavsnitten endast visas om de tillåts på den aktuella platsen.

I följande exempel visas två förkonfigurerade fragment - Varning och Fel som kan infogas på den aktuella platsen i dokumentet.

![](images/insert-snippet.png){width="300" align="left"}

När du väljer ett fragment från listan infogas det på den aktuella eller nästa giltiga platsen i dokumentet. På följande skärmbild visas det felutdrag som infogats i dokumentet:

![](images/error-snippet.png){width="400" align="left"}

**Infoga/redigera bildschema** - ![](images/imagemap-rectangle.svg)

Infogar ett bildschema på den markerade bilden. En bild med klickbara områden som länkar till ämnen eller webbsidor kallas för ett bildschema.

Markera en bild i det aktuella avsnittet och klicka på ikonen Infoga/redigera bildschema för att öppna dialogrutan Infoga bildschema.

![](images/insert-image-map.png){width="650" align="left"}

Välj önskad formrektangel ![](images/imagemap-rectangle-toolbar.png), Cirkel ![](images/imagemap-circle-toolbar.png)eller polygon ![](images/imagemap-polygon-toolbr.png) för att definiera ett område över en bild som du vill använda som länk. När du har definierat ett område visas dialogrutan Referens där du måste ange länken till det interna eller externa innehållet:

![](images/reference-dialog.png){width="650" align="left"}

Om områden överlappar varandra kan du flytta formen framåt eller flytta den bakåt genom att klicka på respektive ikon i verktygsfältet. Du kan också ta bort ett område genom att markera det och klicka på ikonen Ta bort. Om du dubbelklickar på ett område öppnas dialogrutan Referens där du kan ändra mållänken. När du har markerat önskade områden på bilden sparar du ändringarna genom att klicka på Klar.

**Checka ut/Checka in** - ![](images/LockClosed_icon.svg)/ ![](images/LockOpen_icon.svg)

Checkar ut eller checkar in den aktuella filen. När användaren checkar ut en fil får han eller hon exklusiv skrivåtkomst till filen. När filen är incheckad sparas ändringarna i den aktuella versionen av filen.

Om du är i Kartvyn och du expanderar den överordnade kartan kan du checka ut alla filer på kartan med ett enda klick. Expandera bara den överordnade mappfilen och markera den överordnade filen, vilket gör att du kan markera alla filer på kartan. Sedan kan du välja **Checka ut**  ![](images/LockClosed_icon.svg) för att låsa alla filer på kartan.

>[!NOTE]
>
> När du checkar in en fil som innehåller ändringar som inte har sparats uppmanas du att spara ändringarna. Om du inte sparar ändringarna checkas bara filen in.

Verktygstipset för Checka in/Checka ut avgörs av egenskapen title i dialogrutan `ui_config.json` -fil.

Mer information finns i [Konfigurera titeln för ikonerna Checka in och Checka ut](../install-guide/conf-checkin-checkout-title.md) i installations- och konfigureringshandboken på plats.


**Växla taggvy** - ![](images/Label_icon.svg)

Taggar är visuella tecken som anger ett elements gränser. En elementgräns markerar början och slutet av ett element. Du kan sedan använda dessa gränser som en visuell referenspunkt för att placera insättningspunkten eller markera texten inom en gräns. Om du vill infoga ett annat element före eller efter ett element i dokumentet kan du placera insättningspunkten före eller efter elementets öppnings- eller slutgräns.

På följande skärmbild visas ett dokument med taggvyn:

![](images/tags-view.png){width="650" align="left"}

Följande åtgärder kan utföras i ett dokument med taggvyn på:

- **Markera ett element**: Klicka på den inledande eller avslutande taggen för ett element för att markera dess innehåll.

- **Expandera eller komprimera taggar**: Klicka på + eller - logga in en tagg för att utöka eller komprimera den.

- **Använda snabbmenyn**: Snabbmenyn innehåller alternativ för att klippa ut, kopiera eller klistra in det markerade elementet. Du kan också infoga ett element före eller efter det markerade elementet. Med de andra alternativen kan du generera ett ID eller öppna egenskapspanelen för det markerade elementet.

- **Dra och släppa element**: Välj taggen för ett element och dra och släpp den enkelt i dokumentet. Om släppplatsen är en giltig plats där elementet tillåts placeras elementet på släppplatsen.


>[!NOTE]
>
> Om en användare aktiverar taggvyn från Web Editor är den fortfarande aktiverad även i alla sessioner. Det innebär att du inte behöver aktivera taggvyn igen för att komma åt den senare. Standardvärdet för taggvyn för en ny användarsession bestäms av egenskapen tagsView i filen ui\_config.json. Mer information finns i *Konfigurera standardvärde för taggvyn* i Installera och konfigurera Adobe Experience Manager Guides as a Cloud Service.

**Aktivera/inaktivera spåra ändringar** ![](images/track-change-icon.svg)

Du kan hålla reda på alla uppdateringar som gjorts i ett dokument genom att aktivera läget Spåra ändringar. När du har aktiverat spårändringar hämtas alla infogningar och borttagningar i dokumentet. Allt borttaget innehåll markeras med Genomstruken och alla infogningar markeras med grön text. Dessutom visas ändringsfälten vid ämnessidans kant. Återigen visas en röd stapel för borttaget innehåll och en grön stapel visas för tillagt innehåll. Om det finns tillägg och borttagning på samma rad visas både gröna och röda staplar.

I följande skärmbild markeras det borttagna och infogade innehållet tillsammans med ändringsfälten:

![](images/track-changes-content.png){width="650" align="left"}

Ett typiskt användningssätt för att spåra ändringar i ett dokument kan vara att utföra peer-granskning. Du kan aktivera spårning av ändringar och dela dokumentet för granskning. Granskaren gör sedan ändringar med spårningsändringar PÅ. När du tar emot dokumentet bör du ha en funktion för att visa de föreslagna uppdateringarna tillsammans med ett praktiskt sätt att acceptera eller ignorera ändringar.

AEM innehåller funktionen Spårade ändringar som innehåller information om de uppdateringar som gjorts i dokumentet. Funktionen Spårade ändringar ger information om vilka uppdateringar som gjordes, vem som gjorde dem och vid vilken tidpunkt. Med funktionen Spårade ändringar kan du enkelt acceptera eller ignorera de föreslagna uppdateringarna i dokumentet.

Du öppnar funktionen genom att klicka på ikonen Spårade ändringar i den högra panelen.

![](images/changes-panel_cs.png){width="300" align="left"}

Om du klickar på en ändring markeras det ändrade innehållet i dokumentet. Du kan acceptera en ändring genom att markera ikonen Acceptera ändring eller ignorera den genom att välja Ignorera ändring.

Om du vill acceptera eller ignorera alla ändringar med ett enda klick väljer du **Acceptera alla** eller **Ignorera alla**.

>[!NOTE]
>
> I förhandsgranskningsläget kan du visa dokumentet med eller utan det ändrade innehållets markeringar. Mer information finns i [Förhandsgranska](web-editor-views.md#preview-mode-id19AAGL00163) läge.

**Sammanfoga** - ![](images/merge-icon.svg)

När du arbetar i en miljö med flera författare blir det svårt att spåra vilka ändringar de andra författarna har gjort i ett ämne eller en karta. Med sammanfogningsfunktionen får du bättre kontroll över inte bara hur ändringarna visas, utan även vilka ändringar som finns i den senaste versionen av dokumentet.

**Sammanfoga ämnesfiler**

Så här sammanfogar du ändringar i ett ämne:

1. Öppna ett ämne i Web Editor.

1. Klicka **Sammanfoga**.

   Dialogrutan Sammanfoga visas.

   ![](images/merge-changes-in-topic.png){width="550" align="left"}

1. *\(Valfritt\)* Du kan även bläddra och välja en ny fil från någon annan plats i databasen.

1. Välj en version av filen som du vill jämföra den aktuella versionen av filen med.

1. Välj:

   - **Spåra ändringar från vald version**: Det här alternativet visar alla innehållsuppdateringar i form av ändringsspårning. Du kan sedan välja att acceptera eller ignorera ändringar i dokumentet en åt gången eller alla på en gång.

   - **Återställ till markerad version**: Det här alternativet återställer den aktuella versionen av dokumentet till den valda versionen. Det här alternativet ger dig ingen kontroll över vilket innehåll som godkänns eller avvisas.

1. Klicka **Klar**.

1. Om du valde **Spåra ändrad från vald version** och alla ändringar från den valda versionen visas i funktionen Spåra ändringar på den högra panelen.

   Du kan välja att acceptera eller ignorera alla kommentarer från panelen Spårade ändringar eller acceptera eller ignorera enskilda kommentarer.


**Sammanfoga kartfiler**

Så här sammanfogar du ändringar i en kartfil:

1. Öppna en karta i Web Editor.

1. Klicka **Sammanfoga**.

   Dialogrutan Sammanfoga visas.

   ![](images/merge-changes-in-map.png){width="550" align="left"}

1. *\(Valfritt\)* Du kan även bläddra och välja en ny fil från någon annan plats i databasen.

1. Välj en version av filen som du vill jämföra den aktuella versionen av filen med.

1. Välj:

   - **Spåra ändringar från vald version**: Det här alternativet visar alla innehållsuppdateringar i form av ändringsspårning. Du kan sedan välja att acceptera eller ignorera ändringar i dokumentet en åt gången eller alla på en gång.

   - **Återställ till markerad version**: Det här alternativet återställer den aktuella versionen av dokumentet till den valda versionen. Det här alternativet ger dig ingen kontroll över vilket innehåll som godkänns eller avvisas.

1. Klicka **Klar**.

   1. Om du valde **Spåra ändrad från vald version** visas alla ändringar från den valda versionen på panelen Spårade ändringar \(till höger\).

      Du kan välja att acceptera eller ignorera alla ändringar på panelen Spårade ändringar eller acceptera eller ignorera enskilda ändringar i kartfilen.


**Tidigare versioner** - ![](images/version-history-web-editor-ico.svg)

AEM innehåller olika sätt att visa versioner som har skapats för ämnesfiler och olika sätt att återgå till en viss version. De flesta av dessa funktioner är dock tillgängliga utanför Web Editor.

Med funktionen Versionshistorik i Web Editor kan du inte bara kontrollera de tillgängliga versionerna och etiketterna i det aktiva ämnet, utan du kan även återgå till valfri version från redigeraren.

Så här får du åtkomst till versionshistoriken och återgår till en specifik version av ditt ämne:

1. Öppna ett ämne i Web Editor.

1. Klicka **Tidigare versioner**.

   Dialogrutan Versionshistorik visas.

   ![](images/version-history-dialog-web-editor.png){width="550" align="left"}

1. Välj en version av ämnet som du vill återgå till i **Välj version** listruta.

   >[!NOTE]
   >
   > Om en version har etiketter som används på den visas de också \(inom hakparenteser\) tillsammans med versionsnumret.

   När du har valt en version i listrutan är alternativet Återställ till markerad version tillgängligt. I förhandsvisningsfönstret visas skillnaderna mellan den aktuella versionen och den valda versionen av ämnet.

   ![](images/version-history-revert-diff-dialog-web-editor.png){width="550" align="left"}

1. Klicka **Återställ till markerad version** om du vill återställa arbetskopian med den valda versionen av ämnet.

   Dialogrutan Återställ version visas.

   ![](images/version-history-revert-dialog-save-working-copy.png){width="550" align="left"}

1. \(*Valfritt*\) Ange en orsak till att du återgår till en tidigare version. Du kan också skapa en ny version av den aktiva arbetskopian av ditt ämne.

1. Klicka **Bekräfta.**

   Arbetskopian av filen återställs till den valda versionen. Om du väljer att skapa en ny version av den aktiva arbetskopian skapas även en ny version av filen med alla arbetsändringar.


När du återgår till en tidigare version visas en visuell indikation på att den version du för närvarande arbetar med inte är den senaste versionen.

![](images/older-version-visual-cue.png){width="800" align="left"}

**Hantering av versionsetiketter** -  ![](images/version-label-icon.svg)

Etiketter hjälper dig att identifiera i vilken fas ett visst ämne finns i DDLC \(Document Development Life Cycle\). När du till exempel arbetar med ett ämne kan du ange etiketten som &quot;Godkänd&quot;. När ett ämne har publicerats och gjorts tillgängligt för kunder kan du tilldela rubriken&quot;Släppt&quot; etikett.

Med AEM stödlinjer kan du ange etiketter i ett frihandstextformat eller använda en uppsättning fördefinierade etiketter. Med den anpassade etiketten kan alla författare i systemet ange en etikett efter eget val. Detta ger flexibilitet, men medför inkonsekventa etiketter i systemet. För att lösa problemet kan administratörer konfigurera en uppsättning fördefinierade etiketter. Mer information om hur du konfigurerar fördefinierade etiketter finns i *Konfigurera och anpassa XML Web Editor* i as a Cloud Service Installera och konfigurera Adobe Experience Manager Guides.

Dessa etiketter visas i en nedrullningsbar lista för författare där de behöver ange en etikett. Detta garanterar att endast fördefinierade, konsekventa etiketter används i systemet.

Det finns olika metoder att använda etiketter på dina ämnen - [Tidigare versioner](web-editor-use-label.md#) i resursens gränssnitt, [Baslinjer](/help/tutorials/user-guide/generate-output-use-baseline-for-publishing.md#id184KD0T305Z) Gränssnitt och webbredigerare. Med funktionen Versionsetikett i Web Editor kan man snabbt och enkelt tilldela etiketter till sina ämnen.

Gör så här om du vill lägga till etiketter i ett ämne från Web Editor:

1. Öppna ett ämne i Web Editor.

1. Klicka **Versionsetikett**.

   Dialogrutan Hantering av versionsetikett visas.

   ![](images/version-label-management-dialog.png){width="650" align="left"}

   Dialogrutan Hantering av versionsetiketter är uppdelad i två delar - den vänstra panelen innehåller en lista med tillgängliga versioner av ämnet tillsammans med listrutan Etikett \(eller en textruta där du kan ange en etikett\) och den högra panelen med en förhandsgranskning av ämnet.

1. Välj den version som du vill använda etiketter på.

   När du väljer en annan version av ämnet från versionslistan visas ändringarna mellan den aktuella versionen och den valda versionen av ämnet på förhandsvisningspanelen

   >[!NOTE]
   >
   > Om en etikett redan används för en version visas den bredvid versionsnumret i listrutan och nedanför listan Välj version. Du kan ta bort en befintlig etikett genom att klicka på \(**x**\) bredvid etiketten.

1. Om administratören har definierat en lista med etiketter visas en nedrullningsbar lista med de etiketter som du kan välja de etiketter du vill använda. Du kan välja flera etiketter i listrutan.

   Annars visas en textruta där du kan ange de etiketter du vill lägga till i ämnet.

   >[!NOTE]
   >
   > Du kan inte använda samma etikett på flera versioner av ett ämne. Om du försöker associera en befintlig etikett kan du ta bort den från den befintliga versionen och använda den på den valda versionen av ämnet.

1. Klicka **Lägg till etikett**.

1. I bekräftelsemeddelandet Använd etikett väljer du **Flytta etikett** om du vill flytta etiketter från en befintlig version till den valda versionen. Om du inte markerar det här alternativet och det finns etiketter som har tilldelats till en annan version av ämnet, flyttas de inte till det valda ämnets version. Sådana etiketter ignoreras i etikettprogramprocessen.


**Skapa granskningsaktivitet** -  ![](images/create-review-task-icon.svg)

Du kan skapa en granskningsåtgärd för det aktuella ämnet eller kartan direkt från webbredigeraren. Öppna filen som du vill skapa granskningsaktiviteten för och klicka på Skapa granskningsuppgift för att starta granskningsprocessen.

>[!NOTE]
>
> Du kan också skapa en granskningsuppgift från granskningspanelen \(till höger\).

Följ instruktionerna i [Granska ämnen och kartor](review.md#) för mer information.

## Vänster panel {#id2051EA0M0HS}

Den vänstra panelen är en beständig panel. Du kan expandera eller komprimera den genom att klicka på ikonen Expandera marginallist \(![](images/sidebar-expand-icon.svg)\). I den utökade vyn visas namnen på de ikoner som visas som verktygstips i den komprimerade vyn.

>[!NOTE]
>
> Det går att ändra storlek på den vänstra panelen. Om du vill ändra storlek på panelen placerar du markören på panelkanten, pekaren ändras till en dubbelriktad pil, klickar och drar för att ändra storlek på panelbredden.

Den vänstra panelen ger dig tillgång till följande funktioner:

**Favoriter** -  ![](images/favorite-collections.svg)

Om du arbetar med en uppsättning filer eller mappar kan du lägga till dem i din favoritlista för att snabbt komma åt dem. I favoritlistan visas en lista med dokument som du har lagt till och andra offentliga favoritdokument från andra användare.

Om du vill skapa en favoritlista eller -samling klickar du på plusikonen bredvid panelen Favoriter för att visa loggen för Ny samling:

![](images/favorite-new-collection.PNG){width="300" align="left"}

Ange en titel och en beskrivning för den favoritsamling som du vill skapa. Om du väljer **Offentlig** visas den här favoriten även för andra användare.

Om du vill lägga till en fil i din favoritsamling använder du någon av följande metoder:

- Navigera till önskad fil eller mapp i databasvyn och klicka på *Alternativ* -ikonen för att öppna snabbmenyn och välja **Lägg till i Favoriter**. I dialogrutan Lägg till i Favoriter kan du välja att lägga till filen/mappen till en befintlig favorit eller skapa en ny.

  ![](images/favorite-add-file-folder.png){width="300" align="left"}

- Högerklicka på en fils flik i redigeraren för att öppna snabbmenyn. Välj **Lägg till** > **Favoriter** om du vill lägga till filen i favoritlistan.

  ![](images/favorite-add-from-file-context-menu_cs.png){width="400" align="left"}

>[!NOTE]
>
> - Om du vill ta bort ett objekt från favoritlistan markerar du alternativikonen bredvid objektet i en favoritsamling och väljer **Ta bort från Favoriter**.
> - Om du vill förhandsgranska filen utan att öppna den markerar du en fil och väljer sedan **Förhandsgranska** på Alternativ-menyn.



**Menyn Alternativ för favoritsamlingen**\
Du kan även utföra många åtgärder med Alternativ-menyn som är tillgänglig för en Favoritsamling:

![](images/favorites-options.png){width="400" align="left"}
- **Byt namn**: Byt namn på den valda samlingen.
- **Ta bort**: Ta bort den markerade samlingen.
- **Uppdatera**: Hämta en ny lista med filer och mappar från databasen.
- **Visa i resursgränssnitt**: Visa fil- eller mappinnehållet i resursgränssnittet.

>[!NOTE]
>
> Du kan även uppdatera listan med hjälp av ikonen Uppdatera högst upp.


**Databasvy** - ![](images/Repository_icon.svg)

När du klickar på ikonen Databasvy visas en lista med filer och mappar som är tillgängliga i DAM.

75 filer läses in samtidigt. Varje gång du klickar **Läs mer**... 75 filer läses in och knappen visas inte när alla filer har listats. Gruppinläsningen är effektiv och du kan komma åt filerna snabbare än att läsa in alla filer som finns i en mapp.

Du kan enkelt navigera till önskad fil i DAM och öppna den i Web Editor. Om du har behörighet att redigera filen kan du göra det.

Du kan också klicka på och spela upp en ljud- eller videofil i Web Editor. Du kan ändra volymen eller vyn för videon. På snabbmenyn har du också möjlighet att hämta, ändra uppspelningshastighet eller visa bild-i-bild.



Om du dubbelklickar på en kartfil öppnas den i **Kartvy**. Mer information finns i **Kartvy** funktionsbeskrivning i [Vänster panel](web-editor-features.md#id2051EA0M0HS) -avsnitt. Om du dubbelklickar på en ämnesfil öppnas den i [Innehållsredigeringsområde](#id2051EB000UI). Du kan navigera och öppna en fil direkt i webbredigeraren, vilket sparar tid och ökar produktiviteten.

**Filtersökning**

Webbredigeraren har förbättrade filter för textsökning. Klicka på Filtersökning \(![](images/filter-search-icon.svg)\) för att öppna filterpanelen. Du kan söka efter en text i de filer som finns på den valda sökvägen i AEM. Till exempel genomsöks&quot;allmänt syfte&quot; i skärmbilden nedan.

![](images/repository-filter-search.png){width="400" align="left"}

Du har även följande alternativ för att filtrera filerna och begränsa sökningen i AEM.

- **DITA-filer**: Du kan söka efter alla **DITA-avsnitt** och **DITA-kartor** finns på den markerade banan.
- **Icke-DITA-filer**: Du kan söka efter **Bildfiler**, **Multimedia** och **Dokument** i den markerade banan.
- **DITA Elements**: Du kan också söka efter specifika värden i attributen för de angivna DITA-elementen.
- **Utcheckad av**: Du kan söka efter filer som har checkats ut av den angivna användaren.
- **Senast ändrad**: Du kan söka efter filer som senast har ändrats efter ett valt datum men före ett valt datum. Du kan också söka efter filer som senast har ändrats under de senaste 2 timmarna, förra veckan, förra månaden eller förra året.
- **Taggar**: Du kan söka efter filer som har särskilda taggar. Du kan antingen skriva taggen eller välja den i listrutan.

**Obs!** Systemadministratören kan också konfigurera textfiltren och visa eller dölja andra filter. Mer information finns i *Konfigurera textfilter* i avsnittet Installera och konfigurera Adobe Experience Manager Guides as a Cloud Service.

Listan med filtrerade filer som innehåller den sökta texten visas. På skärmbilden ovan visas till exempel de filer som innehåller texten &quot;allmänt syfte&quot;. Du kan markera flera filer i den filtrerade listan om du vill dra och släppa dem i en karta som har öppnats för redigering.

**Alternativ-menyn**

Förutom att öppna filer från den vänstra panelen kan du även utföra många åtgärder med hjälp av

Menyn Alternativ finns i databasvyn. Du kan se olika alternativ beroende på om du väljer en mapp, ämnesfil eller mediefil.

**Alternativ för en mapp**

Du kan utföra följande åtgärder med Alternativ-menyn som är tillgänglig för en *mapp* i databasvyn:

![](images/options-menu-folder_cs.PNG){width="550" align="left"}


- **Skapa**: Skapa ett nytt DITA-ämne, en DITA-karta eller en mapp. Mer information finns i  **Skapa ämnen från databasvyn** proceduren i [Vänster panel](web-editor-features.md#id2051EA0M0HS) -avsnitt.



- **Överför resurser**: Överför en fil från ditt lokala system till den valda mappen i AEM. Du kan också dra och släppa filer från ditt lokala system till ditt aktuella arbetspass. Det här är mycket användbart om du vill infoga bilder från ditt lokala system i avsnittet.

  ![](images/upload-assets.png){width="550" align="left"}

  Du kan välja en mapp där du vill överföra filen och en förhandsvisning av bilden visas också. Om du vill byta namn på filen kan du göra det i textrutan för filnamn. Klicka på Överför för att slutföra filöverföringen. Om du har dragit och släppt en bildfil till ett ämne, läggs bildfilen till i artikeln och den överförs också.

  Om administratören har aktiverat alternativet UUID i *XMLEditorConfig* så ser du UUID för den överförda bilden i **Källa** -egenskap.

  ![](images/uuid-in-source-upload-image_cs.png){width="800" align="left"}

- **Sök efter filer i mappen**: Flyttar fokus till databassökning där du kan ange söktermen. Sökningen utförs under den valda mappen i databasen. Du kan också använda ett filter för att returnera DITA-filer, bildfiler eller båda.

  ![](images/find-files-in-folders-repo-view_cs.png){width="400" align="left"}

  Du kan också söka med hjälp av filens UUID. I så fall visar sökresultaten titeln på DITA/XML-filen och om filen är en bildfil visas filens UUID. I följande sökexempel genomsöks UUID för en bildfil och i sökresultaten visas UUID för den ursprungliga bildfilen och avsnittsrubriken för den fil där bilden refereras.

  ![](images/uuid-repo-search-image-topic-file_cs.png){width="300" align="left"}

- **Komprimera alla**: Dölj alla öppna mappar i databasen och visa endast mapparna på rotnivå.

  >[!NOTE]
  >
  > Använd **\>** -ikonen bredvid en mapp för att expandera den.

- **Lägg till i Favoriter**: Lägger till den markerade mappen i favoriter. Du kan lägga till den i en befintlig eller ny favoritsamling.

- **Uppdatera**: Hämta en ny lista med filer och mappar från databasen.
- **Visa i resursgränssnitt**: Visa mappinnehållet i resursgränssnittet.

**Alternativ för en fil**

Du kan se olika alternativ på Alternativ-menyn beroende på om du väljer en mediefil eller en DITA-fil. Några vanliga alternativ för både media och DITA-filer är:

- Duplicera
- Checka ut/Checka in
- Förhandsgranska
- Flytta till
- Byt namn
- Ta bort
- Kopiera
- Komprimera alla
- Lägg till i Favoriter
- Egenskaper
- Visa i resursgränssnitt

![](images/options-menu-repo-view-file-level.png){width="550" align="left"}

De olika alternativen på Alternativ-menyn förklaras nedan:

- **Redigera**: Öppna filen för redigering. Om det är en .ditamap/.bookmap-fil öppnas den i [Avancerad kartredigerare](map-editor-advanced-map-editor.md#) för redigering.

- **Duplicera**: Använd det här alternativet om du vill skapa en dubblett eller en kopia av den markerade filen. Du kan också ändra namn på den duplicerade filen i kommandotolken Duplicera resurs. Som standard skapas filen med suffixet \(som filnamn\_1.extension\). Filens namn är detsamma som källfilen och den nya filen börjar med version 1.0. Alla referenser, taggar och metadata kopieras medan baslinjerna inte kopieras i den duplicerade filen.
- **Checka ut**: Låsa den markerade filen för redigering. För en låst fil ändras alternativet till **Checka in**.

  >[!NOTE]
  >
  > - Om en fil är låst eller utcheckad av en användare och du håller muspekaren över låsikonen visas den användare \(namn\) som har låst filen.
  > - När du checkar in en fil som innehåller ändringar som inte har sparats uppmanas du att spara ändringarna. Om du inte sparar ändringarna checkas bara filen in.

- **Förhandsgranska**: Få en snabb förhandsvisning av filen (.dita, .xml, audio, video eller image) utan att öppna den. Du kan ändra storlek på förhandsgranskningsfönstret. Om innehållet innehåller `<xref>` eller `<conref>`kan du markera den för att öppna den på en ny flik. Filens titel visas i fönstret. Om det inte finns någon titel visas filnamnet. Stäng **Förhandsgranska** kan du antingen välja stängningsikonen eller klicka var som helst utanför rutan.

  ![](images/quick-preview_cs.png){width="800" align="left"}

- **Byt namn**: Använd det här alternativet om du vill byta namn på den markerade filen. Ange namnet på den nya filen i dialogrutan **Byt namn på resurs** -dialogrutan.
   - Du kan byta namn på en fil av valfri typ.
   - Du kan inte ändra filtillägget.
   - Två filer kan inte ha samma namn. Du kan alltså inte byta namn på en fil till ett namn som redan finns. Ett fel visas.

- **Flytta till**: Använd det här alternativet om du vill flytta den markerade filen till en annan mapp.
   - Du kan antingen skriva namnet på målmappen eller välja **Markera bana** för att välja målmappen.
   - Du kan flytta en fil av valfri typ till valfritt mål i innehållsmappen.
   - Två filer kan inte ha samma namn. Du kan alltså inte flytta en fil till en mapp där det redan finns en fil med samma namn.

  Om du försöker flytta en fil till en mapp där det finns en fil med samma namn men en annan titel, visas dialogrutan Byt namn och flytta filen. Du måste byta namn på filen innan du flyttar den. Den flyttade filen i målmappen har det nya filnamnet.

  ![](images/rename-move-asset.png){width="550" align="left"}

  >[!NOTE]
  > Du kan också dra och släppa en fil till en annan målmapp.

  **Uteslutningsscenarier**

  AEM Guides tillåter inte att du byter namn på eller flyttar en fil i följande scenarier:

   - Du kan inte flytta eller byta namn på en fil om den ingår i en granskning eller ett översättningsarbetsflöde.

   - Om någon annan användare checkar ut filen kan du inte byta namn på den eller flytta den. Du kommer inte att se alternativet Byt namn eller Flytta till för filen.

  >[!NOTE]
  > Om administratören har gett dig behörighet för en mapp är det bara **Byt namn** eller **Flytta till** visas.

  <details>
    <summary> Cloud Services </summary>

  Om du byter namn på eller flyttar en fil bryts inte befintliga referenser från eller till filen, eftersom varje fil har ett unikt UUID.
  </details>



- **Ta bort**: Använd det här alternativet om du vill ta bort den markerade filen. En bekräftelse visas innan filen tas bort.

   - En bekräftelse visas innan filen tas bort.
   - Om det inte finns någon referens till filen från någon annan fil tas den bort och ett meddelande om att åtgärden lyckades visas.
   - Om filen är utcheckad kan du inte ta bort den och ett felmeddelande visas.

     >[!NOTE]
     >
     > Om administratören har förhindrat att utcheckade filer tas bort visas endast felmeddelandet. Mer information finns i *Förhindra borttagning av utcheckade filer* i avsnittet Installera och konfigurera Adobe Experience Manager Guides as a Cloud Service.

   - Om filen läggs till i en favoritsamling visas **Tvinga borttagning** visas och du kan framtvinga borttagning.
   - Om någon annan fil refererar till filen **Tvinga borttagning** med bekräftelsemeddelandet visas och du kan framtvinga borttagning av filen:

     ![](images/options-menu-force-delete.png){width="550" align="left"}

     >[!NOTE]
     >
     > Om administratören har gett filborttagningsbehörighet **Tvinga borttagning** är aktiverat. Annars, **Tvinga borttagning** är inaktiverat och ett meddelande visas om att du inte har behörighet att ta bort refererade filer. Mer information finns i *Förhindra borttagning av refererade filer* i avsnittet Installera och konfigurera Adobe Experience Manager Guides as a Cloud Service.

   - Om du tar bort ett refererat ämne och har öppnat filen som innehåller referenser för redigering, visas den brutna länken för den refererade filen.

  >[!NOTE]
  >
  > Du kan även ta bort den markerade filen på liknande sätt med tangenten Delete på tangentbordet.

- **Kopiera**: Du kan välja mellan följande alternativ:

   - **Kopiera UUID**: Kopiera UUID för den valda filen till Urklipp.

   - **Kopiera bana**: Kopiera hela sökvägen för den markerade filen till Urklipp.

- **Komprimera alla**: Komprimera alla filer i databasen. Endast mapparna på den översta nivån i databasen visas.
- **Lägg till**: Du kan välja mellan följande alternativ:
   - **Favoriter**: Lägger till den markerade filen i favoriter. Du kan lägga till den i en befintlig eller ny favoritsamling.

   - **Återanvändbart innehåll**: Lägger till den markerade filen i listan Återanvändbart innehåll i den vänstra panelen.

- **Egenskaper**: Använd det här alternativet om du vill öppna egenskapssidan för den markerade filen. Den här egenskapssidan kan också nås från resursgränssnittet genom att markera en fil och klicka på egenskapsikonen i verktygsfältet.

- **Open Map Dashboard**: Om den valda filen är en DITA-karta öppnas kartkontrollpanelen.

- **Visa i resursgränssnitt**: Använd det här om du vill visa en förhandsgranskning av en .dita/.xml-fil i resursgränssnittet. Om det är en .ditamap/.bookmap-fil visas alla ämnesfiler på kartan i en enda enhetlig sida-för-sida-vy.

- **Snabbgenerering**: Generera utdata för den valda filen. Utdata kan bara genereras för filer som är en del av en förinställning. Mer information finns i [Artikelbaserad publicering från webbredigeraren](web-editor-article-publishing.md#id218CK0U019I).


**Skapa ämnen från databasvyn**

Du kan välja att skapa ett nytt ämne, en ny karta eller en ny mapp från ikonen + bredvid databaspanelen eller från snabbmenyn för en mapp i databasvyn.

***Skapa ett ämne***

När du väljer att *skapa ett nytt ämne* på menyn visas följande dialogruta:

![](images/create-topic-dialog.png){width="300" align="left"}

I **Skapa nytt ämne** kan du lämna följande information:

- En mall som ämnet baseras på. Om du till exempel har en färdig installation kan du välja bland mallarna Tom, Koncept, DITAVAL, Referens, Uppgift, Ämne och Felsökning.

  Om mappen har en konfigurerad mappprofil visas endast de ämnesmallar som har konfigurerats i mappprofilen.

- Sökväg där du vill spara ämnesfilen. Som standard visas sökvägen till den markerade mappen i databasen i fältet Sökväg.
- En rubrik för ämnet.

- *\(Valfritt\)* Ämnets filnamn. Filnamnet föreslås automatiskt baserat på ämnet Titel.

  Om administratören har aktiverat automatiska filnamn baserat på UUID-inställningen visas inte fältet Namn så som visas på skärmbilden nedan:

  ![](images/new-topic-without-filename.PNG){width="300" align="left"}


När du klickar **Skapa**, skapas ämnet på den angivna sökvägen. Dessutom öppnas ämnet i Web Editor för redigering.

***Skapa en DITA-karta***

När du väljer att *skapa en ny DITA-karta* får du följande dialogruta:

![](images/create-map-dialog.png){width="300" align="left"}

I **Skapa ny karta** kan du lämna följande information:

- En mall som kartan baseras på. Om du till exempel har en färdig inställning kan du välja från bokmappsmallarna eller DITA-mappningsmallarna.

- Sökväg där du vill spara kartfilen. Som standard visas sökvägen till den markerade mappen i databasen i fältet Sökväg.
- A **Titel** för kartan.

- *\(Valfritt\)* Mappningens filnamn. Filnamnet föreslås automatiskt baserat på kartans titel.

  Om administratören har aktiverat automatiska filnamn baserat på UUID-inställningen visas inte fältet Namn.


När du klickar **Skapa** skapas och läggs kartan till i den mapp som anges i fältet Sökväg. Kartan öppnas även i Kartvyn. Du kan öppna kartfilen i kartredigeraren och lägga till avsnitt i den. Mer information om hur du lägger till ämnen i en kartfil finns i [Skapa en karta](map-editor-create-map.md#).

***Skapa en mapp***

När du väljer att *skapa en ny mapp* får du **Skapa ny mapp** dialog:

![](images/new-folder-dialog_cs.png){width="300" align="left"}

Ange en **Titel** för mappen, som konverteras automatiskt till mappnamnet. Sökvägen är den plats där du vill spara kartfilen. Som standard visas sökvägen till den markerade mappen i databasen i fältet Sökväg. När du klickar **Skapa** skapas och läggs mappen till i den mapp som alternativet Skapa mapp kördes från.

**Kartvy** -  ![](images/map-view-icon.svg)

När du klickar på ikonen Kartvy visas en lista med ämnen i kartfilen. Om du inte har öppnat någon kartfil visas kartvyn som tom. Om du dubbelklickar på en kartfil öppnas kartfilen i den här vyn. Du kan dubbelklicka på en fil på kartan för att öppna den i Web Editor. När du öppnar en karta i kartvyn visas den aktuella kartans titel i mitten av huvudverktygsfältet. Om titeln är för lång visas en ellips och du kan också hovra över titeln för att se den fullständiga titeln i verktygstipset. Om du har redigeringsbehörighet för kartfilerna kan du även redigera filerna. Mer information om hur du öppnar och redigerar ett avsnitt via DITA-kartan finns i [Redigera ämnen via DITA-kartan](map-editor-advanced-map-editor.md#id17ACJ0F0FHS).

Du kan utföra följande åtgärder på Alternativ-menyn i kartfilen:

![](images/options-menu-map-view_cs.png){width="550" align="left"}

- **Redigera**: Öppna kartfilen för redigering i Avancerad kartredigerare.

- **Markera alla**: Markera alla filer på kartan.

- **Radera markering**: Avmarkera de markerade filerna på kartan.

- **Checka ut och Lås**: Checka ut och lås de markerade filerna på kartan.

- **Avbryt utcheckning och Lås upp**: Låser upp kartfilen och gör den tillgänglig för redigering. Ändringarna återställs inte till tidigare versioner.

- **Spara som ny version och Lås upp**: Skapa en nyare version och släpp låset på de markerade filerna på kartan.

- **Förhandsgranska**: Öppna en förhandsgranskning av kartfilen. I den här vyn visas alla ämnesfiler på kartan i en enhetlig sida vid sida-vy.

- **Kopiera**: Du kan välja mellan följande alternativ:
   - **Kopiera UUID**: Kopiera UUID för mappningsfilen till Urklipp.
   - **Kopiera bana**: Kopiera den fullständiga sökvägen för kartfilen till Urklipp.

- **Sök i databas**: Visar platsen för kartfilen i databasen \(eller DAM\).

- **Lägg till**: Du kan välja mellan följande alternativ:
   - **Favoriter**: Lägger till kartfilen i favoriter. Du kan lägga till den i en befintlig eller ny favoritsamling.

   - **Återanvändbart innehåll**: Lägger till kartfilen i listan Återanvändbart innehåll i den vänstra panelen.

- **Egenskaper**: Använd detta för att öppna egenskapssidan för mappningsfilen. Den här egenskapssidan kan också nås från resursgränssnittet genom att markera en fil och klicka på egenskapsikonen i verktygsfältet.

- **Open Map Dashboard**: Öppna kartkontrollpanelen.

- **Visa i resursgränssnitt**: Använd det här om du vill visa en förhandsgranskning av kartfilen i resursgränssnittet. I den här vyn visas alla ämnesfiler på kartan i en enhetlig sida vid sida-vy.

- **Snabbgenerering**: Generera utdata för den markerade karfilen. Utdata kan bara genereras för filer som är en del av en förinställning. Mer information finns i [Artikelbaserad publicering från webbredigeraren](web-editor-article-publishing.md#id218CK0U019I).
- **Stäng**: Stänger kartfilen.

På följande skärmbild visas Alternativ-menyn för en fil i DITA-kartvyn:

![](images/options-menu-file_cs.PNG){width="550" align="left"}

Du kan utföra följande åtgärder på Alternativ-menyn:

- **Redigera**: Öppna filen för redigering. Om det är en .ditamap/.bookmap-fil öppnas den i [Avancerad kartredigerare](map-editor-advanced-map-editor.md#) för redigering.

- **Checka ut**: Checka ut den valda filen. För en utcheckad fil ändras alternativet till **Checka in**.



  >[!NOTE]
  >
  > - Om en fil är låst eller utcheckad av en användare och du håller muspekaren över låsikonen visas den användare \(namn\) som har låst filen.
  > - När du checkar in en fil uppmanas du att spara ändringarna. Om du inte sparar ändringarna checkas bara filen in.

- **Förhandsgranska**: Få en snabb förhandsvisning av filen (.dita, .xml, audio, video eller image) utan att öppna den. Du kan ändra storlek på förhandsgranskningsfönstret. Om innehållet innehåller `<xref>` eller `<conref>`kan du markera den för att öppna den på en ny flik.  Filens titel visas i fönstret. Om det inte finns någon titel visas filnamnet. Stäng **Förhandsgranska** kan du antingen välja stängningsikonen eller klicka var som helst utanför rutan.
- **Kopiera**: Du kan välja mellan följande alternativ:
   - **Kopiera UUID**: Kopiera UUID för den valda filen till Urklipp.
   - **Kopiera bana**: Kopiera hela sökvägen för den markerade filen till Urklipp.


- **Sök i databas**: Visar platsen för den valda filen i databasen \(eller DAM\).
- **Expandera alla**: Expandera alla ämnen i kartfilerna.

- **Komprimera alla**: Komprimera alla ämnen som är en del av den aktuella kartfilen.

- **Lägg till**: Du kan välja mellan följande alternativ:
   - **Favoriter**: Lägger till den markerade filen i favoriter. Du kan lägga till den i en befintlig eller ny favoritsamling.

   - **Återanvändbart innehåll**: Lägger till den markerade filen i listan Återanvändbart innehåll i den vänstra panelen.

- **Egenskaper**: Använd det här alternativet om du vill öppna egenskapssidan för den markerade filen. Den här egenskapssidan kan också nås från resursgränssnittet genom att markera en fil och klicka på egenskapsikonen i verktygsfältet.

- **Visa i resursgränssnitt**: Använd det här om du vill visa en förhandsgranskning av en .dita/.xml-fil i resursgränssnittet. Om det är en .ditamap/.bookmap-fil visas alla ämnesfiler på kartan i en enda enhetlig sida-för-sida-vy.

- **Snabbgenerering**: Generera utdata för den valda filen. Utdata kan bara genereras för filer som är en del av en förinställning. Mer information finns i [Artikelbaserad publicering från webbredigeraren](web-editor-article-publishing.md#id218CK0U019I).

>[!NOTE]
>
> Du kan också öppna och redigera egenskaperna för markerade ämnen i en DITA-karta från **Fler alternativ** längst ned i Kartvyn.

**Dispositionsvy** -  ![](images/outline-icon.svg)

När du klickar på ikonen Dispositionsvy visas den hierarkiska vyn över de element som används i dokumentet.

![](images/outline-view_cs.png){width="300" align="left"}

I dispositionsvyn finns följande funktioner:

- En trädvy över alla element som används i dokumentet.

- Om ett element har ett ID, attribut och text kan du se dem tillsammans med elementet.

- Öppna dispositionsvyn i både författarvyn och källvyn.

- Använd den nedrullningsbara filterlistan för att visa alla element eller endast brutna referenser:

- Om du klickar på ett element i dispositionsvyn markeras elementets innehåll i författar- eller källvyn. Dispositionsvyn är fortfarande synkroniserad med författar- och källvyn. Om du gör några ändringar i en vy kan du se dem i dispositionsvyn. Om du till exempel lägger till ett stycke eller uppdaterar ett element i redigeringsvyn visas det i dispositionsvyn.

  ![](images/select-element-content-outline-view_cs.png){width="650" align="left"}

- Dra och släpp element. Du kan enkelt ersätta ett element genom att släppa ett annat element på det. Om du drar och släpper ett element över ett annat element och du ser en fyrkantig ruta runt elementet, indikerar det att elementet kommer att ersättas. Den ersätter elementet som elementet släpps på.

  ![](images/replace-element-outline-view_cs.png){width="300" align="left"}

  Om du drar och släpper ett element visar en streckad rektangel att elementet kan placeras på den aktuella platsen. Om dra och släpp-funktionen är ogiltig visas ett felmeddelande som anger att åtgärden inte är tillåten.

  ![](images/drop-element-outline-view_cs.png){width="300" align="left"}

- The **Alternativ** i *Dispositionsvy* I kan du utföra allmänna åtgärder som Klipp ut, Kopiera, Ta bort, Generera ID, Infoga element före eller efter det aktuella elementet, Byta namn på eller ersätta ett element, Bryt ned ett element och skapa ett utdrag av det markerade elementet.

>[!NOTE]
>
>Mer information om Generera-ID, Infoga element före eller efter det aktuella elementet och Bryt upp ett element finns i [Andra funktioner i Web Editor](web-editor-other-features.md#).

**Visningsalternativ för panelen Dispositionsvy**

I listrutan Visningsalternativ kan du välja att se följande om elementet har dem:

- **Visa ID**: Visar elementets id.
- **Visa attribut**: Visar attributet tillsammans med dess värde.
- **Visa text**: Visar texten. Om texten är längre än 20 tecken visas en ellips.

Om ett blockelement har en egen text visas det tillsammans med det blockelementet. Om den inte har någon egen text visas texten för det första underordnade elementet tillsammans med det blockelementet.

![](images/outline-view-block-element.png){width="550" align="left"}

Om administratören har skapat en profil för attribut får du dessa attribut tillsammans med deras konfigurerade värden. Du kan också tilldela visningsattribut som konfigurerats av administratören under **Visa attribut** i redigeringsinställningarna. De attribut som är definierade för ett element visas i layoutvyn och dispositionsvyn.


Mer information finns i *Visa attribut* inom *Inställningar för Redigeraren* funktionsbeskrivning i [Vänster panel](web-editor-features.md#id2051EA0M0HS) -avsnitt.

**Sökfunktion**
Med sökfunktionen kan du söka efter ett element med hjälp av dess namn, id, text eller attributvärde.

Sökningen är skiftlägesokänslig och matchar strängen exakt. Sökresultaten sorteras utifrån elementets placering i dokumentet.

Du kan söka efter en sträng i elementet om den visas på panelen Dispositionsvy. Om strängen &quot;Adobe&quot; till exempel finns i elementets text och visas på panelen Dispositionsvy (som du har valt) **Visa text** från listrutan Visningsalternativ) filtreras elementet som innehåller. Men om texten inte visas på panelen Dispositionsvy (eftersom du inte har markerat den) **Visa text** från listrutan Visningsalternativ) filtreras inte elementet som innehåller. På samma sätt finns strängen i ID:t eller attributen om du har markerat dem.



**Återanvändbart innehåll** -  ![](images/content-reuse-icon.png)

En av huvudfunktionerna i DITA är möjligheten att återanvända innehåll. Panelen Återanvändbart innehåll kan lagra dina DITA-filer från vilken du vanligtvis infogar återanvändbart innehåll. När du har lagt till DITA-filerna finns de kvar i panelen Återanvändbart innehåll mellan sessionerna. Det innebär att du inte behöver lägga till dina DITA-filer igen för att komma åt dem senare.

Du kan helt enkelt dra och släppa återanvändbart innehåll från panelen till det aktuella ämnet så infogas det enkelt och snabbt. Du kan också förhandsgranska innehållet innan du infogar det i dokumentet.

Om du vill lägga till en DITA-fil på panelen Återanvändbart innehåll använder du någon av följande metoder:

- Klicka på ikonen + bredvid Återanvändbart innehåll för att öppna dialogrutan Bläddra efter fil. Markera filen som du vill lägga till och klicka på **Lägg till** för att slutföra processen.

  ![](images/reuse-content-add-dita-file_cs.png){width="650" align="left"}

- Klicka på alternativikonen för den önskade filen i databasvyn och välj **Lägg till i återanvändbart innehåll** på snabbmenyn.

- Högerklicka på en fils flik i redigeraren för att öppna snabbmenyn och välja **Lägg till i återanvändbart innehåll**.


När filen har lagts till kan du se alla återanvändbara innehållselement från filen på panelen Återanvändbart innehåll. Återanvändbart innehåll visas med deras ID:n och elementnamn.

När du lägger till en fil i listan Återanvändbart innehåll visas filens namn i stället för filens UUID. Om du vill kontrollera filens UUID håller du muspekaren över filens namn och filens UUID visas i verktygstipset.

![](images/uuid-reusable-content-file-title_cs.png){width="300" align="left"}

>[!NOTE]
>
> Du kan lägga till flera filer i listan över återanvändbart innehåll. Sedan kan du infoga önskat innehåll från panelen Återanvändbart innehåll i dokumentet.

**Uppdatera**: Söker efter allt återanvändbart innehåll och visar en ny lista med återanvändbart innehåll.

Använd någon av följande metoder om du vill infoga innehåll från panelen Återanvändbart innehåll:

- Håll muspekaren över ett element som du vill infoga, klicka på alternativikonen och välj **Infoga återanvändbart innehåll**.

  ![](images/insert-reusable-content_cs.png){width="400" align="left"}

  >[!NOTE]
  >
  > Markera en fil och välj sedan **Förhandsgranska** från **Alternativ** om du vill förhandsgranska filen utan att öppna den. Du kan också förhandsgranska referenserna i ett ämne. Referens-ID:t visas i fönstret.
  >
  > The **Förhandsgranska** finns även i **Alternativ** -menyn för ett element, vilket ger dig en snabb förhandsvisning av elementet innan du infogar det.

- Dra och släpp det återanvändbara innehållsobjektet från panelen till önskad plats i dokumentet.



**Ordlista** -  ![](images/glossary.svg)

Med AEM stödlinjer kan du enkelt skapa och använda ordboksdokument. Du kan skapa ordlisteämnesfiler och sedan inkludera dem i en gemensam ordlista. När den här kartan har lagts till som rotkarta visas ordlisteposterna på ordlistepanelen.

![](images/glossary-panel.png){width="650" align="left"}

Om du vill infoga en term från ordlistan drar och släpper du posten från panelen till önskad plats i ämnet. På Alternativ-menyn för en ordlista kan du snabbt få **Förhandsgranska** Ingångsperioden. **Kopiera bana** av postens termfil, eller leta reda på postens fil i databasen.

Utför följande steg för att söka efter och ersätta textermerna med ordlisteförkortningar:

1. Öppna det DITA-avsnitt eller den DITA-karta där du vill söka efter och konvertera texten eller termerna.
1. Välj ordlistepanelen för att visa de ordlistor som finns i rotkartan. Du kan dra och släppa dessa termer för att lägga till dem i det öppna ämnet.
1. Välj **Aktiveringspunkt** tool \( ![](images/hotspot-icon.svg)\) i ordlistepanelen om du vill söka efter och konvertera specifika textermer till länkade ordlisteförkortningar. Du kan också använda den för att söka efter ordboksförkortningar och konvertera dem till texttermer.

![](images/glossary-hotspot-tool.png){width="300" align="left"}

Du kan konfigurera följande inställningar för verktyget Aktiveringspunkt:

![](images/Glossary-search-keys.png){width="300" align="left"}

- **Ordlistenycklar**: Välj de ordlistenycklar på DITA-kartan som du vill använda för sökningen i det valda avsnittet. De valda tangenterna visas nedan. Du kan ta bort en markerad tangent genom att klicka på **Ta bort** -ikon.

- **Ämnen**: Välj antingen **Aktuellt ämne** som öppnas i Web Editor, alla **Öppnade ämnen** på den aktuella kartan, eller **Aktuell karta** som redigeras i kartredigeraren för att söka efter villkoren.
- **Filtrera ämnen efter status**: Du kan välja att begränsa sökningen till ämnen som har den valda dokumentstatusen. Ämnen kan vara i statusläget Utkast, Redigera, Under granskning, Godkänd, Granskad, Klar eller i något av de tillstånd som organisationen har konfigurerat.
- **Åtgärd**: Du kan välja att antingen söka efter ordlistenycklar **Manuellt för varje ämne** eller **Automatiskt för alla ämnen**. Om du väljer **Manuellt för varje ämne** uppmanas du att bekräfta innan du konverterar varje term i varje avsnitt. Om du väljer **Automatiskt för alla ämnen**, konverteras alla termer i alla ämnen automatiskt.
- **Konvertera**: Du kan antingen konvertera en sökbar **Text till ordlista** eller **Ordlista till text.**
- **Alternativ**: Du kan välja bland följande alternativ:
   - **Skiftlägeskänslig matchning**: Söker efter en term för att hitta matchningen som har samma skiftläge. USB matchar till exempel inte usb.
   - **Konvertera endast den första instansen**: Om det finns flera förekomster av den sökta termen i ett ämne konverteras endast den första förekomsten.
   - **Checka ut fil före konvertering**: Den sökta filen checkas ut innan termerna konverteras.
   - **Skapa en ny version efter konvertering**: En ny version av ämnet skapas när konverteringen av termer har slutförts.
- **Nästa** visas om du väljer **Manuellt för varje ämne** alternativ. Klicka **Nästa** om du vill konvertera villkoren för varje ämne utifrån de valda inställningarna. Där uppmanas du att konvertera termer i varje ämne och går vidare till nästa fil. Du kan välja att konvertera en term eller hoppa över den och gå till nästa term.

  ![](images/manual-convert-skip.png){width="300" align="left"}

- **Konvertera** visas om du väljer **Automatiskt för alla ämnen** alternativ. Välj **Konvertera** om du vill konvertera alla termer i dokumentet till länkade ordlisteförkortningar.

En lista med **Uppdaterade ämnen** med konverterade termer och **Ämnen med fel** visas. Håll pekaren över \( ![](images/info-icon.svg)\) vid Ämnen med Fel om du vill visa information om felet.

![](images/glossary-converted-terms-error.png){width="300" align="left"}

>[!NOTE]
>
> Uppdatera avsnittet om du vill visa de konverterade termerna.

**Villkor** -  ![](images/conditions-icon.svg)

På villkorspanelen visas villkorsattributen som definierats av administratören i den globala profilen eller på mappnivå. Du kan lägga till villkor i innehållet genom att helt enkelt dra och släppa det önskade villkoret i innehållet. Det villkorliga innehållet markeras med den färg som är definierad för att det ska vara lätt att identifiera.

Du kan också använda flera villkor för ett element genom att dra och släppa flera villkor för ett element. När du använder flera villkor för ett element visas de använda villkoren separerade med kommatecken på egenskapspanelen.

![](images/multiple-conditions-applied_cs.png){width="800" align="left"}

I kodvyn avgränsas emellertid villkoren med en blankstegsavgränsare. När du lägger till eller redigerar ett villkor i kodvyn måste du se till att flera villkor avgränsas med ett mellanslag.

>[!IMPORTANT]
>
> Följande skärmbild är av en användare med administratörsbehörighet. Som användare med administratörsbehörighet kan du lägga till, redigera och ta bort villkor. Annars kan du som vanlig författare bara välja att använda villkor.

![](images/conditional-content-through-panel_cs.png){width="800" align="left"}

Om du vill lägga till eller definiera ett villkor klickar du på +-ikonen bredvid villkorspanelen för att öppna dialogrutan Definiera villkor:

![](images/conditional-panel-create-cond.png){width="400" align="left"}

I attributlistan väljer du det villkorsattribut som du vill definiera, anger ett värde för villkoret och anger sedan etiketten som visas på villkorspanelen. Du kan också definiera en färg för villkoret. Den här färgen anges som bakgrundsfärg för innehållet som villkoret används i

Om du vill redigera ett villkor väljer du **Redigera** på Alternativ-menyn. Dialogrutan Redigera villkor visas:

![](images/conditional-panel-edit-cond.png){width="400" align="left"}

Ange informationen på samma sätt som den konfigureras när du definierar ett nytt villkor.

**Ämnesschema** -  ![](images/subject_scheme_panel-icon.svg)

Ämnesscheman är en specialiserad form av DITA-kartor som används för att definiera taxonomiska ämnen och kontrollerade värden. Beroende på dina behov kan du skapa en ämneskarta och referera till den i rotmappfilen. Med AEM kan du definiera hierarkin på den kapslade nivån för ämnesdefinitionerna i ditt ämnesschema.

Du kan enkelt skapa och sedan använda ämnesschemat i ett ämnesschema. När den här kartan har lagts till som din rotkarta visas ämnesschemat i panelen Ämnesschema. Panelen Ämnesschema visar det tillgängliga ämnesschemat på ett kapslat eller hierarkiskt sätt.

AEM har också stöd för kapslade ämnesschemamappningar på nivå, och du kan ha flera ämnesscheman definierade under rottemats schema.

I följande exempel visas hur du använder ämnesschemat i AEM.

1. Skapa en ämnesschemafil i ett valfritt verktyg. Följande XML-kod skapar ett ämnesschema som binder värden för `platform` -attribut.

   ```XML
   <?xml version="1.0" encoding="UTF-8"?>
   <!DOCTYPE subjectScheme PUBLIC "-//OASIS//DTD DITA Subject Scheme Map//EN" "subjectScheme.dtd">
   <subjectScheme id="GUID-4f942f63-9a20-4355-999f-eab7c6273270">
       <title>rw</title>
       <!-- Define new OS values that are merged with those in the unixOS scheme -->
       <subjectdef keys="os">
           <subjectdef keys="linux">    </subjectdef>
           <subjectdef keys="mswin">    </subjectdef>
           <subjectdef keys="zos">    </subjectdef>
       </subjectdef>
       <!-- Define application values -->
       <subjectdef keys="app" navtitle="Applications">
           <subjectdef keys="apacheserv">    </subjectdef>
           <subjectdef keys="mysql">    </subjectdef>
       </subjectdef>
       <!-- Define an enumeration of the platform attribute, equal to       each value in the OS subject. This makes the following values       valid for the platform attribute: linux, mswin, zos -->
       <enumerationdef>
           <attributedef name="platform">    </attributedef>
           <subjectdef keyref="os">    </subjectdef>
       </enumerationdef>
       <!-- Define an enumeration of the otherprops attribute, equal to       each value in the application subjects.       This makes the following values valid for the otherprops attribute:       apacheserv, mysql -->
       <enumerationdef>
           <attributedef name="otherprops">    </attributedef>
           <subjectdef keyref="app">    </subjectdef>
       </enumerationdef>
   </subjectScheme>
   ```

   ![](images/subject-scheme-panel.png){width="300" align="left"}

1. Spara filen med tillägget a.ditamap och överför den till valfri mapp i DAM.

   >[!NOTE]
   >
   > Du kan lägga till en referens till ämnesschemafilen i den överordnade DITA-kartan.

   ![](images/subject-scheme-root-map.png){width="550" align="left"}

1. Ange den överordnade kartan som rotkarta i **Användarinställningar**. När den här kartan har lagts till som din rotkarta visas ämnesschemat i panelen Ämnesschema.

   ![](images/subject-scheme-user-preferences.png){width="400" align="left"}

1. Öppna den fil i Web Editor där du vill använda definitionerna för ämnesschemat.
1. Använd ämnesschemat på ditt innehåll genom att helt enkelt dra och släppa det önskade ämnesschemat till ditt innehåll. Innehållet markeras sedan i den definierade färgen.

   ![](images/subject-scheme-apply.png){width="650" align="left"}

**Hantera hierarkiska definitioner av ämnesdefinitioner och uppräkningar**

Förutom att hantera uppräkningarna och ämnesdefinitionerna som finns på samma karta, innehåller AEM stödlinjer även funktionen som definierar uppräkningar och ämnesdefinitioner i två separata kartor. Du kan definiera en eller flera ämnesdefinitioner i en karta och uppräkningsdefinitionerna i en annan karta och sedan lägga till kartreferensen. I följande XML-kod skapas ämnesdefinitioner och uppräkningsdefinitioner i två separata kartor.

Ämnesdefinitionerna definieras i `subject_scheme_map_1.ditamap`


```XML
  <?xml version="1.0" encoding="UTF-8"?> 
    <!DOCTYPE subjectScheme PUBLIC "-//OASIS//DTD DITA Subject Scheme Map//EN" "../dtd/libs/fmdita/dita_resources/DITA-1.3/dtd/subjectScheme/dtd/subjectScheme.dtd"> 
    <subjectScheme id="subject-scheme.ditamap_f0bfda58-377b-446f-bf49-e31bc87792b3"> 

    <title>subject_scheme_map_1</title> 
    
    <subjectdef keys="os" navtitle="Operating system">
        <subjectdef keys="linux" navtitle="Linux">
        <subjectdef keys="redhat" navtitle="RedHat Linux">
        </subjectdef>
        <subjectdef keys="suse" navtitle="SuSE Linux">
        </subjectdef>
        </subjectdef>
        <subjectdef keys="windows" navtitle="Windows">
        </subjectdef>
        <subjectdef keys="zos" navtitle="z/OS">
        </subjectdef>
        </subjectdef>
        <subjectdef keys="deliveryTargetValues">
        <subjectdef keys="print">
        </subjectdef>
        <subjectdef keys="online">
        </subjectdef>
    </subjectdef>
    <subjectdef keys="mobile" navtitle="Mobile">
        <subjectdef keys="android" navtitle="Android">
        </subjectdef>
        <subjectdef keys="ios" navtitle="iOS">
    </subjectdef>
    </subjectdef>
    <subjectdef keys="cloud" navtitle="Cloud">
        <subjectdef keys="aws" navtitle="Amazon Web Services">
        </subjectdef>
        <subjectdef keys="azure" navtitle="Microsoft Azure">
        </subjectdef>
        <subjectdef keys="gcp" navtitle="Google Cloud Platform">
        </subjectdef>
    </subjectdef>
    </subjectScheme>
```

Uppräkningsdefinitionen finns i subject_scheme_map_2.ditamap.

```XML
    ?xml version="1.0" encoding="UTF-8"?> 
        <!DOCTYPE subjectScheme PUBLIC "-//OASIS//DTD DITA Subject Scheme Map//EN" "../dtd/libs/fmdita/dita_resources/DITA-1.3/dtd/subjectScheme/dtd/subjectScheme.dtd"> 
        <subjectScheme id="subject-scheme.ditamap_17c433d9-0558-44d4-826e-3a3373a4c5ae"> 
        <title>subject_scheme_map_2</title> 
        <mapref format="ditamap" href="subject_scheme_map_1.ditamap" type="subjectScheme"> 
        </mapref> 
        <enumerationdef>
        <attributedef name="platform">
        </attributedef>
        <subjectdef keyref="mobile">
        </subjectdef>
        <subjectdef keyref="cloud">
        </subjectdef>
        </enumerationdef>
        </subjectScheme>
```

Här definieras ämnesdefinitioner i `subject_scheme_map_1.ditamap`  medan uppräkningsdef finns i `subject_scheme_map_2.ditamap`. Referensen till `subject_scheme_map_1.ditamap` läggs också till i `subject_scheme_map_2.ditamap`.

>[!NOTE]
>
> Som `subject_scheme_map_1.ditamap` och `subject_scheme_map_2.ditamap` är refererade till varandra och därför är ämnesscheman lösta.

Referenserna för ämnesuppräkning löses i följande prioritetsordning:

1. Samma karta
1. Refererad karta


Referenserna löses inte om uppräkningen inte hittas i samma karta och den refererade kartan.




**Begränsa värdena till ett visst element**

Du kan också begränsa villkoren till vissa element i ett ämne. Använd `<elementdef>` -taggen för att definiera elementet och `<attributedef>` -tagg för att definiera det villkor som kan tillämpas på elementet.  Om du inte lägger till `<elementdef>` -taggen kan du använda villkoren för alla element.
Använd till exempel följande uppräkning för att begränsa `@platform` attributet till `<shortdesc>` -element.  De andra villkoren är synliga för alla element.

```XML
<enumerationdef>
    <elementdef name="shortdesc">
    </elementdef>
    <attributedef name="platform">
    </attributedef>
    <subjectdef keyref="deliveryTargetValues">
    </subjectdef>
    <subjectdef keyref="os">
    </subjectdef>
  </enumerationdef>
```

</details>


**Listrutan Attribut**

Du kan också ändra värdet för ämnesschemat med hjälp av listrutan Attribut på panelen Innehållsegenskaper i redigeringsvyn. Om du vill ändra värdet väljer du ett värde i listrutan Attribut.

![](images/subject-scheme-attribute-dropdown.png){width="300" align="left"}

Du kan också använda värden för ett attribut genom att välja flera värden i listrutan.

**Källvy**

Du kan också ändra värdena från attributets listruta i källvyn. I källvyn kan du inte heller lägga till felaktiga värden.

![](images/subject-scheme-code-error.png){width="550" align="left"}

**Visa och använd ämnesschemat från villkorspanelen**

Du kan också visa och använda ämnesschemat från villkorspanelen.

Om du vill visa ämnesschemat från villkorspanelen måste systemadministratören välja alternativet **Visa Ämnesschema på panelen Villkor** under fliken Villkor i redigeringsinställningarna. Mer information finns i [Fliken Villkor](#id21BMNE0602V).

På villkorspanelen visas den platta lodräta strukturen för ämnesdefinitionerna i ämnesschemat.

![](images/subject-scheme-condtions-panel.png){width="300" align="left"}

Du kan lägga till villkor i innehållet genom att dra och släppa det önskade villkoret i innehållet. Villkorsinnehållet markeras med den färg som är definierad för villkoret.

**Fragment** -  ![](images/insert-snippet-icon.svg)

Kodavsnitt är små innehållsfragment som kan återanvändas i olika ämnen i dokumentationsprojektet. På panelen Kodavsnitt visas en samling med innehållsfragment som du har skapat. Om du vill infoga ett fragment drar och släpper du fragmentet från panelen till önskad plats i avsnittet. På fragmentpanelen kan du lägga till, redigera, ta bort, förhandsgranska och infoga ett fragment.

>[!IMPORTANT]
>
> Följande skärmbild är av en användare med administratörsbehörighet. Som användare med administratörsbehörighet kan du lägga till, redigera och ta bort fragment. I annat fall får du som vanlig författare bara alternativ för att förhandsgranska och infoga ett fragment.

![](images/snippets-panel_cs.png){width="400" align="left"}

Om du vill lägga till ett fragment använder du någon av följande metoder:

- Klicka på ikonen + bredvid Fragment för att öppna dialogrutan Nytt fragment.

  ![](images/snippet-new-dialog.png){width="550" align="left"}

  I dialogrutan Nytt fragment anger du en rubrik som visas på fragmentpanelen, en beskrivning och en XML-kod för det fragmentinnehåll som du vill skapa. Klicka **Skapa** för att spara och skapa fragmentet.

- Högerklicka på elementets synliga del som du vill använda som textutdrag i området för innehållsredigering och välj **Skapa fragment** på snabbmenyn. Dialogrutan Nytt kodfragment visas med XML-koden för det valda elementet i dialogrutan **Innehåll** fält. Ange **Titel** och **Beskrivning** för fragmentet och klicka på **Skapa** för att spara fragmentet.

- Högerklicka var som helst på det innehåll som du vill använda som utdrag i området för innehållsredigering och välj **Skapa fragment** på snabbmenyn. Dialogrutan Nytt kodfragment visas med XML-koden för det valda elementet i dialogrutan **Innehåll** fält. Ange **Titel** och **Beskrivning** för fragmentet och klicka på **Skapa** för att spara fragmentet.

  Följande skärmbild markerar vägbeskrivningen och innehållsområdet där du kan anropa snabbmenyn.

  ![](images/snippet-create-from-breadcrumb-content.png){width="350" align="left"}


Om du vill infoga ett fragment använder du någon av följande metoder:

- Välj ett fragment på fragmentpanelen och dra och släpp det på önskad plats i avsnittet.

- Placera insättningspunkten där du vill infoga fragmentet och välj Infoga fragment på Alternativ-menyn för fragmentet.


>[!NOTE]
>
> På snabbmenyn för en fragmentpost kan du även välja Redigera, Ta bort, Hämta en förhandsgranskning eller Infoga ett fragment.

**Mallar** -  ![](images/templates-icon.svg)

Mallpanelen är bara tillgänglig för administratörer. Med den här panelen kan administratören enkelt skapa och hantera mallar som sedan kan användas av författarna. Som standard är mallarna kategoriserade under *Karta* och *Ämne* textmallar.

![](images/templates-panel_cs.png){width="550" align="left"}

Om du vill skapa en mall klickar du på ikonen + bredvid Mallar och väljer en mall som du vill skapa. Om du väljer **Ämnesmall** visas dialogrutan Skapa ny ämnesmall:

![](images/create-new-topic-template.PNG){width="400" align="left"}

Välj den typ av mall som du vill skapa från **Mall** listruta. Ange **Titel**, som visas på panelen Mallar. The **Namn** av mallen föreslås automatiskt baserat på titeln, men du kan ange ett annat filnamn.

>[!NOTE]
>
> Om administratören har aktiverat automatiska filnamn baserat på UUID-inställningen visas inte fältet Namn.

När mallen har skapats måste du lägga till den i din globala profil eller mappnivåprofil. När mallen har lagts till börjar författarna se den nya mallen i processen för att skapa ämnen/kartor.

Med Alternativ-menyn på en befintlig mall kan du välja att **Redigera** eller **Duplicera** den. Vid duplicering behålls mallens struktur och typ \(av dokument\) och du kan återanvända den för att skapa en annan mall från den.

**Granska** -  ![](images/active-review-tasklist-icon.svg)

AEM innehåller en funktion för att visa alla granskningsuppgifter i dina projekt. Du kan visa alla granskningsprojekt och de aktiva granskningsåtgärderna i granskningsprojekten, som du är en del av från **Granska** -panelen.  Du kan sedan öppna granskningsåtgärderna och visa kommentarerna från olika granskare.
Granskningspanelen visar granskningsåtgärderna. Som författare kan du adressera kommentarerna i ett ämne med hjälp av webbredigeraren.


Så här visar du granskningskommentarerna i de aktiva granskningsuppgifterna som finns i dina projekt:

1. Välj granskning ![](images/active-review-tasklist-icon.svg)   till vänster. The **Granska** panelen öppnas.  Alla granskningsprojekt och aktiva granskningsåtgärder i granskningsprojekten som du är en del av visas.

   ![](images/web-editor-review-panel.png){width="300" align="left"}
1. Välj ett granskningsprojekt och välj sedan en granskningsuppgift i listan för att öppna den.
1. Du kan även filtrera dina projekt på följande sätt:

   - Ange söktermen eller texten som du vill hitta i projektets titel. Tryck sedan på Retur för att utföra sökningen. Du kan till exempel söka i alla projekt med termen&quot;space&quot; i titeln.

   - Välj ![](images/filter-search-icon.svg)  för att öppna **Filter** -dialogrutan. Du kan välja alla eller endast specifika projekt. De valda projekten listas i **Granska** -panelen.
     ![](images/active-review-select-project.png){width="300" align="left"}

     The **Uppgifter som jag har initierat** är aktiverat som standard. Du kan bara visa de uppgifter som du har initierat.

1. Som standard visas en lista över ämnen som har kommentarer kopplade till sig i granskningsprojektet. Använd de filter som behövs från den vänstra listen för att filtrera ämnen baserat på granskningskommentarerna som finns i dem:

   - **Visa alla ämnen**: Visar alla ämnen som finns i projekten.
   - **Visa ämnen med kommentarer**: Visa endast de ämnen som innehåller granskningskommentarer.
1. Du kan också ange söktermen eller texten som du vill söka efter i avsnittets rubrik eller filsökväg. De ämnen som innehåller termen i titeln eller filsökvägen visas.
1. Dubbelklicka på ett ämne för att öppna det i författarvyn. Du kan visa kommentarerna i **Kommentar** -panelen.
   ![](images/active-review-task-comments.png){width="800" align="left"}


   >[!NOTE]
   > 
   > The **Granska** och **Kommentar** Panelen är alltid synkroniserad. På panelen Kommentarer läses kommentarerna in baserat på granskningsåtgärden som läses in på panelen Granska.
   > Mer information om hur du hanterar kommentarerna finns i [Adressgranskningskommentarer](review-address-review-comments.md#).

**Sök och ersätt** -  ![](images/FindAndReplace_icon.svg)

Ikonen Sök och ersätt finns längst ned på den vänstra panelen. På panelen Sök och ersätt kan du söka efter och ersätta text mellan filer på en karta eller i en mapp i databasen. Du kan söka och ersätta i alla avsnitt av en karta samt i ämnen som finns i undermappningarna på kartan.

![](images/map-find-replace.png){width="800" align="left"}

Utför följande steg om du vill söka och ersätta globalt:

1. Öppna den globala **Sök och ersätt** -panelen.
1. Klicka på **Titta in i** Välj ett av följande alternativ för att utföra sökningen.
   - **Aktuell karta**: Söka i den öppna kartan

     >[!NOTE]
     >
     > Det här alternativet visas om du redan har öppnat en karta för redigering.

   - **Bana**: Om du vill söka på den markerade sökvägen
   - **Välj karta**: Om du vill söka i den markerade kartan

1. Du kan klicka på **Alternativ** och välj bland följande alternativ:

   - **Checka ut fil före Ersätt**: Välj det här alternativet om du vill checka ut en fil automatiskt innan du ersätter söktermen. Den här inställningen är mer relevant om administratören har aktiverat konfigurationen för utcheckning av en fil innan redigering. När backend-inställningen är aktiverad bör du välja det här alternativet. Det förhindrar att dialogrutan för utcheckning av filer uppmanar dig att checka ut alla filer innan du gör några ändringar. Om du inte markerar det här alternativet visas en uppmaning innan en fil öppnas för redigering.
   - **Endast hela ord**: Välj det här alternativet om du vill söka efter hela söksträngen. Om du t.ex. skriver över i söksträngen returnerar sökresultatet alla filer som innehåller ord som t.ex. over och overview. Om du vill begränsa sökningen till att returnera exakt den angivna termen väljer du det här alternativet.
   - **Skapa ny version efter ersättning**: Välj det här alternativet om du vill skapa en ny version av det ämne i vilket du väljer att ersätta texten. Du kan också ange versionskommentarer som läggs till för varje uppdaterad fil.

     Om du inte markerar det här alternativet sparas ändringarna i den aktuella versionen av ämnet och ingen ny version skapas.

   - **Inkludera indirekt referens**: Välj det här alternativet om du vill söka efter strängen i de indirekta referenserna även inom DITA-kartan. Som standard är detta inaktiverat, så sökningen utförs endast på direktreferenser.

1. Ange söktermen eller texten som du vill söka efter.
1. Ange den text som du vill ersätta söktermen med.
1. Tryck på Enter eller välj **Sök** icon \( ![](images/search-icon.svg)\) för att utföra sökningen.
1. Välj en fil i sökresultatlistan. Filen öppnas i området för innehållsredigering där den sökta termen är markerad i innehållet.
1. Öppna den globala **Sök och ersätt** -panelen.
1. Klicka på **Titta in i** Välj ett av följande alternativ för att utföra sökningen.

   - **Aktuell karta**: Söka i den öppna kartan

     >[!NOTE]
     >
     > Det här alternativet visas om du redan har öppnat en karta för redigering.

   - **Bana**: Om du vill söka på den markerade sökvägen
   - **Välj karta**: Om du vill söka i den markerade kartan

1. Du kan klicka på **Alternativ** och välj bland följande alternativ:

   - **Checka ut fil före Ersätt**: Välj det här alternativet om du vill checka ut en fil automatiskt innan du ersätter söktermen. Den här inställningen är mer relevant om administratören har aktiverat konfigurationen för utcheckning av en fil innan redigering. När backend-inställningen är aktiverad bör du välja det här alternativet. Det förhindrar att dialogrutan för utcheckning av filer uppmanar dig att checka ut alla filer innan du gör några ändringar. Om du inte markerar det här alternativet visas en uppmaning innan en fil öppnas för redigering.

   - **Endast hela ord**: Välj det här alternativet om du vill söka efter hela söksträngen. Om du t.ex. skriver över i söksträngen returnerar sökresultatet alla filer som innehåller ord som t.ex. over och overview. Om du vill begränsa sökningen till att returnera exakt den angivna termen väljer du det här alternativet.

   - **Skapa ny version efter ersättning**: Välj det här alternativet om du vill skapa en ny version av det ämne i vilket du väljer att ersätta texten. Du kan också ange versionskommentarer som läggs till för varje uppdaterad fil.

     Om du inte markerar det här alternativet sparas ändringarna i den aktuella versionen av ämnet och ingen ny version skapas.

   - **Inkludera indirekt referens**: Välj det här alternativet om du vill söka efter strängen i de indirekta referenserna även inom DITA-kartan. Som standard är detta inaktiverat, så sökningen utförs endast på direktreferenser.

1. Ange söktermen eller texten som du vill söka efter.

1. Ange den text som du vill ersätta söktermen med.

1. Tryck på Enter eller välj **Sök** icon \( ![](images/search-icon.svg)\) för att utföra sökningen.
1. Välj en fil i sökresultatlistan. Filen öppnas i området för innehållsredigering där den sökta termen är markerad i innehållet.

1. Klicka **Ersätt en förekomst** \( ![](images/replace-icon.svg)\) om du vill ersätta den markerade söktermen i avsnittet eller klicka på Nästa matchning ![](images/next-match-in-search.png) eller ![](images/previous-match-in-search.png) Föregående matchning om du vill gå till nästa eller föregående förekomst av texten.

1. Klicka **Ersätt alla i filen** \( ![](images/replace-all-in-file-icon.svg)\) om du vill ersätta alla förekomster av den sökta termen i en enda fil med ersätt-termen med ett enda klick. Du får ett meddelande när du har ersatt alla förekomster i den valda filen.

   >[!NOTE]
   >
   > Hovra över en fil från sökresultatlistan för att se ikonen Ersätt alla i fil till höger om den. Du kan också visa ikonen Ignorera fil för att ta bort filen från sökresultatet. De filer som du ignorerar tas bort från listan och den sökta termen ersätts inte i dem.

1. Klicka **Ersätt alla** \( ![](images/replace-all-in-file-icon.svg)\) till höger högst upp i listan om du vill ersätta alla förekomster av den sökta termen i alla filer med termen ersätt med ett enda klick.

   >[!NOTE]
   >
   > Aktivera **Ersätt alla** -ikonen måste systemadministratören välja alternativet **Aktivera Ersätt alla** under **Allmänt** tabba in **Inställningar för Redigeraren**.


Det går bara att ersätta en åtgärd åt gången i hela systemet, och tills åtgärden utförs visas statusen Ersätt alla pågående. Du kan också avbryta åtgärden Ersätt alla däremellan eller se loggrapporten. Om du avbryter åtgärden får du ett meddelande om det i Inkorgen. Du får ett meddelande om att åtgärden lyckades när alla förekomster i den valda filen har ersatts.

![](images/replace-all-in-progress.png){width="400" align="left"}

Du kan också använda **Sök på karta** från **Alternativ** menyn för en karta för att söka efter och ersätta text i en karta. Det här alternativet visas för en karta som öppnas på databaspanelen eller i kartvyn.

![](images/map-options-menu.png){width="550" align="left"}

## Innehållsredigeringsområde {#id2051EB000UI}

Innehållsredigeringsområdet är där innehållet i ditt ämne eller din karta visas. Du gör alla innehållsredigeringar i det här området. Det ger en WYSIWYG-vy över det innehåll du redigerar. Du kan ha flera ämnen öppna samtidigt, som visas på respektive flik. Under filens flik finns elementets bredd vid den aktuella markörpositionen. I det övre högra hörnet av området för innehållsredigering visas versionsnumret för det aktuella ämnet.

![](images/content-editing-area.png){width="650" align="left"}

## Höger panel {#id2051EB003YK}

Den högra panelen är en beständig panel som innehåller information om det markerade dokumentet.

>[!NOTE]
>
> Du kan ändra storlek på den högra panelen. Om du vill ändra storlek på panelen placerar du markören på panelkanten, pekaren ändras till en dubbelriktad pil, klickar och drar för att ändra storlek på panelbredden.

Den högra panelen ger dig tillgång till följande funktioner:

**Innehållsegenskaper** -  ![](images/content-properties-icon.svg)

Du kommer åt funktionen Innehållsegenskaper genom att klicka på ikonen Innehållsegenskaper i den högra panelen. Panelen Innehållsegenskaper innehåller information om vilken typ av element som är markerat i dokumentet och dess attribut. Du kan också lägga till attribut genom att markera attributet i listrutan och ange ett attributvärde.

>[!NOTE]
>
> Även om ämnet innehåller refererat innehåll kan du lägga till attribut på det med egenskapspanelen.

Om administratören har skapat en profil för attribut får du dessa attribut tillsammans med deras konfigurerade värden. Med innehållsegenskapspanelen kan du välja dessa attribut och tilldela dem till relevant innehåll i ditt ämne. På så sätt kan du också skapa villkorsstyrt innehåll som sedan kan användas för att skapa villkorsstyrda utdata. Mer information om hur du skapar utdata med hjälp av villkorliga förinställningar finns i [Använda förinställningar för villkor](generate-output-use-condition-presets.md#).

![](images/properties-tab-attributes_cs.png){width="300" align="left"}

**Filegenskaper** -  ![](images/topic-properties-icon.svg)

Visa egenskaperna för den markerade filen genom att klicka på ikonen Filegenskaper i den högra panelen. File Properties har följande två avsnitt:

**Allmänt**

I avsnittet Allmänt får du tillgång till följande funktioner:

![](images/file-properties-general.png){width="300" align="left"}

- **Namn**: Visar filnamnet för det markerade ämnet. Filnamnet är hyperlänkat till egenskapssidan för den markerade filen.
- **ID**: Visar ID:t för det markerade ämnet.
- **Metadatataggar**: Detta är metataggar för ämnet. De anges från taggfältet på egenskapssidan.
- **Språk**: Visar språket för ämnet. Den ställs in från språkfältet på egenskapssidan.
- **Skapad den**: Visar datum och tid då ämnet skapades.
- **Utcheckad av**: Visar användaren som checkade ut ämnet.
- **Dokumenttillstånd**: Du kan välja och uppdatera dokumenttillståndet för det ämne som är öppet. Mer information finns i [Dokumenttillstånd ](web-editor-document-states.md#)*.*

**Obs!** Du kan kopiera attributvärdena för de olika fälten i filegenskaperna till Urklipp.

**Referenser**

I avsnittet Referenser får du tillgång till följande funktioner:

![](images/file-properties-references.png){width="300" align="left"}

- **Används i**: I referenslistan listas de dokument där den aktuella filen refereras eller används.
- **Utgående länkar:** Utgående länkar visar de dokument som det aktuella dokumentet refererar till.

Håll muspekaren över filens referens och hämta filens sökväg och UUID i verktygstipset.

**Obs!** Alla Använd in- och utgående referenser är hyperlänkade till dokumenten. Du kan enkelt öppna och redigera länkade dokument.

Förutom att öppna filer kan du även utföra många åtgärder med **Alternativ** i avsnittet Referenser. Några av de åtgärder du kan utföra är Redigera, Förhandsgranska, Kopiera UUID, Kopiera sökväg, Lägg till i Favoriter, Egenskaper och Kontrollpanelen för Open Map.

**Granska** -  ![](images/review-icon.svg)

När du klickar på granskningsikonen öppnas granskningspanelen där du kan skapa en granskningsuppgift för det dokument som är öppet.

![](images/review-panel-before-opening.png){width="300" align="left"}

Om du har skapat flera granskningsprojekt kan du välja ett i listrutan och få tillgång till granskningskommentarerna.

Med hjälp av granskningspanelen kan du visa och publicera svar på kommentarer som ges i ämnet. Du kan godkänna eller avvisa kommentarerna en i taget.

Mer information finns i [Adressgranskningskommentarer](review-address-review-comments.md#).

**Spårade ändringar** -  ![](images/track-change-icon.svg)

Med funktionen Spårade ändringar i den högra panelen kan du visa information om alla uppdateringar som gjorts i ett dokument. Du kan även söka efter specifika uppdateringar av dokumentet.

>[!NOTE]
>
> Funktionen Spårade ändringar visar alla uppdateringar som har spårats med funktionen Aktivera/inaktivera Spåra ändringar i huvudverktygsfältet. Mer information finns i [Aktivera/inaktivera spåra ändringar](#id205DF0203Y4).

**Överordnat ämne:**[ Arbeta med webbredigeraren](web-editor.md)
