---
title: Infoga ett innehållssfragment från datakällan
description: Lär dig hur du infogar ett innehållsavdrag från datakällan
source-git-commit: e4fcf6c7b7e69d83edb91e25081dae6e7cf1ae89
workflow-type: tm+mt
source-wordcount: '608'
ht-degree: 0%

---


# Infoga ett innehållssfragment från datakällan

AEM innehåller funktioner för att ansluta till datakällan. Du kan hämta dina data, infoga dem i dina ämnen och redigera dem. Du kan enkelt skapa ett innehållsavdrag med generatorn för innehållsavdrag och återanvända det i dina ämnen.

Utför följande steg för att skapa ett innehållskfragment med hjälp av generatorn för innehållsfragment och infoga det i ditt avsnitt:

1. Välj **Datakällor** ![](images/data-source-icon.svg)   i den vänstra panelen för att visa de anslutna datakällorna. Panelen Datakällor öppnas och visar alla anslutna datakällor. Mer information finns i [Konfigurera en datakällanslutning](../cs-install-guide/conf-data-source-connector.md).
   >[!NOTE]
   >
   > Du ser de datakällor som administratören har konfigurerat anslutningen för.

1. Välj en datakälla om du vill visa de innehållsfragmentgeneratorer som är tillgängliga för den valda datakällan.
   ![](images/code-snippet-generator.png){width="300" align="left"}
1. Välj **Lägg till** om du vill lägga till en ny generator för innehållsfragment. The **Lägg till generator för innehållsfragment** panelen öppnas.

1. Skriv frågan i textrutan Datafråga.
1. Välj den mall som mappar med datakällan från **Datamappningsmall** listruta.
De färdiga mallarna för den valda datakällan visas i listrutan. Du kan till exempel visa mallen &quot;sql-table&quot; för datakällan med namnet &quot;PostgreSQL&quot;-datakälla.

   >[!NOTE]
   >  
   > Om administratören har konfigurerat anpassade mallar visas även dessa mallar i listrutan (baserat på mallsökvägskonfigurationerna som din administratör har konfigurerat).

1. Klicka **Hämta** för att hämta data från datakällan och tillämpa mallen på data som är resultat av SQL-frågan.
1. Du kan visa data i förhandsgranskningen eller DITA-källvyn.

   1. I förhandsgranskningen visas hur data visas när de infogas i innehållet. I förhandsvisningen visas en liten del av data i den valda mallens format.
Till exempel:
      * Om du har valt en SQL-tabellmall kan du visa SQL-data i tabellformat.
      * Om du har valt mallen Jira-ordered-list kan du visa en ordnad lista för Jira-problemen.

   1. I källvyn visas data i DITA-källvyn.
      ![](images/add-content-snippet-generator.png){width="800" align="left"}
1. Om du vill spara resultatet av frågan anger du namnet på generatorn och klickar sedan på **LÄGG TILL**.   En ny generator för innehållsfragment läggs till i listan.

   >[!NOTE]
   >
   > Du måste följa namnkonventionen för den nya innehållsgeneratorns namn. Du kan inte ha ett mellanslag i namnet på generatorn för innehållsfragment. Du kan inte heller spara en ny innehållsgenerator med namnet på en befintlig innehållsgenerator. Ett fel inträffar.

## Alternativ för generering av innehållsfragment

Högerklicka på en generator för innehållsfragment för att öppna Alternativ. Med alternativen kan du utföra följande åtgärder:
* **Infoga**: Använd det här alternativet om du vill infoga det markerade innehållsfragmentet i det ämne som har öppnats för redigering i webbredigeraren. När data infogas som utdrag kan du även redigera data i ämnet i Web Editor.

  >[!NOTE]
  > 
  > Alternativet Infoga visas bara när du redigerar ett ämne.

* **Redigera**: Använd det här alternativet om du vill göra ändringar i generatorn för innehållsfragment och spara den.
* **Ta bort**: Använd det här alternativet om du vill ta bort den markerade generatorn för innehållsfragment.
* **Duplicera**: Använd det här alternativet om du vill skapa en dubblett eller en kopia av den valda generatorn för innehållskodfragment. Dupliceringen skapas med ett suffix (som generator_1) som standard.

### Infoga ett frågesfragment

Du kan också använda **Infoga frågesfragment** ![](images/data-source-icon.svg)   i huvudverktygsfältet för att infoga datagreppet i avsnitten.  Du kan välja en generator i listrutan, redigera frågan eller ändra mallen och infoga data i avsnittet.

![](images/insert-content-snippet.png){width="800" align="left"}




