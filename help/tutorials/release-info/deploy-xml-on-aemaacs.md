---
title: Lägga till [!DNL AEM Guides] till [!DNL AEM as a Cloud Service] miljö
description: Lär dig hur du lägger till [!DNL AEM Guides] till [!DNL AEM as a Cloud Service] miljö
source-git-commit: 880cd344ceb65ea339be699ebcad41c0d62e168a
workflow-type: tm+mt
source-wordcount: '198'
ht-degree: 0%

---

# [!DNL AEM Guides] as a Cloud Service driftsättning

Lär dig hur du lägger till [!DNL Guides] till [!DNL AEM as a Cloud Service] miljö.

## Manuell distribution via Cloud Manager Git-pipeline

Om du har köpt [!DNL AEM Guides] as a Cloud Service before March 29, 2022, follow these deployment instructions:

* Om du börjar om kan du ersätta koden som har genererats av [!UICONTROL Cloud Manager] med koden från nedanstående rapport, som redan har ett XML-plugin-program integrerat: https://github.com/Adobe-TCS/XML-documentation-for-AEMaaCS

* Om du redan har incheckade anpassningar i [!UICONTROL Cloud Manager] git repo, du kan se rapporten nedan för instruktioner om hur du lägger till XML-plugin i din befintliga kod: https://github.com/Adobe-TCS/DoX-Installer-for-AEMaaCS

## Distribution via Cloud Manager

Om du är en kund som köpt [!DNL AEM Guides] as a Cloud Service den 2022-03-29 Följ dessa anvisningar för att lägga till [!DNL Guides] till [!DNL AEM as a Cloud Service] miljö:

1. Logga in på [!UICONTROL Cloud Manager].

1. Redigera programmet som du vill konfigurera [!DNL AEM Guides].

1. Växla till **[!UICONTROL Solutions and Add-ons]** -fliken.

1. I **[!UICONTROL Solutions and Add-ons]** tabell, klicka på **[!UICONTROL Assets]**.

1. Välj **[!UICONTROL Guides]** och markera **[!UICONTROL Save]**.

Du har konfigurerat ditt program för automatisk etablering av AEM.

![Configuring AEM Guides solution](assets/addon-configuration.png)

>[!NOTE]
>
>Installera [!DNL AEM Guides] i alla miljöer som omfattas av det integrerade programmet måste du köra den pipeline som är kopplad till miljön. Ingen ytterligare konfiguration krävs i Git-kodbasen för CM för installation [!DNL AEM Guides].
