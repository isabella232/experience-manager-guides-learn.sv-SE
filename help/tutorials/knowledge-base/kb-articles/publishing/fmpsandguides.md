---
title: Publicera med FrameMaker Publishing Server (FMPS) i AEM Guides
description: Publicera med FMPS via AEM
source-git-commit: 1d118aeda42d76b0a9f34ca29fdeedb0165739fd
workflow-type: tm+mt
source-wordcount: '715'
ht-degree: 0%

---


# Publicera med FrameMaker Publishing Server (FMPS) i AEM Guides

Integreringen av AEM Guides med FrameMaker Publishing Server kan vara den bästa lösningen om du är ute efter högkvalitativ automatiserad publicering.\
Artikeln hjälper dig att konfigurera och köra FMPS med AEM stödlinjer.

## FMPS-kompatibilitet med AEM stödlinjer

- Kompatibilitet med 4.1-AEM: [4.1 kompatibilitetsmatris ](https://experienceleague.adobe.com/docs/experience-manager-guides-learn/tutorials/release-info/release-notes/on-prem-release-notes/release-notes-4.1.html?lang=en/#compatibility-matrix)
- Kompatibilitet med 4.0-AEM: [4.0 kompatibilitetsmatris](https://helpx.adobe.com/xml-documentation-for-experience-manager/release-note/release-notes-xml-documentation-solution-4-0.html/#Compatibility%20matrix)
- Senaste versionen: [Senaste versionsinformation](https://experienceleague.adobe.com/docs/experience-manager-guides-learn/tutorials/release-info/latest-release-info.html?lang=en)

## Installation

Se följande för AEM och installation och konfiguration av FMPS

### AEM stödlinjer

Installation och konfiguration, se: [ 4.1 installation och konfigurationer ](https://helpx.adobe.com/content/dam/help/en/xml-documentation-solution/4-1-2/Adobe-Experience-Manager-Guides_Installation-Configuration-Guide_EN.pdf)

### FMPS

För FMPS-installation kan du se [Länk till YouTube ](https://www.youtube.com/watch?v=2deelyM5VA8&amp;t) eller [Installation och konfiguration av FMPS ](https://help.adobe.com/en_US/framemaker/server/index.html#t=fmps-user-guide%2Finstall_config_fmps.html%23install_config_fmps&amp;rhtocid=_2)

## Nödvändiga konfigurationer

FrameMaker Publishing Server (FMPS) kan användas för att generera DITA-innehåll. FMPS stöder ett stort antal utdataformat. Ändra följande egenskaper för paketet&quot;com.adobe.fmdita.config.ConfigManager&quot; i webbkonsolen för att konfigurera AEM för att använda FMPS.

Öppna webbkonsolen genom att gå till http://\&lt;server name=&quot;&quot;>:\&lt;port>/system/console/configMgr.

**Konfigurationsegenskaper och deras beskrivning** [4.1 installation och konfiguration ](https://helpx.adobe.com/content/dam/help/en/xml-documentation-solution/4-1-2/Adobe-Experience-Manager-Guides_Installation-Configuration-Guide_EN.pdf#page=89)

## Kör test:

Med FMPS kan du automatiskt publicera **PDF, responsiv HTML5** och **Epub** för dina DITA- och FM-resurser.

Välj FrameMaker Publishing Server på menyn &quot;Generera PDF med&quot;.

Användaren kan ange &quot;settings File(.sts)&quot; och &quot;ditaval&quot;. Filtreringen görs med hjälp av diaval baserat på de villkor du anger.

- **Anger fil**: En fil med publiceringsinställningarna FrameMaker/FMPS som innehåller alla inställningar som du vill att FMPS ska använda vid publicering. Du kan till exempel skapa utdata med en anpassad mall, skapa märken och utfall (PDF) och skapa PDF med innehållsförteckning.
- **FMPS-förinställning:** Det är en fördefinierad kombination av fil för avvikelse och inställningar. I stället för att ge separata fil för redigering och inställningar kan användaren förskapa FMPS-förinställningar som kan återanvändas för publiceringsbehov.

**Obs!** Standardsysteminställningen används av FMPS för att publicera om du inte väljer någon av inställningarna eller FMPS-förinställningen.

Det är en konflikt om du väljer FMPS-förinställningen och även har angett anpassade inställningar eller en diavalfil från AEM. I det här fallet har FMPS-förinställningen företräde framför den anpassade inställnings- eller avstavningsfilen.

### Originalpublicering med FMPS:

Du kan publicera baslinjer som du redan skapat med FMPS2020.0.2 eller senare.

**Exempel på FMPS-inställningsfil (.sts-fil) för att komma igång:** [Exempel på FMPS-inställningsfil ](https://acrobat.adobe.com/link/track?uri=urn:aaid:scds:US:ef750752-7a7e-4e51-923e-6b7d9861ed54) (zippa upp den här filen)

## Vanliga frågor och felsökning:

- ### FMPS-publicering misslyckas med Timeout-undantag

>Kontrollera och öka värdet för FMPS-timeout (sekunder) i /system/console/configMgr/com.adobe.fmdita.config.ConfigManager

- ### Det gick inte att hämta FMPS-förinställningen i listrutan

>Kontrollera att du har skapat en fördefinierad FMPS-förinställning på servern och att anslutningsinställningarna är korrekta.

- ### Jag får Blank PDF när jag publicerar

>Om du använder UUID kontrollerar du att du har markerat Använd UUID-baserad referens i redigeringsinställningarna för FrameMaker och omvänt för icke-UID-AEM.

- ### Mina inställningar/ändringar tillämpas inte i det slutliga publicerade resultatet

>Kontrollera att du inte väljer FMPS-förinställningen och inställnings-/diavalfilen samtidigt. Använd FrameMaker för att kontrollera utdata manuellt.

- ### Baslinjen publiceras inte från FMPS

>FMPS2020.0.2 eller senare versioner är kompatibla med baslinjepublicering.
>Se till att baslinjen har skapats på rätt sätt. Gå till Map Dashboard— Topics - Download Map och välj Use Baseline.
- ### Publiceringsuppgifter från FMPS tar längre tid än andra motorer

>Vid publicering från FMPS är den idealiska fasta huvudtiden cirka 3-4 minuter. Om du tror att det är längre kontaktar du FMPS-administratören eller kontaktar supporten för Adobe.

## Andra resurser:

[FMPS - utbildning och support](https://helpx.adobe.com/support/framemaker-publishing-server.html)

[AEM Guides Learn and Support](https://helpx.adobe.com/in/support/xml-documentation-for-experience-manager.html)

[FrameMaker- och FMPS-community](https://community.adobe.com/t5/framemaker/ct-p/ct-framemaker?page=1&amp;sort=latest_replies&amp;lang=all&amp;tabid=all)

[AEM Guides Community](https://experienceleaguecommunities.adobe.com/t5/experience-manager-guides/ct-p/aem-xml-documentation)
