---
title: REST API för att arbeta med villkorsattribut
description: Läs mer om REST API för att arbeta med villkorsattribut
source-git-commit: 880cd344ceb65ea339be699ebcad41c0d62e168a
workflow-type: tm+mt
source-wordcount: '147'
ht-degree: 0%

---

# REST API för att arbeta med villkorsattribut {#id175UB30E05Z}

Med följande REST API kan du lägga till villkorsattribut i en mappprofil.

## Lägg till villkorsattribut i en mappnivåprofil

En mappmetod som lägger till villkorsstyrda attribut i en viss mappnivåprofil.

**Begär URL**:\
http://*&lt;aem-guides-server>*: *&lt;port-number>*/bin/fmdita/folderprofiles

**Parametrar**:\
|Namn|Typ|Obligatorisk|Beskrivning| |—|—|—|—| |`:operation`|String|Yes|Namnet på den åtgärd som anropas. Värdet för den här parametern är ``ADDATTRIBUTEPROFILES``. <br> **Obs!** Värdet är inte skiftlägeskänsligt.| |`profilename`|String|Yes|Visningsnamn för den mappnivåprofil där villkorsattributen ska läggas till.| |`conditionalprofiles`|JSON-matris|Yes|En JSON-matris som består av villkorsattributets namn och värden. Följande kodexempel visar JSON-arrayen med två attribut - `platform` och `product` med flera värden tilldelade.|

```JSON
[  {    name: "platform",    
        values: [       
                {value: "win", label: "Windows"},       
                {value: "mac", label: "Mac OS"}    
                ]},
                {    
                    name: "product",    
                    values: [      
                        {value: "aem_1", label: "AEM 6.1"},     
                        {value: "aem_4,  label: "AEM 6.4"}  
                        ]  
                }]
```

**Svarsvärden**:\
Returnerar ett HTTP 200 \(Slutförd\)-svar.
