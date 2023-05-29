---
title: Konfigurera anpassad DITA-OT i [!DNL AEM Guides]
description: Lär dig hur du ställer in anpassad DITA-OT i [!DNL Adobe Experience Manager Guides]
role: Admin
exl-id: f479c2cf-5b8b-4517-be97-81303468007a
source-git-commit: 6ae539eff23b1fd5f1d74878b03cf6dd5b20a57d
workflow-type: tm+mt
source-wordcount: '149'
ht-degree: 0%

---

# Konfigurera anpassad DITA-OT i [!DNL AEM Guides] för AEM

Stegen för att lägga till en anpassad DITA-OT beskrivs i avsnittet _Använda anpassade DITA-OT-plugin-program_ i _Installations- och konfigureringshandbok_.

På en hög nivå är stegen:

+ Skaffa grundläggande DITA-OT
   + Om du vill få ett exemplar av färdiga DITA-OT från [!DNL AEM Guides], hämta det från sökvägen `/etc/fmdita/dita_resources/DITA-OT.zip`
   + Om du vill hämta en annan version kan du hämta från [dita-ot-repo](https://www.dita-ot.org/download)
+ Gör ändringar i DITA-OT som [lägga till nytt plugin-program](https://www.dita-ot.org/dev/topics/plugins-installing.html)eller anpassa befintliga plugin-program (se exempel i avsnittet med relaterade länkar nedan)
+ Överför `DITA-OT.zip` mottagen till `/apps/<project-folder>/dita_resources` (vi rekommenderar att du skapar en anpassad projektmapp)
+ Lägg till DITA-profil via **[!UICONTROL Tools]** > **[!UICONTROL Guides]** > **[!UICONTROL DITA Profiles]** (använd DITA-OT-sökvägen där den anpassade DITA-OT-filen överförs, se skärmbild nedan)
   ![DITA-profiler](assets/dita-profile.png)

>[!MORELIKETHIS]
>
>+ [Anpassa DITA-OT-pluginexempel](https://www.dita-ot.org/dev/topics/pdf-customization.html)

