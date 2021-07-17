# **Import/Export Command-line Tool**
Allows you to import and export portals, and various catalog items such as master pages, containers, widgets, and structured content types on different environments.  
> **Note**: *Developers can access the Import/Export Command-line Tool in the release package version 5.6.0. Inside the package, it can be found in the* `importer-5.6.0-SNAPSHOT-jar-with-dependencies.jar` *file.*


The command-line tool commands are given below:  
| Command | Description |
| --- | --- |
| `export-portal` | Exports the portal with content. |
| `export-portal-model` | Exports the model XML of the portal. |
|  `export-page` | Exports a master page. |
| `export-widget` | Exports a widget. |
| `export-layout` | Exports a layout or container. |
| `import-portal-model` | Imports the model XML of the portal. |
| `import-archive` | Imports an archive. <br/> **Note**: *The archive can contain elements such as Master Page, Portal, etc.* |

## Import a Widget  
Allows adding/updating an object into another environment. It supports importing widgets and other following items:  
- Containers
- Portals
- Master Pages
- Content Types

Component archives allow you to import widgets and containers items in different environments.  When importing the widget, the CXP Object Model is updated and the resources included in the archive are written in the configured context root.  

### Syntax
To use the Import/Export tool, you need to run from the Class-Path:
```
java -jar importer-5.6.0-SNAPSHOT-jar-with-dependencies.jar import-widget -a C:/Temp/Widget-StateLinkWidget-a625d0ef.zip -s http://lion:8280/orchestrator or http://panther:8480/orch -u username -p password -P corporate, marketing
```  
### Parameters
| Parameter | Data Type | Description | Required |
| --- | --- | --- | --- |
| `a` | string | `path/archivefilename` Path to the archive you are importing. | Yes |
| `s` | string | `serverurl` URL address of the server performing the import or export. The default is `http://lion:8280/orchestrator or http://panther:8480/orch`. | Yes |
| `u` | string | `username` Unique name associated with the user. Default is `username`. | Yes |
| `p` | string | `password` Secret code associated with the user. Default is `password`. | Yes |
| `P` | string | `portalname` Name of Portal(s) where you are importing the widget or other item. | No |

> **Note:** *To import item(s) directly to multiple portals at the same time, use the `P` parameter in your syntax. It allows you to add the names of portals where you want to import the widget or other item into*.