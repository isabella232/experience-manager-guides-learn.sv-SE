---
title: Versionsinformation för [!DNL AEM Guides], mars 2022-utgåvan
description: Marsutgåva av [!DNL Adobe Experience Manager Guides] as a Cloud Service
exl-id: 885edbb5-dfe4-4bdc-bb66-0df64addb094
source-git-commit: b5e64512956f0a7f33c2021bc431d69239f2a088
workflow-type: tm+mt
source-wordcount: '768'
ht-degree: 1%

---

# Marsutgåva av [!DNL Adobe Experience Manager Guides] as a Cloud Service

## Uppgradera till mars-utgåvan

Uppgradera din nuvarande [!DNL Adobe Experience Manager Guides] as a Cloud Service (kallas senare *[!DNL AEM Guides]as a Cloud Service*) genom att utföra följande steg:
1. Ta en titt på Cloud Servicens Git-kod och växla till den gren som är konfigurerad i Cloud Servicens pipeline för den miljö du vill uppgradera.
2. Uppdatera `<dox.version>` egenskap i `/dox/dox.installer/pom.xml` fil med dina Cloud Services Git-kod till 2022.3.123.
3. Genomför ändringarna och kör Cloud Servicens pipeline för att uppgradera till mars-versionen av [!DNL AEM Guides] as a Cloud Service.

## Kompatibilitetsmatris

I det här avsnittet visas kompatibilitetsmatrisen för de program som stöds av [!DNL AEM Guides] as a Cloud Service March 2022 release.

### FrameMaker och FrameMaker Publishing Server

| FMPS | FrameMaker |
| --- | --- |
| Inte kompatibel | 2020 uppdatering 4 och senare |
|  |  |


### Syrgasanslutning

| [!DNL AEM Guides] Cloud-utgåva | Syrgasanslutningsfönster | Syrgasanslutning Mac |
| --- | --- | --- |
| 2022.3.0 | 2.4.0 | 2.4.0 |
|  |  |  |

*Originalplan och villkor skapade i AEM stöds i FMPS-versioner från och med 2020.2.

## Nya funktioner och förbättringar

### Ny kontrollpanel för baslinje

[!DNL AEM Guides] as a Cloud Service March-versionen innehåller baslinjefunktionen som är integrerad i Web Editor. Nu kan du skapa baslinjer från Web Editor och använda dem för att publicera eller översätta ämnen från olika versioner.

Obs! Uppdatera den senaste versionen för uppgraderat system **ui_config.json** för mappprofil.

Använd den här funktionen om du vill skapa en baslinje med en specifik version av de ämnen som är tillgängliga ett visst datum och en viss tid. Du får även API-stöd för att skapa eller uppdatera en baslinje med en etikett som definierats för en ämnesversion.

![fliken hantera baslinje](assets/baseline-manage.png)

Du kan söka efter filer baserat på filnamn eller filplats. Du kan också filtrera ämnen som ska visas i redigeringsfönstret för baslinjen och sortera dem baserat på specifika kolumner.

![fliken hantera baslinje](assets/baseline-filter.png)

Prestandan för skapandet av baslinjen har förbättrats ytterligare. Processen att skapa baslinjer är asynkron, så du kan fortsätta redigera andra filer i Web Editor medan baslinjen skapas. Mer information finns i *Skapa och hantera baslinjer från Web Editor* i användarhandboken.

Obs! Fliken Baslinje på kartkontrollpanelen är dold som standard. Administratören kan aktivera fliken Baslinje på kartkontrollpanelen.

### Förbättrat uppdateringsbeteende för webbredigeraren

Följande förbättringar är nu tillgängliga vid uppdatering av webbläsaren i Web Editor:

* Nu har du stöd för att uppdatera webbläsaren medan du redigerar innehållet i webbredigeraren. Om du trycker på ikonen för uppdatering av webbläsaren när en eller flera filer med osparade ändringar öppnas för redigering, uppmanas du att spara filerna eller avbryta uppdateringsåtgärden.

* Även när du uppdaterar webbläsaren behålls vyerna från den vänstra panelen och den högra panelen.

* Det aktiva ämnet eller DITA-kartan öppnas på nytt i området för innehållsredigering.

### Förbättrad publicering

Publiceringsprocessen har förbättrats ytterligare i mars-versionen av [!DNL AEM Guides] as a Cloud Service:

* Baslinjer har använts för metadata AEM webbplatsens utdata. Du kan också bearbeta egenskaperna för en baslinjeversion som metadata. Om ingen baslinje har definierats bearbetas egenskaperna för den senaste versionen som metadata.

* The **Filnamn** och **Kommandoradsargument för DITA-OT** alternativ har lagts till för HTML 5, EPUB och anpassade förinställningar. Nu kan du ange filnamnet som du vill spara utdata med. Du kan också ange ytterligare argument som du vill att DITA-OT ska behandla när du genererar utdata.

## Åtgärdade problem

De buggar som har åtgärdats i olika områden listas nedan:

* Det går inte att lägga till förgrundselement, bakgrundselement i en bokmapp med hjälp av redigerarens redigeringsvy. (7652)
* Referensträdet bryts när ett ämne har tagits bort och en flyttningsåtgärd har utförts. (8804)
* Undantag tas emot när innehållet visas efter att en resurs har överförts. (3638)
* Ett fel inträffar när filer vars överordnade mapp har specialtecken i filnamnet öppnas i Syrgas (med **Redigera i syrgas** ). (8918)
* The **Sök i databas** går inte att hitta och markera DITA-kartan i XML-redigeraren. (8796)
* Filtreringen ger inte rätt resultat när flera attribut läggs till i innehållet i XML-redigeraren. (8795)
* Ett fel inträffar när en användare läggs till som administratör i mappprofilen när användar-ID:t är numeriskt. (8908)

## Kända fel

Adobe har identifierat följande kända problem i [!DNL AEM Guides] as a Cloud Service March release.

* Om du tar bort etiketter i direkta referenser tas även etiketterna bort från indirekta referenser.

* Det går inte att spegla den uppdaterade baslinjetiteln utan att uppdatera baslinjepanelen manuellt.

* Funktionen för förhandsgranskning av version på panelen Versionshistorik visar inte förhandsgranskningen av ett valt ämne.
