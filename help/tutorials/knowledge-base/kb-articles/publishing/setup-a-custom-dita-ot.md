---
title: Konfigurera anpassad DITA-OT i [!DNL AEM Guides]
description: Lär dig hur du ställer in anpassad DITA-OT i [!DNL Adobe Experience Manager Guides]
role: Admin
source-git-commit: 880cd344ceb65ea339be699ebcad41c0d62e168a
workflow-type: tm+mt
source-wordcount: '139'
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
