---
title: Konfigurera giltiga filnamn för AEM
description: Lär dig hur du konfigurerar giltiga filnamn för AEM webbplatsutdata
source-git-commit: 880cd344ceb65ea339be699ebcad41c0d62e168a
workflow-type: tm+mt
source-wordcount: '146'
ht-degree: 0%

---

# Konfigurera giltiga filnamn för AEM {#id214GK0X0KXA}

På samma sätt som listan med giltiga filnamnstecken som tillåts för DITA-avsnitt kan du även konfigurera en lista med giltiga filnamnstecken för AEM. Några av de kända tecken som inte tillåts i en URL är: ``'<>`@$``. Dessa tecken har konfigurerats för att automatiskt konverteras till ett understreck &quot;`_`&quot; när de påträffas när AEM genererar platsens utdatafilnamn.

Använd instruktionerna i [Konfigurationsåsidosättningar](download-install-additional-config-override.md#) för att skapa konfigurationsfilen. I konfigurationsfilen anger du följande \(egenskap\)-information för att ange giltiga tecken i AEM platsutdata:

| PID | Egenskapsnyckel | Egenskapsvärde |
|---|------------|--------------|
| `com.adobe.fmdita.common.SanitizeNodeNameImpl` | `aemsite.DisallowedFileNameChars` | Lägg till tecken som du vill ersätta med ett understreck i AEM Platsens utdatafilnamn. <br> **Standardvärde**: ``'<\>\`@$`` |

**Överordnat ämne:**[ Konfigurera filnamn](conf-file-names.md)
