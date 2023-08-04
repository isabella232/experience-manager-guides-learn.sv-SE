---
title: Konfigurera AEM för Native PDF
description: Konfigurera AEM för Native PDF
exl-id: 40266ca0-0b0b-4418-b606-f70270addbaa
source-git-commit: 45dfe6078039001327e91ae85ea2a5beeacb2d59
workflow-type: tm+mt
source-wordcount: '0'
ht-degree: 0%

---

# Konfigurera AEM för Native PDF

AEM Guides innehåller en inbyggd PDF-motor som gör det möjligt att designa, utveckla och publicera innehåll i PDF-format.

Det gör det möjligt att skapa olika sidlayouter, CSS-mallar och utforma PDF-mallarna tillsammans med sidlayouterna och CSS.

Hur du konfigurerar det här inbyggda PDF i AEM varierar beroende på operativsystem. Använd konfigurationsstegen nedan baserat på vilket operativsystem AEM är installerat på.

## Förutsättningar

Lägsta krav för att installera PDF som har sitt ursprung:

- Installerad Java Platform, Standard Edition 8 eller 11 JDK (Java SE Development Kit) och JRE (Java SE Runtime Environment)
- AEM 6.5 SP13, SP12, SP11 eller SP10
- Stödlinjer 4.1 och senare (icke-UID eller UUID)

Publiceringsmotorn i PDF behöver Oracle-JDK för att generera nodmodulerna i AEM crx-quickstart-mapp. Det har stöd för följande operativsystem som standard:

- Windows 10, Windows 2019-server och senare.
- Linux - (RHEL 8 och senare, CentOS 7 och senare, Ubuntu 18 och senare)
- Mac OS (Intel-baserad)

## Konfigurationssteg för Windows Server (JAVA 11/8)

1. Kontrollera att AEM inte är tillgänglig.
2. Högerklicka på Windows-ikonen i aktivitetsfältet och välj System.
3. Klicka på Avancerade systeminställningar i fönstret Inställningar under Relaterade inställningar.
4. Klicka på Miljövariabler på fliken Avancerat.
5. Klicka på &quot;_Nytt_&quot; för att skapa en ny miljövariabel.
6. Ange variabelnamnet JAVA_HOME.
7. Ange sökvägen till Java-installationen i värdefältet och klicka på OK.

   Till exempel:

   JAVA 11:

   C:\Program Files\JAVA\jdk-11.0.15.1

   JAVA 8:

   C:\Program Files\JAVA\ jdk1.8.0_144

8. Lägg till välj Sökväg från systemvariabler och klicka på Redigera.

9. Nu anger variablerna i Sökväg värdet för Serversökväg och klickar på OK.

   Till exempel:

   JAVA 11:

   %JAVA_HOME%\bin\server\

   JAVA 8:

   %JAVA_HOME%\jre\bin\server\

10. Klicka på OK igen i dialogrutan Miljövariabler.
11. Klicka på OK igen i dialogrutan Systemegenskaper.
12. Starta AEM server nu.
13. Generera PDF från förinställningar i webbredigeraren.

## Konfigurationssteg för Linux Server (RHEL7/centOS 7)

1. Kontrollera att AEM inte är tillgänglig
2. Verifiera variabeln JAVA_HOME genom att göra eko $JAVA_HOME
3. Om variabeln JAVA_HOME inte är inställd följer du steg 4. I annat fall går du direkt till steg 5.
4. Ange variabeln JAVA_HOME med hjälp av kommandona nedan, baserat på den installerade Java-versionen

   Till exempel:

   JAVA 11:

   1. exportera JAVA\_HOME=/usr/lib/jvm/java-11.0.15.1
   2. exportera PATH=$PATH: $JAVA\_HOME/bin
   3. exportera LD\_LIBRARY\_PATH=/usr/lib/jvm/jdk-11.0.15.1/lib/server:/usr/java/jdk-11.0.15.1/lib/server

   JAVA 8:

   1. exportera JAVA\_HOME=/usr/lib/jvm/java-11.0.15.1
   2. exportera PATH=$PATH: $JAVA\_HOME/bin

5. Starta om AEM Server och gå till steg 12 om du använder Guides version 4.2 eller senare.
6. Kopiera &quot;_node_modules.zip_&quot; som finns i slutet av den här artikeln i katalogen crx-quickstart/profiles/nodatum—b1aad0a7-9079-e56c-1ed8-6fcababe8166/.
7. Öppna terminal i crx-quickstart/profiles/nodats—b1aad0a7-9079-e56c-1ed8-6fcababe8166/ plats.
8. Ta bort nod_modules-katalog med kommandot nedan

   **rm -rf node_modules**

9. Zippa upp nod_modules.zip med kommandot nedan

   **unzip node_modules.zip**

10. Om kommandot unzip inte är installerat/känns igen kan det installeras med följande kommando

   **unzip för installation av yum**

11. Installera fontconfig-paketet.
Kommando: teckensnittskonfiguration för yum-installation
12. Generera PDF från förinställningar i webbredigeraren.

**ANMÄRKNING** : node_modules.zip-paketet kan hämtas [här](https://acrobat.adobe.com/link/track?uri=urn:aaid:scds:US:295d8f03-41e1-429b-8465-2761ce3c2fb3).

Manuell import av de hämtade nodmodulerna för Linux-operativsystemet är en tillfällig lösning för användare som använder Guides 4.1 eller tidigare versioner (steg 6-12)

## Konfigurationssteg för Mac-dator (JAVA 11/8)

1. Installera Oracle JAVA 11 eller Oracle JAVA 8.
2. Ställ in JAVA_HOME-miljövariabeln på den installerade JAVA-katalogen.
3. Öppna ett Unix-skal.
(Bash används här för att konfigurera konfigurationen)

   Kommando: nano ~/.bashrc

4. Ange variabeln JAVA_HOME med hjälp av kommandona nedan, baserat på den installerade Java-versionen

   Till exempel:

   JAVA 11:

   exportera JAVA\_HOME= /Library/Java/JavaVirtualMachines/jdk-11.0.15.1.jdk/Contents/Home

5. Läs in basfras igen

   Kommando: källa ~/.bashrc.

6. Kontrollera att JAVA_HOME är inställt med kommandoeko $JAVA_HOME

7. Utför följande tre kommandon AEM installationssökvägen

   C:/{aem-installation-folder}/crx-quickstart/profiles/nodatum—b1aad0a7-9079-e56c-1ed8-6fcababe8166

   i) hitta . -type d -exec chmod 0755 {} \; ii) hitta . -type f -exec chmod 0755 {} \; iii) .node-darwin/lib/node_modules/npm/bin/npm-cli.js —prefix . install —unsafe-perm —scripts-prepend-node-path

8. Kontrollera om Java är installerat med kommandot nedan

   i) Kör **./node-darwin/bin/node** från mappen /crx-quickstart/profiles/nodejs—b1aad0a7-9079-e56c-1ed8-6fcababe8166

   ![mac](../assets/publishing/mac.png)

   ii) a = require(&#39;java&#39;)

9. Installera fontconfig-paketet.
Kommando: apt install fontconfig

10. Generera PDF från förinställningar i webbredigeraren.

## Felsökning

Nedan visas de vanligaste felen som kan uppstå under genereringen av PDF när miljövariablerna inte ställs in korrekt.

### Undantag för null-pekare i Windows/Mac OS

![null-pekarundantag](../assets/publishing/null-pointer-exception.png)

Om problemet kvarstår även efter att Java-miljöinställningarna har korrigerats, validera följande:

1. Kontrollera om förinställningen för utdata är korrekt definierad eller skapa en ny förinställning utan blanksteg.

2. Kontrollera nodresurskatalogen på /libs/fmdta/node_resources för att se till att alla nödvändiga bibliotek installeras under installationen.

### Bibliotek saknas i RHEL 7 Linux OS

![bibliotek som saknas](../assets/publishing/missing-libraries.png)

### Tidsgräns för publiceringsprocess. Processen slutfördes inte under den angivna tiden 0ms

![tidsgräns för publiceringsprocess](../assets/publishing/publish-process-timeout.png)

Validera timeout-egenskapsvärdet för nodatumnoden i /var/dxml/profiles/b1aad0a7-9079-e56c-1ed8-6fcababe8166/nodatums i CRX-databasen. Standardvärdet är 300.



Om du råkar ut för problem när du utför något av ovanstående steg kan du skicka din fråga till AEM Guides Community [forum](https://experienceleaguecommunities.adobe.com/t5/experience-manager-guides/ct-p/aem-xml-documentation) om du behöver hjälp.
