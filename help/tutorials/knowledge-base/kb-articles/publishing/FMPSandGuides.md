---
source-git-commit: da88662ec770b12a25ba4afd876e6eeac793cfc5
workflow-type: tm+mt
source-wordcount: '661'
ht-degree: 0%

---


# FrameMaker Publishing Server (FMPS) och AEM

**AEM Guides-integreringen med FrameMaker Publishing Server skulle kunna vara en bra lösning om du ville ha högkvalitativ automatiserad publicering.\
Nedan finns en artikel som hjälper dig att konfigurera och köra FMPS med AEM stödlinjer.**

## Kompatibilitet mellan FMPS och AEM stödlinjer:

- Kompatibilitet med 4.1-AEM: [Länk](https://experienceleague.adobe.com/docs/experience-manager-guides-learn/tutorials/release-info/release-notes/on-prem-release-notes/release-notes-4.1.html?lang=en/#compatibility-matrix)

- Kompatibilitet med 4.0-AEM: [Länk](https://helpx.adobe.com/xml-documentation-for-experience-manager/release-note/release-notes-xml-documentation-solution-4-0.html/#Compatibility%20matrix)

- Framtida version: [Länk](https://experienceleague.adobe.com/docs/experience-manager-guides-learn/tutorials/release-info/latest-release-info.html?lang=en)

## Installation:

### AEM stödlinjer:

Installation och konfiguration hänvisar till: [Länk](https://helpx.adobe.com/content/dam/help/en/xml-documentation-solution/4-1-2/Adobe-Experience-Manager-Guides_Installation-Configuration-Guide_EN.pdf)

### FMPS:

För FMPS-installation kan du se [Videolänk](https://www.youtube.com/watch?v=2deelyM5VA8&amp;t) eller [Dokumentation](https://help.adobe.com/en_US/framemaker/server/index.html#t=fmps-user-guide%2Finstall_config_fmps.html%23install_config_fmps&amp;rhtocid=_2)

## Nödvändiga konfigurationer:

DITA-innehållet kan skrivas ut med FrameMaker Publishing Server (FMPS). Du kan skapa utdata i vilket som helst av de många format som FMPS stöder.
I webbkonsolen ändrar du följande egenskaper för paketet com.adobe.fmdita.config.ConfigManager för att konfigurera AEM stödlinjer så att de använder FMPS.

Öppna webbkonsolen genom att gå till http://\&lt;server name=&quot;&quot;>:\&lt;port>/system/console/configMgr .

**Konfigurationsegenskaper och dess beskrivning:** [Länk](https://helpx.adobe.com/content/dam/help/en/xml-documentation-solution/4-1-2/Adobe-Experience-Manager-Guides_Installation-Configuration-Guide_EN.pdf#page=89)

## Kör test:

Med FMPS kan du automatiskt publicera **PDF, responsiv HTML5** och **Epub** för dina DITA- och FM-resurser.

Välj FrameMaker Publishing Server på menyn &quot;Generera PDF med&quot;.

Användaren kan ange &quot;Settings File(.sts)&quot; och &quot;ditaval. Filtreringen görs med Ditaval baserat på de villkor du anger.

- **Anger fil**: FrameMaker /FMPS Publish-inställning som innehåller alla inställningar som du vill att FMPS ska använda vid publicering Till exempel: , Generera utdata med anpassad mall, Generera märken och utfall (PDF), Generera PDF med innehållsförteckning, index osv.
- **FMPS finns:** I fördefinierad kombination av Ditaval- och Settings-filen kan användaren skapa en FMPS-förinställning i stället för att ge en separat Ditaval- och inställningsfil som kan återanvändas för publiceringsbehov.

**Obs!**  Om du inte väljer någon av inställningarna eller FMPS-förinställningen publiceras FMPS med standardsysteminställningen.

Om du har valt FMPS-förinställning och även har angett Inställningar/Ditaval-fil från AEM hamnar detta i konflikt och FMPS-förinställningen ges företräde framför anpassade inställningar/Ditaval-filer.

### Originalpublicering med FMPS:

Du kan publicera baslinjer som du redan skapat med FMPS2020.0.2 eller senare.

**Exempelfil för FMPS-inställningar (.sts-fil) för att komma igång:** [Länk](https://acrobat.adobe.com/link/track?uri=urn:aaid:scds:US:ef750752-7a7e-4e51-923e-6b7d9861ed54) (zippa upp den här filen)

## Vanliga frågor och felsökning:

- ### FMPS-publicering misslyckas med Timeout-undantag

Kontrollera och öka värdet för FMPS-timeout (sekunder) i /system/console/configMgr/com.adobe.fmdita.config.ConfigManager

- ### Det gick inte att hämta FMPS-förinställningen i listrutan

Kontrollera att du har skapat en fördefinierad FMPS-förinställning på servern och att anslutningsinställningarna är korrekta.

- ### Jag håller på att bli tom PDF vid publiceringen.

Om du använder UUID ska du kontrollera att du har markerat &quot;Använd UUID-baserad referens&quot; i EditPreferences för FrameMaker och vice versa för icke-UID-AEM

- ### Mina inställningar/Ditaval tillämpas inte i det slutliga publicerade resultatet

Kontrollera att du inte markerar både Setting/Ditaval-fil och FMPS Preset parallellt.Kontrollera utdata manuellt med FrameMaker

- ### Baslinjen publiceras inte från FMPS

Originalpublicering är kompatibelt med FMPS2020.0.2 eller senare.\
Kontrollera att baslinjen är korrekt skapad genom att gå till Nedladdningskarta för panelavsnitt och välja &quot;Använd baslinje&quot;.

- ### Publiceringsuppgift från FMPS tar längre tid än andra motorer.

Det kommer att finnas ett idealiskt fast sidhuvud på ca. Endast 3-4 minuter vid publicering från FMPS än andra motorer. Om du tror att det är mer än så kan du kontakta FMPS-administratören eller kontakta Adobe Support.

## Andra resurser:

### [FMPS - utbildning och support](https://helpx.adobe.com/support/framemaker-publishing-server.html)

### [AEM Lär dig mer och support](https://helpx.adobe.com/in/support/xml-documentation-for-experience-manager.html)

### [FrameMaker- och FMPS-community](https://community.adobe.com/t5/framemaker/ct-p/ct-framemaker?page=1&amp;sort=latest_replies&amp;lang=all&amp;tabid=all)

### [Community för AEM Guides](https://experienceleaguecommunities.adobe.com/t5/experience-manager-guides/ct-p/aem-xml-documentation)
