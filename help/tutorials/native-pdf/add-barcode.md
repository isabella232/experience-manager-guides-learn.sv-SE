---
title: Publiceringsfunktion för PDF | Lägg till streckkod
description: Lär dig hur du lägger till streckkoder.
source-git-commit: 6cea7a92eed8f7b1d4a0763baae65ccccd71790e
workflow-type: tm+mt
source-wordcount: '294'
ht-degree: 1%

---

# Lägga till en streckkod i PDF-utdata

Streckkoder är användbara när du vill inkludera information som enkelt kan bearbetas av maskiner. På samma sätt används QR-koder för länkar som läsarna kan öppna med sina mobila enheter.

Den här självstudiekursen hjälper dig att lägga till streckkoder ovanpå varje sida i utdata från PDF.

## Steg för att generera en streckkod

Så här genererar du en streckkod:

### Lägg till ett resurs-ID till DITA-kartan

Lägg till ett resurs-ID-element på DITA-kartan. Resurs-ID fungerar som huvudindata för att generera streckkoden.

```xml
<?xml version="1.0" encoding="UTF-8"?>
<!DOCTYPE map PUBLIC "-//OASIS//DTD DITA Map//EN" "technicalContent/dtd/map.dtd">
<map id="GUID-3c330691-4dac-4020-904a-d2d6246aeeb1-en">
  <title>Barcode Sample</title>
  <topicmeta>
    <resourceid id="7a5bda1c-b1db-4fd8-8763-a731e2e8abba">
    </resourceid>
  </topicmeta>
  <topicref href="GUID-139f6c64-bea3-4f17-8b22-ee131557e249-en.dita" type="topic">
  </topicref>
</map>  
```

Du kan också redigera resurs-ID:t i redigeringsläget.

<img src="./assets/barcode-map.png" alt="Exempelutdata med streckkod" width="700">


### Lägga till en streckkodsplatshållare i mallhuvudet

Ändra `Common.plt` i **Grundläggande** mall för att lägga till en streckkod efter projekttiteln.

```html
...
  <div data-region="header">
    <p class="chapter-header"><span data-field="project-title" data-format="default">Project Title</span> </p>
    <p><span class="barcode" data-field="metadata" data-format="default" data-subtype="//resourceid/@id">Resource ID (barcode)</span></p>
  </div>
} 
...
```


### Uppdatera mallens CSS för att återge ett streckkodsvärde

Ändra `content.css` för att återge en streckkod under genereringen av PDF. Olika streckkodstyper som qrcode och pdf417 stöds.  Mer information finns i [Streckkodstyper](#barcode-types).



```css
...
.barcode {
  -ro-replacedelement: barcode;
  -ro-barcode-type: code128;
}
...
```

När du har utfört de föregående stegen kan du generera PDF-utdata med en streckkod.

I följande skärmbild visas en exempelstreckkod i utdata från PDF.

<img src="./assets/barcode-output-sample.png" alt="Exempelutdata med streckkod" width="700">


## Streckkodstyper {#barcode-types}

| Typ | CSS-attribut | Ytterligare attribut |
| ------------------------------- | ----------------------- | -------------------------- |
| QR-kod | qrcode |  |
| PDF417 | pdf417 |  |
| DataMatrix | data-matrix |  |
| Aztec-kod | aztec-code |  |
| Stödrastermatris | grid-matrix |  |
| Maxicode | maxicode-läge-4 |  |
| Micro QR | microqr |  |
| Kod ett | code-one |  |
| Kodablock F | codablockf |  |
| GS1 Databar Limited | databar-begränsad |  |
| GS1-databasens omnidirectional | databar, enkelriktad |  |
| EAN-13 | ean-13 |  |
| GS1-128 (EAN-128) | code128 | -ro-barcode-encoding: gs1; |
| ITF-14 | itf14 |  |
| UPC-A | upc-a |  |
| Kod 128 | code128 |  |
| Varvad 2 av 5 | code2of5 interleaved |  |
| POSTNET | postnet |  |
| Dutch Post Kixcode | kixcode |  |
| Korea Post | Korea-post |  |
| Deutsche Post Leitcode | dp-leitcode |  |
| Australien | auspost |  |
| Logmars | logmars |  |
| Farmakood | farmakologi |  |
| USPS OneCode (Intelligent Mail) | usps-onecode |  |


