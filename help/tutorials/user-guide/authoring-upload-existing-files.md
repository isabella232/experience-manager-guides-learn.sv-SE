---
title: Överför filer
description: Lär dig hur du överför filer
exl-id: d6a73953-94dd-4fa5-b09c-5e4c77fead62
source-git-commit: 8073716bccacbe8d6a158b44d5106b083e3a5dcd
workflow-type: tm+mt
source-wordcount: '407'
ht-degree: 0%

---

# Överför filer {#id176FF000JUI}

Det är mest troligt att du har en databas med befintligt DITA-innehåll som du vill använda med AEM stödlinjer. För sådant befintligt innehåll kan du använda någon av följande metoder för att massöverföra ditt innehåll till AEM.

>[!IMPORTANT]
>
> Se [Lägga till digitala resurser i Adobe Experience Manager as a Cloud Service Assets](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/assets/manage/add-assets.html) om du vill ha mer information om de innehållsöverföringsmetoder som stöds i AEM.

## Användargränssnittet i Resurskonsolen

Du kan markera innehåll på skrivbordet och dra det AEM användargränssnittet \(webbläsare\) till målmappen. Mer information finns i [Överför resurser](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/assets/manage/add-assets.html#upload-assets) i AEM.

## AEM

Använd AEM datorprogram om du är kreatör och vill hantera mediefiler på din lokala dator. Du kan öppna och redigera dessa resurser med skrivbordsprogrammen. Du kan också underhålla versioner och dela filer med andra användare. Mer information finns i [AEM](https://experienceleague.adobe.com/docs/experience-manager-desktop-app/using/using.html).

## Massinhämtning av resurser

Om du har storskalig migrering och ibland massimporteringar använder du Resursimport för att överföra ditt innehåll. Med det här verktyget kan du överföra massinnehåll från datalager som stöds, som Azure eller S3. Mer information finns i [Massinhämtning av resurser](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/assets/manage/add-assets.html?lang=en#asset-bulk-ingestor).

## Använd FrameMaker för massöverföring

Adobe FrameMaker har en kraftfull AEM som gör det enkelt att ladda upp befintliga DITA-dokument och andra FrameMaker-dokument \(`.book` och `.fm`\) till AEM. Du kan använda olika funktioner för filöverföring, till exempel för att överföra en fil, överföra en hel mapp med eller utan beroenden \(som innehållsreferenser, korsreferenser och bilder\).

Mer information om hur du använder massöverföring i FrameMaker finns i avsnittet *Skapa en CRX-mapp och överför filer* i användarhandboken för FrameMaker.

## Felhantering vid överföring av innehåll {#id201MI0I04Y4}

Om det inte går att överföra en eller flera filer visas ett meddelande i slutet av överföringsprocessen med en lista över filer som inte kunde överföras:

![](images/uuid-files-failed-to-upload_cs.png){width="650" align="center"}

Mer information om hur de olika scenarierna för filöverföring visas i [Överför DITA-innehåll](authoring-file-management.md#).

Om du använder ett verktyg som AEM skrivbordsapp eller massinläsare för resurser, styrs åtgärden som ska utföras på en dubblettfil av en inställning på den AEM servern. Kontakta systemadministratören om du vill veta mer om den här konfigurationen.

**Överordnat ämne:**[ Hantera innehåll](authoring.md)
