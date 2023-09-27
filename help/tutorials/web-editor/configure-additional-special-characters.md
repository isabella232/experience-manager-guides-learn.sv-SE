---
title: Konfigurera ytterligare specialtecken i verktygsfältet i Web Editor
description: Lär dig hur du konfigurerar ytterligare specialtecken i webbredigeraren AEM stödlinjer.
feature: Web Editor
role: User
exl-id: 0fbc05a5-a6b0-4f6b-bbc4-8fca03581d90
source-git-commit: 8504a0a52d381044bf1f0d6e7de3585ebecf3a7b
workflow-type: tm+mt
source-wordcount: '259'
ht-degree: 0%

---

# Konfigurera ytterligare specialtecken i Web Editor-verktygsfältet

Det finns ett kortkommando i webbredigeringsverktygsfältet där författaren kan infoga specialtecknen.
Detsamma visas på skärmbilden nedan:

![Specialtecken](assets/special-chars.png)


Här kan du konfigurera teckenlistan. Följ stegen nedan om du behöver lägga till fler tecken:

+ Logga in AEM och öppna läget CRXDE Lite.

+ Skapa filen symbols.json på följande plats: &#39;/apps/fmdita/xmleditor/&#39; (du kan kopiera standardfilen från - &#39;/libs/fmdita/clientlibs/clientlibs/xmleditor/symbols.json&#39; plats)

+ Lägg till specialteckendefinitionen i filen symbols.json som:

```
{
      "label": "Logical Symbols",
      "items": [
        {
          "name": "≥",
          "title": "Greater-Than or Equal To"
        },
        {
          "name": "≤",
          "title": "Smaller-Than or Equal To"
        }
      ]
}
```

Strukturen för filen symbols.json förklaras nedan:

+ &quot;label&quot;: &quot;Logical Symbols&quot;: This specifies the category for the special characters. I fragmentet definieras en kategori med namnet&quot;Logisk symbol&quot;.

+ &quot;items&quot;: Detta definierar samlingen av specialtecken i kategorin.

+ &quot;name&quot;: &quot;≥&quot;, &quot;title&quot;: &quot;Greater-Than or Equal To&quot;: This is the definition of the special character. Den börjar med etiketten &quot;name&quot;, som inte får ändras. Namnet följs av specialtecknet. &quot;title&quot; är namnet eller titeln på specialtecknet som visas som verktygstips för specialtecknet.

Du kan definiera flera definitioner av specialtecken i en kategori.

Då läggs ytterligare en kategori till i dialogrutan med specialtecken:

![Specialsymbolkategori](assets/special-char-category.png)

![Infoga specialtecken](assets/insert-special-char.png)

>[!MORELIKETHIS]
>
>+ [Installations- och konfigureringshandbok](https://helpx.adobe.com/content/dam/help/en/xml-documentation-solution/3-6/XML-Documentation-for-Adobe-Experience-Manager_Installation-Configuration-Guide_EN.pdf)
