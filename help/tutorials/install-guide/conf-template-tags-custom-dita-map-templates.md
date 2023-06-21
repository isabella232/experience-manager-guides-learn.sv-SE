---
title: Konfigurera anpassad DITA-mappningsmall
description: Lär dig hur du konfigurerar en anpassad DITA-mappningsmall
exl-id: 2ad0fc50-97fd-437e-94cc-db5f51f3bc3f
source-git-commit: 0dea2f1d17e7d9b12d07b459a10a00c1dd7460a5
workflow-type: tm+mt
source-wordcount: '331'
ht-degree: 0%

---

# Konfigurera anpassad DITA-mappningsmall {#id1774F04F05Z}

AEM Guides innehåller två färdiga mallar för kartor - DITA-karta och Bookmap. Du kan skapa kartor baserade på dessa mallar; Du kan också definiera egna mappningsmallar som sedan kan användas för att skapa nya kartor.

Följ de här stegen för att lägga till egna mappningsmallar:

1. Logga in i Adobe Experience Manager som administratör.

1. I resursgränssnittet navigerar du till den mapp som konfigurerats för att lagra mappningsmallfilerna. Som standard lagras alla mappningsmallar i mappen /content/dam/dita-templates/maps.

   >[!NOTE]
   >
   > Information om hur du konfigurerar en anpassad plats för lagring av ämne- eller mappmallar finns i [Konfigurera anpassad sökväg till DITA-mallmapp](conf-template-tags-custom-dita-topic-template.md#id191LCF0095Z)

1. Klicka **Skapa** \> **DITA-mall**.

1. På sidan Design väljer du den typ av karta som du vill skapa.

   >[!NOTE]
   >
   > Du kan använda karta- eller bokmappsmallen som bas för den nya mallen.

1. Klicka på **Nästa**.

1. På den nya mallsidan Egenskaper anger du en **Titel** och **Namn** för mallen.

   >[!NOTE]
   >
   > Namnet föreslås automatiskt baserat på mallens rubrik. Om du vill ange namnet manuellt kontrollerar du att namnet inte innehåller blanksteg, apostrof eller klammerparenteser och slutar med .ditamap.

1. Klicka **Skapa**.

   Meddelandet Kartan har skapats visas.

   Du kan välja att öppna mallen för redigering i kartredigeraren eller spara mallfilen på malllagringsplatsen. När mallen har skapats kan du använda kartredigeraren för att anpassa mallen efter dina behov. När du har skapat en mall måste du associera den med en global profil eller en profil på mappnivå.


Nästa gång du skapar en ny karta visas mallen på sidan Design. Mer information om hur du skapar en DITA-karta finns i *Använda Adobe Experience Manager-stödlinjer*.

>[!TIP]
>
> Se *Egna mallar* i Best practices Guide för bästa praxis när det gäller att använda anpassade kartmallar.

**Överordnat ämne:** [Konfigurera ämne- och mappningsmallar](conf-template-tags.md)
