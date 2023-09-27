---
title: Arbeta med den avancerade kartredigeraren
description: Lär dig hur du arbetar med den avancerade kartredigeraren i AEM. Lär dig funktionerna i den avancerade kartredigeraren. Redigera ämnen via en DITA-karta och använd layoutvyn, författarvyn och förhandsgranskningsläget.
exl-id: 4f48d489-d13e-4285-8870-373f0324f5f6
source-git-commit: 8504a0a52d381044bf1f0d6e7de3585ebecf3a7b
workflow-type: tm+mt
source-wordcount: '3701'
ht-degree: 0%

---

# Arbeta med den avancerade kartredigeraren {#id1942D0S0IHS}

Avancerad kartredigerare har ett intuitivt användargränssnitt och liknar Web Editor. När du öppnar en kartfil i Web Editor får du ett alternativ för att redigera kartfilen med hjälp av gränssnittet Avancerad kartredigerare. Med Avancerad kartredigerare kan du lägga till ämnesreferenser, nyckelreferenser, strukturera innehållet och mycket annat.

Förutom att redigera kartfiler direkt från Web Editor kan du även öppna ämnesfiler i en karta för redigering i Web Editor. I det här avsnittet beskrivs funktionerna i Avancerad kartredigerare och hur du kan öppna och redigera filer i en DITA-karta i webbredigeraren.

## Lägga till ämnen i en kartfil

Utför följande steg för att skapa kartfilen med hjälp av den avancerade kartredigeraren:

1. Navigera i resursgränssnittet till den kartfil som du vill redigera.

   >[!NOTE]
   >
   > Kontrollera att du inte har aktiverat resursurvalsläget.

1. Om du vill låsa kartfilen exklusivt markerar du kartfilen och klickar på **Checka ut**.

   >[!NOTE]
   >
   > När du har ett exklusivt lås på en kartfil kan andra användare inte redigera kartan. De kan dock arbeta med ämnen i kartfilen. Om administratören har konfigurerat Web Editor för att checka ut filer innan du redigerar kommer du inte att kunna redigera en fil förrän du checkar ut den. Om den är konfigurerad blir du ombedd att checka in en utcheckad fil innan du stänger den

1. När kartfilen är markerad klickar du på **Redigera ämnen**.

   ![](images/edit-map-main-menu.png){width="800" align="left"}

   Du kan också välja **Redigera ämnen** på kartfilens åtgärdsmeny:

   ![](images/edit-map-action-menu.png){width="800" align="left"}

   Kartfilen öppnas för redigering i webbredigeraren.

1. Klicka på **Redigera** -ikon.

   ![](images/edit-map-icon.png){width="550" align="left"}

   Kartan öppnas i gränssnittet Avancerad kartredigerare. Om du har öppnat en ny kartfil visas endast kartans titel i redigeraren.

   ![](images/new-map-file-in-editor.png){width="800" align="left"}

   - **A** - \(*Huvudverktygsfältet*\): Det liknar huvudverktygsfältet i Web Editor. Se [Huvudverktygsfältet](web-editor-features.md#id2051EA0G05Z) i Web Editor för mer information.

   - **B** - \(*Sekundärt verktygsfält*\) Det här är det sekundära verktygsfältet där du kan arbeta med kartfiler. Mer information om de funktioner som är tillgängliga via det sekundära verktygsfältet finns i [Funktioner i verktygsfältet i Avancerad kartredigerare](#id205DEC0005Z).

   - **C** - \(*Kartvyer*\): Gör att du kan växla mellan layouten, författaren, källan och förhandsvisningen i Kartredigeraren. The **Layout** I kan du ordna ämnen på en DITA-karta. Detta ger kartans träd eller hierarkiska vy. The **Upphovsman** I kan du redigera ämnen i Kartredigeraren. Detta ger även en WYSIWYG-vy av kartfilen. The **Källa** kan du arbeta med kartfilens underliggande XML. Med Förhandsgranska får du en samlad vy över alla avsnitt och undermappar i kartfilen. The **Stäng** länkar stänger kartfilen.

   - **D** - \(*Vänster panel*\): Ger åtkomst till den vänstra panelen så att du kan komma åt funktionerna Favoriter, Databas, Karta, Disposition och andra. Du kan expandera eller komprimera den genom att klicka på ikonen Expandera marginallist \(![](images/sidebar-expand-icon.svg)\). Mer information om funktionerna i den vänstra panelen finns i [Vänster panel](web-editor-features.md#id2051EA0M0HS) i webbredigeraren.

   - **E** - \(*Mittområde*\): Område för redigering av kartinnehåll.

   - **F** - \(*Höger panel*\): Ger åtkomst till panelen Egenskaper. Du kan se innehållsegenskaperna och mappningsegenskaperna för det markerade ämnet eller kartan. Mer information om de funktioner som är tillgängliga på den här panelen finns i [Höger panel](web-editor-features.md#id2051EB003YK) i webbredigeraren.

1. I den vänstra panelen växlar du till **Databasvy**.

1. I AEM-databasen navigerar du till den mapp som innehåller de ämnen eller undermappar som du vill lägga till.

1. Välj ämne- eller mappningsfilen i **Databasvy** och dra och släpp det i redigeringsområdet för kartinnehåll.

   Ämnet läggs till på kartan.

   ![](images/map-editor-add-topic.png){width="800" align="left"}

1. Om du vill lägga till efterföljande ämnen eller en undermappning drar och släpper du ämnet eller undermappningen till önskad plats på kartan.

   Tänk på följande när du skapar kartfilen:

   - Filen läggs till på en plats där det vågräta fältet visas i kartredigeringsområdet. På följande skärmbild visas *Ökning* kommer att läggas till mellan *Allmän beskrivning* och *Start- och landningswebbplats* ämnen.

     ![](images/horizontal-line-in-adv-map-editor.png){width="350" align="left"}

   - Om du vill ersätta ett ämne placerar du ämnet överst, till vänster eller till höger om det ämne som du vill ersätta. Ett lodrätt fält till vänster eller höger om ett ämne anger att det kommer att ersättas med det ämne som släpps på det.

     ![](images/vertical-bar-left-right.png){width="550" align="left"}

     Innan du ersätter ett ämne får du dock en bekräftelse. Ämnet ersätts först när du har bekräftat det.

     ![](images/replace-topic-confirm.png){width="300" align="left"}

   - Om du lägger till en undermapp till din DITA-karta visas underkartan som en länk i DITA-kartan. Om du vill visa alla ämnen i underkartan Ctrl-klickar du på länken för underkartan. Undermappens innehåll visas på en ny flik. Om du vill öppna ett ämne från DITA-kartan Ctrl-klickar du på ämneslänken så öppnas det på den nya fliken.

   - Du kan använda kortkommandona CTRL+Z och CTRL+Y eller deras respektive ikoner i verktygsfältet för att ångra eller göra om ändringar i kartan.

   - Om du vill ändra positionen för ett ämne markerar du ämnet \(genom att klicka på avsnittsikonen\) och drar och släpper det på önskad plats i kartfilen. Kontrollera att det vågräta fältet är synligt på den plats där du vill placera ämnet. I följande skärmbild är ämnet *Start- och landningswebbplats* flyttas efter *Ökning* ämne.

     ![](images/move-topic-adv-map-editor.png){width="350" align="left"}

   - Om du vill kontrollera kartfilens egenskaper högerklickar du var som helst i kartredigeringsområdet och väljer **Egenskaper** på snabbmenyn. Baserat på din AEM kan du se egenskaper som metadata, schemaaktivering, referenser, dokumenttillstånd med mera.

1. Klicka **Spara**.


## Funktioner i verktygsfältet i Avancerad kartredigerare {#id205DEC0005Z}

Verktygsfältet i Avancerad kartredigerare liknar avsnittet Webbredigerare. Grundläggande åtgärder som att växla den vänstra panelen, spara karta, skapa en ny version av kartan, ångra/göra om senaste åtgärden och ta bort de markerade elementen är vanliga i båda redigerarna. Mer information om hur dessa åtgärder fungerar finns i [Bekanta dig med Web Editors funktioner](web-editor-features.md#) -avsnitt.

Följande kartspecifika åtgärder är också tillgängliga i verktygsfältet i layoutvyn och författarvyn:

## Layoutvyn {#id205DEC0005Z_layout_view}

När du öppnar en karta för redigering öppnas layoutvyn i kartredigeraren. I layoutvyn visas karthierarkin i en trädvy där du kan ordna avsnitten i en karta.

>[!NOTE]
>
> I layoutvyn visas endast de referenser som finns i en karta. Om några referenser bryts visas en liten tvärsymbol till vänster om referensen

Du kan utföra följande åtgärder i layoutvyn:

**Infoga ämnesreferens** - ![](images/insert-topic-reference.png)

Visar dialogrutan för ämnessökning. Navigera till avsnittet/mappfilen som du vill infoga och klicka på Välj för att lägga till den på kartan.
![](images/insert-topic-reference-dialog.png){width="800" align="left"}


**Infoga ämnesgrupp** - ![](images/insert-topic-group.png)

Infoga `topicgroup` -element. Mer information om gruppering av ämnen finns i [topicgroup](https://docs.oasis-open.org/dita/v1.0/langspec/topicgroup.html) dokumentation i OASIS DITA Language Specification.

**Infoga nyckeldefinition** - ![](images/Key_icon.svg)

Visar dialogrutan Infoga nyckelord. Använd den här dialogrutan för att definiera en nyckeldefinition som du vill använda på kartan.

![](images/insert-key-definition-dialog.png){width="300" align="left"}

**Infoga före/infoga efter** - ![](images/insert_element_before_icon.svg) / ![](images/insert_element_after_icon.svg)

Visar dialogrutan Infoga element. Markera det element som du vill infoga på kartan. Beroende på åtgärden infogas det nya elementet före eller efter det aktuella elementet i kartan.

**Infoga frontpunkt** - ![](images/frontmatter.svg)

Den här ikonen visas när du öppnar ett bokschema för redigering. Du kan infoga komponenter i början av boken som en innehållsförteckning, ett index och en lista med tabeller.

**Infoga bakgrundsmaterial** - ![](images/backmatter.svg)

Den här ikonen visas när du öppnar ett bokschema för redigering. Du kan infoga komponenter för en ände av boken som ett index, en ordlista och en lista med illustrationer.

**Flytta det markerade objektet åt vänster/höger** - ![](images/left-arrow-icon.png) / ![](images/right-arrow-icon.png)

Klicka på vänsterpilen om du vill flytta ämnet mot vänster sida i hierarkin. Detta befordrar i huvudsak respektive ämne en nivå upp i hierarkin. Om du till exempel klickar på vänsterpilen medan ett underordnat ämne är markerat blir det samma ämne som det ovanför. På samma sätt, om du klickar på högerpilen, flyttas ämnet åt höger så att det blir underordnat ämnet ovanför det.

**Flytta det markerade objektet uppåt/nedåt![](images/arrowup.svg)** - / ![](images/arrowdown.svg)

Klicka på upp- eller nedpilsikonerna för att flytta ämnet uppåt eller nedåt i hierarkin.

>[!NOTE]
>
> Du kan också dra och släppa referenserna för att flytta dem på en karta.

**Lås/lås upp** - ![](images/LockClosed_icon.svg) / ![](images/LockOpen_icon.svg)

Hämtar ett lås på kartfilen och släpper låset. Om du har osparade ändringar i kartfilen uppmanas du att spara kartfilen när du släpper låset. Ändringarna sparas i den aktuella versionen av kartfilen.

**Sammanfoga** - ![](images/merge-icon.svg)

Mer information om hur du sammanfogar innehåll från en annan version av samma eller en annan fil finns i [Sammanfoga](web-editor-features.md#id205DF04E0HS) i webbredigeraren.

**Tidigare versioner** - ![](images/version-history-web-editor-ico.svg)

Kontrollera de tillgängliga versionerna och etiketterna för det aktiva ämnet och gå tillbaka till valfri version från redigeraren.

**Versionsetikett** - ![](images/version-label-icon.svg)

Visar dialogrutan för versionsetiketthantering. Välj en version i listrutan. Välj den etikett som du vill använda för den valda versionen och klicka på **Lägg till etikett** för att lägga till den.

**Visningsalternativ** - ![](images/view-options.svg)

Visar en listruta där du kan välja Visa radnummer, Visa kryssruta och Visa filnamn.

- **Visa radnummer**

Visar eller döljer radnumret för varje ämne. Radnumren visas beroende på nivån i hierarkin.

- **Visa kryssruta**

Visar eller döljer en kryssruta för varje ämne. Du kan använda kryssrutan för att markera ämnet och utföra olika åtgärder på Alternativ-menyn. Mer information finns i [Alternativ](#id228ID8006H8) -menyn.

- **Visa filnamn**

Visar filnamnet på ämnesrubrikerna.

>[!NOTE]
>
> När du håller pekaren över ett temats titel visas filsökvägen.


**Visa ämnen baserat på villkorsstyrda filter** Om du har tillämpat några villkor för ett ämne visas en filterikon till höger om ämnet. När du håller pekaren över en filterikon visas det använda villkoret och dess attributvärde.

**Menyn Alternativ i layoutvyn**

Förutom att ordna ämnen i kartfilen kan du även utföra följande åtgärder med Alternativ-menyn som är tillgänglig för ett element i layoutvyn:

![](images/map-editor-options-menu.png){width="650" align="left"}

- **Lägg till**: Du kan välja att lägga till ett nytt ämne eller en tom referens från Kartredigeraren:
   - **Tom referens**: Med det här alternativet kan du lägga till en tom referens på DITA-kartan. Du kan dubbelklicka på den infogade tomma referensen senare och lägga till ämnesinformationen. Mer information finns i [Skapa ett ämne](web-editor-features.md#id228ICI0105U) i webbredigeraren.
   - **Nytt ämne**: När du väljer att skapa ett nytt ämne på menyn visas dialogrutan Skapa nytt ämne. Ange nödvändig information i dialogrutan Skapa nytt ämne och klicka på Skapa. Mer information finns i [Skapa ett ämne](web-editor-features.md#id228ICI0105U) i webbredigeraren.
- **Flytta**: Du kan välja att flytta ett ämne uppåt/nedåt/höger/vänster i hierarkin.Du kan också dra och släppa ett ämne eller en karta från databaspanelen till kartan som öppnas i kartredigeraren.
- **Ångra**: Ångra den senaste åtgärden i layoutvyn.
- **Gör om**: Gör om den senaste åtgärden i layoutvyn.
- **Kopiera**: Kopiera den markerade referensen från kartfilen.

  >[!NOTE]
  >
  > Du kan visa och sedan markera kryssrutorna för att kopiera flera referenser.

- **Klistra in**: Klistra in de kopierade referenserna på den aktuella platsen i hierarkin.
- **Ta bort**: Ta bort de markerade referenserna från kartfilen.

  >[!NOTE]
  >
  > Du kan visa och sedan markera kryssrutorna för att ta bort flera referenser.


## Högerpanelen i kartredigeraren

På den högra panelen visas Innehållsegenskaper och Kartegenskaper i layoutvyn i kartredigeraren.

**Innehållsegenskaper**

Panelen Innehållsegenskaper innehåller information om vilken typ av ämne som är markerat på kartan, dess länk-URL och dess attribut. Mer information finns i [Innehållsegenskaper](web-editor-features.md#id228IDB00HMM) i webbredigeraren.

- **Andra attribut** Om administratören har skapat en profil för attribut får du dessa attribut tillsammans med deras konfigurerade värden. Med innehållsegenskapspanelen kan du välja dessa attribut och tilldela dem till relevant innehåll i ditt ämne. Du kan också tilldela attribut som konfigurerats av administratören under **Visa attribut** i redigeringsinställningarna. De attribut som är definierade för ett element visas i layoutvyn och dispositionsvyn. Detta hjälper dig att snabbt få en överblick över alla ämnen i en karta för vilka ett visst attribut har definierats. Alla ämnen som har plattformsattributet definierat som Android.

  ![](images/layout-inline-attributes.png){width="650" align="left"}


  Mer information finns i *Visa attribut* inom *Inställningar för Redigeraren* funktionsbeskrivning i [Vänster panel](web-editor-features.md#id2051EA0M0HS) -avsnitt.

- **Metadata** Med hjälp av metadata kan du ange metadatainformation. Du kan definiera navigeringsrubriken, länktexten, kortbeskrivningen och nyckelorden.

Mer information om attribut och metadata för standardämnen finns i [topicref](https://docs.oasis-open.org/dita/v1.2/os/spec/langref/topicref.html) dokumentation i OASIS DITA Language Specification.

**Kartegenskaper**

Visar dialogrutan Kartegenskaper där du kan ange attribut och metadatainformation för kartan.

## Författarvy {#id205DEC0005Z_author_view}

The **Upphovsman** I kan du redigera DITA-kartan i Web Editor. Detta visar WYSIWYG-vyn i kartredigeraren och några av de ikoner som visas i redigeringsvyn är desamma som layoutvyn. Mer information finns i [Layoutvyn](#id205DEC0005Z_layout_view). Dessutom kan du se följande ikoner och utföra relaterade uppgifter i redigeringsvyn:

**Infoga före/infoga efter** - ![](images/insert_element_before_icon.svg) / ![](images/insert_element_after_icon.svg)

Visar dialogrutan Infoga element. Markera det element som du vill infoga på kartan. Beroende på åtgärden infogas det nya elementet före eller efter det aktuella elementet i kartan.

**Infoga element** - ![](images/Add_icon.svg)

Visar dialogrutan Infoga element. Markera elementet som du vill infoga. Du kan använda tangentbordet för att bläddra igenom elementlistan och trycka på Retur för att infoga önskat element. Du kan också klicka direkt på elementet för att infoga det på kartan.

**Infoga relationstabell** - ![](images/relationship_table_icon.svg)

Infogar en relationstabell i kartan. Eftersom begreppet att arbeta med relationstabellen är detsamma som beskrivs i avsnittet Grundläggande kartredigerare finns mer information i [Arbeta med relationstabeller i den grundläggande kartredigeraren](map-editor-basic-map-editor.md#id1944B0I0COB) för mer information.

**Infoga återanvändbart innehåll** - ![](images/content-reuse-icon.png)

Visar dialogrutan Återanvänd innehåll. Använd den här dialogrutan för att infoga innehållet som du vill återanvända på kartan.

**Uppdatera navigeringsrubriksattribut** - ![](images/navtitle-refresh-icon.svg)

Synkroniserar `title` element i en refererad fil i en karta med det värde som anges i `@navtitle` -attribut. Du kan lägga till olika typer av referensfiler på en karta, till exempel avsnitt-, referens-, uppgift-, \(sub\)-kartor. De flesta av dessa filer har stöd för `@navtitle` -attribut. Om en fil innehåller `@navtitle` -attribut, sedan `@navtitle` attributet för samma fil på kartan uppdateras. Om `@navtitle` -attributet finns inte, sedan `@navtitle` attributet läggs till i referensfilen och dess `title` uppdateras även för att visa `@navtitle`.

>[!NOTE]
>
> Administratören kan konfigurera automatisk tillägg `@navtitle` för alla referensfiler som du lägger till på en karta. Mer information om hur du konfigurerar automatisk tillägg `@navtitle` attribut, se *Inkludera @navtitle-attribut som standard* i Installera och konfigurera Adobe Experience Manager Guides as a Cloud Service.

Klicka på ikonen Uppdatera navigeringsrubrikattribut för att synkronisera `title` -element och `@navtitle` attributets värden.

**Växla taggvy** - ![](images/Label_icon.svg)

Visar eller döljer XML-märkorden. Taggarna fungerar som visuella tecken som anger ett elements gräns. I det här läget, om du vill infoga en ämne/mappningsreferens, drar och släpper du den önskade filen före eller efter taggen. Det vågräta fältet visas inte i taggvyn.

**Aktivera/inaktivera spåra ändringar** - ![](images/track-change-icon.svg)

Du kan hålla reda på alla uppdateringar som gjorts i kartfilen genom att aktivera läget Spåra ändringar. När du har aktiverat spårändringar hämtas alla infogningar och borttagningar i dokumentet. Mer information finns i [Aktivera/inaktivera spåra ändringar](web-editor-features.md#id205DF0203Y4) i webbredigeraren.

**Skapa granskningsaktivitet** - ![](images/create-review-task-icon.svg)

Du kan skapa en granskningsåtgärd för det aktuella ämnet eller kartan direkt från webbredigeraren. Öppna filen som du vill skapa granskningsaktiviteten för och klicka på Skapa granskningsuppgift för att starta granskningsprocessen. Följ instruktionerna i [Granska ämnen och kartor](review.md#) för mer information.

## Redigera ämnen via DITA-kartan {#id17ACJ0F0FHS}

Om du redigerar ett enskilt ämne får inte författaren hela kontexten. En författare har ingen information om var ett ämne placeras på en DITA-karta. Utan den här kontextuella informationen blir det lite svårt för författare att skapa innehåll.

Med AEM Guides kan författare öppna en DITA-karta i webbredigeraren och se var ämnen finns på kartan. Detta hjälper författare att veta exakt var exakt ämnet placeras på kartan och skapa mer relevant innehåll. Om det finns flera författare som arbetar med ett projekt kan de också veta vilka ämnen som är tillgängliga på kartan och återanvända innehållet där det behövs.

Så här redigerar du ämnen via en DITA-karta:

1. Navigera till DITA-kartan som innehåller de ämnen du vill redigera i resursgränssnittet.
1. Klicka på DITA-kartan för att öppna den i DITA-kartkonsolen.
1. Välj **Ämnen** om du vill visa en lista med ämnen som är tillgängliga på DITA-kartan.

   >[!TIP]
   >
   > På fliken Ämnen kan du hämta kartfilen med tillhörande beroenden. Mer information finns i [Exportera en DITA-kartfil](authoring-download-assets.md#id218UBA00IXA).

1. Klicka på i huvudverktygsfältet **Redigera ämnen**.

   DITA-kartan öppnas i webbredigeraren.

   >[!NOTE]
   >
   > Du kan också välja DITA-mappningsfilen i resursgränssnittet och klicka på **Redigera ämnen** i huvudverktygsfältet för att starta Web Editor.

   ![](images/web-editor-map-view_cs.png){width="350" align="left"}

1. \(*Valfritt*\) Du kan också välja ett ämne på kartan och checka ut filen innan du redigerar den. Om du vill checka ut filen väljer du en eller flera filer i den vänstra rutan och klickar på **Utcheckning**. Du kan också låsa upp en fil genom att markera den utcheckade filen och klicka på **Avbryt utcheckning och Lås upp** i Kartvyn.

   >[!IMPORTANT]
   >
   > Om administratören har konfigurerat **Inaktivera redigering utan utcheckning** måste du checka ut filen innan du redigerar. Om du inte checkar ut filen öppnas dokumentet i skrivskyddat läge i redigeraren.

   Följande skärmbild markerar ikonerna för utcheckning och låsning \(A\), Avbryt utcheckning och Lås upp \(B\), Spara som ny version och Lås upp \(C\), Redigera \(D\), Förhandsgranska \(E\), olika ikoner med olika filtyper i DITA \(F\) och filer som är utcheckade \(G\).

   ![](images/file-checkout-map-editor.png){width="550" align="left"}

1. Klicka på en ämneslänk för att öppna den i Web Editor för redigering.

   Du kan öppna flera ämnen i redigeraren och varje ämne öppnas på en ny flik i redigeraren. Även om din DITA-karta innehåller underkartor öppnas även ämnen från underkartorna på en ny flik för redigering. Om du vill visa ämnen under en undermappning kan du klicka på och expandera undermappningen.

   ![](images/web-editor-multiple-topics.png){width="800" align="left"}

   Om du klickar på en kartfil öppnas kartan på en ny flik i webbläsaren.

1. När du är klar med redigeringen av ämnena kan du göra följande:

   - Du kan spara dem en och en. Klicka på **Stäng utan att spara** Om du har frågor visas en dialogruta där du uppmanas att spara de osparade avsnitten:

     ![](images/save-multiple-topics.PNG){width="550" align="left"}

     Du kan välja att spara alla markerade ämnen eller avmarkera de ämnen som du inte vill spara.

   - Du kan checka in ämnet med **Spara som ny version och lås upp** -knappen. När du sparar en revidering av ämnet skapas en ny revidering och låset släpps också.
   - Om administratören har aktiverat alternativet att checka in filer när de stängs visas en uppmaning om att spara filer när de utcheckade filerna stängs. När det här alternativet är aktiverat visas listan med utcheckade filer som behöver sparas när du stänger redigeraren med ändrade filer. De utcheckade filerna visas med en låsikon:

     ![](images/save-on-close.PNG){width="550" align="left"}

      - Klicka på **Stäng utan att spara** stänger filerna utan att spara några ändringar.

      - Klicka på **Spara** sparar ändringarna, men checkar inte in filerna.

      - Markera **Kontrollerar filer** och sedan klicka på **Spara** -knappen checkar in filerna \(skapar en annan version\) och sparar även filerna.


## Förhandsgranska en karta

Förutom att kunna se positionen för varje ämnesfil i en karta, är det önskvärt att kartinnehållet visas i ett sammanhängande flöde. Med funktionen Förhandsgranska karta kan du se hela innehållet i karfilen med ett enda klick. Du behöver inte generera utdata från kartfilen för att se hur hela kartan kommer att se ut när den har publicerats. Du kan enkelt öppna kartans förhandsgranskning och alla ämnen och undermappar återges i form av en bok.

Du kommer åt förhandsgranskningen av en karta från:

- **Resursgränssnitt**: I resursgränssnittet navigerar du till kartpositionen, markerar kartfilen och väljer **Förhandsgranska karta** i verktygsfältet. Förhandsgranskningen av kartan visas på en ny flik. Du kan visa innehållet i alla ämnen i förhandsgranskningsläget. I den här vyn kan du inte redigera något ämne.

  >[!NOTE]
  >
  > Om *Förhandsgranska karta* alternativet är inte synligt i huvudverktygsfältet, det kan ha flyttats under **Mer** verktygsfältmenyn.

- **Avancerad kartredigerare**: I Avancerad kartredigerare klickar du på ikonen Förhandsgranska för att visa förhandsgranskningen av den aktuella kartan.

  ![](images/map-preview-icon.png){width="350" align="left"}

  Du kan utföra följande åtgärder i förhandsgranskningsläget:

   - Högerklicka på ett ämne och välj **Redigera** om du vill öppna ämnet för redigering på en ny flik.

     >[!NOTE]
     >
     > Om du inte har redigeringsbehörighet öppnas avsnittet i skrivskyddat läge.

   - Hoppa till det önskade avsnittet genom att klicka på ämnesrubriken i schematrädet \(i den vänstra panelen\).

   - Det aktuella avsnittet i förhandsvisningen av kartan markeras också i schematrädet.


**Överordnat ämne:**[ Arbeta med kartredigeraren](map-editor.md)
