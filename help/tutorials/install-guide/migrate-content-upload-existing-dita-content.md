---
title: Överför befintligt DITA-innehåll
description: Lär dig hur du överför befintligt DITA-innehåll
source-git-commit: 5ac066bb8db32944abd046f64da11eeb1bdbe467
workflow-type: tm+mt
source-wordcount: '1200'
ht-degree: 0%

---


# Överför befintligt DITA-innehåll {#id176FF000JUI}

Det är mest troligt att du har en databas med befintligt DITA-innehåll som du vill använda med AEM stödlinjer. För sådant befintligt innehåll kan du använda någon av följande metoder för att massöverföra ditt innehåll till AEM.

## Använda ett WebDAV-verktyg

Om du redigerar ämnen och kartor i en annan DITA-redigerare kan du använda valfritt WebDAV-verktyg för att överföra filerna. I proceduren i det här avsnittet används WinSCP som WebDAV-verktyg för att överföra innehåll.

Utför följande steg för att använda WinSCP för att överföra filer:

1. Hämta och installera WinSCP på datorn.

1. Starta WinSCP-appen.

   Dialogrutan Inloggning visas.

1. I inloggningsdialogrutan anger du en ny platsinställning genom att välja WebDAV som **Filprotokoll** och tillhandahålla andra anslutningsdetaljer som:

   - URL:en där din AEM finns,

   - portnumret \(standard är 4502\), och

   - användarnamn och lösenord för att komma åt AEM.

1. Klicka **Inloggning**.

   När anslutningen är klar visas innehållet i AEM Assets i WinSCP-användargränssnittet. Du kan enkelt bläddra bland, skapa, uppdatera eller ta bort innehåll med WinSCP-filutforskaren.


## Använd FrameMaker

Adobe FrameMaker har en kraftfull AEM som gör det enkelt att överföra befintliga DITA-dokument och andra FrameMaker-dokument \(.book och .fm\) till AEM. Du kan använda olika funktioner för filöverföring, till exempel för att överföra en fil, överföra en hel mapp med eller utan beroenden \(som innehållsreferenser, korsreferenser och bilder\).

Utför följande steg om du vill använda FrameMakers AEM Connector för att överföra innehåll:

1. Starta FrameMaker.

1. Öppna **Anslutningshanteraren** -dialogrutan.

   ![](assets/fm-aem-connector.png){width="550" align="left"}

1. Ange följande information för att ansluta till AEM databas:

   - **Namn**: Ange ett beskrivande namn som identifierar anslutningen till AEM.
   - **Server**: Ange URL-adressen och portnumret för AEM.

   - **Användarnamn**/**Lösenord**: Ange användarnamn och lösenord för att komma åt AEM.

1. Klicka **Anslut**.

   När anslutningen har upprättats visas resurser från den AEM databasen i databashanterarfönstret.

   ![](assets/fm-repo-manager.png){width="550" align="left"}

   Om du högerklickar på en fil eller mapp kan du utföra relaterade åtgärder. Om du till exempel högerklickar på en mapp får du alternativ för att överföra en fil, överföra filen med beroenden, överföra en hel mapp och så vidare.


## Konfigurera UUID-filnamnsmönster

När du importerar innehåll behöver inte filnamnen baseras på UUID. I ett system som använder UUID-baserade filnamn är det obligatoriskt att referera till alla filer med deras UUID i stället för deras ursprungliga filnamn. Om en importerad fil inte har UUID-baserade filnamn kan du konfigurera systemet så att det lägger till ett UUID i filegenskapen. Detta UUID används sedan för att referera till sådana filer där UUID inte används för att namnge filerna.

Utför följande steg för att kontrollera filnamn mot ett UUID-mönster och tilldela UUID till filer som inte har tilldelats ett UUID:

1. Öppna konfigurationssidan för Adobe Experience Manager Web Console.

   Standardwebbadressen för åtkomst till konfigurationssidan är:

   ```http
   http://<server name>:<port>/system/console/configMgr
   ```

1. Sök efter och klicka på *com.adobe.fmdita.config.ConfigManager* paket.

1. I **UUID-filnamnsmönster** anger du ett mönster för att kontrollera den importerade filens namn.

   Om en fil inte följer det angivna mönstret läggs ett UUID till i filens egenskap och alla referenser till filen uppdateras med filens UUID.

1. Klicka **Spara**.


## Överföra innehåll med UUID med ett WebDav-verktyg {#id201MI0I04Y4}

Du kan använda någon av följande metoder för att överföra ditt innehåll med UUID:

- Dra-och-släpp innehåll från det lokala systemet.
- Använd **Skapa** \> **Filer** arbetsflöde från AEM Assets UI.
- Använd ett verktyg som WinSCP.

Om du använder ett verktyg som WinSCP kan du definiera vilken åtgärd som ska utföras på en duplicerad fil genom att ange **Flytta gammal fil med samma UUID till ny mapp** i configMgr. Det här alternativet definierar vilken åtgärd som utförs på en fil som är tillgänglig på någon annan plats i AEM. Den här inställningen är tillgänglig i *com.adobe.fmdita.config.ConfigManager* i configMgr.

Som standard är **Flytta gammal fil med samma UUID till ny mapp** är PÅ. Det innebär att när filen som överförs finns i någon annan mapp i databasen flyttas den befintliga filen till den aktuella platsen och skrivs över med filen som överförs. Om du inte markerar det här alternativet skrivs filen över på sin befintliga plats.

**Ytterligare information om att arbeta med UUID-baserade filer**:

Följande punkter måste beaktas när innehåll flyttas eller kopieras i AEM:

- När du kopierar en eller flera filer från en plats till en annan skapas ett nytt UUID för filer som inte har något UUID. Detta UUID läggs till i filens metadata.

- Om en fil har en konflikt eller har en dubblett, genereras ett unikt filnamn för den nya filen som kopieras eller flyttas.

- Två filer kan inte ha samma UUID. Alla nya filer tilldelas ett unikt UUID.


Följande punkter måste beaktas när du flyttar eller kopierar innehåll från ditt lokala system till AEM:

- Om en fil överförs av två olika användare samtidigt, kommer den fil som bearbetas senare att skriva över den tidigare filen. En sådan metod är dock sällsynt och bör undvikas.

- När du checkar ut innehåll från den AEM databasen och gör ändringar i det lokala systemet, kontrollerar du att filnamnet inte ändras när du överför filen.


## Använda vändkommandon

Du kan också använda kontrollkommandon för att skapa en mapp i DAM, överföra filer och lägga till metadata i det överförda innehållet.

**Skapa en mapp**

Kör följande kommando för att skapa en mapp AEM databasen:

```curl
curl --user <username>:<password> --data jcr:primaryType=sling:Folder "<server folder path>"
```

Ange följande parametrar för att skapa en mapp:

- `<username>:<passowrd>`: Ange användarnamn och lösenord för att komma åt AEM. Användaren måste ha behörighet att skapa mappar.

- `jcr:primaryType=sling:Folder`: Ange den här parametern *as* för att skapa en mapptypresurs.

- `<server folder path>`: Fullständig mappsökväg med namnet på den nya mappen som du vill skapa i AEM. Om du till exempel anger sökvägen som `http://192.168.1.1:4502/content/dam/projects/AEM-Guides`och sedan mappen `AEM-Guides` skapas i `projects` i DAM.


**Överföra en fil**

Kör följande kommando för att överföra en fil i AEM:

```curl
curl --user <username>:<password> -T "<local file path>" "<server folder path>"
```

Ange följande parametrar för att överföra en fil:

- `<username>:<passowrd>`: Ange användarnamn och lösenord för att komma åt AEM. Den här användaren måste ha skrivbehörighet för `server folder path`.

- ``local file path``: Fullständig filsökväg på det lokala system som du vill överföra.

- `<server folder path>`: Fullständig mappsökväg på den AEM servern där du vill överföra filen.


**Lägg till metadata**

Kör följande kommando för att lägga till metadata i en fil:

```curl
curl --user <username>:<password> -F<attribute name>=<value> <metadata node path>
```

Ange följande parametrar för att lägga till metadatainformation:

- `<username>:<passowrd>`: Ange användarnamn och lösenord för att komma åt AEM. Den här användaren måste ha skrivbehörighet för ``metadata node path``.

- ``-F<attribute name>=<value>``: The `<attribute name>` är namnet på metadataattributet, till exempel `audience` och `<value>` kan `internal`. Du kan ange flera attributnamnvärdespar avgränsade med blanksteg.

- `<metadata node path>`: Fullständig mappsökväg med filnamnet och dess metadatanod. Om du till exempel anger sökvägen som `http://192.168.1.1:4502/content/dam/projects/AEM-Guides/intro.xml/jcr:content/metadata`och den angivna metadatainformationen är `intro.xml` -fil.


**Överordnat ämne:**[ Migrera befintligt innehåll](migrate-content.md)

