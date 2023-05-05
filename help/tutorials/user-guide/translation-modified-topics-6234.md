---
title: Översätt ändrade ämnen
description: Lär dig hur du översätter ändrade ämnen
exl-id: 48b868c3-27ec-4641-b40d-17a641be7497
source-git-commit: c74badebbcb4733fb9caa79c646b1d1e5c8bfe8e
workflow-type: tm+mt
source-wordcount: '603'
ht-degree: 0%

---

# Översätt ändrade ämnen {#id16A5A0B6072}

Om du ändrar något i vissa ämnen måste dessa ämnen översättas på nytt. Du kan hålla reda på ändrade ämnen från DITA-kartan. Klicka på DITA-mappningsfilen i källmappen för språkkopiering och klicka på fliken Översättning. Du kan se statusen för varje ämne oavsett om det kräver omöversättning eller inte.

Utför följande steg för att skicka ett ändrat ämne för omöversättning:

1. Klicka på DITA-mappningsfilen i källspråkets kopieringsmapp.

1. Klicka på **Översättning** -fliken.

1. I **Filter** till vänster väljer du **Översätta språk** som du vill kontrollera statusen för och klicka på **Klar**.

   Du kan se översättningsstatusen för varje avsnitt. De ämnen som har en annan version av ämnet tillgänglig än vad som skickades för översättning, visar en **Inaktuell** status.

   >[!NOTE]
   >
   > Översättningsarbetsflödet jämför den senast sparade versionen av ämnesfilen i källspråksmappen med den översatta versionen.

   Om du klickar på pilen visas mer information. du kan se den aktuella språkkopian.

   ![](images/out-of-sync-uuid.png){width="800" align="left"}

1. Klicka i kryssrutan för att markera de ämnen som du vill skicka för omöversättning.

   När du väljer ett osynkroniserat datum visas **Skapa/uppdatera språkkopior** visas på referenspanelen och **Stäng status för ej synkroniserad** ovanför **Filter** ikon.

   Du kan använda **Stäng ur synkronisering** om du vill åsidosätta statusen Inaktuell för ämnena på DITA-kartan. Om du till exempel har gjort vissa ändringar i den engelska versionen av ämnet som inte behöver översättas kan du använda den här knappen och ändra statusen Inaktuell för det markerade ämnet.

   >[!NOTE]
   >
   > Om du klickar på **Stäng status för ej synkroniserad** anger det att ämnesstatusen är Uppdaterad för de valda inaktuella ämnena.

1. Klicka **Uppdatera språkkopior** och konfigurera översättningsjobbet.

1. Du kan välja att skapa ett nytt översättningsprojekt eller lägga till ämnen i ett befintligt översättningsprojekt. Ange nödvändig information för att konfigurera översättningsprojektet.

1. Klicka **Starta**.

   Ett bekräftelsemeddelande som visar att ämnet har skickats för översättning visas.

1. Navigera till översättningsprojektet i projektkonsolen. Ett nytt översättningsjobbkort skapas i mappen. Klicka på ellipsen för att visa resurserna i mappen.

   ![](images/incremental-job.PNG){width="300" align="left"}

1. Klicka på pilen på översättningsjobbkortet och välj **Starta** från listan. Ett meddelande meddelar att jobbet har startats.

   Du kan även visa statusen för det ämne som översätts när du klickar på ellipsen längst ned på översättningsjobbkortet.

   >[!NOTE]
   >
   > Om du använder översättningstjänsten för människor måste du exportera innehållet för översättning. När du har det översatta innehållet måste du importera det tillbaka till översättningsprojektet.

1. När översättningen är klar ändras statusen till **Klar att granska**. Klicka på ellipsen för att se ämnesinformation och gör något av följande i verktygsfältet:

   - Klicka **Visa i resurser** för att se och verifiera översättningen.

   - Klicka **Acceptera översättning** om du tror att ändringarna har översatts korrekt. Ett bekräftelsemeddelande visas.

   - Klicka **Avvisa översättning** om du tror att jobbet behöver göras om. Ett meddelande om avvisning visas.
   >[!NOTE]
   >
   > Det är viktigt att acceptera eller avvisa den översatta resursen, annars stannar filen kvar på den tillfälliga platsen och kopieras inte till DAM.

1. Gå tillbaka till DITA-mappningsfilen i källspråksmappen i Assets UI. De omöversatta ämnena är nu synkroniserade.


**Överordnat ämne:**[&#x200B;Översätta innehåll](translation.md)
