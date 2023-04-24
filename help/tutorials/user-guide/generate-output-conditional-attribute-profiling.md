---
title: Profilering av villkorliga attribut
description: Lär dig hur du använder villkorlig attributprofilering
source-git-commit: 7cd719921e68ac1763d09d9665d912e3697e5849
workflow-type: tm+mt
source-wordcount: '465'
ht-degree: 0%

---


# Profilering av villkorliga attribut {#id1843I0HN0Y4}

På företagsnivå är det mycket viktigt att se till att ni har ett standardiserat taggningssystem. Taggar och villkorliga attribut kan kopplas till digitala resurser i databasen, vilket gör det enklare att publicera utdata baserat på valda villkor. Du kan till exempel skapa villkorsattribut för Windows- och Mac-innehåll. Sedan lägger du till dessa attribut i det relevanta innehållet i dina ämnen. När du publicerar innehåll kan du välja om du vill publicera endast Windows- eller Mac-innehåll.

Med AEM Guides kan du enkelt skapa och associera villkorliga attribut med relevanta DITA-attribut. Du kan definiera villkorliga attribut på global nivå eller på mappnivå. De globalt definierade villkoren visas i alla projekt och mappspecifika villkor visas bara i projekt som skapats i den angivna mappen. Innehållsförfattare kan använda dessa villkorsstyrda attribut för att villkoralisera innehåll i sina DITA-avsnitt eller -kartor som de skapar eller använder. Dessa villkor kan sedan användas av utgivaren för att skapa villkorliga förinställningar. Med hjälp av de villkorliga förinställningarna kan utgivaren bestämma vilket villkor som ska inkluderas och exkluderas från publicerade utdata.

>[!NOTE]
>
> Du kan skapa eller redigera villkorliga attribut i en mappprofil som du har tillgång till. Om systemadministratören inte har gett dig åtkomst till en mappprofil kan du inte skapa eller redigera villkorliga attribut i mappprofilen.

Så här definierar du villkorliga attribut:

1. Klicka på länken Adobe Experience Manager överst och välj **verktyg**.

1. Välj **Stödlinjer** i listan över verktyg.

1. Klicka på **Mappprofiler** och välj en mappprofil.

   >[!NOTE]
   >
   > Du kan inte redigera den globala profilen.

1. Klicka på **Villkorliga attribut** och klicka **Redigera**.

   Tabellen Villkorliga attribut visas.

1. Klicka **Lägg till**.

1. Ange **Namn**, **Värde** och en **Etikett** för attributet.

   Du kan spara en profil med endast attributnamnet. Ett attribut kan dock bara användas när det har ett angivet värde. Om du anger både värde och etikett för ett attribut visas bara attributets värde i Web Editor. Etiketten visas för publiceringsadministratören när den villkorliga förinställningen skapas.

   På följande skärmbild visas definitionen för `platform` attribut med värdet `unix` och en etikett på `Red Hat Linux`.

   ![](images/add-profile.png)

1. Om du vill lägga till fler värden för samma attribut klickar du på **+** och ange ytterligare värde och etikett.

1. Om du vill lägga till fler attribut klickar du på **Lägg till**.

1. Klicka **Spara** för att spara ändringarna.


The `platform` -attributet lagras i systemet. När en författare bestämmer sig för att använda `platform` i ett DITA-ämne i en mapp ser de värdena på fliken Egenskaper i Web Editor.

![](images/properties-tab.png)

**Överordnat ämne:**[ Generering av utdata](generate-output.md)

