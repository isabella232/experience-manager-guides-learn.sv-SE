---
title: Översätta innehåll
description: Lär dig hur du översätter innehåll
source-git-commit: 880cd344ceb65ea339be699ebcad41c0d62e168a
workflow-type: tm+mt
source-wordcount: '651'
ht-degree: 0%

---

# Översätta innehåll {#id181GB0400UI}

Automatisera översättning av sidinnehåll, resurser och användargenererat innehåll för att skapa och underhålla flerspråkiga webbplatser. Om du vill automatisera arbetsflöden för översättning integrerar du översättare med AEM och skapar projekt för översättning av innehåll till flera språk. AEM har stöd för arbetsflöden för översättning mellan människor och datorer.

- Översättning till människor: Innehållet skickas till din översättningsleverantör och översätts av professionella översättare. När det är klart returneras det översatta innehållet och importeras till AEM. När översättningsleverantören är integrerad med AEM utbyts innehåll automatiskt mellan AEM och översättningsleverantören

- Maskinöversättning: Maskinöversättningstjänsten översätter omedelbart ditt innehåll


Översättning av innehåll omfattar följande steg:

1. AEM [översättningstjänst](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/sites/administering/reusing-content/translation/integration-framework.html?lang=en) och skapa konfigurationer för ramverk för översättningsintegrering.

1. Koppla sidorna i din språkinställning till översättningstjänsten och ramverkskonfigurationerna.

1. Identifiera typen av [innehåll att översätta](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/sites/administering/reusing-content/translation/rules.html?lang=en).

1. [Förbered innehållet för översättning](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/sites/administering/reusing-content/translation/preparation.html?lang=en) genom att skapa språkinställningarna och skapa rotsidorna för språkkopior.

1. Skapa [översättningsprojekt](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/sites/administering/reusing-content/translation/managing-projects.html?lang=en) för att samla det innehåll som ska översättas och förbereda översättningsprocessen.

1. Använd översättningsprojekt för att [hantera innehållsöversättning](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/sites/administering/reusing-content/translation/managing-projects.html?lang=en) -processen.


När översättningstjänstleverantören inte tillhandahåller någon koppling till integrering med AEM stöder AEM manuell export och import av översatt innehåll i XML-format.

>[!TIP]
>
> Se *Översättning* i Best practices Guide.

## Konfigurera översättningsfliken på DITA-kartpanelen

Så här döljer du översättningsfliken på DITA-kartkontrollpanelen:

1. Använd instruktionerna i [Konfigurationsåsidosättningar](download-install-additional-config-override.md#) för att skapa konfigurationsfilen.
1. Ange följande \(egenskap\)-information i konfigurationsfilen för att konfigurera översättningsfliken på kartkontrollpanelen:

   | PID | Egenskapsnyckel | Egenskapsvärde |
   |---|------------|--------------|
   | `com.adobe.fmdita.config.ConfigManager` | `tabs.translation` | Boolean \( true/ false\).<br> **Standardvärde**: `true` |

   >[!NOTE]
   >
   > Den här konfigurationen är aktiverad som standard och översättningsfliken är inte tillgänglig på kartkontrollpanelen.


## Konfigurera komponentbaserat översättningsarbetsflöde

Om kopplingen för översättningsleverantören inte stöder DITA-innehåll måste det komponentbaserade översättningsarbetsflödet aktiveras. När det är aktiverat skickas det översättningsbara innehållet som metadata för resursen. Kopplingen måste dock ha stöd för översättning av metadata för resurser för att det här arbetsflödet ska fungera.

Baserat på det översättningsarbetsflöde som används i konfigurationen bör det komponentbaserade arbetsflödesalternativet för översättning konfigureras. Använd instruktionerna i [Konfigurationsåsidosättningar](download-install-additional-config-override.md#) för att skapa konfigurationsfilen. Ange följande \(egenskap\)-information i konfigurationsfilen för att konfigurera komponentbaserat översättningsarbetsflöde:

| PID | Egenskapsnyckel | Egenskapsvärde |
|---|------------|--------------|
| `com.adobe.fmdita.config.ConfigManager` | `component.translation` | Boolean: <br> - Om du använder mänsklig översättning *Inaktivera* \( `false`\) **Komponentbaserat översättningsarbetsflöde** alternativ. <br> - Om du använder maskinöversättning *Aktivera \( `true`\)* den **Komponentbaserat översättningsarbetsflöde** alternativ. |

>[!NOTE]
>
> Om du använder översättningskoppling måste du kontrollera att du har konfigurerat anslutningen enligt beskrivningen i *[Konfigurera översättningsintegreringsramverket](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/sites/administering/reusing-content/translation/integration-framework.html?lang=en)* i AEM.

>[!IMPORTANT]
>
> När du har konfigurerat översättningskonfigurationerna kontrollerar du att du har konfigurerat rätt molnkonfiguration för språkmapparna.

## Konfigurera efterbearbetning av tillfälliga språkkopior

När du initierar översättningsarbetsflödet skapas tillfälliga språkkopior av källinnehållet. Du kan välja att aktivera eller inaktivera efterbearbetningen för dessa tillfälliga filer. I efterbearbetningen löses de inkommande och utgående referenserna från filerna, dokumentläget ställs in tillsammans med andra åtgärder. Om du aktiverar efterbearbetning för de här temporära filerna kan översättningsprocessen ta längre tid att slutföra. Därför rekommenderar vi att alternativet för efterbearbetning är inaktiverat.

Använd instruktionerna i [Konfigurationsåsidosättningar](download-install-additional-config-override.md#) för att skapa konfigurationsfilen. Ange följande \(egenskap\)-information i konfigurationsfilen för att konfigurera efterbearbetning av tillfälliga språkkopior:

| PID | Egenskapsnyckel | Egenskapsvärde |
|---|------------|--------------|
| `com.adobe.fmdita.config.ConfigManager` | `postprocess.temporary.langcopies` | Boolean: <br> - Om du inte vill köra efterbearbetningen av de temporära filerna ska du *Inaktivera* \( false\) **Post-process language copies** alternativ.<br> - Om du vill köra efterbearbetningen av de temporära filerna ska du *Aktivera* \( true\) **Post-process language copies** alternativ.<br> **Standardvärde**: false |
