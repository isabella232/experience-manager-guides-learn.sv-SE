---
title: Konfigurera och anpassa arbetsflöden
description: Lär dig hur du konfigurerar och anpassar arbetsflöden
source-git-commit: 4f15166b1b250578f07e223b0260aacf402224be
workflow-type: tm+mt
source-wordcount: '1387'
ht-degree: 0%

---


# Konfigurera och anpassa arbetsflöden {#id181AI0OJ0RO}

Med arbetsflöden kan du automatisera Adobe Experience Manager \(AEM\)-aktiviteter. Ett arbetsflöde består av en serie steg som körs i en viss ordning. Du kan definiera en distinkt aktivitet som ska köras i varje steg. Du kan till exempel skicka ett e-postmeddelande till alla granskare i en grupp när en ämnesgranskning skapas. Eller skicka ett meddelande till utgivaren när en utdatagenereringsåtgärd har slutförts.

Mer information om arbetsflöden i AEM finns i:

- [Administrera arbetsflödesinstanser](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/sites/administering/workflows-administering.html)

- Använda och delta i arbetsflöden: [Arbeta med projektarbetsflöden](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/sites/authoring/projects/workflows.html).


Avsnitten i det här avsnittet visar olika anpassningar som du kan göra i de standardarbetsflöden som finns i AEM.

## Anpassa granskningsarbetsflödet {#id176NE0C00HS}

Alla organisationers skribenter arbetar på ett specifikt sätt för att uppfylla sina verksamhetskrav. I vissa organisationer finns det en dedikerad redigerare, medan andra organisationer kan ha ett automatiserat system för redaktionell granskning. I en organisation kan t.ex. ett vanligt arbetsflöde för redigering och publicering omfatta uppgifter som - när en författare har redigerat innehållet går det automatiskt till granskarna och när granskningen är klar går det till utgivaren för att generera det slutliga resultatet. I AEM kan aktiviteter som du gör med ditt innehåll och dina resurser kombineras i form av en process och mappas till ett AEM arbetsflöde. Mer information om arbetsflöden i AEM finns i [Administrera arbetsflöden](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/sites/administering/workflows-administering.html) i AEM.

Med AEM kan du anpassa standardarbetsflödet för granskning. Du kan använda följande fyra anpassade granskningsrelaterade processer tillsammans med dina andra arbetsflöden för redigering och publicering.

- **Skapa granskning**: I den här processen förbereds de metadata som krävs för att skapa en granskningsåtgärd. Den tilldelar till exempel granskarna granskningsbehörighet, ställer in status för de ämnen som ska granskas, ställer in tidslinjer för granskningen med mera. Av de fyra processerna är detta den enda obligatoriska processen som måste ingå i ditt anpassade arbetsflöde. I ditt arbetsflöde kan du välja att inkludera eller exkludera de andra tre processerna.

- **Tilldela granskningsuppgift**: Den här processen skapar granskningsaktiviteten och skickar uppgiftsmeddelandet till initieraren och granskarna.

- **Skicka e-post för granskning**: Den här processen skickar e-postmeddelandet till initieraren och granskarna.

- **Schemalägg jobb för att stänga granskning**: Denna process ser till att granskningsprocessen slutförs när tidsgränsen nås.


När du skapar ett anpassat granskningsarbetsflöde är den första uppgiften att ange de metadata som behövs för att skapa granskningsprocessen. Om du vill göra det kan du skapa ett ECMA-skript. Ett exempel på ECMA-skript som tilldelar metadata ges nedan:

```javascript
var workflowdata=workItem.getWorkflowData();
workflowdata.getMetaDataMap().put("initiator","admin");
workflowdata.getMetaDataMap().put("operation","AEM_REVIEW");
workflowdata.getMetaDataMap().put("orgTopics","/content/dam/xml-solution/review.xml");
workflowdata.getMetaDataMap().put("payloadJson","{\"base\":\"/content/dam/xml-solution\",\"asset\":[\"/content/dam/xml-solution/review.xml\"],\"referrer\":\""}");
workflowdata.getMetaDataMap().put("deadline","2017-06-27T13:19:00.000+05:30");
workflowdata.getMetaDataMap().put("title","Review through custom workflow");
workflowdata.getMetaDataMap().put("description","Initiate this review process using the AEM workflow");
workflowdata.getMetaDataMap().put("assignee","user-one", "user-two");
workflowdata.getMetaDataMap().put("status","1");
workflowdata.getMetaDataMap().put("projectPath","/content/projects/review");
workflowdata.getMetaDataMap().put("startTime", System.currentTimeMillis());
```

Du kan skapa det här skriptet i `/etc/workflows/scripts` nod. I följande tabell beskrivs de egenskaper som tilldelas av detta ECMA-skript:

| Egenskap | Typ | Beskrivning |
|--------|----|-----------|
| `initiator` | Sträng | Användar-ID för den användare som initierar granskningsaktiviteten. |
| `operation` | Sträng | Ett statiskt värde anges som `AEM_REVIEW`. |
| `orgTopics` | Sträng | Sökväg till de ämnen som delas för granskning. Ange flera ämnen avgränsade med kommatecken. |
| `payloadJson` | JSON-objekt | Ange följande värden: -   `base`: sökvägen till den överordnade mappen som innehåller ämnet som skickats för granskning. <br> -   `asset`: sökvägen till det ämne som skickats för granskning. <br> -   `referrer`: lämna det tomt. |
| `deadline` | Sträng | Ange tiden i `yyyy-MM-dd'T'HH:mm:ss.SSSXXX` format. |
| `title` | Sträng | Ange en rubrik för granskningsaktiviteten. |
| `description` | Sträng | Ange en beskrivning för granskningsaktiviteten. |
| `assignee` | Sträng | Användar-ID för de användare till vilka du vill skicka ämnet för granskning. |
| `status` | Heltal | Ett statiskt värde angett som 1. |
| `startTime` | Lång | Använd `System.currentTimeMillis()` för att hämta aktuell systemtid. |

När du har skapat skriptet anropar du det innan du anropar processen Skapa granskning i arbetsflödet. Beroende på dina behov kan du sedan anropa de andra granskningsarbetsflödena.

### Ta bort granskningsarbetsflöde från rensningskonfigurationen

Om du vill förbättra arbetsflödesmotorns prestanda kan du regelbundet rensa slutförda arbetsflödesinstanser från AEM. Om du använder AEM standardkonfigurationer rensas alla färdiga arbetsflödesinstanser efter en viss tidsperiod. Detta resulterar också i att alla granskningsarbetsflöden rensas från AEM.

Du kan förhindra att granskningsarbetsflöden rensas automatiskt genom att ta bort granskningsarbetsflödesmodellen \(information\) från den automatiska rensningskonfigurationen. Du måste använda **Rensa arbetsflöde för Adobe Granite** om du vill ta bort arbetsflödesmodellerna för granskning från listan för automatisk rensning.

I **Rensa arbetsflöde för Adobe Granite** ska du se till att du anger minst ett arbetsflöde som du kan rensa utan problem. Du kan t.ex. använda något av följande arbetsflöden som skapas AEM stödlinjer:

- /etc/workflow/models/publishditamap/jcr:content/model
- /etc/workflow/models/post-dita-project-creation-tasks/ jcr:content/model

Lägga till ett arbetsflöde i **Rensa arbetsflöde för Adobe Granite** säkerställer att AEM bara tar bort de arbetsflöden som finns i listan i konfigurationen. Detta förhindrar AEM från att rensa granskningsarbetsflödesinformationen.

Mer information om hur du konfigurerar **Rensa arbetsflöde för Adobe Granite**, se *Administrera arbetsflödesinstanser* i AEM.

### Anpassa e-postmallar

I ett antal arbetsflöden för AEM stödlinjer används e-postmeddelanden. Om du till exempel initierar en granskningsåtgärd skickas ett e-postmeddelande till granskarna. Om du vill vara säker på att e-postmeddelandet skickas måste du aktivera den här funktionen i AEM. Om du vill aktivera e-postmeddelanden i AEM läser du artikeln [Skickar e-post](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/implementing/developing/development-guidelines.html#sending-email) i AEM.

AEM innehåller en uppsättning e-postmallar som du kan anpassa. Följ de här stegen för att anpassa de här mallarna:

1. Hämta paketet med hjälp av Pakethanteraren `/libs/fmdita/mail` -fil.

   >[!NOTE]
   >
   > Gör inga anpassningar i standardkonfigurationsfilerna tillgängliga i ``libs`` nod. Du måste skapa en övertäckning av ``libs`` noden i ``apps`` noda och uppdatera de nödvändiga filerna i ``apps`` endast nod.

1. E-postmappen innehåller följande anpassningsbara mallar:

   | Mallfilnamn | Beskrivning |
   |-----------------|-----------|
   | closereview.html | Den här e-postmallen används när en granskningsuppgift stängs. |
   | createreview.html | Den här e-postmallen används när en ny granskningsuppgift skapas. |
   | reviewapproval.css | Den här CSS-filen innehåller formateringen för e-postmallar. |


## Anpassa arbetsflödet för efterhandsproduktion {#id17A6GI004Y4}

AEM Guides ger dig flexibilitet att ange ett arbetsflöde för postutdata. Du kan utföra vissa efterbehandlingsåtgärder på utdata som genereras med hjälp av AEM stödlinjer. Du kan till exempel använda vissa CQ-taggar på den genererade AEM för webbplatsutdata, ange vissa egenskaper för utdata från PDF eller skicka ett e-postmeddelande till en uppsättning användare när utdata har genererats.

Du kan skapa en ny arbetsflödesmodell som du kan använda som arbetsflöde för att skapa utdata. När ett arbetsflöde för generering efter utdata aktiveras, delar arbetsflödet kontextuell information via arbetsflödets metadatamappning, som du kan använda för att utföra bearbetning av genererade utdata. I följande tabell beskrivs den sammanhangsberoende information som delas som metadata:

| Egenskap | Typ | Beskrivning |
|--------|----|-----------|
| ``outputName`` | Sträng | Namnet på den förinställning som används för att generera utdata. |
| `generatedPath` | Sträng | Sökväg i DAM där genererade utdata lagras. |
| `outputType` | com.adobe.fmdita.output.OutputType | Typ av förinställning för utdata. |
| `outputTitle` | Sträng | Namnet på förinställningen för utdata. |
| `outputHistoryPath` | Sträng | Databassökväg för noden history. |
| `isSuccess` | Boolean | En flagga som visar slutstatusen för utdatagenereringsprocessen - om den lyckades eller inte. |
| `logPath` | Sträng | Sökväg i DAM där loggarna för utdatagenerering sparas. |
| `generatedTime` | Lång | Tid då utdatagenereringsprocessen utlöstes. |
| `initiator` | Sträng | Användar-ID för användaren som utlöste arbetsflödet för generering av utdata. |

Om du vill använda metadata för generering av utdata kan du skapa ett ECMA-skript eller ett OSGi-paket. Ett exempel på ECMA-skript som använder metadata ges nedan:

>[!NOTE]
>
> Du kan skapa det här skriptet i ``/etc/workflows/scripts`` nod.

```javascript
var session = workflowSession.getSession(); // Obtain session object to read/write the repository.
var payload = workItem.getWorkflowData().getPayload().toString(); // Get the workflow payload (the ditamap file on which the generation was triggered)
var metadata = workItem.getWorkflowData().getMetaDataMap(); // Get the workflow metadata object
var generatedPath = metadata.get("generatedPath"); // supplied by AEM Guides
var username = metadata.get("initiator"); // supplied by AEM Guides
var successful = metadata.get("isSuccess"); // supplied by AEM Guides
var title = metadata.get("outputTitle"); // supplied by AEM Guides
var subject = "Output Generation Finished";
var message = "Generation of output " + title + " just finished " + 
(successful ? "successfully. " : "unsuccessfully. ");
    message += "It was triggered by " + username;    
if (successful) {
    message += "<br/><br/>The path to the generated output is " + 
generatedPath;
}
/*
    MailerAPI.sendMail("dl-docs-authors", subject, message);
*/
```

När du har skapat skriptet anropar du det anpassade skriptet i arbetsflödet. Beroende på dina behov kan du sedan anropa de andra arbetsflödesprocesserna. När du har utformat ditt arbetsflöde kan du ringa *Slutför postgenerering* som det sista steget i arbetsflödet. The *Slutför postgenerering* steg säkerställer att status för utdatagenereringsaktiviteten uppdateras till *Slutförd* när processen för generering av utdata har slutförts. När du har skapat ett anpassat arbetsflöde för postutdata kan du konfigurera det med alla förinställningar för utdatagenerering. Välj önskat arbetsflöde i *Kör arbetsflöde efter generering* egenskapen för den förinställning som krävs. När du kör en utdatagenereringsuppgift med den konfigurerade förinställningen ändras aktivitetsstatusen \(på fliken Utdata\) till *Efterbearbetning*.

