---
sidebar_position: 3
source-git-commit: 42052b37724f97e34ab007db4cc3d9f9524ad3a2
workflow-type: tm+mt
source-wordcount: '330'
ht-degree: 0%

---

# Anpassa appen

Vår app följer en MVC-struktur (modell, vy, styrenhet)

## Modell

Modellen definierar de olika attributen och lagrar deras värden. Värdena för de olika attribut som lagras i modellen kan nås från kontrollenheten med hjälp av syntaxen

```typescript
this.model.attributeName
```

För anpassning i programmet läggs alla nya attribut till under en karta i modellen.
Om du vill ange ett nytt attribut i modellen använder vi följande syntax i kontrollenheten:

```typescript
this.model.extraProps.set("key", value)
```

För att komma åt ett attribut som lagts till i modellen använder vi följande syntax:

```typescript
const value = this.model.extraProps.get("key")
```

## Visa

Vyn definierar appens användargränssnitt. Vi använder JSON-filer för att definiera visningen av våra filer. Här definierar vi komponenterna, css (som anges i komponenternas extraklass) och återger de värden som lagras i modellen.
I vår app definieras varje vy med en JSON. JSON refereras till med sina unika ID:n som kallas `id`.

## Styrenhet

Kontrollenheten används för att hantera händelser och bearbeta data. Kontrollenheten används för att hämta och skicka data från servern, det är gränssnittet mellan det som visas i användargränssnittet och lagras på serverdelen.

- För att ange värden vid initieringen använder vi `init` funktion.
- Om du vill lägga till en metod i kontrollenheten använder vi följande syntax:

```typescript
methodName: function(args){
    // functionality
}
```

The `methodName` här fungerar som `key` referera till metoden i JSON (vyn) eller i andra funktioner

- För att anropa en metod i kontrollenheten använder vi syntaxen

```typescript
this.next('methodName', args)
```

## Exempel

Låt oss nu använda ett enkelt exempel för att visa hur dessa tre komponenter interagerar med varandra.
Vi ska lägga till en knapp som byter etikettvärde med ett klick

### Visa exempel

Här nedan definierar vi JSON för en knapp som visar en dynamisk text som lagras i modellen under variabelnamnet `buttonLabel`.
I det här exemplet ändras etiketten när du klickar på knappen.

```JSON
{
    "component": "button",
    "label": "@extraProps.buttonLabel",
    "variant": "cta",
    "on-click": "switchButtonLabel",
}
```

### Exempel på modell

i detta fall `extraProps.buttonLabel` innehåller knappens etikett

### Exempel på styrenhet

```typescript
  controller: {
    init: function () {
      this.model.extraProps.set("buttonLabel", "Submit")
    },

    switchButtonLabel(){
        const buttonLabel = this.model.extraProps.get("buttonLabel") === "Submit"? "Cancel" : "Submit"
        this.model.extraProps.set("buttonLabel", buttonLabel)
    }
  }
```

Nedanför GIF visas koden ovan i aktion
![basic_customization](imgs/basic_customisation.gif "Knappen Grundläggande anpassning")
