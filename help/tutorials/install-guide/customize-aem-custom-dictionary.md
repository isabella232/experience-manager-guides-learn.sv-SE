---
title: Anpassa AEM standardordlista
description: Lär dig hur du anpassar AEM standardordlista
source-git-commit: 5ac066bb8db32944abd046f64da11eeb1bdbe467
workflow-type: tm+mt
source-wordcount: '173'
ht-degree: 0%

---


# Anpassa AEM standardordlista {#id209SD8000WU}

Webbredigeraren kan konfigureras att använda AEM stavningskontroll eller webbläsarens stavningskontroll. Om du väljer att arbeta med AEM stavningskontroll får du flexibilitet att definiera din egen ordlista. Dessa anpassade ord läggs sedan till i AEM ordlista och de här orden får inte flaggan \(som felaktiga\) i Web Editor.

Följ de här stegen för att skapa din egen ordlista som läggs till AEM ordlista:

1. Logga in AEM och öppna läget CRXDE Lite.

1. Navigera till följande nod:

   /apps/fmdita/config

1. Skapa en ny fil med namnet user\_dictionary.txt.

1. Öppna filen och lägg till en lista med ord som du vill definiera i din egen ordlista.

   På följande skärmbild visas en lista med egna ord som lagts till i filen user\_dictionary.txt:

   ![](assets/custom-words-list-dictionary.png){width="650" align="left"}

1. Spara och stäng filen.


Författare måste starta om sin Web Editor-session för att den anpassade ordlistan ska uppdateras i AEM.

**Överordnat ämne:**[ Anpassa Web Editor](conf-web-editor.md)

