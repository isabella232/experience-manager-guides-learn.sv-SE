---
title: AEM
description: Senaste AEM och AEM
exl-id: 780697a9-bdc6-40c2-b258-64639fe30f88
source-git-commit: f836ad2178524b1ddfb89fdfa728a8b06cb02c2c
workflow-type: tm+mt
source-wordcount: '1188'
ht-degree: 0%

---

# [!DNL AEM Guides] Utgåvor

[!DNL Adobe Experience Manager Guides] är ett program som distribueras till AEM. Det är en kraftfull, komponentbaserad innehållshanteringslösning (CCMS) som möjliggör inbyggt DITA-stöd i Adobe Experience Manager och ger möjlighet att AEM hantera DITA-baserad framtagning och leverans av innehåll.

Paket med AEM stödlinjer är tillgängliga i två varianter - UUID-bygge och icke-UID-byggen.

## UUID- och icke-UUID-byggen

De viktigaste skillnaderna mellan UUID- och icke-UID-byggen är följande:

|  | Icke-UID-bygge | UUID-bygge |
|---|---|---|
| **Identifiering av tillgångar** | Alla resurser identifieras med hjälp av sökvägen för resursen i databasen. | Alla resurser identifieras med sitt UUID (unikt ID som genereras av systemet när resursen först överfördes). |
| **Referensskapande** | Alla innehållsreferenser skapas baserat på deras sökvägar. | Alla innehållsreferenser skapas baserat på deras UUID. |

### Fördelar med UUID-bygge

* UUID-installationen har högre prestanda:
   * Referenser är banoberoende: Referenshanteringssystemet är medvetet om länkarna eftersom referenserna skapas baserat på UUID:n och inte sökvägarna.
   * Flyttnings-/uppdateringsåtgärderna är effektiva: UUID:n förblir desamma även om resurserna flyttas till en annan sökväg i databasen. Ingen bearbetning krävs för att korrigera referenserna mellan resurserna vid flytt/uppdatering.
* UUID-bygget ser framåt, eftersom vi även använder det här ramverket för molnkonfiguration av AEM.


### Välj mellan de två byggen

* Om du är ny kund rekommenderar vi att du använder UUID-bygge.
* Om du är en befintlig kund kan du välja att gå över till UUID-bygge eftersom migreringen från icke-UID till UUID nu är möjlig. Mer information finns i *Migrering av icke-UID till UUID-innehåll* i **Installera och konfigurera Adobe Experience Manager Guides.**

>[!NOTE]
>
>* Kunderna måste välja mellan UUID- och icke-UID-läge vid den första konfigurationen (om du behöver hjälp, kontakta Customer Success Manager för att få hjälp med att fatta beslut baserat på din användning).
>* När man uppgraderar från en version av AEM Guides till en nyare version måste man se till att man väljer samma läge (UUID/icke-UID) för att matcha det befintliga läget. En icke-UID-build ska inte uppgraderas direkt till en UUID-build. Att gå från icke-UID-bygge till UUID-bygge kräver innehållsmigrering.


**Uppgraderar byggen**

När du uppgraderar från en äldre version till en nyare version av [!DNL AEM Guides]kan du behöva köra migreringsskript. Se Versionsinformation och versionsspecifik dokumentation för uppgraderingsinstruktioner.

Alla uppgraderingssökvägar stöds inte direkt. Till exempel går det bara att uppgradera direkt till version 4.0 från version 3.8. Om du har en tidigare version än 3.8 hittar du uppgraderingsinstruktioner i den versionsspecifika dokumentationen [Hjälparkiv](https://helpx.adobe.com/xml-documentation-for-experience-manager/archive.html).
Kontakta er Customer Success Manager för att validera uppgraderingsprocessen.

**[!DNL AEM Guides]Bygger**

Följande lista innehåller de senaste [!DNL AEM Guides] paket tillgängliga för installation på AMS eller On-Prem, motsvarande AEM (krav), nedladdningslänkar till paket och annan användbar information. Vi rekommenderar att du endast använder den senaste versionen av [!DNL AEM Guides]. Om du av någon anledning behöver tillgång till äldre versioner kan du ansluta till ditt kontos Customer Success Manager.

>[!NOTE]
>
>Kontakta din Customer Success Manager för att få tillgång till [!DNL AEM Guides] bygger för AEM as a Cloud Service.

| [!DNL AEM Guides] Frigör | Versionsinformation | AEM | Skapa nedladdningslänkar |
|---|---|---|---|
| **AEM 4.2** | [4.2 Versionsinformation](https://experienceleague.adobe.com/docs/experience-manager-guides-learn/tutorials/release-info/release-notes/on-prem-release-notes/release-notes-4.2.html) | **Ej UUID och UUID 4.2**<br><br> AEM 6.5 SP15, SP14, SP13 eller SP12 <br><br>Java: 11 eller 8<br><br> | **Ej UID**: <br> **AEM 6.5** <br>[4.2](https://experience.adobe.com/#/downloads/content/software-distribution/en/aem.html?package=%2Fcontent%2Fsoftware-distribution%2Fen%2Fdetails.html%2Fcontent%2Fdam%2Faem%2Fpublic%2Faemdox%2F4-2%2F4-2-non-uuid%2Fcom.adobe.fmdita-6.5-4.2.229.zip)<br><br> **UUID** <br>**AEM 6.5** <br>[4.2](https://experience.adobe.com/#/downloads/content/software-distribution/en/aem.html?package=%2Fcontent%2Fsoftware-distribution%2Fen%2Fdetails.html%2Fcontent%2Fdam%2Faem%2Fpublic%2Faemdox%2F4-2%2F4-2-uuid%2Fcom.adobe.fmdita-6.5-uuid-4.2.229.zip)<br> |
| **AEM 4.1** | [4.1.x Versionsinformation](https://experienceleague.adobe.com/docs/experience-manager-guides-learn/tutorials/release-info/release-notes/on-prem-release-notes/release-notes-4.1.html) | **Ej UUID och UUID 4.1.2**<br><br> AEM 6.5 SP13, SP12, SP11 eller SP10 <br>Java: 11 eller 8 <br><br>**Ej UUID och UUID 4.1**<br><br> AEM 6.5 SP13, SP12, SP11 eller SP10 | **Ej UID**: <br> **AEM 6.5** <br>[4.1](https://experience.adobe.com/#/downloads/content/software-distribution/en/aem.html?package=%2Fcontent%2Fsoftware-distribution%2Fen%2Fdetails.html%2Fcontent%2Fdam%2Faem%2Fpublic%2Faemdox%2F4-1%2F4-1-non-uuid%2Fcom.adobe.fmdita-6.5-4.1.159.zip)<br>[4.1.2](https://experience.adobe.com/#/downloads/content/software-distribution/en/aem.html?package=%2Fcontent%2Fsoftware-distribution%2Fen%2Fdetails.html%2Fcontent%2Fdam%2Faem%2Fpublic%2Faemdox%2F4-1-2%2F4-1-2-non-uuid%2Fcom.adobe.fmdita-6.5-sp-4.1.2.11.zip)<br>[4.1.3](https://experience.adobe.com/#/downloads/content/software-distribution/en/aem.html?package=%2Fcontent%2Fsoftware-distribution%2Fen%2Fdetails.html%2Fcontent%2Fdam%2Faem%2Fpublic%2Faemdox%2F4-1-3%2F4-1-3-non-uuid%2Fcom.adobe.fmdita-6.5-sp-4.1.3.2.zip)<br><br> **UUID** <br>**AEM 6.5** <br>[4.1](https://experience.adobe.com/#/downloads/content/software-distribution/en/aem.html?package=%2Fcontent%2Fsoftware-distribution%2Fen%2Fdetails.html%2Fcontent%2Fdam%2Faem%2Fpublic%2Faemdox%2F4-1%2F4-1-uuid%2Fcom.adobe.fmdita-6.5-uuid-4.1.159.zip)<br>[4.1.2](https://experience.adobe.com/#/downloads/content/software-distribution/en/aem.html?package=%2Fcontent%2Fsoftware-distribution%2Fen%2Fdetails.html%2Fcontent%2Fdam%2Faem%2Fpublic%2Faemdox%2F4-1-2%2F4-1-2-uuid%2Fcom.adobe.fmdita.uuid-6.5-sp-4.1.2.11.zip)<br>[4.1.3](https://experience.adobe.com/#/downloads/content/software-distribution/en/aem.html?package=%2Fcontent%2Fsoftware-distribution%2Fen%2Fdetails.html%2Fcontent%2Fdam%2Faem%2Fpublic%2Faemdox%2F4-1-3%2F4-1-3-uuid%2Fcom.adobe.fmdita.uuid-6.5-sp-4.1.3.2.zip) |
| **AEM Guides 4.0** | [4.0.x Versionsinformation](https://helpx.adobe.com/xml-documentation-for-experience-manager/release-note/release-notes-xml-documentation-solution-4-0.html) | **Ej UUID och UUID 4.0.3**<br> AEM 6.5 SP12, SP11, SP10 eller SP9 <br>Java: 11 eller 8 <br><br> <br>**Ej UUID och UUID 4.0.2** <br> AEM 6.5 SP12, SP11, SP10 eller SP9 <br>Java: 11 eller 8 <br><br> **Ej UUID och UUID 4.0** <br> AEM 6.5 SP11, SP10 eller SP9 | **Ej UID**: <br> **AEM 6.5** <br>[4.0.3](https://experience.adobe.com/#/downloads/content/software-distribution/en/aem.html?package=%2Fcontent%2Fsoftware-distribution%2Fen%2Fdetails.html%2Fcontent%2Fdam%2Faem%2Fpublic%2Faemdox%2F4-0-3%2F4-0-2-non-uuid%2Fcom.adobe.fmdita-6.5-hotfix-4.0.3.1.zip)<br>[4.0.2](https://experience.adobe.com/#/downloads/content/software-distribution/en/aem.html?package=%2Fcontent%2Fsoftware-distribution%2Fen%2Fdetails.html%2Fcontent%2Fdam%2Faem%2Fpublic%2Faemdox%2F4-0-2%2F4-0-2-non-uuid%2Fcom.adobe.fmdita-6.5-sp-4.0.2.10.zip)  <br> [4.0](https://experience.adobe.com/#/downloads/content/software-distribution/en/aem.html?package=/content/software-distribution/en/details.html/content/dam/aem/public/aemdox/4-0/4-0-non-uuid/com.adobe.fmdita-6.5-4.0.70.zip)  <br><br> **UUID** <br>**AEM 6.5**  <br>[4.0.3](https://experience.adobe.com/#/downloads/content/software-distribution/en/aem.html?package=%2Fcontent%2Fsoftware-distribution%2Fen%2Fdetails.html%2Fcontent%2Fdam%2Faem%2Fpublic%2Faemdox%2F4-0-3%2F4-0-3-uuid%2Fcom.adobe.fmdita.uuid-6.5-hotfix-4.0.3.1.zip) <br>[4.0.2](https://experience.adobe.com/#/downloads/content/software-distribution/en/aem.html?package=%2Fcontent%2Fsoftware-distribution%2Fen%2Fdetails.html%2Fcontent%2Fdam%2Faem%2Fpublic%2Faemdox%2F4-0-2%2F4-0-2-uuid%2Fcom.adobe.fmdita.uuid-6.5-sp-4.0.2.10.zip)<br> [4.0](https://experience.adobe.com/#/downloads/content/software-distribution/en/aem.html?package=/content/software-distribution/en/details.html/content/dam/aem/public/aemdox/4-0/4-0-uuid/com.adobe.fmdita-6.5-uuid-4.0.70.zip) |
| **AEM 3.8.5** <br> 3.8.5 är en SP-version utöver 3.8. <br>3.8-versionen får inte installeras fristående eftersom 3.8.5 SP innehåller en viktig korrigering. <br>Kunden måste först installera 3.8 och sedan SP 3.8.5. | [Versionsinformation om 3.8.x](https://helpx.adobe.com/xml-documentation-for-experience-manager/release-note/release-notes-xml-documentation-solution-3-8.html) | **Ej UID** <br> AEM 6.5 SP9 eller SP8 <br> AEM 6.4 SP8 <br> AEM 6.3 SP3 <br><br> **UUID** <br> AEM 6.5 SP9 eller SP8 | **Ej UID**: <br> **AEM 6.5** <br> [3.8.5 SP](https://experience.adobe.com/#/downloads/content/software-distribution/en/aem.html?package=/content/software-distribution/en/details.html/content/dam/aem/public/aemdox/3-8-5/com.adobe.fmdita-6.5-hotfix-3.8.5.2.zip) <br>[3.8](https://experience.adobe.com/#/downloads/content/software-distribution/en/aem.html?package=/content/software-distribution/en/details.html/content/dam/aem/public/aemdox/3-8/com.adobe.fmdita-6.5-3.8.166.zip)<br> **AEM 6.4** <br> [3.8.5 SP](https://experience.adobe.com/#/downloads/content/software-distribution/en/aem.html?package=/content/software-distribution/en/details.html/content/dam/aem/public/aemdox/3-8-5/com.adobe.fmdita-6.4-hotfix-3.8.5.1.zip) <br>[3.8](https://experience.adobe.com/#/downloads/content/software-distribution/en/aem.html?package=/content/software-distribution/en/details.html/content/dam/aem/public/aemdox/3-8/com.adobe.fmdita-6.4-3.8.166.zip) <br> **AEM 6.3** <br> [3.8.5 SP](https://experience.adobe.com/#/downloads/content/software-distribution/en/aem.html?package=/content/software-distribution/en/details.html/content/dam/aem/public/aemdox/3-8-5/com.adobe.fmdita-6.3-hotfix-3.8.5.1.zip) <br>[3.8](https://experience.adobe.com/#/downloads/content/software-distribution/en/aem.html?package=/content/software-distribution/en/details.html/content/dam/aem/public/aemdox/3-8/com.adobe.fmdita-6.3-3.8.166.zip) <br><br> **UUID** <br>**AEM 6.5** <br> [3.8.5 SP](https://experience.adobe.com/#/downloads/content/software-distribution/en/aem.html?package=/content/software-distribution/en/details.html/content/dam/aem/public/aemdox/3-8-5uuid/com.adobe.fmdita.uuid-6.5-hotfix-3.8.5.2.zip) <br> [3.8](https://experience.adobe.com/#/downloads/content/software-distribution/en/aem.html?package=/content/software-distribution/en/details.html/content/dam/aem/public/aemdox/3-8uuid/com.adobe.fmdita.uuid-6.5-3.8.168.zip) |
