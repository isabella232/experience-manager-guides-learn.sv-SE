---
title: Ange avancerad kartredigerare som standard
description: Lär dig hur du anger den avancerade kartredigeraren som standard
source-git-commit: 801c306fa120e7889d4b9428fd5bee2849bf1956
workflow-type: tm+mt
source-wordcount: '199'
ht-degree: 0%

---


# Ange avancerad kartredigerare som standard {#id181AI0003PN}

AEM innehåller en grundläggande kartredigerare och en avancerad kartredigerare. Med den grundläggande kartredigeraren får du alla funktioner som behövs för att skapa kartfilen. Avancerad kartredigerare har mycket fler funktioner och är integrerad i webbredigeraren. Med Advanced Map Editor kan man skapa och redigera DITA-kartfiler i ett lättanvänt gränssnitt.

När en ny kartfil skapas öppnas den som standard i den grundläggande kartredigeraren. Du kan ändra det här beteendet genom att aktivera inställningen för att öppna den avancerade kartredigeraren som standard.

Utför följande steg för att göra den avancerade kartredigeraren till standardredigerare för kartfilerna:

1. Öppna konfigurationssidan för Adobe Experience Manager Web Console.

   Standardwebbadressen för åtkomst till konfigurationssidan är:

   ```http
   http://<server name>:<port>/system/console/configMgr
   ```

1. Sök efter och klicka på **com.adobe.fmdita.xmleditor.config.XmlEditorConfig** paket.

1. Välj **Dölj snabbredigeraren för kartor** alternativ.

   När det här alternativet är markerat visas inte länken för redigeringsprogrammet för grundläggande kartor någonstans i användargränssnittet. Som standard öppnas kartfiler i Avancerad kartredigerare.


