---
title: Använd anpassad DITA-OT- och DITA-specialisering
description: Lär dig hur du använder anpassad DITA-OT- och DITA-specialisering
source-git-commit: 5ac066bb8db32944abd046f64da11eeb1bdbe467
workflow-type: tm+mt
source-wordcount: '2075'
ht-degree: 0%

---


# Använd anpassad DITA-OT- och DITA-specialisering {#id181GAJ0005Z}

DITA Open Toolkit \(DITA-OT\) är en uppsättning Java-baserade verktyg med öppen källkod som hanterar DITA-kartor och ämnesinnehåll. Med AEM Guides kan du enkelt importera och använda anpassade DITA-OT-plugin-program. När AEM har importerats kan du konfigurera stödlinjerna så att de använder det anpassade plugin-programmet DITA-OT för att generera utdata i vilket format som helst. När du genererar utdata markerar du bara DITA-OT-alternativet och AEM Guides använder det anpassade plugin-programmet DITA-OT för att generera utdata.

Om du vill bearbeta Ant-parametrar när du publicerar utdata är det enkelt att göra det med AEM. Du kan ange vilka Ant-parametrar som du vill använda och vilka som ska bearbetas i publiceringsprocessen.

>[!NOTE]
>
> AEM Guides levereras med DITA-OT version 3.3.2. AEM har dock stöd för DITA-OT version 1.7 och senare. En fullständig lista över DITA-OT-versioner finns på [DITA-OT-versioner](http://www.dita-ot.org/download).

>[!TIP]
>
> Se *Konfiguration av DITA-OT-profiler* och *Använda anpassad DITA-OT* i Best practices Guide om de effektivaste strategierna med anpassade DITA-OT-plugin-program.

## Använda anpassade DITA-OT-plugin-program {#id181NH1020L7}

Det finns två sätt att använda en anpassad DITA-OT-plugin för publicering. Den första metoden är att överföra det anpassade plugin-programmet DITA-OT till AEM. Den andra metoden är att spara det anpassade DITA-OT-plugin-programmet på servern, skapa en profil och ange platsen för det anpassade DITA-OT-plugin-programmet i din profil.

Som standard innehåller AEM stödlinjer en förkonfigurerad profil som innehåller konfigurationerna för standardmallarna som ska användas för att redigera och publicera innehåll. Du kan skapa anpassade profiler med anpassade mallar som ska användas när du redigerar dokument och anpassade DITA-OT-plugin-program för publicering av innehåll.

Standardpaketet för DITA-OT som finns i AEM Guides innehåller Apache FOP XSL-FO-processor, som inte stöder återgivning av MathML-ekvationer. Om du använder MathML-ekvationer i ditt innehåll måste du se till att du har integrerat ett MathML-renderingsprogram för Apache FOP eller använder en annan XSL-FO-processor.

>[!IMPORTANT]
>
> Om du har uppgraderat AEM stödlinjer från version 2.2 till 2.5.1 eller 2.6 plockas alla ändringar som görs via konfigurationshanteraren automatiskt och lagras i standardprofilen.

Utför följande steg för att överföra ett anpassat DITA-OT-plugin-program till AEM:

1. Logga in AEM och öppna läget CRXDE Lite.

1. Ladda ned `DITA-OT.ZIP` -fil.

   Platsen för `DITA-OT.ZIP` filen är `/libs/fmdita/dita_resources/DITA-OT.zip`.

   ![](assets/dita-ot-zip-in-crx.png)

1. Extrahera innehållet i zip-filen på servern.

1. Använd en DITA-OT-plugin för att integrera den nya versionen av DITA-OT med din anpassade DITA-OT-plugin.

   >[!NOTE]
   >
   > Klasssökvägsavgränsaren i plugin-programmets ZIP-fil är operativsystemberoende, vilket innebär att om servern finns i Windows är klassökvägsavgränsaren en annan än den som används i Linux. Mer information om hur du integrerar plugin-program manuellt finns i *Installera plugin-program manuellt* i DITA-OT-dokumentationen.

1. Skapa ZIP-filen igen med samma namn \(`DITA-OT.ZIP`\) och mappstrukturen.

1. Överför den uppdaterade ZIP-filen tillbaka till AEM.

   Kontrollera följande innan du överför ZIP-filen:

   - Kör integratorn \(för att installera det anpassade plugin-programmet\) i ett Mac/Linux OS för att undvika problem med filavgränsare - eftersom Windows och Linux OS har olika filavgränsare är det inbyggda plugin-programmet i Mac/Linux OS kompatibelt med både Windows- och Linux-installationen.
   - Se till att `DITA-OT.ZIP` filen innehåller en mapp med namnet&quot;DITA-OT&quot; som innehåller alla relevanta plugin-program och filer.
   - Kontrollera att `DITA-OT.ZIP` filen som du skapar är av mimeType: &quot;nt:file&quot; \(motsvarar den primära typen av ZIP-fil när den överförs till AEM\). Använd ett WebDAV-verktyg eller koddistribution för att överföra den här ZIP-filen till önskad sökväg i AEM. \(Använd inte AEM pakethanterare för att distribuera den här ZIP-filen eftersom den inte är ett AEM innehållspaket utan bara en arkivfil.\)

   >[!NOTE]
   >
   > Vi rekommenderar att du inte skriver över DITA-OT-standardpaketet. Du bör överföra ditt anpassade DITA-OT-paket som innehåller ditt plugin-program till någon annan plats under `apps` mapp.

1. Öppna DITA-standardprofilen för redigering och spara den \(utan att göra några uppdateringar\) för att ändringarna ska börja gälla.


Utför följande steg för att skapa en ny profil och konfigurera den så att den använder ett anpassat DITA-OT-plugin-program som lagras på servern:

1. Lagra det anpassade plugin-programmet DITA-OT på servern.

   >[!NOTE]
   >
   > Mappstrukturen för lagring av det anpassade DITA-OT-plugin-programmet bör vara: `\*<parent-folder\>*\DITA-OT`.

1. Klicka på länken Adobe Experience Manager överst och välj **verktyg**.

1. Välj **Stödlinjer** i listan över verktyg.

1. Klicka på **DITA-profiler** platta.

   >[!NOTE]
   >
   > Standardprofilinformationen visas på sidan Profiler. Om du har uppgraderat AEM stödlinjer från version 2.2 till 2.5.1 eller 2.6 plockas alla ändringar som görs via konfigurationshanteraren automatiskt och lagras i standardprofilen.

1. Du kan välja att redigera standardprofilen, skapa en ny profil eller duplicera inställningar från standardprofilen för att skapa en ny profil.

   >[!NOTE]
   >
   > Du kan uppdatera standardprofilen, men du kan inte ta bort den. Alla nya profiler som du skapar kan dock redigeras och tas bort.

1. Konfigurera följande egenskaper för att använda det anpassade DITA-OT-plugin-programmet:

   | Egenskapsnamn | Beskrivning |
   |-------------|-----------|
   | **Profilegenskaper** |
   | Profilnamn | Ange ett unikt namn för den här profilen. |
   | Återanvänd utdata | *\(Valfritt\)* Om din profil baseras på en befintlig profil väljer du det här alternativet. Om du väljer det här alternativet kan du vara säker på att AEM inte extraherar innehållet i DITA-OT-paketet igen och återanvänder det befintliga DITA-OT-paketet. |
   | Sökväg för profilextrahering | *\(Valfritt\)* Ange sökvägen där DITA-OT finns på disken. Som standard paketerar AEM stödlinjer ett DITA-OT-paket i sin databas och det extraheras på disken på den här sökvägen.<br>**Anteckning** Du kan definiera den här sökvägen med hjälp av en befintlig systemvariabel eller egenskap. Se beskrivningen av [DITA-OT-miljövariabler](#id181NH0YN0AX) för mer information. |
   | Tilldelad sökväg | \(*Valfritt*\) Ange den sökväg i din innehållsdatabas som den här profilen gäller för. Du kan ange flera platser. |
   | **DITA-OT-egenskaper** |
   | DITA-OT-timeout | \(*Valfritt*\) Ange tiden \(i sekunder\) för vilken AEM väntar på ett svar från DITA-OT-plugin-programmet. Om inget svar tas emot under den angivna tiden avbryts publiceringsaktiviteten och aktiviteten flaggas som misslyckad. Felloggarna är också tillgängliga i loggfilen för generering av utdata. <br>Standardvärde: 300 sekunder \(5 minuter\) |
   | DITA-OT PDF argument | Ange kommandoradsargumenten som bearbetas av det anpassade plugin-programmet DITA-OT för att generera utdata från PDF. För alla anpassade DITA-OT-profiler anger du följande kommandoradsargument:`-lib plugins/org.dita.pdf2.fop/lib/` |
   | DITA-OT AEM argument | \(*Valfritt*\) Ange egna kommandoradsargument som bearbetas av det anpassade DITA-OT-plugin-programmet för att generera AEM platsutdata. |
   | DITA-OT-bibliotekssökvägar | \(*Valfritt*\) Ange ytterligare bibliotekssökvägar för DITA-OT-plugin-programmet. |
   | DITA-OT Bygg XML | \(*Valfritt*\) Ange sökvägen till det anpassade Ant-byggskriptet som paketerats med det anpassade DITA-OT-plugin-programmet. Den här sökvägen är relativ till DITA-OT-katalogen i filsystemet. |
   | DITA-OT Ant Script-mapp | \(Valfritt\) Ange sökvägen till skriptmappen DITA-OT Ant. Den här sökvägen är relativ till DITA-OT-katalogen i filsystemet. |
   | DITA-OT-miljövariabler | *\(Valfritt\)* Ange miljövariabler som ska överföras till DITA-OT-processen. Som standard lägger AEM stödlinjer till fyra variabler - `ANT_OPTS`, `ANT_HOME`, `PATH`och `CLASSPATH`. <br> Du kan återanvända de befintliga systemmiljövariablerna eller egenskaperna för att skapa nya miljövariabler. Om du till exempel har `JAVA_HOME` systemvariabel som är definierad i ditt system och du vill definiera en ny systemvariabel som kallas `JAVA_BIN` som byggts med `JAVA_HOME`. Sedan kan du lägga till definitionen av `JAVA_BIN` as:<br> `JAVA_BIN= ${JAVA_HOME}/bin` <br> **Anteckning** Du kan också använda Java-systemegenskaper för att skapa miljövariabler. Om AEM startskript till exempel definierar en Java-systemegenskap `java.io.tmpdir` till en tillfällig katalog kan du använda den här egenskapen för att definiera den nya variabeln som: `${java.io.tmpdir}/fmdita/dita_ot`. <br> **Viktigt** Om du vill återanvända en befintlig systemvariabel eller egenskap måste den omslutas av `${}`. |
   | Skriv över DITA-OT-utdata | *\(Valfritt\)* Om det här alternativet är markerat kan du ange det DITA-OT-paket som finns på din lokala dator för att generera utdata med DITA-OT. Den här konfigurationen ställs in vid aktivering av ConfigManager. <br> Om du vill ange sökvägen till ett DITA-OT-paket som lagras på AEM server avmarkerar du det här alternativet. |
   | AEM DITA-OT Zip Path/ Local DITA-OT Directory Path | Beroende på vad du har valt i Skriv över DITA-OT-utdata anger du den fullständiga sökvägen där den anpassade DITA-OT.zip-filen lagras. Detta kan vara sökvägen i AEM eller det lokala systemet. |
   | DITA-OT-plug-in-sökväg | Sökväg för det anpassade plugin-programmet. Denna plugin integreras automatiskt med DITA-OT-huvudpaketet. |
   | Integrera kataloger | \(*Valfritt*\) Sökväg till de anpassade DTD- och XSD-filerna catalog.xml i AEM. Detta bör endast anges när katalogerna saknas i DITA-OT-paketet. Katalogerna integreras automatiskt med huvudversionen av DITA-OT som ett plugin-program. |
   | Lägg till katalog för system-ID | \(*Valfritt*\) Välj det här alternativet endast om det saknas offentliga ID-poster i katalogen eller om DITA-filerna bara använder de system-ID som är relativa till serversökvägen som de överförs från. |
   | Tillfällig DITA-OT-sökväg | *\(Valfritt\)* Ange en tillfällig plats där DITA-filer kopieras för bearbetning. Innan DITA-OT bearbetar filer kopieras de på den här tillfälliga platsen. Som standard är den tillfälliga lagringsplatsen: <br> **Anteckning** Du kan definiera den här sökvägen med hjälp av en befintlig systemvariabel eller egenskap. Se beskrivningen av [DITA-OT-miljövariabler](#id181NH0YN0AX) för mer information. |

   >[!NOTE]
   >
   >  Installationsprogrammet för AEM Guides skapar två miljövariabler som du kan använda för att ange sökvägen till de anpassade DITA-OT-plugin-filerna. Dessa miljövariabler är: DITAOT\_DIR, som innehåller sökvägen till DITA-OT-katalogen i filsystemet, och DITAMAP\_DIR, som innehåller sökvägen där DITA-kartinnehållet extraheras i filsystemet.

1. Klicka **Klar** för att spara profilen.


>[!NOTE]
>
> Du kan exportera den anpassade DITA-profilen som ett paket och överföra den till andra AEM Guides-instanser för att spara tid. Mer information finns i [Bilaga](appendix.md).

## Integrera DITA-specialisering {#id211MB0E00XA}

DITA-specialisering är processen att skapa nya DITA-strukturer genom att lägga till nya element eller ta bort befintliga element. Om du vill skapa ett nytt DITA-element kan du ta ett befintligt DITA-element som bas och ändra det enligt dina redigeringskrav. Med DITA-specialisering kan ni skapa anpassade informationsmodeller som uppfyller era verksamhetskrav samtidigt som ni behåller fördelarna med den befintliga DITA-arkitekturen.

Du kan använda profilfunktionen för att lagra anpassade DITA-specialiseringsinställningar. Dessa inställningar kan sedan användas när du redigerar och publicerar anpassat DITA-innehåll. I AEM kan du använda publikt ID och system-ID i dina anpassade DTD-/XSD-filer.

>[!NOTE]
>
> AEM Guides Web Editor har inte stöd för XSD.

Följ de här stegen för att skapa en ny profil och konfigurera den så att den använder specialiserade DTD- och XSD-AEM-guider:

1. Skapa en specialmapp på din lokala dator som innehåller specialiserade DTD- och XSD-filer.

1. Ange DTD-information i dialogrutan `catalog.xml` som också måste inkluderas i specialmappen.

   >[!NOTE]
   >
   > När det gäller DITA 1.3 är standardplatsen för DTD `catalog.xml` filen i AEM: `/libs/fmdita/dita_resources/DITA-1.3/dtd/catalog.xml`.

1. Ange XSD-information i dialogrutan `catalog.xml` som också måste inkluderas i specialmappen.

   >[!NOTE]
   >
   > När det gäller DITA 1.3 är standardplatsen för XSD-filen catalog.xml i den AEM databasen: `/libs/fmdita/dita_resources/DITA-1.3/xsd/catalog.xml`.

1. Överför mappen till följande plats:

   `/libs/fmdita/dita_resources`

1. Klicka på länken Adobe Experience Manager överst och välj **verktyg**.

1. Välj **Stödlinjer** i listan över verktyg.

1. Klicka på&#x200B;**DITA-profiler** platta.

   >[!NOTE]
   >
   > Standardprofilinformationen visas på sidan Profiler. Om du har uppgraderat AEM stödlinjer från version 2.2 till 2.5.1 eller 2.6 plockas alla ändringar som görs via konfigurationshanteraren automatiskt och lagras i standardprofilen.

1. Du kan välja att redigera standardprofilen, skapa en ny profil eller duplicera inställningar från standardprofilen för att skapa en ny profil.

   >[!NOTE]
   >
   > Du kan inte ta bort standardprofilen. Alla nya profiler som du skapar kan dock redigeras och tas bort.

1. I **Schema** \> **Katalog** inställningar anger du sökvägen till den anpassade DTD- och XSD-filen `catalog.xml` filer i din AEM.

1. Välj **Lägg till katalog för system-ID** alternativ.

   >[!NOTE]
   >
   > Välj bara det här alternativet om det saknas offentliga ID-poster i katalogen eller om DITA-filerna bara använder de system-ID som är relativa till den lokala filsökvägen som de överförs från.

   Mer information om andra egenskaper på profilsidan finns i egenskapstabellen i [Steg 6](#id17A9F0D075Z) i [Använda anpassade DITA-OT-plugin-program](#id181NH1020L7) -avsnitt.

1. Klicka **Klar** för att spara profilen.


>[!NOTE]
>
> Du kan exportera den anpassade DITA-profilen som ett paket och överföra den till andra AEM Guides-instanser för att spara tid. Mer information finns i [Appendix.md](appendix.md).

