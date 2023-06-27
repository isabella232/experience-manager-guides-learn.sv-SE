---
title: AEM
description: Lär dig hur du uppgraderar AEM
source-git-commit: 6051181e243cf71919901093c1b5590f21832545
workflow-type: tm+mt
source-wordcount: '104'
ht-degree: 0%

---


# AEM {#id213BD050YPH}

1. Gå till din Cloud Managers Git-databas.

1. Uppdatera dox/dox.installer/pom.xml.

1. Uppdatera värdet för variabeln dox.version till versionsinformationen som tillhandahålls av Adobe.

1. Genomför ändringarna och kör Cloud Manager-pipeline för att distribuera det uppgraderade paketet.


>[!NOTE]
>
> Mer information om att använda CI/CD-pipeline finns i [Använda CI/CD-pipeline i Adobe Cloud Manager](https://experienceleague.adobe.com/docs/experience-manager-learn/foundation/cloud-manager/use-the-cicd-pipeline-in-cloud-manager-for-aem.html).

## Rensa webbläsarcache

När uppgraderingen är klar måste alla användare rensa webbläsarens cache innan de kan använda den uppgraderade versionen av AEM.

**Överordnat ämne:**[ Hämta och installera](download-install.md)

