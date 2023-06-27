---
title: Konfigurera en datakällanslutning
description: Lär dig hur du konfigurerar en datakällanslutning
source-git-commit: 760d765a364a49aaff8787eea4f067b3f0e25103
workflow-type: tm+mt
source-wordcount: '387'
ht-degree: 0%

---


# Konfigurera en datakällanslutning

AEM Guides innehåller färdiga anslutningar för JIRA- och SQL-databaser (MySQL, PostgreSQL, SQL Server, SQLite). Du kan också lägga till andra kopplingar genom att utöka standardgränssnitten. Med följande konfiguration kan du enkelt lägga till olika datakällor. När du har lagt till dem kan du visa datakällorna i Web Editor.

Utför följande steg för att konfigurera en datakällanslutning och använd den sedan från Web Editor:

## Konfigurera en koppling

Du kan konfigurera en färdig anslutning genom att överföra en JSON-fil. Du kan använda följande exempelkonfigurationsfiler för att konfigurera anslutningar för Jira- och SQL-databaser (MySQL, PostgreSQL, SQL Server, SQLite).

Ett exempel på en installationsfil för Jiras grundläggande autentisering med användarnamn och lösenord:

```
{
	"connectorClazz": "com.adobe.guides.konnect.definitions.ootb.connector.rest.JiraConnector",
	"configName": "Jira",
	"templateFolders": ["/content/dam/dita-templates/konnect/jira"],
	"connectionConfig": {
		"configClazz": "com.adobe.guides.konnect.definitions.ootb.config.rest.BasicAuthRestConfig",
		"configData": {
			"username": "jirausername",
			"password": "jirapassword",
			"url": "https://jira.corp.adobe.com/rest/api/latest/search"
		}
	}
}
```

Spara som `jira.json`.

En exempelkonfigurationsfil för Jiras grundläggande autentisering med token:

```
{
	"connectorClazz": "com.adobe.guides.konnect.definitions.ootb.connector.rest.JiraConnector",
	"configName": "Jira",
	"templateFolders": ["/content/dam/dita-templates/konnect/jira"],
	"connectionConfig": {
		"configClazz": "com.adobe.guides.konnect.definitions.ootb.config.rest.BasicAuthRestConfig",
		"configData": {
			"token": "jiraauthtoken",
			"url": "https://jira.corp.adobe.com/rest/api/latest/search"
		}
	}
}
```

Spara som `jira.json`.

Ett exempel på en konfigurationsfil för Jiras grundläggande autentisering med nyckelordet &quot;Basic&quot; i:

```
{
	"connectorClazz": "com.adobe.guides.konnect.definitions.ootb.connector.rest.JiraConnector",
	"configName": "Jira",
	"templateFolders": ["/content/dam/dita-templates/konnect/jira"],
	"connectionConfig": {
		"configClazz": "com.adobe.guides.konnect.definitions.ootb.config.rest.BasicAuthRestConfig",
		"configData": {
			"token": "Basic jiraauthtoken",
			"url": "https://jira.corp.adobe.com/rest/api/latest/search"
		}
	}
}
```

Spara som `jira.json`.

Ett exempel på en installationsfil för MySQL-autentisering:

```
{
	"connectorClazz": "com.adobe.guides.konnect.definitions.ootb.connector.sql.MySqlConnector",
	"configName": "MySQL",
	"templateFolders": ["/content/dam/dita-templates/konnect/sql"],
	"connectionConfig": {
		"configClazz": "com.adobe.guides.konnect.definitions.ootb.config.sql.UserPassSqlConfig",
		"configData": {
			"username": "admin",
			"password": "admin",
			"driver": "com.mysql.jdbc.Driver",
			"connectionString": "jdbc:mysql://host.corp.adobe.com:3306/plm"
		}
	}
}
```

Spara som `mysql.json`.

Ett exempel på en installationsfil för PostgreSQL:s grundläggande autentisering:

```
{
	"connectorClazz": "com.adobe.guides.konnect.definitions.ootb.connector.sql.PostgreSqlConnector",
	"configName": "PostgreSQL",
	"templateFolders": ["/content/dam/dita-templates/konnect/sql"],
	"connectionConfig": {
		"configClazz": "com.adobe.guides.konnect.definitions.ootb.config.sql.UserPassSqlConfig",
		"configData": {
			"username": "admin",
			"password": "admin",
			"driver": "org.postgresql.Driver",
			"connectionString": "jdbc:postgresql://host:port/database"
		}
	}
}
```

Spara som `postgres.json`.

Ett exempel på en installationsfil för MS SQL Server grundläggande autentisering:

```
{
	"connectorClazz": "com.adobe.guides.konnect.definitions.ootb.connector.sql.MsSqlServerConnector",
	"configName": "MSSQLServer",
	"templateFolders": ["/content/dam/dita-templates/konnect/sql"],
	"connectionConfig": {
		"configClazz": "com.adobe.guides.konnect.definitions.ootb.config.sql.UserPassSqlConfig",
		"configData": {
			"username": "admin",
			"password": "admin",
			"driver": "com.microsoft.sqlserver.jdbc.SQLServerDriver",
			"connectionString": "jdbc:sqlserver://10.10.10.10\\SQLEXPRESS01:1433;database=TutorialDB;encrypt=false;trustServerCertificate=true"
		}
	}
}
```

Spara som `mssqlserver.json`.

Ett exempel på en installationsfil för SQLite grundläggande autentisering:

```
{
	"connectorClazz": "com.adobe.guides.konnect.definitions.ootb.connector.sql.SqliteConnector",
	"configName": "SQLiteServer",
	"templateFolders": ["/content/dam/dita-templates/konnect/sql"],
	"connectionConfig": {
		"configClazz": "com.adobe.guides.konnect.definitions.ootb.config.sql.UserPassSqlConfig",
		"configData": {
			"username": "admin",
			"password": "admin",
			"driver": "org.sqlite.JDBC",
			"connectionString": "jdbc:sqlite:sample.db"
		}
	}
}
```

Spara som `sqqlite.json`.

### Anpassa en kopplingskonfiguration

Med AEM Guides kan du anpassa vissa värden i konfigurationsfilen efter användarens behov.

| Egenskapsnamn | Beskrivning |
|---|---|
| configName | Användaren kan ange ett konfigurationsnamn som hjälper till att identifiera kopplingen |
| templateFolders | Lista med mappar som mallar hämtas från |

Andra fält anpassas baserat på den config-klass som valts för att köra anslutningsprogrammet.

## Överför filen till en plats i AEM

Överför filen till någon plats i AEM Assets.

Till exempel,  `/var/dxml/konnect/jira.json`

## Skapa konfiguration med REST API

Du kan registrera konfigurationen med REST API. Mer information finns i *REST API för att registrera en datakällkoppling* i API-referens för Adobe Experience Manager-guider.

När du har konfigurerat datakällan visas kopplingen under panelen Datakällor i Web Editor. Sedan kan du ansluta till datakällan och infoga ett innehållskuvert i dina ämnen. Mer information finns i [Infoga ett innehållssfragment från datakällan](../user-guide/web-editor-content-snippet.md).

