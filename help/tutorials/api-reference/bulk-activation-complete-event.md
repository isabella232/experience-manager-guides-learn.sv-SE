---
title: Händelsehanterare för slutförd gruppaktivering
description: Läs om händelsehanterare för massaktivering
source-git-commit: 4b0e3f7cf777d2b98eb394fd89235acddef4769a
workflow-type: tm+mt
source-wordcount: '185'
ht-degree: 2%

---

# Händelsehanterare för slutförd gruppaktivering

Stödlinjer i Experience Manager visar `com/adobe/fmdita/replication/complete` händelse som används för att utföra åtgärder efter att en gruppaktiveringsprocess har slutförts. Den här händelsen utlöses när en gruppaktiveringsprocess slutförs. Om du t.ex. kör gruppaktiveringen av en förinställning för AEM plats för en karta anropas den här händelsen när aktiveringsprocessen har avslutats.


Du måste skapa en AEM händelsehanterare för att kunna läsa de egenskaper som är tillgängliga i den här händelsen och utföra ytterligare bearbetning.

Händelseinformation förklaras nedan:

**Händelsenamn**:

```
com/adobe/fmdita/replication/complete 
```

**Parametrar**: |Namn|Typ|Beskrivning| |—|—|—| |`path`|String|Sökvägen till filen som utlöste den här händelsen. <br> Till exempel, `/content/output/sites/ditamap1-ditamap`. <br> Det är en lista med sökvägar som är serialiserade som en JSON-array.| |`messageType`|String|Meddelandets typ. <br>Möjligt alternativ: `REPLICATION`| |`action`|String|Detta är den åtgärd som utfördes. <br>Möjligt alternativ: `BulkReplicate`| |`user`|String|Användaren som startade åtgärden.| |`result`|String|Resultatet av gruppaktiveringen. Det är ett serialiserat JSON-objekt: <br>`{"success":boolean,"code":integer,"message":"" }`| |`agentId`|String|Det agent-ID som används i replikeringen. Till exempel, `"publish"`.| |`importMode`|String|Importläge används i aktivering. Möjliga alternativ är: <br>`REPLACE, MERGE, UPDATE`.|


**Exempel på händelseavlyssnare**:

```XML
@Component(service = EventHandler.class,
        immediate = true,
        property = {
                EventConstants.EVENT_TOPIC + "=" + "com/adobe/fmdita/replication/complete",
        })
 
public class SampleEventHandler implements EventHandler {
 
    protected final Logger log = LoggerFactory.getLogger(this.getClass());
 
    @Override
    public void handleEvent(final Event event) {
        Map<String, String> properties = new HashMap<>();
        properties.put("paths", (String) event.getProperty("paths"));
        properties.put("messageType", (String) event.getProperty("messageType"));
        properties.put("action", (String) event.getProperty("action"));
        properties.put("result", (String) event.getProperty("result"));
        properties.put("user", (String) event.getProperty("user"));
        properties.put("agentId", (String) event.getProperty("agentId"));
        properties.put("importMode", (String) event.getProperty("importMode"));
 
        String eventTopic = event.getTopic();
        log.debug("eventTopic {}", eventTopic);
        for(Map.Entry entry:properties.entrySet()) {
            log.debug(entry.getKey() + " : " + entry.getValue());
        }
 
    }
}
```
