---
title: Uteslut stycken i ett ämne från översättning
description: Exkludera stycken i ett ämne från översättning
feature: Translation
role: User
source-git-commit: 880cd344ceb65ea339be699ebcad41c0d62e168a
workflow-type: tm+mt
source-wordcount: '148'
ht-degree: 0%

---

# Exkludera stycken i ett ämne från översättning

Det enklaste sättet är att använda attributet translation=no.

+ Författare kan infoga det extra attributet som **translation=no** i de stycken som de inte vill översätta. Översättningsleverantören måste informeras och de kan göra konfigurationer i slutet för att ignorera texten med det här attributet.
+ OOTB-maskinöversättning (med provversionen av Microsoft Translation Connector) uppvisar samma beteende.
+ Testa med Microsoft Translation: om du definierar **translate=no** på styckenivå översätts inte hela stycket. Det här attributet kan definieras för alla element och innehållet i det elementet kommer inte att översättas.


Här är några skärmbilder som ytterligare förklarar:

**Källinnehåll**

![Källinnehåll](assets/source-content.jpg)

**Översatt innehåll på spanska**

![Översatt innehåll på spanska](assets/trans-content.jpg)
