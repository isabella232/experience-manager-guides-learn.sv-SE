---
title: Översätta innehåll i AEM stödlinjer
description: Lär dig hur du översätter innehåll
source-git-commit: 9fe396dcfd2e3570ec386c958d7d4efdb4d608e5
workflow-type: tm+mt
source-wordcount: '758'
ht-degree: 0%

---


# Översätta innehåll {#id181GB0400UI}

Automatisera översättning av sidinnehåll, resurser och användargenererat innehåll för att skapa och underhålla flerspråkiga webbplatser. Om du vill automatisera arbetsflöden för översättning integrerar du översättare med AEM och skapar projekt för översättning av innehåll till flera språk. AEM har stöd för arbetsflöden för översättning mellan människor och datorer.

- Översättning: Innehållet skickas till översättningsleverantören och översätts av professionella översättare. När det är klart returneras det översatta innehållet och importeras till AEM. När översättningsleverantören är integrerad med AEM utbyts innehåll automatiskt mellan AEM och översättningsleverantören

- Maskinöversättning: Maskinöversättningstjänsten översätter ditt innehåll omedelbart


Översättning av innehåll omfattar följande steg:

1. AEM [översättningstjänst](https://helpx.adobe.com/experience-manager/6-5/sites/administering/using/tc-tic.html#ConnectingtoaTranslationServiceProvider) och skapa [konfigurationer för översättningsintegreringsramverk](https://helpx.adobe.com/experience-manager/6-5/sites/administering/using/tc-tic.html#CreatingaTranslationIntegrationConfiguration).

1. Koppla sidorna på ditt språk till överordnad [översättningstjänst och ramverkskonfigurationer](https://helpx.adobe.com/experience-manager/6-5/sites/administering/using/tc-tic.html#ConfiguringPagesforTranslation).

1. Identifiera typen av [innehåll att översätta](https://helpx.adobe.com/experience-manager/6-5/sites/administering/using/tc-rules.html).

1. [Förbered innehållet för översättning](https://helpx.adobe.com/experience-manager/6-5/sites/administering/using/tc-prep.html) genom att skapa det överordnad språket och skapa rotsidorna för språkkopior.

1. Skapa [översättningsprojekt](https://helpx.adobe.com/experience-manager/6-5/sites/administering/using/tc-manage.html) för att samla det innehåll som ska översättas och förbereda översättningsprocessen.

1. Använd översättningsprojekt för att [hantera innehållsöversättning](https://helpx.adobe.com/experience-manager/6-5/sites/administering/using/tc-manage.html) -processen.


När översättningstjänstleverantören inte tillhandahåller någon koppling till AEM stöder AEM manuell export och import av översatt innehåll i XML-format.

>[!TIP]
>
> Se *Översättning* finns i Best practices guide för översättning av innehåll.

## Konfigurera översättningsfliken på DITA-kartpanelen

Alternativet Dölj översättningsflik är inte aktiverat som standard och du måste aktivera det från configMgr. Så här döljer du översättningsfliken på DITA-kartkontrollpanelen:

1. Öppna konfigurationssidan för Adobe Experience Manager Web Console.

   Standardwebbadressen för åtkomst till konfigurationssidan är:

   ```http
   http://<server name>:<port>/system/console/configMgr
   ```

1. Sök efter och klicka på **com.adobe.fmdita.config.ConfigManager** paket.

1. Välj **Dölj översättningsflik** om du vill dölja översättningsfliken på kartkontrollpanelen.

   >[!NOTE]
   >
   > Den här egenskapen är inaktiverad som standard och översättningsfliken är tillgänglig på kartkontrollpanelen.

1. Klicka **Spara**.

## Konfigurera komponentbaserat översättningsarbetsflöde

Om kopplingen för översättningsleverantören inte stöder DITA-innehåll måste det komponentbaserade översättningsarbetsflödet aktiveras. När det är aktiverat skickas det översättningsbara innehållet som metadata för resursen. Kopplingen måste dock ha stöd för översättning av metadata för resurser för att det här arbetsflödet ska fungera.

Baserat på det översättningsarbetsflöde som används i konfigurationen bör det komponentbaserade arbetsflödesalternativet för översättning konfigureras enligt följande:

1. Öppna konfigurationssidan för Adobe Experience Manager Web Console.

   Standardwebbadressen för åtkomst till konfigurationssidan är:

   ```http
   http://<server name>:<port>/system/console/configMgr
   ```

1. Sök efter och klicka på **com.adobe.fmdita.config.ConfigManager** paket.

1. Konfigurera **Komponentbaserat DITA-översättningsarbetsflöde** alternativ enligt dina inställningar:

   - Om du använder mänsklig översättning *Inaktivera* den **Komponentbaserat översättningsarbetsflöde** alternativ.

   - Om du använder maskinöversättning *Aktivera* den **Komponentbaserat översättningsarbetsflöde** alternativ.
   >[!NOTE]
   >
   > Om du använder översättningskoppling måste du kontrollera att du har konfigurerat anslutningen enligt beskrivningen i *[Konfigurera översättningsintegreringsramverket](https://helpx.adobe.com/experience-manager/6-5/sites/administering/using/tc-tic.html)* i AEM.

1. Klicka **Spara**.


>[!IMPORTANT]
>
> När du har konfigurerat översättningskonfigurationerna kontrollerar du att du har konfigurerat rätt molnkonfiguration för språkmapparna.

## Konfigurera efterbearbetning av tillfälliga språkkopior

När du initierar översättningsarbetsflödet skapas tillfälliga språkkopior av källinnehållet. Du kan välja att aktivera eller inaktivera efterbearbetningen för dessa tillfälliga filer. I efterbearbetningen löses de inkommande och utgående referenserna från filerna, dokumentläget ställs in tillsammans med andra åtgärder. Om du aktiverar efterbearbetning för de här temporära filerna kan översättningsprocessen ta längre tid att slutföra. Därför rekommenderar vi att alternativet för efterbearbetning är inaktiverat.

Som standard är alternativet för efterbearbetning av tillfälliga filer inaktiverat. Du kan konfigurera det här alternativet genom att utföra följande steg:

1. Öppna konfigurationssidan för Adobe Experience Manager Web Console.

   Standardwebbadressen för åtkomst till konfigurationssidan är:

   ```http
   http://<server name>:<port>/system/console/configMgr
   ```

1. Sök efter och klicka på **com.adobe.fmdita.config.ConfigManager** paket.

1. Konfigurera **Post-process language copies** alternativ enligt dina inställningar:

   - \(*Standard*\) Om du inte vill köra efterbearbetningen av de temporära filerna ska du *Inaktivera* den **Post-process language copies** alternativ.

   - Om du vill köra efterbearbetningen av de temporära filerna ska du *Aktivera* den **Post-process language copies** alternativ.

1. Klicka **Spara**.


