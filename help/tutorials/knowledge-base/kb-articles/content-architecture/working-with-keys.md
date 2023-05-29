---
title: Arbeta med tangenter
description: Så här skapar du nycklar som ska användas i hela organisationens innehåll
role: Admin
exl-id: b8e3a6d2-ea82-4fdb-bd16-3f4b6594af52
source-git-commit: c8feab55ed3b8e7b36ec46b21f63155766627e40
workflow-type: tm+mt
source-wordcount: '173'
ht-degree: 0%

---

# Skapa nycklar

Organisationer bör använda nycklar i de fall där de har viss återanvändbar och vanlig text, som produktnamn eller produkttonhöjd, som används på många ställen men som ofta ändras. Om du använder tangenter för sådan återanvändbar text kan du överföra en uppdatering på flera ställen genom att göra ändringen på en enda plats, t.ex. i nyckelvärdet.

## Steg 1: Skapa en global karta för att lagra nycklar

Skapa en karta och lägg till [!UICONTROL keyref] -element.

```
<?xml version="1.0" encoding="UTF-8"?>
<!DOCTYPE map PUBLIC "-//OASIS//DTD DITA Map//EN" "technicalContent/dtd/map.dtd">
<mapid="map.ditamap_ffbdbf06-8658-4311-ad84-1c631bba904f">
  <title>global-keys-map</title>
  <keydefkeys="adobe">
    <topicmeta>
      <linktext>Adobe Systems</linktext>
    </topicmeta>
  </keydef>
  <keydefkeys="AEM">
    <topicmeta>
      <linktext>Adobe Experience Manager</linktext>
    </topicmeta>
  </keydef>
</map>
```

Här har du definierat två definitioner, som visas ovan, som en [!UICONTROL keyref] as _AEM_ för _Adobe Experience Manager_ text.

## Steg 2: Lägg till den här kartan i publikationskartan

```
<?xml version="1.0" encoding="UTF-8"?>
<!DOCTYPE map PUBLIC "-//OASIS//DTD DITA Map//EN" "technicalContent/dtd/map.dtd">
<mapid="map.ditamap_cbf4a96d-e382-4e8c-8830-bcc093fe6638">
  <title>sample-map</title>
  <topicrefhref="sample-topic-using-the-keys.dita"type="topic">
  </topicref>
  <maprefformat="ditamap"href="global-keys-map.ditamap"type="map">
  </mapref>
</map>
```

## Steg 3: Använd tangenterna för att referera till variablerna som definieras i den globala tangentkartan

+ Redigera ämnet och lägg till nyckelvärdet med [!UICONTROL keyref].
+ Som framgår av skärmbilden visas ett litet fönster där du kan välja nyckelord. Detta visas när du lägger till nyckelordselementet.
   ![Infoga element](assets/insert_element.png)
   ![Nyckelreferens](assets/key_ref.png)

```
<?xml version="1.0" encoding="UTF-8"?>
<!DOCTYPE topic PUBLIC "-//OASIS//DTD DITA Topic//EN" "technicalContent/dtd/topic.dtd">
<topicid="topic.dita_31b00e61-04b5-4193-af7a-68503e88b087">
  <title>sample-topic-using-the-keys</title>
  <shortdesc></shortdesc>
  <body>
    <p>This is a sample topic using the keys defined in the global map</p>
    <p>here i am using the key definition for AEM :<keywordkeyref="AEM"></keyword></p>
  </body>
</topic>
```
