---
title: Översätta dokument från Web Editor
description: Översätt ditt innehåll till flera språk från webbredigeraren. Lär dig hur du skapar ett översättningsprojekt, lägger till regler, visar versioner och stänger filer som inte är synkroniserade i AEM.
source-git-commit: 880cd344ceb65ea339be699ebcad41c0d62e168a
workflow-type: tm+mt
source-wordcount: '1907'
ht-degree: 0%

---

# Översätta dokument från Web Editor {#id21BKF0Z0YZF}

>[!TIP]
>
> Vi rekommenderar att du använder den här översättningsfunktionen i webbredigeraren om du har uppgraderat till AEM Guides as a Cloud Service February 2022 eller senare.

AEM Guides har en kraftfull funktion i Web Editor som gör att du kan översätta ditt innehåll till flera språk. Du kan skapa ett nytt översättningsprojekt och sedan lägga till översättningsjobben i det befintliga översättningsprojektet. Du kan också skapa ett flerspråkigt översättningsprojekt som innehåller översättningsjobb för alla valda språk.

>[!NOTE]
>
> Administratören kan konfigurera fliken Hantera \(används för översättning\) i Web Editor. Mer information finns i *Konfigurera översättningsfunktionen i webbredigeraren* i avsnittet Installera och konfigurera Adobe Experience Manager Guides as a Cloud Service.

## Innan du börjar

Innan du utför stegen i den här proceduren måste du se till att du har skapat språkroten och målmapparna

1. Skapa en rotmapp där källinnehållet lagras. Rotmappen måste skapas med språknamnet \(till exempel engelska\) eller språkkoden \(en\).
1. Skapa de målmappar som du vill översätta innehållet till. Om du till exempel vill översätta ditt innehåll till tyska eller franska måste du skapa en mapp med namnet -de \(för tyska\) eller -fr \(för franska\).

>[!NOTE]
>
> Rotmappen och målmapparna måste skapas på samma nivå.

## Skapa ett översättningsprojekt

1. Öppna DITA-mappningsfilen i mappningsvyn på databaspanelen.
1. Klicka på **Hantera** -fliken. På översättningspanelen visas den hyperlänkade titeln för DITA-kartan tillsammans med **Språk** lista.
1. Från **Språk** väljer du den språkinställning som du vill översätta projektet till. Du kan välja **Alla** för att översätta projektet till alla tillgängliga språk.

   >[!NOTE]
   >
   > Listan innehåller språkmapparna tillsammans med deras språkkoder. Till exempel franska \(fr\) och tyska \(de\).

   >[!IMPORTANT]
   >
   > Språk visar endast de språk för vilka en språkmapp skapas parallellt med källspråket. En språkmapp som skapats på en annan nivå, t.ex. en nivå ned från källspråksmappen, visas inte heller. Se till att du skapar alla målspråksmappar på samma nivå som källspråksmappen.

   ![](images/translation-languages.png){width="350" align="left"}

1. Du kan även använda följande alternativ:

   **Använd baslinje:** Du kan välja en baslinje för att översätta projektet. Klicka på Använd baslinje och välj en baslinje som skapats på kartan. Alla filer som ingår i den valda baslinjen visas på översättningssidan. När innehållet har översatts kan du exportera den översatta baslinjen. Mer information om hur du exporterar den översatta baslinjen finns i [Exportera översatt originalplan](generate-output-use-baseline-for-publishing.md#id196SE600GHS).

   **Använd den senaste versionen som den**: Välj om du vill filtrera ämnesversionen utifrån datum och tid när de skapades. När du väljer ett datum och en tid visas endast den senaste versionen av filerna som skapades på eller före det valda datumet och tiden.

1. Klicka **Använd**. En lista med information om ämnen och associerade resurser visas.
1. Markera de ämnen som du vill skicka för översättning. Du kan också använda alternativen för ämnesfiltrering för följande kolumner:

   - **Titel**: Källfilens namn.  Håll pekaren över källfilens namn för att visa målfilens eller den översatta filens namn.
   - **Filnamn**: Källfilens namn
   - **Filtyp**: Källfilens typ. De tillgängliga alternativen är Karta, Ämne och Bild.
   - **Referenstyp**: Direkta eller indirekta referenser
   - **Version**: Källfilens versionsnummer
   - **Versionsetikett**: Etikett för den valda versionen av källfilen
   - **Målversion**: Målfilens versionsnummer
   - **Dokumenttillstånd**: Källfilens tillstånd. De tillgängliga alternativen är Utkast, Under granskning och Granskad.
   - **Målspråk**: Det språk som du vill översätta källfilen till
   - **Översättningsstatus**: De tillgängliga alternativen är: Osynkroniserad, Kopia saknas, Pågår och Synkroniserad.
   - **Måletikett**: Etikett för den valda versionen av målfilen
1. Klicka **Skicka för översättning** längst upp till höger.

   ![](images/translation-send.png){width="800" align="left"}

1. Välj **Skapa ett nytt översättningsprojekt**.

   ![](images/translation-project-types.png){width="350" align="left"}

   Förutom ett nytt översättningsprojekt kan du även välja mellan följande alternativ:

   - Du kan **Skapa en struktur** endast för översättningsprojektet.
   - Du kan **Skapa ett nytt XLIFF-översättningsprojekt** för att konvertera XML-innehållet till XLIFF (XML Localization Interchange File Format). XLIFF är ett öppet XML-baserat format som används för att standardisera dataöverföringen mellan olika verktyg som används i innehållsöversättningsprocessen. AEM har stöd för XLIFF version 1.2. I ett XLIFF-projekt exporteras innehållet till det branschledande XLIFF-formatet, som kan tillhandahållas översättningsleverantörer. XLIFF-formatet möjliggör återanvändning av segment som du redan har översatt under översättningsfasen.\
     När XLIFF-innehållet har översatts kan det importeras till AEM stödlinjer, vilket skapar en översatt version av det ursprungliga DITA-projektet.

     >[!NOTE]
     >
     > XLIFF-export fungerar bara med mänsklig översättningskonfiguration.

   - Du kan välja **Skapa ett nytt flerspråkigt översättningsprojekt** som kommer att innehålla översättningsjobb för alla språk som du har valt för översättning. Om du till exempel har valt franska, tyska och spanska skapas ett projekt som innehåller översättningsjobb för alla tre språken.
   - Om du redan har ett översättningsprojekt kan du lägga till ämnen i det projektet. Välj Lägg till i **Befintligt översättningsprojekt** i projektlistan och välj ett projekt i listan Befintliga översättningsprojekt. Du kan sortera dessa projekt efter den senaste, stigande eller fallande ordningen.

     >[!NOTE]
     >
     > Om ditt befintliga projekt är ett omfångsprojekt har det &#39;\(omfång\)&#39; i sitt namn.

   - Om du behöver skapa omfånget för ett projekt som ska översättas kan du välja **Skapa ett nytt omfångsöversättningsprojekt**. Kopiorna skickas inte för översättning och den ursprungliga översättningsstatusen för filerna behålls. Det påverkar inte målspråkskopian av ämnen som skickas för omfång.
1. I **Projektets titel** anger du en rubrik för projektet.
1. Klicka **Skapa** för att skapa ett nytt översättningsprojekt.

   Ett nytt översättningsprojekt skapas med den valda versionen av ämnena. Nu visas ett popup-meddelande som bekräftar att översättningsprojektet har skapats. När alla målspråkskopior är tillgängliga i översättningsprojektet visas ett meddelande i Inkorgen. När målspråkskopiorna är tillgängliga i översättningsprojektet kan du påbörja översättningsjobbet. Mer information finns i [Starta översättningsjobbet](translation-first-time.md#id225IK030OE8).

   >[!NOTE]
   >
   > Om du avvisar översättningen för ett eller flera ämnen i ett översättningsjobb, visas **Pågår** översättningsstatusen för alla avvisade ämnen återställs till den ursprungliga statusen. Statusen för de refererade ämnena kontrolleras och återställs enligt det senaste översättningstillståndet. Översättningsfilerna som skapats i målprojektet tas inte bort även om översättningen avvisas för dem.

## Lägg till översättningsreglerna

Med AEM Guides kan administratören konfigurera översättningsreglerna. SRX-formatet (Segmentation Rules eXchange) är en standard för utbyte av segmenteringsregler mellan olika användare och olika översättningsmiljöer. Du kan skapa en mapp och lägga till dina anpassade SRX-filer i den.

SRX-filer ska namnges som `<language-code>.srx`. Exempel: en-US eller ar-AE.

>[Anteckning]
>Titeln är inte skiftlägeskänslig, så du kan ha &#39;en-US&#39;, &#39;en-us&#39; eller &#39;EN-us&#39;. AEM kan också matcha &#39;-&#39; (bindestreck) eller &#39;_&#39; (understreck). Du kan alltså ha &#39;en-US&#39; eller &#39;en_US&#39;.

Du kan också placera de här filerna i en mapp under AEM resursrot som är `./content/dam`.



När du har skapat mappen som innehåller SRX-filerna kan du lägga till mappsökvägen i platskonfigurationen för Translation SRX i mappprofilen.

Vi rekommenderar att du bara behåller SRX-filer i den mapp som är konfigurerad i mappprofilen för att få bättre prestanda.


AEM Guides väljer SRX-reglerna enligt översättningsprojektets källspråk. Den söker efter en anpassad SRX-fil för ett språk, och om du inte definierar en anpassad SRX-fil väljs reglerna enligt reglerna för översättning utanför rutan.


Mer information om hur du konfigurerar globala profiler och profiler på mappnivå finns i *Konfigurera redigeringsmallar* i Installera och konfigurera Adobe Experience Manager Guides as a Cloud Service.

## Skicka versionsetiketten till målversionen

Med AEM stödlinjer kan du skicka källfilens etikett till målfilen. Det gör det enklare att identifiera källversionen för den översatta filen.

Om du vill lägga till källversionsetiketten i målkopian måste systemadministratören välja alternativet **Sprid källversionsetiketter till målversionen** under **Översättning** tabba in **Inställningar för Redigeraren**.

Om du till exempel har källfiler med versionsetiketten `Release 1.0` som används på dem kan du också skicka källetiketten \(`Release 1.0`\) till den översatta filen.

![](images/translation-pass-source-label.png){width="650" align="left"}

>[!NOTE]
>
> Källetiketten är bara kopplad till en målversion. Om du flyttar källetiketten till en annan version återspeglas den automatiskt i den senaste måletiketten.

## Visa versionsskillnad för filer som inte är synkroniserade 

AEM innehåller en funktion för att kontrollera skillnaderna mellan den valda versionen och den senaste översatta källversionen av avsnitten. Du kan översätta **Slut på synkronisering** filer baserat på gjorda ändringar.

![](images/translation-version-diff.png){width="800" align="left"}

Välj **Visa differens** icon \(![](images/show-difference-icon.svg)\) om du vill se skillnaderna mellan den senaste översatta versionen och den aktuella versionen av den markerade filen.

>[!NOTE]
>
> **Visa differens** icon \(![](images/show-difference-icon.svg)\) visas bara för DITA-filer som har översättningsstatusen som **Slut på synkronisering**.

The **Versionsskillnad** visas. Den visar **Senaste översatta version** och **Vald version** nummer till vänster. I förhandsgranskningsfönstret visas skillnaderna mellan den senaste översatta versionen och den valda versionen av ämnet.

![](images/version-diff.png){width="650" align="left"}

## Stäng av synkroniserade resurser

Om du gör ändringar i vissa resurser blir dessa resurser inte synkroniserade. Du kan antingen översätta de ändrade resurserna på nytt eller välja att inte längre synkronisera. Om du t.ex. har gjort några mycket små ändringar som egentligen inte behöver en översättning, kan du markera deras status som Synkroniserad.

Så här stänger du statusen Skickat synkronisering:

1. Markera de icke-synkroniserade resurser som du vill ändra statusen för.
1. Välj **Synkronisera markering** button \(![](images/translation-mark-in-sync-icon.svg)\) överst. The **Synkronisera markering** visas.

   ![](images/translation-mark-in-sync.png){width="550" align="left"}

1. Klicka **Tvinga synkronisering**. Statusen är synkroniserad för de valda Out-of-sync-resurserna.

>[!NOTE]
>
> **Synkronisera markering** button \(![](images/translation-mark-in-sync-icon.svg)\) visas bara för resurser som har översättningsstatusen Inte synkroniserad.

## Visa pågående översättningsprojekt för en karta eller ett ämne

Vissa av referenserna på översättningsinstrumentpanelen kanske håller på att bearbetas. Dessa referenser har en **Pågår** länk under **Översättningsstatus** kolumn. När du klickar på länken **Pågående projekt** öppnas. I dialogrutan visas en lista med alla pågående översättningsprojekt \(tillsammans med målspråket\) som innehåller den valda referensen.

>[!NOTE]
>
> Du kan se länken Pågår för de översatta projekt som har skapats i AEM Guidad as a Cloud Service februari 2023 eller senare.

Klicka på namnet på referensen i dialogrutan för att öppna den i förhandsgranskningsläge. Du kan också klicka på översättningsprojektet för att starta översättningen.

![](images/translation-in-progress.png){width="550" align="left"}

**Överordnat ämne:**[ Arbeta med webbredigeraren](web-editor.md)
