---
title: Versionsinformation | Adobe Experience Manager Guides as a Cloud Service, aprilversion 2022
description: aprilversion av Adobe Experience Manager Guides as a Cloud Service
exl-id: c735ba24-a803-454b-8723-57dacf90061b
source-git-commit: b5e64512956f0a7f33c2021bc431d69239f2a088
workflow-type: tm+mt
source-wordcount: '799'
ht-degree: 2%

---

# aprilversion av Adobe Experience Manager Guides as a Cloud Service

## Uppgradera till aprilversionen

Uppgradera din nuvarande [!DNL Adobe Experience Manager Guides] as a Cloud Service (kallas senare *[!DNL AEM Guides]as a Cloud Service*) genom att utföra följande steg:
1. Ta en titt på Cloud Servicens Git-kod och växla till den gren som är konfigurerad i Cloud Servicens pipeline för den miljö du vill uppgradera.
2. Uppdatera `<dox.version>` egenskap i `/dox/dox.installer/pom.xml` fil med dina Cloud Services Git-kod till 2022.4.133.
3. Genomför ändringarna och kör Cloud Servicens pipeline för att uppgradera till aprilversionen av [!DNL AEM Guides] as a Cloud Service.

## Kompatibilitetsmatris

I det här avsnittet visas kompatibilitetsmatrisen för de program som stöds av [!DNL AEM Guides] as a Cloud Service aprilversion 2022.

### FrameMaker och FrameMaker Publishing Server

| FMPS | FrameMaker |
| --- | --- |
| Inte kompatibel | 2020 uppdatering 4 och senare |
|  |  |


### Syrgasanslutning

| AEM Guides Cloud Release | Syrgasanslutningsfönster | Syrgasanslutning Mac |
| --- | --- | --- |
| 2022.4.0 | 2.5.6 | 2.5.6 |
|  |  |  |

*Originalplan och villkor skapade i AEM stöds i FMPS-versioner från och med 2020.2.

## Nya funktioner och förbättringar

Många förbättringar och nya funktioner har lagts till i Web Editor:

### Förbättrad tangentupplösning

En DITA-innehållsnyckelreferens infogar en del av innehållet från ett ämne i ett annat. Den använder en nyckel för att hitta innehållet. De nyckelreferenser som är associerade med ett DITA-avsnitt måste lösas. Den markerade rotkartan har högsta prioritet för att lösa nyckelreferenser.

![dialogruta för användarinställningar](assets/user-preferences.png)

Nu löses nyckelreferenserna utifrån rotmappningen som angetts i följande prioritetsordning:

1. Användarinställningar
2. Kartvyn, panel
3. Mappprofil

Mer information finns i *Lös nyckelreferenser* i användarhandboken.

### Lägga till en anpassad panel i den vänstra panelen

Nu kan du lägga till en anpassad panel i den vänstra panelen i Web Editor. Du kan använda en anpassad panel för olika syften, som att ge hjälp eller utföra testningen för ett projekt. Om en anpassad panel har konfigurerats visas den också i listan med paneler i **Inställningar för Redigeraren**. Du kan växla om du vill visa eller dölja den anpassade panelen.

### Möjlighet att ändra dokumentstatus för ämnen i en DITA-karta

Nu kan du enkelt ändra dokumentstatus för valda ämnen i en DITA-karta. Du kan också öppna och redigera egenskaperna för markerade ämnen i en DITA-karta från **Fler alternativ** längst ned på panelen Kartvy.

![valda ämnesegenskaper](assets/map-view-properties.png)

### Versionsinformation som visas i förhandsgranskningsläget

Webbredigeraren hjälper dig att hantera dina versioner. Nu kan du även se versionen av det aktiva ämnet eller DITA-kartan i det övre högra hörnet av ämnesfliken i förhandsgranskningsläget för ett ämne.

![förhandsgranskningsversion](assets/preview-version.png)

## Åtgärdade problem

De buggar som har åtgärdats i olika områden listas nedan:

* Nya etiketter visas inte automatiskt i listrutan Lägg till/ta bort etikett, utan en uppdatering av baslinjen krävs. (9249)
* Det går inte att redigera baslinjetiteln om en baslinje har skapats med etikettvillkor. (9171)
* Publiceringsjobb som använder en baslinje fastnar i vänteläge om baslinjestatusen ändras till &quot;misslyckades&quot;. (9194)
* Om du tar bort etiketter i direkta referenser tas även etiketterna bort från indirekta referenser. (9257)
* Om du söker medan du skriver uppstår oönskade sökningar i databasvyn. (9307)
* Problem uppstår när ett nyckelord används i titeln för fliken. (9318)
* Baslinjen kan inte användas när en etikett med blanksteg läggs till. (9362)
* AEM visar inte ordlisteelement korrekt. (8936)
* Konsolfel inträffar när **Utdata** i Web Editor. (8715)
* Felmeddelandet som visas när en manuell posttyp publiceras via Salesforce är inte intuitivt. (8952)
* Validera med villkorsattribut öppnas inte direkt, utan användaren måste öppna filen igen för att kunna se valideringarna. (9300)
* Det går inte att ta bort metadata när en DITA-karta har publicerats med metadata.  (9178)
* Översättningspanelen visas även när DITA-kartan öppnas i kartredigeraren. (9053)
* Anpassad DTD som definieras av användaren har inte högre prioritet än standard-DITA DTD som är inbäddad i DITA-OT. (9104)
* I funktionen Native PDF misslyckas överföringen i mallarna för filer som inte är DITA eller bilder. (9070)
* Auktoriseringsmekanismen kör två frågor i stället för en, i vissa specialscenarier. (9221)
* Publicering av AEM webbplatsutdata misslyckas när anpassad DTD används. (9243)
* Fotnoter som kan användas som referenser rullar inte till fotnotsavsnittet i AEM. (9234)

## Kända fel

Adobe har identifierat följande kända problem i [!DNL AEM Guides] as a Cloud Service aprilversion.

* Webbredigeraren rapporterar inget fel när två eller flera baslinjer har skapats med samma namn, men det finns skillnader i mellanrum eller skiftläge. Till exempel&quot;adobe&quot; och&quot;Adobe&quot; eller&quot;Adobe&quot;.
* Syrgaskontakten låser sig regelbundet när du ofta loggar in eller loggar ut eller växlar mellan olika autentiseringstyper.
