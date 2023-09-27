---
title: Återanvänd innehåll - rapport
description: Lär dig hur du visar rapporten för återanvändning av innehåll i AEM. Generera rapporten för att hitta procentsatsen för återanvändning av innehåll.
exl-id: 658ae0fd-9032-4480-b9e4-fe4fec261e72
source-git-commit: 8504a0a52d381044bf1f0d6e7de3585ebecf3a7b
workflow-type: tm+mt
source-wordcount: '424'
ht-degree: 0%

---

# Återanvänd innehåll - rapport {#id205BB900OQD}

En annan användbar rapport som du kan generera är återanvändningsrapporten för innehåll. Den här rapporten beräknar den genomsnittliga användningen av innehåll, vilket är mycket användbart för projektledare och affärsägare för att se hur mycket innehåll som återanvänds.

>[!TIP]
>
> För att återanvändningsrapporten för innehåll ska fungera på rätt sätt måste du aktivera efterbearbetningsarbetsflödet. Kontakta systemadministratören för att aktivera efterbearbetningsarbetsflöden.

Utför följande steg för att visa rapporten för återanvändning av innehåll:

1. Klicka på länken Adobe Experience Manager överst och välj **verktyg**.

1. Välj **Stödlinjer** i listan över verktyg.

1. Klicka på **Återanvänd innehåll - rapport** platta.

1. Klicka **Bläddra** om du vill välja en sökväg där ämnen finns eller ange sökvägen manuellt.

   Rapporten skapas genom att innehållet i den överordnade och alla underordnade mappar genomsöks.

1. Klicka **Generera rapport** för att få rapporten om återanvändning av innehåll.

   ![](images/content-reuse-uuid.png){width="800" align="left"}

   Rapportsidan är uppdelad i två delar:

   - **Rapportsammanfattning:**

     Visar en lista över genomsnittlig återanvändning av innehåll, som beräknas som Instansen för återanvändning av innehåll/totalt ämnesantal. Den här rapporten tar hänsyn till alla direkta innehållsreferenser på första nivån och ämnesreferenser för beräkning. Instanserna för återanvändning av innehåll beräknas som summan av värdena i fältet Antal gånger som återanvänds. Det ämne som återanvänds mest finns också med i rapportsammanfattningen. Om du klickar på ämneslänken i det mest återanvända ämnet öppnas ämnesens förhandsgranskning.

   - **Information:**

     Avsnittet Detaljer innehåller följande kolumner:

      - **Titel**: Ämnets namn. Om du klickar på ämneslänken öppnas ämnesförhandsgranskningen.

      - **UUID**: Filens universellt unika identifierare \(UUID\).

      - **Storlek**: Filstorlek i byte.

      - **Status**: Dokumentets aktuella status - Utkast, Under granskning eller Granskad.

      - **Antal gånger som återanvänts**: Antal gånger motsvarande ämne har återanvänts. Detta beräknas som summan av posterna i Refererad av kolumner minus 1.

      - **Refererad av**: De ämnen i vilka motsvarande ämne har refererats. Här beaktas endast de direkta \(första nivån\) referenserna. Flera ämnen avgränsas med kommatecken. UUID för den refererade filen anges också i parenteser. Om du klickar på avsnittets titellänk öppnas ämnesförhandsvisningen.


>[!NOTE]
>
> Du kan också exportera återanvändningsrapporten för innehåll i CSV-format. Klicka på länken Exportera till CSV längst upp till vänster på skärmen och välj en plats där du vill spara CSV-filen. Du kan sedan öppna den här CSV-filen i valfri CSV-redigerare.

**Överordnat ämne:**[ Rapporter](reports-intro.md)
