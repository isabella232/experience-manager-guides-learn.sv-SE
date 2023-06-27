---
title: Användaradministration och -säkerhet
description: Se hur användaradministration och säkerhet fungerar
source-git-commit: 6051181e243cf71919901093c1b5590f21832545
workflow-type: tm+mt
source-wordcount: '716'
ht-degree: 0%

---


# Användaradministration och -säkerhet {#id181AED00G5Z}

Om du vill komma åt och konfigurera funktioner i AEM måste du skapa användare. Dessa användare kan sedan tilldelas behörigheter för att få tillgång till alla eller vissa funktioner i AEM. Lär dig konfigurera och underhålla användarauktorisering och förstå också teorin bakom hur autentisering och auktorisering fungerar i AEM.

Följande ämnen i AEM visar hur du kan förstå användaradministration och säkerhetsrelaterade koncept och funktioner:

- [AEM användare, grupper och behörigheter](https://experienceleague.adobe.com/docs/experience-manager-learn/cloud-service/accessing/aem-users-groups-and-permissions.html)

- [Användaradministration och -säkerhet](https://experienceleague.adobe.com/docs/experience-manager-65/administering/security/security.html)


## Användargrupper som har skapats AEM stödlinjer {#id181TF0K0MHT}

AEM Guides innehåller tre färdiga grupper för att hantera olika uppgifter i ett DITA-projekt. Dessa grupper är: *Författare*, *Granskare* och *Utgivare*. Beroende på vilken grupp en användare är kopplad till, kan de utföra specifika åtgärder. Publiceringsuppgifterna kan till exempel bara utföras av en utgivare, men inte av en författare eller granskare. På samma sätt kan en författare skapa ett nytt ämne, och en granskare kan bara granska ett ämne.

>[!TIP]
>
> Se *Behörigheter* i Best practices Guide för bästa praxis när det gäller att ange användarbehörigheter.

I följande tabell visas olika uppgifter och grupper som kan utföra dessa uppgifter:

| Uppgift | Författare | Granskare | Utgivare |
|----|-------|---------|----------|
| Skapa DITA-ämne | Ja |   | Ja |
| Skapa DITA-karta | Ja |   | Ja |
| Kartsamlingar | Ja |   | Ja |
| Skapa granskningsuppgift | Ja |   | Ja |
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
| Skapa granskningsuppgift | Ja |   | Ja |
| Redigera | Ja |   | Ja |
| **Tillgängliga funktioner i DITA-kartkonsolen \(fliken Baslinjer\)** |
| Skapa |   |   | Ja |
| Redigera |   |   | Ja |
| Duplicera |   |   | Ja |
| Ta bort |   |   | Ja |
| DITA-kartkonsol \(fliken Rapporter\) | Ja |   | Ja |
| **Tillgängliga funktioner i DITA-kartkonsolen \(Villkorsförinställningar\)** |
| Skapa/redigera villkorsförinställning |   |   | Ja |

## Ytterligare information om användargrupper

Följande lista innehåller rekommendationer och punkter som rör användargrupper och motsvarande behörigheter:

- Om du vill att en användare ska starta arbetsflödet för översättning eller granskning kontrollerar du att användaren är medlem i *Utgivare* och *projekt-administratörsgrupp*.

- Användarna måste ha behörighet att läsa, skapa, ta bort och ändra på käll- och målspråksmapparna som de behöver arbeta med.

- Om du skapar ett projekt är du ägare av projektet med *Utgivare* behörigheter. För att andra användare i ett projekt ska kunna se sina teammedlemmar, skapa uppgifter eller skapa arbetsflöden måste de ha läsåtkomst på `/home/users` och `/home/groups` noder. Ett sätt att ge läsåtkomst på `/home/users` och `/home/groups` är genom att ge läsåtkomst till `projects-users` grupp.

- *Granskare* Du kan komma åt och lägga till granskningskommentarer för ett ämne som granskas från projektkonsolen eller från meddelandelänken i inkorgen. Dessutom är den här åtkomsten bara tillgänglig tills granskningsaktiviteten är öppen.

- Som standard *Utgivare* har behörighet och behörighet för följande mappar i DAM:

   - `/content/fmdita` -\> Läs och skriv

   - `/content/dam/fmdita-outputs` -\> Läs och skriv

   - `/content/output/sites` -\> Läs och skriv

  Du måste ge explicit läs- och skrivbehörighet till utgivaren om du använder någon annan plats än de standardpubliceringsplatser som nämns ovan.

- Alla användare under *Författare*, *Granskare* och *Utgivare* grupper har läsåtkomst för allt innehåll i DAM.

- Behörigheter på mappnivå måste tilldelas användare via sidan för användaradministration.

- Om du vill att dina användare ska kunna utföra sökåtgärder på DAM ska du göra användarna till medlemmar i *dam-users* grupp.

- Om du vill ge administratörsbehörighet till en användare kan du göra det genom att ge användaren åtkomst via AEM standardgrupper som *administratörer*, *projekt-administratörer* eller OSGI-konfiguration \(Felix console\).

- Om du vill ge en användare behörighet att ändra ett dokumenttillstånd måste du lägga till användaren i avsnittet om tillståndsövergång i dokumentets tillståndsprofil.

[1](#fnsrc_1) If *Författare* och *Utgivare* är inbjudna till en granskning.[2](#fnsrc_2) Beroende på vilka rättigheter användaren har i dokumentets tillståndsprofil.

