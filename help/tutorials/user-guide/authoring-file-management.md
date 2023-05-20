---
title: Hantera filer och mappar
description: Lär dig hur du hanterar filer och mappar
exl-id: e7810b06-f49f-467a-b987-a5e6f731d4cf
source-git-commit: 8073716bccacbe8d6a158b44d5106b083e3a5dcd
workflow-type: tm+mt
source-wordcount: '2502'
ht-degree: 0%

---

# Hantera filer och mappar {#id2116G0L08XA}

I det här avsnittet beskrivs hur AEM hanterar grundläggande filåtgärder, som kopiera, klistra in, dra och släppa samt ta bort filer. Följande scenarier är möjliga:

## Kopiera och klistra in filer

**Om filen har ett läsbart filnamn**

- *Om filen med samma namn inte finns i målmappen*: En ny kopia av filen skapas och ett UUID tilldelas också. Här är filnamnet detsamma som det ursprungliga filnamnet.
- *Om filen med samma namn redan finns i målmappen*: En ny kopia av filen skapas med suffixet \(som filename0.extension\). Ett UUID tilldelas också till den nya filen.


**Om filnamnet baseras på ett UUID-mönster**

- *Om filen med samma namn inte finns i målmappen*: En ny kopia av filen skapas och ett nytt UUID tilldelas också på den nya platsen. Här är filnamnet samma som UUID.
- *Om filen med samma namn redan finns i målmappen*: En ny kopia av filen skapas och ett nytt UUID tilldelas också. Filnamnet är samma som UUID.


## Kopiera och klistra in mappar

**Kopiera och klistra in mapp på samma plats**

- *Mappen innehåller filer med läsbara filnamn*: En ny kopia av mappen skapas med suffixet \(som mappnamn0\). Ett nytt UUID tilldelas också till filerna i mappen. Filnamnen ändras dock inte.

- *Mappen innehåller filer med filnamn som baseras på ett UUID-mönster*: En ny kopia av mappen skapas med suffixet \(som mappnamn0\). Ett nytt UUID tilldelas också till alla filer i den nya mappen. Filnamnen ändras också. filnamnen är samma som det nya UUID:t.


**Kopiera och klistra in mapp på en annan plats**

- *Mappen innehåller filer med läsbara filnamn*: En ny kopia av mappen skapas och ett nytt UUID tilldelas till alla filer i mappen på den nya platsen. Här ändras inte mapp- eller filnamnen.

- *Mappen innehåller filer med filnamn som baseras på ett UUID-mönster*: En ny kopia av mappen skapas med samma namn som den ursprungliga mappen. Ett nytt UUID tilldelas också till alla filer i den nya mappen. Filnamnen ändras också. filnamnen är samma som det nya UUID:t.


## Dra och släppa filer

**Dra-och-släpp med läsbara filnamn**

- *Dra och släpp på samma plats*: Du har möjlighet att **Skriv över befintlig fil\(er\)**, **Behåll båda filerna** och ett alternativ för att skapa en version av den befintliga arbetskopian.

   ![](images/uuid-human-readable-drag-drop-same-location.PNG){width="650" align="center"}

   Om du väljer **Skriv över befintlig fil\(er\)** ersätter filen som överförs den aktuella arbetsversionen av den befintliga filen på den ursprungliga platsen. UUID skapas eller ändras inte.

   Om du väljer **Behåll båda filerna** skapas en ny kopia av filen med suffixet \(som filename0.extension\). Ett nytt UUID tilldelas också till den nyligen kopierade filen.

   Om du väljer alternativet Skriv över befintlig fil, och väljer alternativet att skapa en version från den befintliga arbetskopian, skapas även en ny version från arbetskopian av dokumentet.

   >[!NOTE]
   >
   > **Skapa ny version för överförd fil** måste aktiveras av administratören. Om den här funktionen är aktiverad skapas en ny version för den överförda filen. Om alternativet är avmarkerat skapas ingen version av den överförda filen. Mer information finns i *Skapa ny version för överförd fil* i avsnittet Installera och konfigurera Adobe Experience Manager Guides as a Cloud Service.

   Om en fil redan har checkats ut av en annan användare för redigering, och du försöker överföra och skriva över den befintliga filen, misslyckas den och visar ett fel.

   >[!NOTE]
   >
   >The **Skriv över utcheckad fil vid överföring** funktionen måste inaktiveras av administratören. Om den här funktionen är aktiverad kan du skriva över utcheckade filer. Om funktionen inte är aktiverad går det inte att skriva över en utcheckad fil. Mer information finns i *Skriv över utcheckad fil vid överföring* i avsnittet Installera och konfigurera Adobe Experience Manager Guides as a Cloud Service.


- *Dra och släpp filer på en annan plats*: En ny kopia av filen skapas och ett nytt UUID tilldelas också på den nya platsen. Här är filnamnet detsamma som det ursprungliga filnamnet.


**Dra och släpp med filnamn som baseras på ett UUID-mönster**

*Dra och släpp filen på samma plats*: Du har möjlighet att **Skriv över befintlig fil\(er\)** tillsammans med alternativet att skapa en version av den befintliga arbetskopian.

![](images/uuid-drag-drop-same-location.PNG){width="650" align="center"}

När filen skrivs över ändras inte filnamnet eller dess UUID.

Om du väljer **Skapa version för befintlig arbetskopia** kan du välja att en ny version av arbetskopian av dokumentet ska skapas, När den nya filen överförs skapas även en ny version av filen och den skapas som arbetskopia av dokumentet.

**Skapa ny version för överförd fil** måste aktiveras av administratören. Om den här funktionen är aktiverad skapas en ny version för den överförda filen. Om alternativet är avmarkerat skapas ingen version av den överförda filen. Mer information finns i *Skapa ny version för överförd fil* i avsnittet Installera och konfigurera Adobe Experience Manager Guides as a Cloud Service.


*Dra och släpp filen på en annan plats*: Du har möjlighet att **Skriv över befintlig fil\(er\)**, **Flytta fil till ny plats** och ett alternativ för att skapa en version av den befintliga arbetskopian.

![](images/uuid-drag-drop-different-location.PNG){width="650" align="center"}

Om du väljer **Skriv över befintlig fil\(er\)** ersätter filen som överförs den befintliga filen på den ursprungliga platsen. UUID skapas eller ändras inte.

Om du väljer **Flytta fil till ny plats** , flyttas den befintliga filen till den aktuella platsen och skrivs sedan över med filen som överförs. När du flyttar en fil till den nya platsen bryts inte befintliga referenser från eller till filen.

Om du väljer alternativet att skapa en version från den befintliga kopian när du ersätter eller flyttar filerna skapas en ny version från arbetskopian av dokumentet. den nya filen antingen ersätts på den befintliga platsen eller flyttas till den nya platsen.


## Flytta flera filer samtidigt

AEM innehåller ett verktyg för flyttning av flera filer som hjälper en administratör att flytta en mapp med ett stort antal filer från en plats till en annan. Med det här verktyget kan du enkelt flytta filer i en eller flera mappar till en annan mapp i AEM. En av de viktigaste funktionerna i det här verktyget är att det inte bara flyttar ett stort antal filer, det bevarar även referenserna till och från de filer som flyttas. Du kan ändra antalet filer som du kan flytta i grupper utan att det påverkar redigerings- och publiceringsåtgärderna.

>[!NOTE]
>
> Verktyget Flytta gruppvis fungerar bara på mappnivå. Om du vill flytta enskilda avsnitt eller mappfiler använder du det vanliga flyttverktyget AEM resursgränssnittet.

Här är några av funktionerna som finns i verktyget Flytta satsvis:

- Du kan justera antalet filer som ska bearbetas i varje grupp. Detta kan kräva att du kör några tester innan du kommer fram till ett optimalt nummer som systemet enkelt kan hantera.
- Redigerings- och publiceringstjänsterna går smidigt utan avbrott i flyttningen.
- Ha fullständig kontroll över tidsintervallet mellan efterföljande batchprocesser av typen \(körning av\). Med det här tidsintervallet säkerställs att efterbearbetningen slutförs innan nästa grupp med filer startas.

- Automatisk hantering av mappar med samma namn. Den här funktionen ser till att även om det finns mappar med samma namn som flyttas, skrivs de inte över.

- Automatisk hantering av referenser till och från filer som flyttas.


Du måste tänka på följande innan du kör gruppbearbetningen:

- Om du planerar att flytta ämnen som är under granskning måste du stänga granskningsprocessen för alla sådana ämnen innan du flyttar dem. Granskningsprocessen avbryts om granskningsåtgärden inte stängs.
- Du får bara köra en enskild massflyttningsåtgärd på systemet när som helst. Detta säkerställer att referenser till och från ämnen som flyttas hanteras på rätt sätt.


Så här flyttar du flera filer samtidigt:

1. Klicka på länken Adobe Experience Manager överst och välj **verktyg**.
1. Välj **Stödlinjer** i listan över verktyg.
1. Klicka på **Verktyget Massflyttning** platta.

   Sidan Verktyg för flyttning av grupp visas.

   ![](images/bulk-move-tool_cs.PNG){width="550" align="center"}

1. Ange följande information på sidan Verktyg för flyttning av flera filer:

   - **Lägg till suffix till dubblettfiler**: Om du flyttar mappar med samma namn måste du markera det här alternativet. I skärmbilden ovan visas t.ex. **Källsökväg** innehåller namnet på de mappar som ska flyttas. Mappen med namnet topic finns på två olika platser - test-A och test-B. När du väljer det här alternativet flyttas mapparna. Den första flyttade mappen får namnet topic medan den andra mappen får namnet topic0. Flyttåtgärden lägger till ett suffix i sekventiell serie \(0, 1, 2 och så vidare\) i mapparna med samma namn.

      Om du flyttar mappar med samma namn utan att markera det här alternativet avbryts åtgärden med ett meddelande.

   - **Källsökväg\(er\)**: Ange platsen för de mappar som du vill flytta. Vanligtvis måste du kopiera och klistra in källplatsen från webbläsarens adressfält. Du kan ange flera mapplatser genom att klicka på **Lägg till** -knappen.

   - **Målsökväg**: Ange platsen där du vill flytta källmapparna.

1. Klicka **Massflyttning**.

   Systemet börjar flytta filer från källan till målplatsen. När processen är klar visas en sammanfattning av flyttprocessen längst ned på sidan.

   ![](images/bulk-move-summary.PNG){width="650" align="center"}


## Sök i DITA-innehåll

Som standard känner AEM inte igen DITA-innehåll, vilket innebär att det inte finns någon mekanism för att söka efter DITA-innehåll i dess databas. AEM stödlinjer lägger till ett lager ovanpå AEM, vilket gör att AEM kan förstå och bearbeta DITA-innehåll. Med funktionen Sök efter DITA-innehåll i AEM Guides kan du söka efter DITA-innehåll i AEM.

>[!NOTE]
>
>Systemadministratören kan konfigurera **DITA-element** sökkomponenten och sedan kan du använda funktionen från AEM Assets UI. Mer information finns i *Lägg till sökkomponenten för DITA-element i resursgränssnittet* i Installera och konfigurera Adobe Experience Manager Guides as a Cloud Service.

Med sökfunktionen kan du:

- söka efter DITA-innehåll baserat på ett elementvärde, till exempel `author`= xml
- Sök efter DITA-innehåll baserat på ett attributvärde; till exempel `@platform`= windows
- Använd en kombination av DITA-element och attributvärde. till exempel `author`= xml `AND` `@platform`= windows

Utför följande steg för att söka efter DITA-innehåll i AEM:

1. Öppna resursgränssnittet.

1. Välj **Filter**.

   ![](images/left-rail-filter.png){width="450" align="center"}

   Alternativen för innehållsfiltrering visas i den vänstra listen. Du hittar också filteralternativet DITA Element, som används för att filtrera DITA-innehåll.

   ![](images/dita-element-search.png){width="450" align="center"}

1. *\(Valfritt\)* I **Välj sökkatalog** bläddrar du till den plats du vill söka i.

1. I **DITA-element** filter, ange **Elementnamn**, **Attribut** och ett värde som du vill söka efter. Om du till exempel vill söka efter dokument som har `author` element som är `@type` skapare du behöver ange den information som visas på skärmbilden nedan:

   ![](images/search-params.png){width="650" align="center"}

   De sökvillkor som anges i **DITA-element** filtret visas högst upp i sökfältet. Filerna som matchar sökvillkoren visas i **Sökresultat** område.

   Tänk på följande när du anger sökvillkoren:

   - Om du vill söka efter en exakt fras anger du frasen i fältet Värde inom citattecken `"`frassökning`"`.
   - Du kan lägga till upp till tre sökvillkor för DITA-element.
   - Om du anger flera sökvillkor kombineras alla med hjälp av AND-logiken.
   - Du kan inte använda jokertecken i sökvillkoren. Om du till exempel vill söka efter plattformen \(attribut\) med värdet Windows kan du inte ange \*form eller Windows.

**Statusfilter för utcheckning i sökning**

Förutom DITA-elementfiltret kan du med hjälp av AEM stödlinjer även söka efter innehåll baserat på utcheckningsstatus. Detta är praktiskt när du snabbt vill filtrera bort filer som är utcheckade av dig och vill checka in dem igen.

Gör så här för att söka efter filer baserat på utcheckningsstatus:

1. Öppna resursgränssnittet.

1. Klicka **Filter** till vänster.
1. Ange söknyckelordet i sökfältet.
1. Använd de filter som krävs från vänster rulle.

   Du kan till exempel använda **Utcheckningsstatus** för att visa utcheckade eller incheckade ämnen. Du kan förfina den här listan ytterligare genom att välja användaren eller gruppen i listan Utcheckad av.

   Sökresultatet visas.


## Ta bort filer

Att ta bort filer från AEM är en begränsad funktion som styrs av systemadministratören. Beroende på konfigurationerna kan det vara svårt att ta bort filer om de är:

- Utcheckad
- Har inkommande eller utgående referenser

Du kan också ta bort filer endast om du tillhör en viss användargrupp som har behörighet att ta bort filer.

>[!NOTE]
>
> Mer information om konfigurationer för filhantering finns i *Förhindra borttagning av utcheckade filer* och *Förhindra borttagning av refererade filer* -avsnitt i as a Cloud Service Installera och konfigurera Adobe Experience Manager Guides.

Om administratören har gett alla användare behörighet att ta bort filer visas följande meddelande när du tar bort filer som innehåller referenser:

![](images/allow_unsafe_delete-force-delete.PNG){width="650" align="center"}

I det här fallet kan du framtvinga borttagning av filer utan att ta bort inkommande eller utgående referenser från filerna.

Om borttagningsbehörigheterna ges till en viss användargrupp visas även ovanstående meddelande för användare som tillhör den gruppen. För andra användare visas dock följande meddelande:

![](images/allow_unsafe_delete_for_delete_assets_group.PNG){width="650" align="center"}

I det här fallet kan användare inte ta bort filer förrän alla inkommande och utgående referenser har tagits bort.

## Arbeta med mediefiler

Mediefiler som bilder och videor är en viktig del av innehållet. När du överför och hanterar ditt innehåll kan du även arbeta med mediefiler.

Om mediefilen har ändrats kan du söka efter och förhandsgranska filerna i **Versionshistorik**.Så här tar du reda på ändringar i olika versioner av en mediefil:

1. Åtkomst till filen i **Resurser, användargränssnitt**.
1. Markera filen som du vill visa versionshistoriken för.
1. Klicka på **Versionshistorik** och välja en version.
1. Du kan också se miniatyrbilder av de olika versionerna under Versionshistorik.

   ![](images/media-version-history-icon.png){width="800" align="center"}

1. Välj den som du vill använda som grundversion i listan och klicka på **Förhandsgranska version**. Förhandsgranskningen av den valda versionen visas i fönstret Förhandsgranska version.

   ![](images/media-version-preview.png){width="650" align="center"}


**Överordnat ämne:**[ Hantera innehåll](authoring.md)
