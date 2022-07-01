---
title: Skapa och använda villkor
description: Lär dig hur du skapar villkor och sedan skapar villkorsstyrd innehållsgenerering i [!DNL AEM Guides]
role: User
exl-id: a86007e3-48d1-458b-84a7-b683e113e5b2
source-git-commit: b5e64512956f0a7f33c2021bc431d69239f2a088
workflow-type: tm+mt
source-wordcount: '223'
ht-degree: 0%

---

# Skapa och använda villkor och generera villkorsstyrda utdata

**Använd skiftläge**

* Författare kan ange villkor för en del av innehållet så att de kan styra om det ska visas i utdata eller inte.

* Författare kan välja att visa/dölja olika villkor vid publiceringen.

* Författare kan till exempel lägga till attribut som version 1.0 och version 2.0 i innehållet och använda villkor för att inkludera version 1.0 för version 1.0 och exkludera version 2.0.

**Steg 1**

Definiera villkor som är relevanta för dokumentationen i [!UICONTROL Folder Profiles]: Se avsnittet **Konfigurera villkorsstyrda attribut för globala profiler eller profiler på mappnivå** in [Sidan 64 i installations- och konfigureringshandboken](https://helpx.adobe.com/content/dam/help/en/xml-documentation-solution/3-8/XML-Documentation-for-Adobe-Experience-Manager_Installation-Configuration-Guide_EN.pdf)

![Konfigurera villkor i mappprofiler](assets/conditions-in-profiles.png)

**Steg 2**

Välj **[!UICONTROL Folder Profile]** definieras i steg 1 i **Användarinställningar** i XML-redigeraren: Se avsnittet **Användarinställningar** in [Sidan 39 i användarhandboken](https://helpx.adobe.com/content/dam/help/en/xml-documentation-solution/3-8/XML-Documentation-for-Adobe-Experience-Manager_User-Guide_EN.pdf)


**Steg 3**

Använd villkoren för att anpassa innehållsavsnitt: Se avsnittet **Villkor** in [Sidan 81 i användarhandboken](https://helpx.adobe.com/content/dam/help/en/xml-documentation-solution/3-8/XML-Documentation-for-Adobe-Experience-Manager_User-Guide_EN.pdf)

![Använd villkor i Web Editor](assets/conditions-in-web-editor.png)

**Steg 4**

Definiera villkorsförinställningar på mappningsnivå för att välja vilka villkor som ska aktiveras i utdata: Se avsnittet **Använda förinställningar för villkor** in [Sidan 184 i användarhandboken](https://helpx.adobe.com/content/dam/help/en/xml-documentation-solution/3-8/XML-Documentation-for-Adobe-Experience-Manager_User-Guide_EN.pdf)
