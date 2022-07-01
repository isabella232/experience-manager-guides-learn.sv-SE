---
title: Konfiguration av redigeringsprogram för AEM
description: Konfigurera redigeraren för AEM
exl-id: 437d9598-4afc-431f-81bd-6762e22656b7
source-git-commit: b5e64512956f0a7f33c2021bc431d69239f2a088
workflow-type: tm+mt
source-wordcount: '780'
ht-degree: 0%

---

# Konfiguration av XML-redigerare

Om du arbetar i en restriktiv miljö kan du välja vilka funktioner författarna kan se genom att anpassa redigerarkonfigurationen i en viss mappprofil. Om du använder den här mappprofilen kan du ändra utseendet på själva redigeraren, CSS-mallarna, tillgängliga fragment och etiketterna för innehållsversionen.

Exempelfiler som du kan välja att använda för den här lektionen finns i filen [xmleditorconfiguration.zip](assets/xmleditorconfiguration.zip).

>[!VIDEO](https://video.tv.adobe.com/v/342762)

## Anpassa standardkonfigurationen för redigeringsgränssnittet

Du kan alltid hämta standardgränssnittskonfigurationen till din lokala dator, göra ändringar i den i valfri textredigerare och sedan överföra den igen.

1. På navigeringsskärmen klickar du på [!UICONTROL **verktyg**] ikon.

   ![Verktygsikon](images/reuse/tools-icon.png)

2. Välj **Stödlinjer** till vänster.

3. Klicka på [!UICONTROL **Mappprofiler**] platta.

   ![Mappprofiler](images/reuse/folder-profiles-tile.png)

4. Välj en mappprofil.

5. Klicka på [!UICONTROL **Konfiguration av XML-redigerare**] -fliken.

6. Klicka [!UICONTROL **Hämta**] Standard.

   ![Hämta standard](images/lesson-4/download-default.png)

Du kan nu öppna och ändra innehållet i en textredigerare. The _Installation och konfiguration av AEM_ Handboken innehåller exempel på hur du tar bort, anpassar eller lägger till funktioner i gränssnittskonfigurationen.

## Överför den ändrade gränssnittskonfigurationen för XML-redigeraren

När du har anpassat gränssnittskonfigurationen kan du överföra den. Observera att en exempelkonfigurationsfil _ui-config-restricted-editor.json_ innehåller en uppsättning ämnen som kan användas i lektionen.

1. Klicka på knappen [!UICONTROL **Konfiguration av XML-redigerare**] -fliken.

2. Under gränssnittskonfigurationen för XML-redigeraren klickar du på [!UICONTROL **Överför**].

   ![Överför](images/lesson-4/upload.png)

3. Dubbelklicka på filen för den ändrade användargränssnittskonfigurationen, eller så som visas här, den medföljande exempelfilen.

   ![Exempel på konfigurationsfil](images/lesson-4/sample-config-file.png)

4. Klicka [!UICONTROL **Spara**] i skärmens övre vänstra hörn.

Den ändrade gränssnittskonfigurationen har överförts.

## Anpassa CSS-mallayouten

Precis som med gränssnittskonfigurationen kan du hämta CSS-mallayouten. Du kan öppna det i en textredigerare och göra ändringar för att anpassa utseendet på ämnet innan du överför det.

1. På navigeringsskärmen klickar du på [!UICONTROL **verktyg**] ikon.

   ![Verktygsikon](images/reuse/tools-icon.png)

2. Välj **Stödlinjer** till vänster.

3. Klicka på [!UICONTROL **Mappprofiler**] platta.

   ![Mappprofiler](images/reuse/folder-profiles-tile.png)

4. Välj en mappprofil.

5. Klicka på [!UICONTROL **Konfiguration av XML-redigerare**] -fliken.

6. Under CSS-mallayout klickar du på [!UICONTROL **Hämta**].

   ![Hämta CSS](images/lesson-4/download-css.png)

Nu kan du ändra och spara CSS-innehållet i en textredigerare.

## Överför den ändrade CSS-mallayouten

När du har anpassat CSS-mallayouten kan du överföra den. Observera att en exempelfil _css-layout-ONLY-draft-comment-change.css_ innehåller en uppsättning ämnen som kan användas i lektionen. Den här filen innehåller bara utkastet till kommentarsändring, medan _css-layout-draft-comment-change.css_ är hela filen som du bara kan använda för testning eller granskning.

1. Klicka på knappen [!UICONTROL **Konfiguration av XML-redigerare**] -fliken.

2. Under CSS-mallayout klickar du på [!UICONTROL **Överför**].

   ![Överför CSS](images/lesson-4/upload-css.png)

3. Dubbelklicka på filen för din egen anpassade CSS-layout eller den exempelfil som visas här.

   ![Exempel på CSS-fil](images/lesson-4/sample-css-file.png)

4. Klicka [!UICONTROL **Spara**] i skärmens övre vänstra hörn.
Du har överfört den anpassade CSS-mallayouten.

## Redigera XML-redigerarkodfragment

Kodavsnitt är återanvändbara innehållsdelar som kan vara specifika för en produkt eller grupp. Observera att exempelfragmenten finns med i supportfilerna för den här lektionen.

1. På navigeringsskärmen klickar du på [!UICONTROL **verktyg**] ikon.

   ![Verktygsikon](images/reuse/tools-icon.png)

2. Välj **Stödlinjer** till vänster.

3. Klicka på [!UICONTROL **Mappprofiler**] platta.

   ![Mappprofiler](images/reuse/folder-profiles-tile.png)

4. Välj en mappprofil.

5. Klicka på [!UICONTROL **Konfiguration av XML-redigerare**] -fliken.

6. Klicka på under XML-redigerarfragment **Överför**.

   ![Överför fragment](images/lesson-4/upload-snippets.png)

7. Välj egna fragment eller använd de medföljande exemplen.

   ![Exempelkod](images/lesson-4/sample-snippet.png)

8. Klicka [!UICONTROL **Spara**] i skärmens övre vänstra hörn.

Du har lagt till nya fragment i redigeraren.

## Anpassa versionsetiketter för XML-innehåll

Som standard kan författare skapa egna etiketter och associera dem med ämnesfiler. Detta kan leda till olika variationer på samma etikett. För att undvika inkonsekventa etiketter kan du även välja i listor med fördefinierade etiketter.

1. På navigeringsskärmen klickar du på [!UICONTROL **verktyg**] ikon.

   ![Verktygsikon](images/reuse/tools-icon.png)

2. Välj **Stödlinjer** till vänster.

3. Klicka på [!UICONTROL **Mappprofiler**] platta.

   ![Mappprofiler](images/reuse/folder-profiles-tile.png)

4. Välj en mappprofil.

5. Klicka på [!UICONTROL **Konfiguration av XML-redigerare**] -fliken.

6. Klicka på under Versionsetiketter för XML-innehåll [!UICONTROL **Hämta**].

   ![Ladda ned etiketter](images/lesson-4/download-labels.png)

Nu kan du anpassa etiketterna efter behov.

## Överför versionsetiketter för XML-innehåll

När du har laddat ned och ändrat etiketterna kan du ladda upp avsnittet XML Content Version Label. Du kan välja att använda exempelfilen _labels.json_, som innehåller en uppsättning ämnen som kan användas i lektionen.

1. Klicka på knappen [!UICONTROL **Konfiguration av XML-redigerare**] -fliken.

2. Klicka på under Versionsetiketter för XML-innehåll [!UICONTROL **Överför**].

   ![Ladda upp etiketter](images/lesson-4/upload-labels.png)

3. Dubbelklicka på filen för antingen egna etiketter eller exempelfilen som visas här.

   ![Exempeletikettfil](images/lesson-4/sample-labels-file.png)

4. Klicka [!UICONTROL **Spara**] i skärmens övre vänstra hörn.

Du har överfört anpassade versionsetiketter för XML-innehåll.
