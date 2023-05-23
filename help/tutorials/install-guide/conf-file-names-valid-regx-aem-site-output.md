---
title: Konfigurera giltiga filnamn för AEM
description: Lär dig hur du konfigurerar giltiga filnamn för AEM webbplatsutdata
source-git-commit: 801c306fa120e7889d4b9428fd5bee2849bf1956
workflow-type: tm+mt
source-wordcount: '140'
ht-degree: 0%

---


# Konfigurera giltiga filnamn för AEM {#id214GK0X0KXA}

På samma sätt som listan med giltiga filnamnstecken som tillåts för DITA-avsnitt kan du även konfigurera en lista med giltiga filnamnstecken för AEM. Några av de kända tecken som inte tillåts i en URL är: ```'<>`@$```. Dessa tecken konverteras automatiskt till understreck&quot;_&quot; när de påträffas när AEM webbplatsens utdatafilnamn genereras. Konfigurationen som gör att du kan ange giltiga tecken i AEM platsutdata finns i `com.adobe.fmdita.common.SanitizeNodeNameImpl` paket. **Ange den otillåtna teckenuppsättningen för publicering till AEM Sites** ange att de ska innehålla tecken som du vill ersätta med ett understreck i AEM platsutdatafilnamn.

**Överordnat ämne:**[ Konfigurera filnamn](conf-file-names.md)

