---
title: Generera element-ID automatiskt
description: Lär dig generera element-ID automatiskt
source-git-commit: 880cd344ceb65ea339be699ebcad41c0d62e168a
workflow-type: tm+mt
source-wordcount: '337'
ht-degree: 0%

---

# Generera element-ID automatiskt {#id20CIL40016I}

AEM Guides genererar ett dokument-ID för alla nya dokument som du skapar. När du t.ex. skapar en DITA-karta, ett ID som `map.ditamap_random_digits` är tilldelad kartans ID. Du kan också definiera element som ett ID genereras och tilldelas automatiskt på.

AEM innehåller enkla konfigurationsinställningar där du behöver definiera elementen som ett ID genereras automatiskt på och ett mönster för ID:t. Som standard är vissa element som `section`, `table`, `ul`, `ol`, har konfigurerats för automatisk generering av ID. Du kan lägga till andra element i den här listan så att när dessa element infogas i ett dokument genererar AEM stödlinjer och tilldelar ett ID baserat på det angivna mönstret

Utför följande steg för att konfigurera element så att de har ett autogenererat ID:

1. Öppna konfigurationssidan för Adobe Experience Manager Web Console.

   Standardwebbadressen för åtkomst till konfigurationssidan är:

   ```http
   http://<server name>:<port>/system/console/configMgr
   ```

1. Sök efter och klicka på **com.adobe.fmdita.xmleditor.config.XmlEditorConfig** paket.

1. I *XmlEditorConfig* inställningar, ange ett eller flera element i **Generera ID automatiskt för elementtaggar** fält.

   >[!NOTE]
   >
   > Elementtaggar är DITA-elementnamn som `body`, `title`, `codeblock`och så vidare. Om du vill ange flera element avgränsar du elementnamnen med ett kommatecken.

1. I **Mönster för att generera ID:n** anger du ett mönster för att generera ett ID.

   Standardvärdet för det här fältet är `${elementName}_${id}`. The `${elementName}` värdet ersätts med elementets namn. The `${id}` variabeln genererar sekventiellt nummer för elementet. Om du till exempel tilldelar styckeelementet ett automatiskt genererat ID:n får det första stycket i avsnittet eller dokumentet ett ID som p\_1, nästa stycke får p\_2 osv. I ett annat dokument startar dock ID-genereringsprocessen om. Det innebär att i ett annat dokument kan ID:n som p\_1 och p\_2 tilldelas styckeelement.

   Om dokumentet redan innehåller ID:n i det angivna mönstret tilldelas dessa ID:n inte till nya element i den automatiska genereringsprocessen.

1. Klicka **Spara**.


**Överordnat ämne:**[ Anpassa Web Editor](conf-web-editor.md)
