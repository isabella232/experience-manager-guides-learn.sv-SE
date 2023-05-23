---
title: Skapa ämnen
description: Lär dig hur du skapar ämnen
exl-id: 336bbbff-f268-40be-ad3a-9c72923be71b
source-git-commit: e69665f3c4a0db10365719ac671cbd3ac0c455ec
workflow-type: tm+mt
source-wordcount: '583'
ht-degree: 0%

---

# Skapa ämnen {#id2056AL00O5Z}

Med AEM Guides kan du skapa DITA-ämnen av typen: variabel, uppgift, begrepp, referens, ordlista, DITAVAL med mera. Förutom att skapa ämnen baserat på färdiga mallar kan du även definiera egna mallar. Mallarna måste läggas till i mappprofilen för att kunna visas i mallvalet Utskrift och webbredigeraren.

Observera att konfiguration av global profil och mappprofil endast är tillgänglig för administratörer på mappnivå. Mer information om hur du konfigurerar globala profiler och profiler på mappnivå finns i *Konfigurera redigeringsmallar* i Installera och konfigurera Adobe Experience Manager Guides för installationen.

Så här skapar du ett ämne:

1. I resursgränssnittet navigerar du till den plats där du vill skapa ämnet.

1. Om du vill skapa ett nytt ämne klickar du på **Skapa** \> **DITA-ämne**.

1. Välj den typ av DITA-dokument som du vill skapa på sidan DesignPrint och klicka på **Nästa**.

   ![](images/create_dita_topic.png){width="800" align="left"}

   Som standard innehåller AEM stödlinjer de vanligaste DITA-ämnesmallarna. Du kan konfigurera fler ämnesmallar enligt organisationens krav, se *Konfigurera redigeringsmallar* i Installera och konfigurera Adobe Experience Manager Guides för installationen.

   >[!NOTE]
   >
   > I listvyn över Assets UI visas DITA-ämnestypen i kolumnen Typ som Ämne, Aktivitet, Koncept, Referens, Glossentry eller DITAVAL. DITA-kartan visas som karta.

1. På sidan Egenskaper anger du dokumentet **Titel**.

1. \(Valfritt\) Ange filen **Namn**.

   Om administratören har konfigurerat det automatiska filnamnet baserat på UUID-inställningen visas inte alternativet att ange filnamnet. Ett UUID-baserat filnamn tilldelas automatiskt till filen.

   Om namngivningsalternativet är tillgängligt föreslås också namnet automatiskt baserat på **Titel** av dokumentet. Om du vill ange dokumentnamnet manuellt kontrollerar du att **Namn** innehåller inga mellanslag, apostrof eller klammerparenteser och slutar med .xml eller .dita. Som standard ersätter AEM stödlinjer alla specialtecken med bindestreck. Mer information om hur du namnger DITA-filer finns i avsnittet Filnamn i Best practices-guiden.

1. Klicka **Skapa**. Meddelandet Ämnet har skapats visas.

   Du kan välja att öppna ämnet för redigering i Web Editor eller att spara ämnesfilen i AEM.

   Varje nytt ämne som du skapar från resursgränssnittet **Skapa** \> **DITA-ämne** eller så har Web Editor tilldelats ett unikt ämne-ID. Värdet för detta ID är själva filnamnet. Ett nytt dokument sparas också som den senaste arbetskopian av ämnet i DAM. Om du inte sparar en revision av ett nyligen skapat ämne kommer du inte att se något versionsnummer i Tidigare versioner. Om du öppnar ämnet för redigering visas versionsinformationen i det övre högra hörnet på ämnesfilens flik:

   ![](images/topic-version-none_cs.png){width="550" align="left"}

   Versionsinformationen för ett nyligen skapat ämne visas som *ingen*. När du sparar en ny version tilldelas den ett versionsnummer som 1.0. Mer information om hur du sparar en ny version finns i [Spara som ny version](web-editor-features.md#save-as-new-version-id209ME400GXA).


>[!NOTE]
>
> Om administratören har konfigurerat Web Editor för att checka ut filer innan du redigerar, kommer du inte att kunna redigera en fil förrän du checkar ut den. Om den är konfigurerad blir du ombedd att checka in utcheckade filer innan du stänger dem.

>[!IMPORTANT]
>
> När du har skapat ditt DITA-avsnitt kan du fortsätta spara ändringarna i arbetskopian och skapa en ny version när du har slutfört uppdateringarna av ämnet.

**Överordnat ämne:**[ Skapa och förhandsgranska ämnen](create-preview-topics.md)
