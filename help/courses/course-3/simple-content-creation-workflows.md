---
title: Arbetsflöden för att skapa enkelt innehåll
description: Skapa innehåll i AEM stödlinjer
exl-id: e4b8e512-0688-44f7-b981-78af33b57b08
source-git-commit: 67ba514616a0bf4449aeda035161d1caae0c3f50
workflow-type: tm+mt
source-wordcount: '719'
ht-degree: 0%

---

# Arbetsflöden för att skapa enkelt innehåll

AEM Guides Editor har flera genvägar som gör det enklare att skapa innehåll. Med dessa genvägar kan användare snabbt lägga till och ändra bilder, arbeta med flera ämnen samtidigt, korrigera fel, ladda ned PDF och arbeta med versioner och etiketter.

>[!VIDEO](https://video.tv.adobe.com/v/342770?quality=12&learn=on)

## Lägga till en bild

Du kan lägga till bilder direkt från en lokal enhet.

1. Dra och släpp bilden direkt i ämnet. The **Överför resurser** visas.

   ![Dialogrutan Överför resurser](images/lesson-15/upload-assets-dialog.png)

1. Ändra mappsökvägen till önskad bildplats.

1. Ändra bildens namn till något som motsvarar dess syfte.

1. Klicka [!UICONTROL **Överför**].

## Ändra en bild

1. Ändra storlek på en bild genom att dra och släppa ett hörn.

1. Flytta en bild till en annan plats i ämnet genom att dra och släppa den.

1. Använd **Innehållsegenskaper** på den högra panelen för att ändra en bilds

   - scale

   - position

   - justering, eller

   - andra attribut.

   ![Innehållsegenskaper](images/lesson-15/content-properties.png)

## Arbeta med flera ämnen

Delad vy är användbart när du jämför ämnen, kopierar och klistrar in mellan ämnen eller drar och släpper innehåll från ett ämne till ett annat.

1. Öppna två eller flera relaterade ämnen.

1. Klicka på en fils titelflik för att öppna snabbmenyn.

1. Välj [!UICONTROL **Dela**].

1. Välj **Höger**.

   ![Delad vy](images/lesson-15/split-view.png)

## Korrigera typografiska fel

1. Leta reda på ordet eller frasen som innehåller felet.

1. Tryck och håll [!UICONTROL **Ctrl**].

1. Klicka på den sekundära musknappen på felet.

1. Välj rätt stavning.

Felet har korrigerats i avsnittstexten.

## Ladda ned ett ämne PDF

Användare kan vilja ladda ned en PDF i det aktuella ämnet för att kommentera eller dela med andra.

1. Klicka [!UICONTROL **Förhandsgranska**] längst upp till höger på skärmen.

1. Klicka på [!UICONTROL **PDF, ikon**] ovanför ämnet. En dialogruta visas.

   ![PDF Export](images/lesson-15/pdf-export.png)

1. Fyll i informationen för antingen **Transformeringsnamn** eller **Kommandoradsargument för DITA-OT** vid behov. Observera att PDF fortfarande genereras om alla fält lämnas tomma.

1. Klicka [!UICONTROL **Hämta**]. PDF genererar.

1. Använd tillgängliga ikoner för att konfigurera, hämta eller dela ämnet i PDF.

## Leta reda på ett ämne i databasen eller kartan

1. Öppna ämnet.

1. Klicka på den sekundära musknappen på fliken Titel.

1. Välj **Sök i**.

1. Välj antingen **Databas** eller **Karta** för att gå till den önskade ämnesplatsen.

## Version av ett ämne

1. Ändra ett ämne.

1. Spara ämnet.

1. Klicka på **Databas** ikonen i den övre vänstra menyn.

   ![Databasikon](images/lesson-15/repository-icon.png)

1. Lägg till **Kommentarer för ny version**.

   ![Dialogrutan Ny version](images/lesson-15/version-dialog.png)

1. Klicka [!UICONTROL **Spara**].

Versionsnumret uppdateras.

## Läs in versionsetiketter

Det kan vara svårt att spåra ett ämnes tillstånd baserat på endast versionsnumret. Etiketter gör det enklare att identifiera exakt status för ett ämne som har genomgått flera revisioner.

1. Välj en **Mappprofil**.

1. Konfigurera XML-redigeraren i mappprofilen.

   a. Välj Redigera längst upp till vänster på skärmen.

   b. Lägg till ett nytt ämne eller använd ett befintligt under Versionsetiketter för XML-innehåll.

   ![Etiketter för innehållsversion](images/lesson-15/version-labels.png)

1. Välj [!UICONTROL **Överför**].

1. Välj en fil som ReviewLabels.json eller liknande. Mer information om hur du skapar en sådan fil finns i en annan video.

1. Klicka [!UICONTROL **Öppna**].

1. Klicka [!UICONTROL **Spara**] längst upp till vänster på skärmen Mappprofil.

1. Klicka [!UICONTROL **Stäng**] överst till höger.

Versionsetiketter har lästs in.

## Tilldela versionsetiketter

1. Läs in versionsetiketter.

1. Klicka på [!UICONTROL **Användarinställningar**] ikonen längst upp till vänster i det aktuella avsnittet.

   ![Mappprofil](images/lesson-15/folder-profile-icon.png)

1. Välj samma mappprofil där versionsetiketter tidigare lästes in.

1. I dialogrutan Användarinställningar kontrollerar du att bassökvägen refererar till samma information som mappprofilen har tillämpats på.

   ![Användarinställningar](images/lesson-15/user-preferences.png)

1. Klicka [!UICONTROL **Spara**].

1. Version av ämnet.

1. Lägg till en kommentar och välj en versionsetikett i listrutan.

   ![Dialogrutan Ny versionsetikett](images/lesson-15/labels-dialog.png)

1. Klicka [!UICONTROL **Spara**].

Versionsnumret uppdateras.

## Visa versionshistorik och etiketter

1. På den vänstra panelen letar du reda på aktuell ämnesrubrik.

1. Klicka på titeln för att öppna snabbmenyn.

1. Välj [!UICONTROL **Visa i resursgränssnitt**].

   ![Resurser, användargränssnitt](images/lesson-15/view-assets-ui.png)

   - Versionshistoriken med etiketter visas till vänster.

   ![Versionshistorik](images/lesson-15/version-history.png)

1. Klicka på en version för att komma åt alternativ som **Återgå till den här versionen** och **Förhandsgranska version**.

## Skapa en ny mall

Det finns mallar för både ämnen och kartor. Administratörer har åtkomst till mallar i den vänstra panelen.

1. Klicka [!UICONTROL **Mallar**] i den vänstra panelen.

1. Välj antingen Karta eller Ämne för att öppna den associerade snabbmenyn.

1. Klicka för att lägga till den nya mallen.

   ![Ny ämnesmall](images/lesson-15/version-history.png)

1. Fyll i fälten i den resulterande dialogrutan.

Skalmallen visas med exempelinnehåll och en exempelstruktur.
