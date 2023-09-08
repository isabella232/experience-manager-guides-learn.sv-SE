---
title: Händelsehanterare för konverteringsprocess
description: Läs mer om händelsehanteraren för konverteringsprocessen
source-git-commit: 8707acf3ba01b7488eea6597c434da73a901d037
workflow-type: tm+mt
source-wordcount: '189'
ht-degree: 0%

---


# Händelsehanterare för konverteringsprocess {#id175UB30E05Z}

AEM Guides visar händelsen com/adobe/fmdita/conversion/complete som används för att utföra eventuella efterbehandlingsåtgärder efter att en dokumentkonverteringsprocess har slutförts. Den här händelsen utlöses när ett icke-DITA-dokument migreras till DITA-filformat. Om du till exempel kör en Word till DITA-konvertering eller InDesign till DITA-konvertering anropas den här händelsen när konverteringsprocessen har avslutats.

Du måste skapa en AEM händelsehanterare för att kunna läsa de egenskaper som är tillgängliga i den här händelsen och utföra ytterligare bearbetning.

Händelseinformation förklaras nedan:

**Händelsenamn**:

```HTTP
com/adobe/fmdita/conversion/complete 
```

**Parametrar**:\
|Namn|Typ|Beskrivning| |—|—|—| |`status`|String|Returstatus för åtgärden som utfördes. Möjliga alternativ är: - LYCKADES: Konverteringsprocessen har slutförts. <br> - SLUTFÖRT MED FEL: Konverteringsprocessen slutfördes, men med vissa fel. <br>- MISSLYCKADES: Konverteringsprocessen misslyckades på grund av ett allvarligt fel.| |`filePath`|String|Absolut sökväg för källfilen \(som ska konverteras\) i AEM.| |`outputPath`|String|Absolut sökväg till målplatsen där de konverterade DITA-filerna ska sparas.| |`logPath`|String|Absolut sökväg för noden där konverteringsloggen ska sparas.|

