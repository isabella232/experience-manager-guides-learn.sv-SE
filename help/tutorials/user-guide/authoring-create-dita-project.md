---
title: Skapa ett DITA-projekt
description: Lär dig hur du skapar ett DITA-projekt
exl-id: 6dc88ac4-249a-4da2-9787-a58370e281ca
source-git-commit: 8823669fd29e8a40a41f9ca5d654b38fbea8e2fa
workflow-type: tm+mt
source-wordcount: '452'
ht-degree: 0%

---

# Skapa ett DITA-projekt {#id1645HA00NM6}

AEM Guides innehåller en DITA-projektmall som du kan använda för att skapa och hantera granskningsåtgärder.

Du kan skapa ett DITA-projekt och sedan använda det för att starta granskningarna. Med ett projekt kan du definiera en deadline och styra de uppgifter och den tid som krävs för att slutföra den granskningsuppgift som du har skapat projektet för.

Du kan lägga till teammedlemmar i ett projekt som sedan kan tilldelas olika roller - Författare, Granskare och Utgivare.

När du har skapat ditt DITA-projekt kan du starta en granskning från webbredigeraren eller resursgränssnittet. Mer information finns i [Skicka ämnen för granskning](review-send-topics-for-review.md#).

När en författare initierar ett granskningsarbetsflöde får de markerade medlemmarna i projektet ett e-postmeddelande. Information om hur du konfigurerar e-postmeddelanden finns i *Anpassa e-postmallar* i Installera och konfigurera Adobe Experience Manager Guides as a Cloud Service.

Så här skapar du ett DITA-projekt:

1. Öppna projektkonsolen.

   Du kan även komma åt projektkonsolen via följande URL:

   ```http
   http://<server name>:<port>/projects.html
   ```

1. Klicka **Skapa** \> **Projekt** för att starta guiden Skapa projekt.

   ![](images/project-console-63.png){width="650" align="left"}

1. På sidan Skapa projekt väljer du **DITA-projekt** mall och klicka på **Nästa**.

1. Ange följande information på sidan Projektegenskaper:

   Information i **Grundläggande** tab:

   ![](images/create-project.png){width="650" align="left"}

   - Ange projektets **Titel**, **Beskrivning** och **Förfallodatum**.

   - Du kan också välja en miniatyrbild för projektet.

   - Som standard blir du projektägare. Så här lägger du till fler användare i det här projektet:
   1. Ange eller välj en användare på **Användare** nedrullningsbar lista.

   1. Välj en användartyp - Författare, Granskare eller Utgivare.

      >[!NOTE]
      >
      >Du kommer att se andra användartyper i den här listrutan, men för ett DITA-projekt bör du bara välja mellan användartypen Författare, Granskare eller Utgivare. Även om du lägger till en användare av en annan typ kommer användaren inte att kunna komma åt några DITA-specifika funktioner som finns i AEM.

   1. Klicka **Lägg till**.

      >[!NOTE]
      >
      >Om du använder AEM Guides version 3.5 eller tidigare visas ett alternativ för att välja en DITA-kartfil för att lösa nyckelreferenser för ämnesredigering, förhandsgranskning och granskningsarbetsflöden. I 3.6 och senare versioner kan du ange rotkartan via webbredigeraren. Mer information finns i [Användarinställningar](web-editor-features.md#id2087G0P40SB) i webbredigeraren. Ett annat sätt att ställa in rotkartan är att konfigurera den på global nivå eller på mappnivå. Mer information finns i *Konfigurera globala profiler eller profiler på mappnivå* i installations- och konfigureringshandboken.
   Information i **Avancerat** tab:

   - Ange ett namn för projektet. Det här namnet används för att skapa URL:en för det här projektet.



1. Klicka **Skapa**.

   Dialogrutan Projekt skapat visas.

1. Klicka **Öppna** för att öppna din projektsida.


**Överordnat ämne:**[ Granska ämnen och kartor](review.md)
