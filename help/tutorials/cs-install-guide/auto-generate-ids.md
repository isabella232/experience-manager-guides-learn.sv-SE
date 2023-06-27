---
title: Generera element-ID automatiskt
description: Lär dig generera element-ID automatiskt
source-git-commit: 4f15166b1b250578f07e223b0260aacf402224be
workflow-type: tm+mt
source-wordcount: '280'
ht-degree: 0%

---


# Generera element-ID automatiskt {#id20CIL40016I}

AEM Guides genererar ett dokument-ID för alla nya dokument som du skapar. När du t.ex. skapar en DITA-karta, ett ID som `map.ditamap_random_digits` är tilldelad kartans ID. Du kan också definiera element som ett ID genereras och tilldelas automatiskt på.

AEM innehåller enkla konfigurationsinställningar där du behöver definiera elementen som ett ID genereras automatiskt på och ett mönster för ID:t. Som standard är vissa element som `section`, `table`, `ul`, `ol`, har konfigurerats för automatisk generering av ID. Du kan lägga till andra element i den här listan så att när dessa element infogas i ett dokument genererar AEM stödlinjer och tilldelar ett ID baserat på det angivna mönstret

Använd instruktionerna i [Konfigurationsåsidosättningar](download-install-additional-config-override.md#) för att skapa konfigurationsfilen. Ange följande \(egenskap\)-information i konfigurationsfilen för att konfigurera autogenererade element-ID:n:

| PID | Egenskapsnyckel | Egenskapsvärde |
|---|------------|--------------|
| `com.adobe.fmdita.xmleditor.config.XmlEditorConfig` | `xmleditor.classes` | Ange en kommaavgränsad lista med element. <br> **Standardvärde**: `"topic, section, table, simpletable, fig, image, ul, ol"` |

Om du vill konfigurera ett mönster för automatiskt genererat ID skapar du en konfigurationsfil med följande egenskaper:

| PID | Egenskapsnyckel | Egenskapsvärde |
|---|------------|--------------|
| `com.adobe.fmdita.xmleditor.config.XmlEditorConfig` | `xmleditor.pattern` | Standardvärdet för det här fältet är inställt på `${elementName}_${id}`. The `${elementName}` värdet ersätts med elementets namn. The `${id}` variabeln genererar sekventiellt nummer för elementet. Om du till exempel tilldelar styckeelementet ett automatiskt genererat ID:n får det första stycket i avsnittet eller dokumentet ett ID som p\_1, nästa stycke får p\_2 osv. I ett annat dokument startar dock ID-genereringsprocessen om. Det innebär att i ett annat dokument kan ID:n som p\_1 och p\_2 tilldelas styckeelement. **Standardvärde**: ``${elementName}_${id}`` |

**Överordnat ämne:**[ Anpassa Web Editor](conf-web-editor.md)

