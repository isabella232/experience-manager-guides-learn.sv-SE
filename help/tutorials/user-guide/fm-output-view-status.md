---
title: Visa status för utdatagenereringsaktiviteten
description: Lär dig hur du visar status för aktiviteten för utdatagenerering
exl-id: 6fdaa547-8446-4ce5-95c3-a63d9c1f27d2
source-git-commit: c74badebbcb4733fb9caa79c646b1d1e5c8bfe8e
workflow-type: tm+mt
source-wordcount: '238'
ht-degree: 0%

---

# Visa status för utdatagenereringsaktiviteten {#viewing_output_history}

När du initierar genereringsuppgiften för ett FrameMaker-dokument skickar AEM stödlinjer den här uppgiften till kön för utdatagenerering. Den här kön uppdateras i realtid och visar statusen för varje utdatagenereringsuppgift i kön.

Utför följande steg för att visa kön för generering av utdata:

1. Navigera till och klicka på det FrameMaker-dokument som du vill kontrollera status för utdatagenereringen i resursgränssnittet.

1. Klicka på Utdata.

   ![](images/output-queued-fm.png){width="800" align="left"}

1. Sidan Utdata är uppdelad i två delar:

   - **Utdata i kö:**

      Visar utdata som väntar på att skapas eller som håller på att genereras. Du kan också hitta den inställning eller förinställning för generering av utdata som används för uppgiften som står i kö, typ, användare som initierade uppgiften, tid sedan uppgiften placerades i kö samt aktuell status.

   - **Genererade utdata**

      Visar en lista över utdataaktiviteter som har slutförts. Informationen som visas här liknar den som visas i avsnittet Utdata i kö, med den enda skillnaden mellan genereringstiden för utdata.

      I den här listan kan du ha uppgifter som har utförts eller uppgifter som misslyckats. För de uppgifter som har slutförts skapas en loggfil, \(logs.txt\), som du kommer åt genom att klicka på länken i kolumnen Genererad den.


**Överordnat ämne:**[ Generera utdata från FrameMaker-dokument](fm-output-generatation.md)
