---
title: Introduktion
description: Introduktion till API-referenshandboken för AEM
exl-id: d8ee9cf7-1d67-4b4a-aa80-64e893a99463
source-git-commit: 112085153aaf246289bd8f91657c95e986df482e
workflow-type: tm+mt
source-wordcount: '730'
ht-degree: 0%

---

# Introduktion {#id1761C0007W7}

Adobe Experience Manager Guides \(kallas senare *AEM stödlinjer*\) är en komplett företagslösning som gör det möjligt för Adobe Experience Manager \(AEM\) att ha CCMS-funktioner (Component Content Management Solution) för att skapa och leverera DITA-baserat material. Kunderna får tillgång till arbetsflödena AEM Guides via programmering med hjälp av API:er för AEM Guides för att integrera dem med andra företagsapplikationer. Dessa API:er kan också användas av Adobe partners för att förbättra AEM genom att utöka dess funktionalitet eller genom att integrera den med andra program eller tjänster.

## AEM Guides API:er

API:erna AEM stödlinjer finns i två format: HTTP och Java. Dessa API:er visar AEM stödlinjers nyckelfunktioner för programutvecklare. Med de här funktionerna kan utvecklare skapa egna plugin-program för att utöka färdiga arbetsflöden. API:erna är tillgängliga när det gäller att hantera utdata för DITA-innehåll, arbeta med DITA-kartor, lägga till villkorsattribut i mappnivåprofiler och konvertera HTML- och Word-dokument till DITA-format.

## Installera JAR på din lokala Apache Maven-databas {#install-jar-local}

För att kunna använda JAR-filer som visas av AEM Guides måste du installera dem i din lokala Apache Maven-databas. Så här installerar du JAR:er på din plats i Maven-databasen:

1. Extrahera innehållet i AEM Guides-paketet \(.zip\) på din dator.

2. I kommandotolken navigerar du till följande mapp i sökvägen för det extraherade innehållet:

   ```
   \jcr_root\libs\fmdita\osgi-bundles\install
   ```

3. Kör följande kommando för att installera API-paketet i din lokala Maven-databas:

   ```
   mvn install:install-file -Dfile=api-X.x.jar -DgroupId=com.adobe.fmdita -DartifactId=api -Dversion=X.x -Dpackaging=jar**
   ```

   >[!NOTE]
   >
   > I ovanstående kommando ska X.x ersättas med det faktiska versionsnumret i parametrarna Dfile och Dversion.

4. \(*Valfritt*\) Installera beroendet i det lokala Maven-projektarkivet. Du kan uppnå detta genom att skapa en mapp i Maven-projektet och sedan köra `mvn install` det kommando som gavs i föregående steg med följande extra parameter:

   ```
   -DlocalRepositoryPath=<path_to_project_repository>
   ```

   Om du vill visa projektets lokala databasmapp för byggprocessen i Maven lägger du till en `repository` -element i den överordnade filen pom.xml enligt nedan:

   ```XML
   <repositories>
      <repository>
         <id>project-repository</id>
         <url>file://${project.basedir}/repository</url>
      </repository>
   </repositories>
   ```


Den här processen installerar API-JAR:er i den lokala Maven-databasen.

## Använda JAR-tjänstens API i ett Maven-projekt

När du har installerat API-JAR i din lokala Maven-databas utför du följande steg för att använda JAR i dina projekt:

1. Lägg till JAR i kodbasen och implementera den i kodbasdatabasen under en mapp, till exempel&quot;beroenden&quot;. Observera att mappnamnet är beroende av kodens bashierarki.

2. Konfigurera pom.xml-projektfilerna enligt följande:

   Överordnat projekts pom.xml-fil:

   >[!IMPORTANT]
   >
   > I följande kodfragment ska X.x ersättas med det faktiska versionsnumret och API JAR:s filnamn. Den här informationen är densamma som i steg 3 i [installationsprocess](#install-jar-local).

   ```XML
   <plugin>
   
       <groupId>org.apache.maven.plugins</groupId>
   
      <artifactId>maven-install-plugin</artifactId>
   
       <version>2.5.2</version>
   
       <configuration>
   
               <groupId>com.adobe.fmdita</groupId>
   
               <artifactId>api</artifactId>
   
               <version>X.x</version>
   
               <file>${basedir}/dependencies/fmdita/api-X.x.jar</file>
   
               <packaging>jar</packaging>
   
               <generatePom>true</generatePom>
   
       </configuration>
   
       <executions>
   
           <execution>
   
               <id>inst_fmdita</id>
   
                   <goals>
   
                       <goal>install-file</goal>
   
                   </goals>
   
                   <phase>clean</phase>
   
           </execution>
   
       </executions>
   </plugin>
   ```

   Den underordnade modulens pom.xml-fil:

   ```XML
   <plugin>
      <groupId>org.apache.maven.plugins</groupId>
   
      <artifactId>maven-install-plugin</artifactId>
   
      <configuration>
   
         <groupId>com.adobe.fmdita</groupId>
   
         <artifactId>api</artifactId>
   
         <version>3.6</version>
   
         <file>${basedir}/../dependencies/fmdita/api-3.6.jar</file>
   
         <packaging>jar</packaging>
   
         <generatePom>true</generatePom>
   
      </configuration>
   
      <executions>
   
         <execution>
   
            <id>inst_fmdita</id>
   
            <goals>
   
               <goal>install-file</goal>
   
            </goals>
   
            <phase>clean</phase>
   
         </execution>
   
      </executions>
   
   </plugin>
   ```


## Konfigurera och använda tjänst-API JAR från den offentliga Maven-databasen

Utför följande steg för att konfigurera och använda JAR för tjänstens API från den offentliga Maven-databasen i dina projekt:

1. Om du vill använda tjänstens API JAR i ett projekt ska du konfigurera AEM Guides public Maven-databasen i filen pom.xml.
2. Konfigurera den offentliga Maven-databasen i filen settings.xml i Maven enligt följande:

   ```XML
   <repository>
      <id>fmdita-public</id>
      <name>fmdita-public</name>
      <url>https://repo.aem-guides.com/repository/fmdita-public</url>
   </repository>
   ```

3. När databasen har konfigurerats lägger du till tjänstens API JAR som ett projektberoende i projektets pom.xml-fil.

   >[!NOTE]
   >
   > Använd samma version av API-JAR som paketet AEM stödlinjer som du har installerat på servern.

4. Konfigurera Maven-beroendet så som visas nedan:

   ```XML
   <dependency>
      <groupId>com.adobe.fmdita</groupId>
      <artifactId>api</artifactId>
      <version>4.0</version>
   </dependency>
   ```


När JAR för tjänst-API har lagts till som ett projektberoende i projektets pom.xml-fil kan du skapa och använda Java-API:er AEM Guides i ditt projekt.

## Använda API JAR från Maven Central-databasen för AEM Guides as a Cloud Service

För AEM Guides as a Cloud Service har API-JAR distribuerats till Maven Central. Du kan använda API JAR utan någon konfiguration.

>[!NOTE]
>
> Namnkonventionen för API-behållaren har uppdaterats enligt namnkonventionen för molntillägg.

Om du vill använda API-JAR måste du lägga till beroendet till ditt projekts pom.xml så som visas nedan:

```XML
<dependency>
   <groupId>com.adobe.aem</groupId>
   <artifactId>aem-guides-sdk-api</artifactId>
   <version>2022.5</version>
</dependency>
```

>[!NOTE]
>
> Eftersom paketen i API JAR fortfarande är desamma krävs ingen kodändring för att använda denna API JAR i de befintliga molnprojekten.

## Ytterligare resurser

Nedan följer en lista över andra användbara resurser i AEM, som finns på sidan [Läs mer &amp; Support](https://helpx.adobe.com/support/xml-documentation-for-experience-manager.html) sida:

- Användarhandbok
- Installations- och konfigureringshandbok
- Snabbstartsguide
- [Hjälparkivsida](https://helpx.adobe.com/xml-documentation-for-experience-manager/archive.html) \(använd äldre versionsdokumentation\)
