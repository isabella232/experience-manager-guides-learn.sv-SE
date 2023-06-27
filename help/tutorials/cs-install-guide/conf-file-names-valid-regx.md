---
title: Konfigurera Regx för giltiga filnamnstecken
description: Lär dig hur du konfigurerar Regx för giltiga filnamnstecken
source-git-commit: 4f15166b1b250578f07e223b0260aacf402224be
workflow-type: tm+mt
source-wordcount: '347'
ht-degree: 0%

---


# Konfigurera Regx för giltiga filnamnstecken {#id214BD0550E8}

Från och med AEM 3.8-utgåvan kan du som administratör definiera en lista med giltiga specialtecken som tillåts i filnamn. I tidigare versioner tilläts användare att definiera filnamn som innehåller specialtecken som `@`, `$`, `>`, med mera. Specialtecknen orsakade problem när ämnen öppnades från DITA-kartpanelen eller när man klickade på länken till ett ämne i innehållsförteckningen, vilket ofta ledde till att sidan inte öppnades på grund av specialtecken i URL:en.

Med den konfiguration som gör att du kan definiera en regx för giltiga filnamnstecken har du full kontroll över hur filerna namnges internt i systemet. Du kan definiera en lista med specialtecken som tillåts i filnamnen. Som standard innehåller den giltiga filnamnskonfigurationen &quot;`a-z A-Z 0-9 - _`&quot;. När du skapar en ny fil kan du ha vilket specialtecken som helst i filens titel, men internt ersätts det med &quot;`-`&quot; i filnamnet. Du kan t.ex. ha filens namn som&quot;Introduktion 1&quot; eller&quot;Introduction@1&quot;, och motsvarande filnamn som genereras för båda dessa fall blir&quot;Introduktion-1&quot;.

Tänk på följande tecken när du definierar en lista med giltiga tecken:`*/:[\]|#%{}?&<>"/+`&quot; ersätts alltid med &quot;`-`&quot;.

Om du inte konfigurerar den giltiga specialteckenlistan kan det hända att du får oväntade resultat när du skapar filen. För att undvika sådana fel rekommenderar vi att du gör den här konfigurationsändringen.

Använd instruktionerna i [Konfigurationsåsidosättningar](download-install-additional-config-override.md#) för att skapa konfigurationsfilen. Ange följande \(egenskap\)-information i konfigurationsfilen för att konfigurera regex för giltiga filnamnstecken:

| PID | Egenskapsnyckel | Egenskapsvärde |
|---|------------|--------------|
| `com.adobe.fmdita.xmleditor.config.XmlEditorConfig` | `valid.characters` | Värdet är ett regex-mönster. Den måste ha tre grundläggande tecken och listan måste börja med ett bindestreck \(-\).<br> **Standardvärde**: \[-a-zA-Z0-9\_\] |

>[!NOTE]
>
> På samma sätt som i listan med giltiga filnamnstecken kan du även ange en lista med giltiga filnamnstecken för AEM. Mer information finns i [Konfigurera giltiga filnamn för AEM](conf-file-names-valid-regx-aem-site-output.md#).

**Överordnat ämne:**[ Konfigurera filnamn](conf-file-names.md)

