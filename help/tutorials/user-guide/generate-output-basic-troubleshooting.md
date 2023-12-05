---
title: Grundläggande felsökning
description: Lös problem med grundläggande felsökning i AEM. Lär dig att visa, kopiera och kontrollera loggfilen i en textredigerare och åtgärda JSP-kompileringsfel.
source-git-commit: 880cd344ceb65ea339be699ebcad41c0d62e168a
workflow-type: tm+mt
source-wordcount: '690'
ht-degree: 0%

---

# Grundläggande felsökning {#id1821I0Y0G0A}

När du arbetar med AEM stödlinjer kan det uppstå fel när du publicerar eller öppnar dokumentet. Sådana fel kan finnas på DITA-kartan, i ämnet eller i AEM. I det här avsnittet finns information om hur du får åtkomst till och tolkar information i loggfilen för utdatagenerering. Om ditt DITA-avsnitt är för stort kan du se JSP-kompileringsfelet. I det här avsnittet finns även information om hur du löser JSP-kompileringsfelet.

## Visa och kontrollera loggfilen {#id1822G0P0CHS}

Utför följande steg för att visa och kontrollera loggfilen för generering av utdata:

1. När du har startat processen för generering av utdata klickar du på **Utdata** i DITA-kartkonsolen.

   The **Allmänt** kolumn i **Genererade utdata** visar ikonerna för att ge en visuell indikation på om utdatagenereringen lyckades eller inte.

   ![](images/output-general-settings.png){width="300" align="left"}

   På skärmbilden ovan visar den första och tredje ikonen misslyckad generering av utdata. Den andra ikonen visar att det gick att generera utdata, men med meddelanden. Den sista genereringen är en lyckad utdatagenerering utan något meddelande.

1. Klicka på länken i **Genererad den** kolumn när jobbet är klart.

   Loggfilen öppnas på en ny flik.

   ![](images/log-file.png){width="800" align="left"}

1. Använd följande filter för att markera texten i loggfilen:
   - Allvarligt: markerar de allvarliga felen i loggfilen med rosa färg.
   - Fel: Markerar felen i loggfilen med orange färg.
   - Varning: Markerar varningarna i loggfilen med lila färg.
   - Info: Markerar informationsmeddelanden i loggfilen med blå färg.
   - Undantag: Markerar undantagen i loggfilen med gul färg.
1. Använd navigeringsknapparna uppåt och nedåt för att hoppa till den markerade texten i loggfilen.

   Du kan även bläddra igenom loggfilen och kontrollera meddelandena.


## Kopiera och kontrollera loggfilen i en textredigerare

Så här kopierar och kontrollerar du loggfilen för generering av utdata i en textredigerare:

1. När du har startat processen för generering av utdata klickar du på **Utdata** i DITA-kartkonsolen.

1. Klicka på länken i **Genererad den** kolumn när jobbet är klart.

   Loggfilen öppnas på en ny flik.

1. Klicka **Kopiera logg** -knappen. Loggfilen kopieras till Urklipp.
1. Öppna en textredigerare och klistra in loggfilen i redigeraren.

1. Bläddra igenom loggfilen och sök efter meddelanden.

   Följande information hjälper dig att avgöra om det finns något fel i DITA-filen eller AEM Guides-processen:

   - *DITA-mappningsfilrelaterat fel*: Om ett fel påträffas i DITA-kartfilen eller i någon annan fil som finns i DITA-kartan innehåller loggfilen strängen &quot;BUILD FAILED&quot;. Du kan kontrollera informationen i loggfilen för att hitta den felaktiga filen och åtgärda problemet.

   I följande exempelavsnitt av loggfilen visas `BUILD FAILED` meddelandet tillsammans med orsaken till felet.

   ![](images/dita-error-in-log-file.png){width="650" align="left"}

   - *AEM Guides-relaterat fel*: Den andra typen av fel som du kan identifiera i loggfilen är relaterat till själva AEM. I det här fallet tolkas DITA-mappningsfilen, men utdatagenereringsprocessen misslyckas på grund av ett internt fel i AEM. För sådana fel måste du be om hjälp från det tekniska supportteamet.

   I följande exempelavsnitt av loggfilen visas `BUILD SUCCESSFUL` meddelande, följt av ett annat tekniskt fel.

   ![](images/process-error-in-log-file.png){width="650" align="left"}


## Åtgärda JSP-kompileringsfel

Om DITA-avsnittet är för stort kan du se JSP-kompileringsfelet \(`org.apache.sling.api.request.TooManyCallsException`\) i webbläsaren. Det här felet kan uppstå när du öppnar ett ämne för redigering, granskning eller publicering.

Utför följande steg för att lösa problemet:

1. I Global Navigation väljer du Tools och väljer Operations \> Web Console.

   Sidan Konfigurera Adobe Experience Manager Web Console visas.

1. Sök efter och klicka på *Apache Sling Main Servlet* -komponenten.

   De konfigurerbara alternativen för huvudservern för Apache Sling visas.

1. Öka värdet för *Antal samtal per begäran* -parametern enligt dina krav.


**Överordnat ämne:**[ Generering av utdata](generate-output.md)
