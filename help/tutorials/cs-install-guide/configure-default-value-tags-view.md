---
title: Konfigurera standardvärde för taggvyn
description: Lär dig hur du konfigurerar standardvärdet för taggvyn
source-git-commit: 6051181e243cf71919901093c1b5590f21832545
workflow-type: tm+mt
source-wordcount: '215'
ht-degree: 0%

---


# Konfigurera standardvärde för taggvyn {#id223GN0M0NDC}

Med AEM Guides kan du konfigurera standardläget för taggvyn i Web Editor, vilket gör att du kan aktivera eller inaktivera taggvyn som standard för en ny användarsession.Utför följande steg för att konfigurera standardvärdet för taggvyn:

1. Hämta UI-konfigurationsfilen genom att logga in i Adobe Experience Manager som administratör.
1. Klicka på länken Adobe Experience Manager överst och välj **verktyg**.
1. Välj **Stödlinjer** i listan med verktyg och klicka på **Mappprofiler**.
1. Klicka på **Global profil** platta.
1. Välj **Konfiguration av XML-redigerare** och klicka på **Redigera** överst.
1. I **Användargränssnittskonfiguration för XML-redigering** klickar du på **Hämta** för att ladda ned `ui_config.json` på din lokala dator.
1. I `ui_config.json` ändrar du standardläget för taggvyn genom att ändra avsnittet defaultValues enligt nedan:

```
"defaultValues":
                {
                "tagsView": true
                }
```

1.) Spara filen och överför den.

>[!NOTE]
>
> Användarens inställning i Web Editor för att aktivera/inaktivera taggvyn har företräde framför det här standardvärdet. Om en användare aktiverar taggvyn från Web Editor är den alltså aktiverad även i alla sessioner.

**Överordnat ämne:**[ Anpassa Web Editor](conf-web-editor.md)

