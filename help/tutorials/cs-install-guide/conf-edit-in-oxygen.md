---
title: Konfigurera alternativet för redigering i syrgas
description: Lär dig hur du konfigurerar alternativet att redigera i plugin-programmet för syreanslutning.
source-git-commit: a209e46e41055348402292e20c229890cd0c01cf
workflow-type: tm+mt
source-wordcount: '104'
ht-degree: 0%

---


# Konfigurera alternativet för redigering i syrgas

AEM Guides gör det även möjligt för användare att redigera sina DITA-avsnitt och DITA-kartor i insticksprogrammet för syreanslutning.

Använd instruktionerna i [Konfigurationsåsidosättningar](download-install-additional-config-override.md#) för att skapa konfigurationsfilen. Ange följande (egenskap) information i konfigurationsfilen för att konfigurera **Redigera i syrgas** alternativ:



| PID | Egenskapsnyckel | Egenskapsvärde |
|---|------------|--------------|
| `com.adobe.fmdita.xmleditor.config.XmlEditorConfig` | `xmleditor.editinoxygen` | Boolean \(true/false\). **Standardvärde**: false |

>[!NOTE]
>
> Den här konfigurationen är inaktiverad som standard och alternativet är inte tillgängligt i Web Editor.

**Överordnat ämne:**[ Anpassa Web Editor](conf-web-editor.md)

