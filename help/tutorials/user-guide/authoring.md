---
title: Hantera innehåll
description: Hantera innehåll och identifiera dina roller och behörigheter i AEM. Lär dig de viktigaste begreppen för innehållshantering och att arbeta med globala profiler eller profiler på mappnivå.
exl-id: d2fa31a7-a8ce-4d17-bd4e-0f51ea751dca
source-git-commit: 3cc7a9bf91881ed09173077be7d7fc7705295e4b
workflow-type: tm+mt
source-wordcount: '722'
ht-degree: 0%

---

# Hantera innehåll {#id164JBG0M0T1}

Innan du börjar med att skapa innehåll måste du bekanta dig med några grundläggande begrepp för innehållshantering i AEM. Börja sedan med att skapa olika användargrupper och ordna era resurser.

## Viktiga begrepp

Några viktiga begrepp inom innehållshantering i AEM är följande:

**Resurshantering**

AEM Guides använder AEM Digital Asset Management \(DAM\) för att hantera dina DITA-filer. Filerna som du överför eller checkar in i DAM lagras som digitala resurser. Du kan hantera och redigera dina resurser i AEM Assets. Mer information om resurshantering finns i [Hantera resurser](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/content/assets/manage/manage-digital-assets.html?lang=en).

**Länkhantering**

Flytta eller byt namn på filer eller ändra mappstrukturen i innehållsdatabasen, utan att oroa dig för brutna referenser. Alla referenser till och från det påverkade innehållet uppdateras automatiskt. Få varningar när du tar bort innehåll som refereras någon annanstans för att förhindra oavsiktliga avbrott.

**Hantera versioner**

AEM Guides ger versionshantering för digitala resurser. Du kan enkelt aktivera den här funktionen från ett valfritt DITA-redigeringsprogram. Låta skribenterna utföra standardversionskontrollfunktioner som in- och utcheckning.

Mer information om hur du skapar versioner eller återgår till en viss version finns i [Förgrena, återställ och efterföljande versionshantering](web-editor-preview-topics.md#id193PG0Y051X).

**Inbyggd DITA-hantering**

AEM stödlinjer bibehåller strukturen i dina DITA-filer, men AEM kan också hantera DITA internt med hjälp av elementmappning för att mappa DITA-elementen till AEM komponenter. Den inbyggda DITA-hanteringen används i funktioner som ämnesförhandsgranskning, AEM Sites-publicering och granskningsarbetsflöden.

## Identifiera din roll och dina behörigheter {#id181TF0K0MHT}

AEM innehåller tre färdiga grupper. Dessa grupper är: *Författare*, *Granskare* och *Utgivare*. Beroende på vilken grupp du är kopplad till har du behörighet att utföra specifika åtgärder enligt tabellen nedan. Publiceringsuppgifterna kan till exempel bara utföras av en utgivare, men inte av en författare eller granskare. På samma sätt kan en författare skapa ett nytt ämne, och en granskare kan bara granska ett ämne.

>[!TIP]
>
> Se *Behörigheter* i Best practices Guide för bästa praxis när det gäller att ange användarbehörigheter.

I följande tabell visas olika uppgifter och grupper som kan utföra dessa uppgifter:

| Uppgift | Författare | Granskare | Utgivare |
|----|-------|---------|----------|
| Skapa DITA-ämne | Ja |   | Ja |
| Skapa DITA-karta | Ja |   | Ja |
| Kartsamlingar | Ja |   | Ja |
| Skapa granskningsaktivitet | Ja |   | Ja |
| Granska ämne[1](#fntarg_1) | Ja | Ja | Ja |
| Nyckelupplösning | Ja |   | Ja |
| Checka ut/Checka in | Ja |   | Ja |
| Redigera ämne | Ja |   | Ja |
| Flytta ämne | Ja |   | Ja |
| Redigera ämnesegenskaper | Ja |   | Ja |
| Kopiera | Ja |   | Ja |
| Ta bort | Ja |   | Ja |
| Dela | Ja |   | Ja |
| **Dokumenttillstånd** |
| Skapa/redigera dokumenttillståndsprofil |   |   | Ja |
| Ändra dokumentläge[2](#fntarg_2) | Ja | Ja | Ja |
| **Tillgängliga funktioner i DITA-kartkonsolen \(fliken Utdatainställningar\)** |
| Generera |   |   | Ja |
| Redigera |   |   | Ja |
| Duplicera |   |   | Ja |
| Skapa |   |   | Ja |
| Ta bort förinställning |   |   | Ja |
| **Tillgängliga funktioner i DITA-kartkonsolen \(fliken Utdata\)** |
| Visa genererade utdata | Ja |   | Ja |
| **Tillgängliga funktioner i DITA-kartkonsolen \(fliken Ämnen\)** |
| Skapa granskningsaktivitet | Ja |   | Ja |
| Redigera | Ja |   | Ja |
| **Tillgängliga funktioner i DITA-kartkonsolen \(fliken Baslinjer\)** |
| Skapa |   |   | Ja |
| Redigera |   |   | Ja |
| Duplicera |   |   | Ja |
| Ta bort |   |   | Ja |
| DITA map console \(Reports tab\) | Ja |   | Ja |
| **Tillgängliga funktioner i DITA-kartkonsolen \(Villkorsförinställningar\)** |
| Skapa/redigera villkorsförinställning |   |   | Ja |

[1](#fnsrc_1) If *Författare* och *Utgivare* är inbjudna till en granskning.

[2](#fnsrc_2) Beroende på vilka rättigheter användaren har i dokumentets tillståndsprofil.

## Krav för innehållsutveckling

**Arbeta med globala profiler eller profiler på mappnivå**

I ett företag kan olika grupper eller produkter använda olika redigeringsmallar, utdatamallar, villkorsattributprofiler \(eller ämnesscheman\) och Web Editor-konfigurationer. Om du konfigurerar dessa endast på Enterprise \(eller global\)-nivå kan det vara svårt för skribenterna eftersom de kommer att se mallar eller profiler som inte är relevanta för dem.

Med AEM Guides kan du konfigurera redigeringsmallar, utdatamallar, villkorsattribut och Web Editor-konfigurationer på global nivå samt på mappnivå. På så sätt kan du dela upp konfigurationerna för olika avdelningar eller produkter i företaget.

Du kan även delegera mappspecifika konfigurationer till en avdelning eller produktadministratörer för att decentralisera administrationen.

Mer information om hur du konfigurerar globala profiler och profiler på mappnivå finns i *Konfigurera globala profiler eller profiler på mappnivå* i Installera och konfigurera Adobe Experience Manager Guides as a Cloud Service.
