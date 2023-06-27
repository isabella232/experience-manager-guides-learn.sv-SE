---
title: Konfigurera tillåtna specialtecken
description: Lär dig hur du konfigurerar tillåtna specialtecken
source-git-commit: 6051181e243cf71919901093c1b5590f21832545
workflow-type: tm+mt
source-wordcount: '206'
ht-degree: 0%

---


# Konfigurera tillåtna specialtecken {#id20CIL600035}

I Web Editor kan du infoga vissa specialtecken som inte finns installerade. Du kan dock anpassa listan med specialtecken som författarna kan infoga i sina dokument. Om du anpassar teckenlistan skrivs standarduppsättningen med specialtecken över. Endast de specialtecken som du lägger till i konfigurationen blir tillgängliga för författarna.

Utför följande steg för att skriva över standardlistan med specialtecken:

1. Skapa `symbols.json` på följande plats i din Cloud Managers Git-databas:

   ```
   /apps/fmdita/xmleditor/
   ```

1. Lägg till specialteckendefinitionen i dialogrutan `symbols.json` fil som:

   ```
   {"symbols": [{"label": "Arrows",
      "items": [
      {   "name": "←",   "title": "Left Arrow"   } 
      ,   
      {   "name": "↑",   "title": "Up Arrow"      } 
      ]   
      }   ]   }
   ```


Strukturen för `symbols.json` filen förklaras nedan:

- `"label": "Arrows"`: Detta anger kategorin för specialtecknen. I fragmentet finns en kategori med namnet `"Arrows"` är definierad.
- `"items"`: Detta definierar samlingen av specialtecken i kategorin.
- `"name": "←", "title": "Left Arrow"`: Detta är definitionen av specialtecknet. Det börjar med `"name"` label, som inte får ändras. Namnet följs av specialtecknet. The `"title"` är namnet eller titeln på specialtecknet som visas som verktygstips för specialtecknet.

  Du kan definiera flera definitioner av specialtecken i en kategori.


**Överordnat ämne:**[ Anpassa Web Editor](conf-web-editor.md)

