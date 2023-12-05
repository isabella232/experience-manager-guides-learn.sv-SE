---
title: Statusrapport för konvertering
description: Konvertera dokument i olika format till DITA i AEM. Lär dig hur du lägger till filter och visar en konverteringsstatusrapport.
source-git-commit: 880cd344ceb65ea339be699ebcad41c0d62e168a
workflow-type: tm+mt
source-wordcount: '319'
ht-degree: 0%

---

# Statusrapport för konvertering {#id205BBA00WZZ}

AEM Guides har en robust konverteringsfunktion för att konvertera dokument i olika format till DITA. I Conversion Status Report finns en samlad vy över alla konverteringsåtgärder som AEM Guides utför.

Följ de här stegen för att visa rapporten om konverteringsstatus:

1. Klicka på länken Adobe Experience Manager överst och välj **verktyg**.

1. Välj **Stödlinjer** i listan över verktyg.

1. Klicka på **Statusrapport för konvertering** platta.

   Statusrapporten för konvertering visas för alla konverteringsåtgärder som körs i systemet.

   ![](images/conversion-status-report.png){width="800" align="left"}

1. Rapportsidan är uppdelad i två delar:

   - **Filter:**

     Du kan filtrera rapportdata baserat på filtyp och konverteringsstatus. I filtypen kan du välja att visa rapportdata för Word-dokument, dokument av typen strukturerad HTML, XML och DocBook. I Status kan du välja att visa rapportdata för aktiviteter som har körts utan fel, misslyckats, aktiverats eller placerats i kö.

     På följande skärmbild visas rapportdata för konverteringsåtgärder som har statusen Misslyckad, Aktiv och Köad.

     ![](images/conversion-report-failed-active-queued.png){width="800" align="left"}

   - **Rapportdata:**

     Rapportdata innehåller följande kolumner:

      - **Filnamn**: Namnet på källfilen som konverteringen kördes på. När du klickar på länken Filnamn kommer du till källdokumentets plats.

      - **Filtyp**: Typ av källdokument, som kan vara Word, strukturerad HTML, XML och DocBook.

      - **Tillagd av**: Namnet på den användare som utförde konverteringsåtgärden.

      - **Tillagt den**: Det datum då uppgiften kördes. Loggfilen hämtas när du klickar på länken Tillagt den.

      - **Bana**: Källdokumentets fullständiga sökväg.

      - **Status**: Status för konverteringsaktiviteterna - Slutfört, Misslyckat, Aktivt eller Köat.

      - **Utdata**: Sökväg till det konverterade dokumentet. Om du klickar på länken Utdata kommer du till den plats där utdata sparas.


**Överordnat ämne:**[ Rapporter](reports-intro.md)
