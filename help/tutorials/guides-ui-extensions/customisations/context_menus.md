---
sidebar_position: 2
source-git-commit: 42052b37724f97e34ab007db4cc3d9f9524ad3a2
workflow-type: tm+mt
source-wordcount: '149'
ht-degree: 0%

---


# Anpassa snabbmenyer

Följande snabbmenyer kan anpassas:

- `file_options`
styrenheter:
   - Kartvy: `ditamap_viewer_controller`
   - Databaspanel: `repository_panel_controller`
   - Favoritpanel: `collection_tree_controller`
   - Referenslänkar för filegenskaper: `file_references_links_controller`
   - Databassökpanel: `repository_search_controller`
   - Ämnesschema: `subject_scheme_tree_controller`

- `folder_options`
styrenheter:
   - Databaspanel: `repository_panel_controller`
   - Favoritpanel: `collection_tree_controller`

- `collection_options`
styrenheter:
   - Favoritpanel: `collection_tree_controller`

- `map_view_options`
styrenheter:
   - Kartvy: `ditamap_viewer_controller`

- `baseline_panel_menu`
styrenheter:
   - Baslinjepanelen: `baseline_panel`

- `preset_item_menu`
styrenheter:
   - Förinställningspanelen: `preset_panel`

Du kan också skapa en egen snabbmeny genom att definiera ett nytt unikt ID.

Nu har varje snabbmeny en `controller id` som är kopplade till den. Den här kontrollenheten hanterar `on-event` funktioner för olika alternativ på snabbmenyn

Låt oss ta ett exempel

```js title=customise_context_menu.js"
const fileOptions = {
    id: "file_options",
    contextMenuWidget: "repository_panel",
    view: {
            items: [
                {
                    component: "div",
                    target: {
                        key:"displayName",value: "Delete",                    
                        viewState: VIEW_STATE.REPLACE
                    }
                },
                {
                    component: "div",
                    target: {
                        key:"displayName",value: "Edit",                    
                        viewState: VIEW_STATE.REPLACE
                    }
                },
                {
                    "displayName": "Download",
                    "data": {
                      "eventid": "downloadFile"
                    },
                    "icon": "downloadFromCloud",
                    "class": "menu-separator",         
                    target: {
                        key:"displayName",value: "Duplicate",                    
                        viewState: VIEW_STATE.REPLACE
                    }
                },
            ]

    },

    controller: {
        downloadFile(){
            const path  = this.model.selectedItem.path
            this.loader.loadDitaFile(path).then((file) => {
              function download_file(name, contents) {
                const mime_type = "text/plain";
        
                const blob = new Blob([contents], {type: mime_type});
        
                const dlink = document.createElement('a');
                dlink.download = name;
                dlink.href = window.URL.createObjectURL(blob);
                dlink.onclick = function() {
                    // revokeObjectURL needs a delay to work properly
                    const that = this;
                    setTimeout(function() {
                        window.URL.revokeObjectURL(that.href);
                    }, 1500);
                };
        
                dlink.click();
                dlink.remove();
            }
            download_file(path,file.xml)
            });
          }
    }
}
```

Låt oss nu förstå vad den här koden gör.

1. `id` används för att identifiera den snabbmeny som vi vill anpassa.
2. `contextMenuWidget` används för att definiera `widget id` eller `component` som anropar snabbmenyn och hanterar `events`.

Resten är densamma, vilket innebär att `view` används för att definiera objekten, `target` identifierar var alternativet ska ersättas, läggas till eller läggas till före och `contextMenuWidget` handtag för `on-click` händelser.
