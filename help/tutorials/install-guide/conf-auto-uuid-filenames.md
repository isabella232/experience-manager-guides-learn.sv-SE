---
title: Konfigurera automatiska filnamn baserat på UUID
description: Lär dig hur du konfigurerar automatiska filnamn baserat på UUID
source-git-commit: 801c306fa120e7889d4b9428fd5bee2849bf1956
workflow-type: tm+mt
source-wordcount: '217'
ht-degree: 0%

---


# Konfigurera automatiska filnamn baserat på UUID {#id205QG070D5Z}

När ett ämne eller en kartfil skapas får författare som standard ett alternativ för att även ange filnamnet. Författare kan fritt tilldela filnamnen enligt sina önskemål. Detta kan dock leda till inkonsekvens och ett stort antal filnamn kan ses i ett stort dokumentationssystem. Som administratör kan du hindra författarna från att tilldela filnamn till de filer de skapar i systemet. För varje nytt ämne eller mappningsfil kan du välja att tilldela UUID-baserade filnamn automatiskt.

Utför följande steg för att automatiskt tilldela UUID-baserade filnamn för alla nya filer som skapas i systemet:

1. Öppna konfigurationssidan för Adobe Experience Manager Web Console.

   Standardwebbadressen för åtkomst till konfigurationssidan är:

   ```http
   http://<server name>:<port>/system/console/configMgr
   ```

1. Sök efter och klicka på *com.adobe.fmdita.xmleditor.config.XmlEditorConfig* paket.

1. Välj **Använd UUID-baserade systemfilnamn** alternativ.

1. Klicka **Spara**.


>[!NOTE]
>
> Som standard är det här alternativet inaktiverat. När det här alternativet är aktiverat kan författare inte ange filnamnet när de skapar ett nytt ämne eller en ny mappningsfil. Du kan skapa ett nytt ämne eller en ny mappfil från resursgränssnittet och webbredigeraren.

**Överordnat ämne:**[ Konfigurera filnamn](conf-file-names.md)

