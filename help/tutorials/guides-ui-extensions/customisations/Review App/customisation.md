---
source-git-commit: 42052b37724f97e34ab007db4cc3d9f9524ad3a2
workflow-type: tm+mt
source-wordcount: '397'
ht-degree: 0%

---
# Anpassa granskningsappen

För att göra det enklare att anpassa granskningsappen har vi tagit fram några krokar som listas och förklaras nedan:

## Review-Comment

- id: `review_comment`
- krok: `this.updateExtraProps`:

Som diskuterades [här](../../aem_guides_framework/basic_customisation.md)och alla nya attribut som läggs till under anpassningen hamnar under `this.model.extraProps`. Metoden `updateExtraProps` I kan du lägga till attribut i en granskningskommentar och även hantera uppdatering och lagring av det tillagda attributet på servern.

### Exempel på användning

Exempel: du vill lägga till fält `commentRationale` och `severity` till dina kommentarer.
Låt oss uppdatera `commentRationale` till &quot;Detta är en viktig mening.&quot; och `severity` till&quot;CRITICAL&quot;.
Detta kan göras med syntaxen:

```typescript
 this.updateExtraProps(
        {'commentRationale': 'This is an important sentence.',
        'severity': 'CRITICAL'}
      )
```

Ovanstående kodfragment hanterar uppdatering och sparande av värdena. De sparade värdena kan återges i användargränssnittet genom att definiera vyn.

```JSON
{
    "component" : "label",
    "label": "@extraProps.commentRationale"
}
```

## Panelen Textbunden granskning

- id: `inline_review_panel`

1. krok: `onNewCommentEvent`
Kroken `onNewCommentEvent` gör att du kan utlösa en händelse eller anropa en metod för en ny kommentar eller svarshändelse.
De argument som tas emot i `onNewCommentEvent` inkludera:
   - händelser: den kommentar/svarshändelse som skickades.
   - newComment: boolesk Om den skickade händelsen var en ny kommentarhändelse, dvs. `highlight`, `insertion`, `deletion`, `sticky note comment`
   - newReply: booleskt Om händelsen som skickades var en ny svarshändelse.

2. krok: `sendExtraProps`

Den här kroken är bra om du vill utöka en `event` och skicka `extraProps` från den interna granskningspanelen. Vi kommer att förklara användningen av de här två krokarna nedan.

### Exempel på intern granskningspanel

Säg att vi vill skicka en extraProp, `userInfo`, varje gång en ny kommentar eller ett nytt svar skickas. Detta görs nu via den interna granskningspanelen, men vi har inte en referens till commentId för den nyligen genererade kommentaren, och därför kan vi skriva följande kod för att uppnå detta.

```typescript
    onNewCommentEvent(args){
      const events = _.get(args, "events")
      const currTopicIndex = tcx.model.getValue(tcx.model.KEYS.REVIEW_CURR_TOPIC) || this.model.currTopicIndex || "0"
      const event = _.get(_.get(events, currTopicIndex), '0')
      const newComment = _.get(args, 'newComment')
      const newReply = _.get(args, 'newReply')
      if ((newComment || newReply) && event) {
        this.next('setUserInfo', event)
      }
    },
```

I ovanstående kodfragment kontrollerar vi om den skickade händelsen var en ny kommentar eller ett nytt svar. Om det finns en ny kommentar eller ett nytt svar anropar vi metoden `setUserInfo`

```typescript
    setUserInfo(event) {
      this.loader?.getUserInfo(event.user).subscribe(userData => {
        const extraProps = {
          "userFirstName": userData?.givenName || '',
          "userLastName": userData?.familyName || '',
          "userTitle": userData?.title || '',
          "userJobTitle": userData?.jobTitle || '',
          'userEmail': userData?.email || '',
        }
        const data = {... event, extraProps}
        this.sendExtraProps(
          data
        )
      })
    },
```

I ovanstående metod utökar vi händelsen till att skicka extraProps som innehåller användarens förnamn, e-postadress, titel osv. Genom att utöka händelsen på det här sättet ser du till att extraProps skickas med rätt commentId och ser till att de bifogas till rätt kommentar.

Kroken `updateExtraProps` anropar automatiskt `sendExtraProps`, så när ska du använda vad?

Vi använder `updateExtraProps` i `review_comment` kontrollenhet, som redan har kommentarens `id` och därför behöver du bara nämna `extraProps.`

The `inline_review_panel` har dock inte åtkomst till kommentarens id, och därför behöver du inte skicka en händelse från den interna granskningspanelen för att `sendExtraProps` kommer att vara till nytta.
