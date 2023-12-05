---
title: Öppna DITA-avsnitt eller DITA-kartfiler på samma flik
description: Lär dig hur du öppnar DITA-avsnitt eller kartfiler på samma flik
source-git-commit: 880cd344ceb65ea339be699ebcad41c0d62e168a
workflow-type: tm+mt
source-wordcount: '208'
ht-degree: 0%

---

# Öppna DITA-avsnitt eller DITA-kartfiler på samma flik {#id223HH0301J3}

När du klickar på en länk till ett ämne eller en kartfil i vissa arbetsflöden öppnas den på en ny flik. Detta kan leda till att många flikar öppnas i webbläsaren, vilket kan påverka din produktivitet. Du kan ändra det här beteendet genom att öppna ett ämne eller en kartfil på en ny flik och tvinga det att öppnas på den aktuella fliken.

Använd instruktionerna i [Konfigurationsåsidosättningar](download-install-additional-config-override.md#) för att skapa konfigurationsfilen. Ange följande \(egenskap\)-information i konfigurationsfilen för att öppna ett ämne eller en kartfil på en ny flik:

| PID | Egenskapsnyckel | Egenskapsvärde |
|---|------------|--------------|
| `com.adobe.fmdita.xmleditor.config.XmlEditorConfig` | `xmleditor.openinsametab` | Boolean \(true/false\). <br> **Standardvärde**: `false` |

Den här inställningen påverkar följande platser där du kan komma åt ämne- eller mappfilerna:

- Skapa DITA-avsnitt \(i slutet av arbetsflödet när du klickar på **Öppna ämne** knapp\)

- Skapa DITA-karta \(i slutet av arbetsflödet när du klickar på **Öppna karta** knapp\)

- Fliken Ämnen i DITA-kartkonsolen

- Fliken Baslinjer i DITA-kartkonsolen

- Fliken Rapporter i DITA-kartkonsolen


**Överordnat ämne:**[ Anpassa Web Editor](conf-web-editor.md)
