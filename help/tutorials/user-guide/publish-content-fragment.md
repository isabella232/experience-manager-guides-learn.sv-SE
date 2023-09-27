---
title: Publicera ett ämne till ett innehållsfragment
description: Publicera ett ämne eller elementen i ett ämne till ett innehållsfragment i AEM.  Lär dig hur du visar innehållsfragment för ett ämne och publicerar dem på nytt.
source-git-commit: 6143bdcb4c8a9e1f35ea752cf1be142ab98a716b
workflow-type: tm+mt
source-wordcount: '613'
ht-degree: 0%

---


# Publicera till ett innehållsfragment

Innehållsfragment är separata innehållsdelar i AEM. De är strukturerade innehåll baserat på en innehållsmodell. Innehållsfragment är rent innehåll utan design- eller layoutinformation. De kan redigeras och hanteras oberoende av de kanaler som AEM stöder. Innehållsfragment är modulära, där innehållet delas upp i mindre komponenter.

Med AEM Guides kan du publicera ett ämne eller elementen i ett ämne till ett innehållsfragment. Du kan skapa en JSON-baserad mappning mellan ett ämne och en innehållsfragmentmodell. Använd den här mappningen för att publicera ett ämne eller elementen i ett ämne till ett innehållsfragment. Du kan sedan använda innehållsfragment på valfri AEM eller extrahera informationen via API:er som stöds av innehållsfragment.


Så här skapar du ett innehållsfragment:

1. Skapa en [innehållsfragmentmodell](https://experienceleague.adobe.com/docs/experience-manager-65/assets/content-fragments/content-fragments-models.html?lang=en) i AEM Assets.
1. Skapa en mapp där du vill spara de innehållsfragment som du skapar baserat på innehållsfragmentmodellen. Exempel:&quot;stock-content-fragments&quot;.
1. Redigera mappens egenskaper (till exempel&quot;stock-content-fragments&quot;) och lägg till sökvägen till mappen, som innehåller innehållsfragmentmodellen i molnkonfigurationen.
Lägg till exempel `/conf/we-retail` i molnkonfigurationen. Den här konfigurationen kopplar alla innehållsfragmentmodeller till mappen.\
   ![lägg till information om molnkonfiguration i mappegenskaperna](images/fragment-folder-cloud-configuration.png){width="650" align="left"}
   *Lägg till molnkonfigurationen i mappegenskaperna för att ansluta den till fragmentmodellerna.*
1. Välj det ämne som du vill publicera i **Databasvy**.
1. Från **Alternativ** meny, välja **Publicera som** > **Innehållsfragment**.
1. I **Publicera som innehållsfragment** fyller du i följande uppgifter:
   ![Lägg till fragmentmodellen och mappningsinformationen i dialogrutan Publicera som innehållsfragment](images/content-fragment-publish.png){width="500" align="left"}
   *Lägg till information om sökväg, modell och mappning för att publicera ett ämne eller dess element som ett innehållsfragment. Du kan skriva över ett befintligt innehållsfragment.*

   * **Bana**: Bläddra och välj sökvägen till mappen där du vill publicera innehållsfragmentet. Du kan också välja ett befintligt innehållsfragment och publicera det.
   * **Titel**: Ange innehållsfragmentets titel.
   * **Namn**: Ange namnet på innehållsfragmentet.
   * **Modell**: Välj den innehållsfragmentmodell som du vill använda för att skapa ditt innehållsfragment. Modellerna hämtas från den mapp som du har konfigurerat i molntjänsterna.
   * **Mappning**: Välj en mappning i listrutan. Den väljer mappningarna från *contentFragmentMapping.json* -fil.



     Beroende på din konfiguration kan administratören lägga till mappningarna i *contentFragmentMapping.json* -fil.

     <details>
        <summary>Cloud Services</summary>

     Läs mer om hur [skapa en mappning mellan ett ämne och ett innehållsfragment](../cs-install-guide/conf-content-fragment-mapping-cs.md) i Cloud Servicens installations- och konfigureringshandbok.
     </details>

     <details>
        <summary> Lokal programvara</summary>

     Läs mer om hur [skapa en mappning mellan ett ämne och ett innehållsfragment](../install-guide/conf-content-fragment-mapping.md) i Installations- och konfigureringshandboken på plats.

     </details>
   * Välj **Skriv över** om ditt innehållsfragment redan finns och du vill skriva över det. AEM Guides visar ett fel om du inte markerar kryssrutan och ditt innehållsfragment redan finns.
1. Klicka **Skapa** för att publicera innehållsfragmentet.
1. Du kan visa innehållsfragmenten för ett ämne under **Fragment** i **Filegenskaper**.

   ![Visa innehållsfragment för ett ämne](images/topic-content-fragments.png){width="300" align="left"}

   *Visa innehållsfragmenten för ett ämne och publicera dem igen.*

Du kan även publicera om innehållsfragmentet för att uppdatera innehållsfragmentet med det senaste innehållet från DITA-avsnittet.



När du har publicerat innehållsfragmenten kan du även använda dem på valfri AEM.

