---
title: Dokumenttillstånd
description: Lär dig hur du använder dokumentläget
source-git-commit: 13106cd1c7f6d38fecb67dd93eef66263eb29bae
workflow-type: tm+mt
source-wordcount: '916'
ht-degree: 0%

---


# Dokumenttillstånd {#id1821HC00URO}

För att hantera dokumentens beredskap AEM stödlinjerna egenskapen för dokumentläge för att ange dokumentets aktuella läge. Med dokumentlägen kan du snabbt ta reda på om ett dokument är nytt, håller på att granskas eller granskas som färdigt.

## Typer av dokumentlägen

Ett dokument kan ha något av de dokumentlägen som är definierade i dokumentlägesprofilen. Ett dokument kan till exempel ha något av följande dokumentlägen:

- Utkast - Anger att dokumentet har skapats och sparats med nya ändringar.
- Granskning - Anger att ett granskningsarbetsflöde har initierats för dokumentet.
- Granskad - Anger att dokumentet har granskats av de avsedda användarna.

Dessa lägen ställs in manuellt eller automatiskt enligt dokumentlägesprofilinställningarna. Om dokumentlägesprofilen till exempel är konfigurerad med startläge som utkast och läget Under granskning är definierat för dokument som granskas. När du sedan skapar ett dokument ställs dokumentläget in på *Utkast*. Om du initierar en granskningsåtgärd ändras dokumentets status till Under granskning.

Du kan också ändra dokumentläget manuellt för ett eller flera dokument. Om du väljer att ändra dokumentläget för flera dokument bestäms emellertid det tillåtna läget av de gemensamma lägena som är tillåtna för de markerade dokumenten. Anta att du har definierat dokumentlägena som Utkast, Granskning, Granskad och Klart att publicera i samma ordning. På dokument ett.dita är läget inställt på *Utkast* och i dokumentet två.dita ställs läget in på Granskad. När du markerar båda - en.dita och två.dita, blir dokumentläget tillåtet *Klar att publicera*. Som two.dita är *Granskad* state, nästa möjliga läge för two.dita är bara *Klar att publicera*, som visas när båda dokumenten är markerade.

>[!NOTE]
>
> Ett dokument kan bara finnas i ett läge åt gången.

## Ändra dokumentläge

Så här ändrar du ett dokuments status:

1. I resursgränssnittet markerar du ett eller flera dokument som du vill ändra dokumenttillståndet för.
1. Klicka på **Egenskaper**.
1. Välj det nya läget på menyn **Dokumenttillstånd** nedrullningsbar meny. Du kan bara markera de dokumentlägen som är tillåtna i avsnittet Tillståndsövergång i dokumentlägesprofilen.

   >[!NOTE]
   >
   >Administratörer kan se alla dokumenttillstånd och ändra dokumentet till ett möjligt läge.

1. Klicka **Spara och stäng**.

## Visa dokumentläge

Kortvyn i resursgränssnittet visar det aktuella läget tillsammans med datumet och storleken för det aktuella DITA-avsnittet eller DITA-kartan.

![](images/document_state.png){width="800" align="left"}

## Använd dokumentlägen i DDLC

Dokumenttillstånd spelar en viktig roll när det gäller att hantera dokumentens livscykel i DDLC. Om organisationen följer DDLC:n strikt blir det en viktig funktion att ha en funktion för att styra redigering av dokument baserat på deras tillstånd. Du kan till exempel tillåta redigering av dokument när de finns i *Utkast* eller *Granskning* lägen. När ett dokument har granskats och är klart att publiceras bör det dock finnas ett sätt att förhindra ytterligare ändringar av dokumentet.

AEM Guides ger ett arbetsflöde för dokumentgodkännande som hjälper dig att styra dokumentutvecklingsprocessens livscykel. När ett dokument är klart att publiceras eller har nått det näst sista läget kan du markera det som godkänt. När ett dokument har godkänts skapar AEM stödlinjer en ny version av dokumentet och gör det skrivskyddat. Du kan sedan flytta dokumentet för publicering eller skapa en baslinje för vidare bearbetning.

Om du vill starta ett nytt releaseformulär för de dokument som har markerats som godkända måste en författare starta en ny release. När du startar en ny release ändras dokumentets status till *Utkast* igen. Genom att ändra dokumentläget till *Utkast* blir dokumentet redigerbart igen och du kan fortsätta arbeta med nästa version.

Så här använder du funktionen för dokumentgodkännande:

>[!NOTE]
>
> Arbetsflödesfunktionen för godkännande måste aktiveras av administratören. Mer information finns i *Aktivera arbetsflöde för godkännande* i avsnittet Installera och konfigurera Adobe Experience Manager Guides as a Cloud Service.

1. Öppna det dokument som du vill markera för godkännande i Web Editor.

1. Klicka på **Markera som godkänd**![](images/mark_approve_icon.svg) ikon.

1. Om dokumentet är i ett läge som ska markeras som godkänt visas följande dialogruta:

   ![](images/mark-approved-correct-state.png){width="550" align="left"}

   Om dokumentet inte kan markeras som godkänt visas följande meddelande:

   ![](images/mark-approved-incorrect-state.png){width="550" align="left"}

1. Om dokumentet är klart att markeras som godkänt väljer du en etikett i listrutan och klickar på **Godkänn**.

   >[!NOTE]
   >
   > Om administratören inte har konfigurerat en fördefinierad lista med etiketter visas ett friformstextfält där du kan ange en etikett.

1. När dokumentet har markerats som godkänt är **Förhandsgranska** i dokumentet visas i skrivskyddat läge.

   ![](images/approved-doc-read-only.png){width="650" align="left"}

   >[!NOTE]
   >
   > I förhandsgranskningsläget tas alla redigeringsalternativ bort från verktygsfältet. Dessutom togs även dokumentets författar- och källvy bort från den övre navigeringen.


När ett dokument har markerats som godkänt går det inte längre att redigera. Om du vill använda dokumentet till nästa version måste du skicka tillbaka det till *Utkast* tillstånd. Så här ändrar du dokumentstatus för ett godkänt dokument tillbaka till *Utkast* utför du följande steg:

1. I ett godkänt dokument klickar du på **Starta en ny release** Ikon ![](images/approved-restart-draft-mode-icon.svg).

   Meddelandet Starta ny release visas.

1. Klicka **Bekräfta**.

   Dokumentets läge ändras till Utkast och dokumentet öppnas i webbredigeraren i redigeringsläge.


**Överordnat ämne:**[ Arbeta med webbredigeraren](web-editor.md)

