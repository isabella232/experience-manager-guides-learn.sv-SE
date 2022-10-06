---
title: AEM
description: Senaste AEM och AEM
exl-id: 780697a9-bdc6-40c2-b258-64639fe30f88
source-git-commit: 58e8594819880c15c0fef9167f39798d3ea040d9
workflow-type: tm+mt
source-wordcount: '842'
ht-degree: 0%

---

# [!DNL AEM Guides] Utgåvor

[!DNL Adobe Experience Manager Guides] är ett program som distribueras till AEM. Det är en kraftfull, komponentbaserad innehållshanteringslösning (CCMS) som möjliggör inbyggt DITA-stöd i Adobe Experience Manager och ger möjlighet att AEM hantera DITA-baserad framtagning och leverans av innehåll.

## UUID kontra UUID förklaras

[!DNL AEM Guides] paket är tillgängliga i två lägen - UUID-bygge och icke-UID-byggen.

Kunderna måste välja mellan UUID och icke UID-läge vid första konfigurationen (kontakta din Customer Success Manager för att få hjälp att fatta beslut baserat på din användning).

Vid uppgradering från en version av [!DNL AEM Guides] till en nyare version måste kunderna se till att de väljer samma läge (UUID/icke-UID) för att matcha det befintliga läget. En icke-UID-version får inte uppgraderas direkt till en UUID-version. Att gå från icke-UID-bygge till UUID-bygge kräver innehållsmigrering.

**Uppgraderar byggen**

När du uppgraderar från en äldre version till en nyare version av [!DNL AEM Guides]kan du behöva köra vissa migreringsskript. Se Versionsinformation och versionsspecifik dokumentation för uppgraderingsinstruktioner.

Alla uppgraderingssökvägar stöds inte direkt. Till exempel går det bara att uppgradera direkt till version 4.0 från version 3.8. Om du har en tidigare version än 3.8 hittar du uppgraderingsinstruktioner i den versionsspecifika dokumentationen [Hjälparkiv](https://helpx.adobe.com/xml-documentation-for-experience-manager/archive.html).
Kontakta er Customer Success Manager för att validera uppgraderingsprocessen.

**[!DNL AEM Guides]Bygger**

Följande lista innehåller de senaste [!DNL AEM Guides] paket tillgängliga för installation på AMS eller On-Prem, motsvarande AEM (krav), nedladdningslänkar till paket och annan användbar information. Vi rekommenderar att du endast använder den senaste versionen av [!DNL AEM Guides]. Om du av någon anledning behöver tillgång till äldre versioner kan du ansluta till ditt kontos Customer Success Manager.

>[!NOTE]
>
>Kontakta din Customer Success Manager för att få tillgång till [!DNL AEM Guides] bygger för AEM as a Cloud Service.

| [!DNL AEM Guides] Frigör | Versionsinformation | AEM | Skapa nedladdningslänkar |
|---|---|---|---|
| **AEM 4.1** | [4.1.x Versionsinformation](https://experienceleague.adobe.com/docs/experience-manager-guides-learn/tutorials/release-info/release-notes/on-prem-release-notes/release-notes-4.1.html) | **Ej UUID och UUID 4.1.2**<br><br> AEM 6.5 SP13, SP12, SP11 eller SP10 <br>Java: 11 eller 8 <br><br>**Ej UUID och UUID 4.1**<br><br> AEM 6.5 SP13, SP12, SP11 eller SP10 | **Ej UID**: <br> **AEM 6.5** <br>[4.1](https://experience.adobe.com/#/downloads/content/software-distribution/en/aem.html?package=%2Fcontent%2Fsoftware-distribution%2Fen%2Fdetails.html%2Fcontent%2Fdam%2Faem%2Fpublic%2Faemdox%2F4-1%2F4-1-non-uuid%2Fcom.adobe.fmdita-6.5-4.1.159.zip), <br>[4.1.2](https://experience.adobe.com/#/downloads/content/software-distribution/en/aem.html?package=%2Fcontent%2Fsoftware-distribution%2Fen%2Fdetails.html%2Fcontent%2Fdam%2Faem%2Fpublic%2Faemdox%2F4-1-2%2F4-1-2-non-uuid%2Fcom.adobe.fmdita-6.5-sp-4.1.2.11.zip)<br><br> **UUID** <br>**AEM 6.5**  <br>[4.1](https://experience.adobe.com/#/downloads/content/software-distribution/en/aem.html?package=%2Fcontent%2Fsoftware-distribution%2Fen%2Fdetails.html%2Fcontent%2Fdam%2Faem%2Fpublic%2Faemdox%2F4-1%2F4-1-uuid%2Fcom.adobe.fmdita-6.5-uuid-4.1.159.zip) <br>[4.1.2](https://experience.adobe.com/#/downloads/content/software-distribution/en/aem.html?package=%2Fcontent%2Fsoftware-distribution%2Fen%2Fdetails.html%2Fcontent%2Fdam%2Faem%2Fpublic%2Faemdox%2F4-1-2%2F4-1-2-uuid%2Fcom.adobe.fmdita.uuid-6.5-sp-4.1.2.11.zip) |
| **AEM Guides 4.0** | [4.0.x Versionsinformation](https://helpx.adobe.com/xml-documentation-for-experience-manager/release-note/release-notes-xml-documentation-solution-4-0.html) | **Ej UUID och UUID 4.0.3**<br> AEM 6.5 SP12, SP11, SP10 eller SP9 <br>Java: 11 eller 8 <br><br> <br>**Ej UUID och UUID 4.0.2** <br> AEM 6.5 SP12, SP11, SP10 eller SP9 <br>Java: 11 eller 8 <br><br> **Ej UUID och UUID 4.0** <br> AEM 6.5 SP11, SP10 eller SP9 | **Ej UID**: <br> **AEM 6.5** <br>[4.0.3](https://experience.adobe.com/#/downloads/content/software-distribution/en/aem.html?package=%2Fcontent%2Fsoftware-distribution%2Fen%2Fdetails.html%2Fcontent%2Fdam%2Faem%2Fpublic%2Faemdox%2F4-0-3%2F4-0-2-non-uuid%2Fcom.adobe.fmdita-6.5-hotfix-4.0.3.1.zip)<br>[4.0.2](https://experience.adobe.com/#/downloads/content/software-distribution/en/aem.html?package=%2Fcontent%2Fsoftware-distribution%2Fen%2Fdetails.html%2Fcontent%2Fdam%2Faem%2Fpublic%2Faemdox%2F4-0-2%2F4-0-2-non-uuid%2Fcom.adobe.fmdita-6.5-sp-4.0.2.10.zip)  <br> [4.0](https://experience.adobe.com/#/downloads/content/software-distribution/en/aem.html?package=/content/software-distribution/en/details.html/content/dam/aem/public/aemdox/4-0/4-0-non-uuid/com.adobe.fmdita-6.5-4.0.70.zip)  <br><br> **UUID** <br>**AEM 6.5**  <br>[4.0.3](https://experience.adobe.com/#/downloads/content/software-distribution/en/aem.html?package=%2Fcontent%2Fsoftware-distribution%2Fen%2Fdetails.html%2Fcontent%2Fdam%2Faem%2Fpublic%2Faemdox%2F4-0-3%2F4-0-3-uuid%2Fcom.adobe.fmdita.uuid-6.5-hotfix-4.0.3.1.zip) <br>[4.0.2](https://experience.adobe.com/#/downloads/content/software-distribution/en/aem.html?package=%2Fcontent%2Fsoftware-distribution%2Fen%2Fdetails.html%2Fcontent%2Fdam%2Faem%2Fpublic%2Faemdox%2F4-0-2%2F4-0-2-uuid%2Fcom.adobe.fmdita.uuid-6.5-sp-4.0.2.10.zip)<br> [4.0](https://experience.adobe.com/#/downloads/content/software-distribution/en/aem.html?package=/content/software-distribution/en/details.html/content/dam/aem/public/aemdox/4-0/4-0-uuid/com.adobe.fmdita-6.5-uuid-4.0.70.zip) |
| **AEM 3.8.5** <br> 3.8.5 är en SP-version utöver 3.8. <br>3.8-versionen får inte installeras fristående eftersom 3.8.5 SP innehåller en viktig korrigering. <br>Kunden måste först installera 3.8 och sedan SP 3.8.5. | [Versionsinformation om 3.8.x](https://helpx.adobe.com/xml-documentation-for-experience-manager/release-note/release-notes-xml-documentation-solution-3-8.html) | **Ej UID** <br> AEM 6.5 SP9 eller SP8 <br> AEM 6.4 SP8 <br> AEM 6.3 SP3 <br><br> **UUID** <br> AEM 6.5 SP9 eller SP8 | **Ej UID**: <br> **AEM 6.5** <br> [3.8.5 SP](https://experience.adobe.com/#/downloads/content/software-distribution/en/aem.html?package=/content/software-distribution/en/details.html/content/dam/aem/public/aemdox/3-8-5/com.adobe.fmdita-6.5-hotfix-3.8.5.2.zip) <br>[3.8](https://experience.adobe.com/#/downloads/content/software-distribution/en/aem.html?package=/content/software-distribution/en/details.html/content/dam/aem/public/aemdox/3-8/com.adobe.fmdita-6.5-3.8.166.zip)<br> **AEM 6.4** <br> [3.8.5 SP](https://experience.adobe.com/#/downloads/content/software-distribution/en/aem.html?package=/content/software-distribution/en/details.html/content/dam/aem/public/aemdox/3-8-5/com.adobe.fmdita-6.4-hotfix-3.8.5.1.zip) <br>[3.8](https://experience.adobe.com/#/downloads/content/software-distribution/en/aem.html?package=/content/software-distribution/en/details.html/content/dam/aem/public/aemdox/3-8/com.adobe.fmdita-6.4-3.8.166.zip) <br> **AEM 6.3** <br> [3.8.5 SP](https://experience.adobe.com/#/downloads/content/software-distribution/en/aem.html?package=/content/software-distribution/en/details.html/content/dam/aem/public/aemdox/3-8-5/com.adobe.fmdita-6.3-hotfix-3.8.5.1.zip) <br>[3.8](https://experience.adobe.com/#/downloads/content/software-distribution/en/aem.html?package=/content/software-distribution/en/details.html/content/dam/aem/public/aemdox/3-8/com.adobe.fmdita-6.3-3.8.166.zip) <br><br> **UUID** <br>**AEM 6.5** <br> [3.8.5 SP](https://experience.adobe.com/#/downloads/content/software-distribution/en/aem.html?package=/content/software-distribution/en/details.html/content/dam/aem/public/aemdox/3-8-5uuid/com.adobe.fmdita.uuid-6.5-hotfix-3.8.5.2.zip) <br> [3.8](https://experience.adobe.com/#/downloads/content/software-distribution/en/aem.html?package=/content/software-distribution/en/details.html/content/dam/aem/public/aemdox/3-8uuid/com.adobe.fmdita.uuid-6.5-3.8.168.zip) |
