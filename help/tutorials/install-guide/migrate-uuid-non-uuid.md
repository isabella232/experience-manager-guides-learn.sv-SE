---
title: Migrering av icke-UID till UUID-innehåll
description: Lär dig hur du migrerar icke-UID till UUID-innehåll
exl-id: 093b380e-9a8b-4e60-aeaa-3458e8c257f2
source-git-commit: 21edbb2f8a49213ea95fac8a957056711219e7e4
workflow-type: tm+mt
source-wordcount: '373'
ht-degree: 0%

---

# Migrering av icke-UID till UUID-innehåll {#id226TI0U20XA}

>[!IMPORTANT]
>
> Du kan migrera icke-UID-innehåll till UUID-servern. Om du vill migrera till UUID-servern måste du ha en server som inte är UUID med AEM guides version 4.0 installerad.

Utför följande steg för att migrera ditt icke-UID-innehåll:

>[!NOTE]
>
> Varje steg är viktigt och om något av stegen saknas kan det leda till att serverdata inte fungerar eller är skadade. Se till att du slutför alla steg.

1. Se till att **Aktivera startprogram för arbetsflöde efter bearbetning** in *com.adobe.fmdita.config.ConfigManager* och **Aktivera efterbearbetning av version** in *com.adobe.fmdita.postprocess.version.PostProcessVersionObservation* är aktiverade.

   ```http
   http://<server name>:<port>/system/console/configMgr/com.adobe.fmdita.config.ConfigManager
   ```

1. Installera UUID-versionen av nästa större version över en version som inte är UUID. Om du till exempel använder 4.0-version som inte är UUID måste du installera UUID version 4.1.

1. På fliken Launcher inaktiverar du följande arbetsflöden och andra arbetsflöden som körs på /content/dam med hjälp av startprogram i `http://localhost:4502/libs/cq/workflow/content/console.html`:

   - **DAM-uppdateringsresurs** arbetsflöde
   - **DAM-metadataåterställning** arbetsflöde

1. Inaktivera **Aktivera startprogram för arbetsflöde efter bearbetning** in *com.adobe.fmdita.config.ConfigManager* och inaktivera **Aktivera efterbearbetning av version** in *com.adobe.fmdita.postprocess.version.PostProcessVersionObservation*.

   ```http
   http://<server name>:<port>/system/console/configMgr/com.adobe.fmdita.config.ConfigManager
   ```

1. Lägg till en separat loggare för `com.adobe.fmdita.uuid.upgrade.UuidUpgrade.`

   Webbläsarsvaret finns också på /content/uid-upgrade/logs.

1. Kör den angivna frågan på en mapp med mindre data med `doReviews=false` innan den körs på / content/dam: `http://localhost:4502/bin/dxml/uuid_upgrade?root=/content/dam/test&doReviews=false`

   >[!TIP]
   >
   >  Du kan kontrollera om alla filer i mappen är korrekt uppgraderade och om alla funktioner bara fungerar för den mappen.

**Parametrar för frågan:**

    - &quot;root&quot;: Rotmapp där uppgraderingen måste ske \(Använd /content/dam för alla databaser.\)
    - &quot;doReviews&quot;: true/false \(Om granskningar måste uppgraderas eller inte. Standardvärdet är false.\)
    - &quot;doBaselines&quot;: true/false \(Om baslinjer måste uppgraderas eller inte. Standardvärdet är true.\)
    -`processLevel`: -1\(misslyckades utan återställning\), 0\(misslyckades med återställning\), 1\(misslyckades med fel\), 2\(uppgraderades utan fel\) \(Vid nytt skriptförsök efter fel behandlas endast filer med &quot;fmUpgradeStatus&quot; &lt;= processLevel igen, annars ignoreras de. Standardvärdet är 1.\)
    -`ignoreImageVersions`: true/false \(Ignorerar bearbetning av bildversioner. Standardvärdet är false.\)
    
    >[!OBS!]
    >
    > Vi kan köra innehållsmigrering på mappnivå eller hela innehållet/mappen eller på samma mapp \(kör migreringen igen\).

1. När servern har migrerats aktiverar du följande arbetsflöden och efterbearbetning för att fortsätta arbeta på servern:

   - **DAM-uppdateringsresurs** arbetsflöde
   - **DAM-metadata** arbetsflöde

>[!NOTE]
>
> Om vissa filer inte bearbetas eller är skadade före migreringen kommer de att vara skadade även efter migreringen.
