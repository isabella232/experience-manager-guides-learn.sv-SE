---
title: Stöd för Schematron i webbredigeraren
description: Arbeta med Schematron i webbredigeraren
source-git-commit: 880cd344ceb65ea339be699ebcad41c0d62e168a
workflow-type: tm+mt
source-wordcount: '379'
ht-degree: 0%

---

# Styra kvaliteten på innehållet i webbredigeraren

I den här artikeln finns en översikt över valideringsmöjligheterna i AEM Guidas webbredigerare.
Genom att designa en webbredigerare utnyttjar DITA-schemainställningarna i systemet för att tvinga användare att skapa DITA-kompatibelt innehåll. Då är allt innehåll som lagras i systemet strukturerat, återanvändbart och giltigt DITA-innehåll.

Förutom stöd för DITA-regler stöder webbredigeraren även validering av innehåll baserat på &quot;*Schematron* regler.

&quot;*Schematron*&quot; är ett regelbaserat valideringsspråk som används för att definiera tester för en XML-fil. Du kan importera schemafilerna och redigera dem i Web Editor. Med hjälp av en &quot;Schematron&quot;-fil kan du definiera vissa regler och sedan validera dem för ett DITA-ämne eller en karta. Schematronreglerna kan säkerställa konsekvens i XML-strukturen genom att införa begränsningar som definieras som regler. Dessa begränsningar drivs av små och medelstora företag som äger innehållets kvalitet och enhetlighet.

    Obs! Webbredigeraren har stöd för ISO-schemat.


## Att veta hur &quot;Schematron&quot; fungerar i webbredigeraren

### Konfigurera schematransregler

Mer information finns i avsnittet Stöd för Schematron-filer i [Användarhandbok](https://helpx.adobe.com/content/dam/help/en/xml-documentation-solution/4-2/Adobe-Experience-Manager-Guides_UUID_User-Guide_EN.pdf#page=148)


### Använd valideringsregler när filen sparas

Med webbläsar-inställningarna kan användarna konfigurera schematrons regler/filer som körs varje gång en användare uppdaterar innehållet. Mer information finns i avsnittet &quot;Validering&quot; i [Användarhandbok](https://helpx.adobe.com/content/dam/help/en/xml-documentation-solution/4-2/Adobe-Experience-Manager-Guides_UUID_User-Guide_EN.pdf#page=58)

![Ange regler från webbredigeringsinställningar](../../../assets/authoring/schematron-editorsettings-validation-tab.png)


### Kan du köra valideringen manuellt?

Ja, som författare/användare när du skapar innehåll kan du använda panelen Schematron i webbredigeraren för att överföra en schematron-fil och köra valideringar för filen som är öppen i redigeraren.

    För att detta ska fungera måste mappprofiladministratören tillåta alla användare att lägga till Schemtron-filer på valideringspanelen. Se redigeringsinställningar (skärmbild ovan)

![Välj Schematron-fil](../../../assets/authoring/schematron-rightpanel-validation-addsch.png)
![Kör validering](../../../assets/authoring/schematron-rightpanel-validation-runsch.png)


### Reglerna stöds

Den aktuella versionen av AEM stöder validering med enbart kontrollbaserade regler. (se [tillgång kontra rapport](https://schematron.com/document/205.html)) Alla regler som baseras på &quot;Rapporter&quot; stöds inte ännu.


### Exempel och mer hjälp om schematreringsregler

#### Exempel på användningsområden

- Kontrollera om en länk är extern och om den har omfånget &quot;external&quot;

  ```
  <sch:pattern>
      <sch:rule context="xref[contains(@href, 'http') or contains(@href, 'https')]">
          <sch:assert test="@scope = 'external' and @format = 'html'">
              All external xref links must be with scope='external' and format='html'
          </sch:assert>
      </sch:rule>
  </sch:pattern>
  ```

- Kontrollera om det finns minst en &quot;topicref&quot; i en karta eller minst en &quot;li&quot; under en &quot;ul&quot;

  ```
  <sch:pattern>
      <sch:rule context="map">
          <sch:assert test="count(topicref) > 0">
              There should be atleast one topicref in map
          </sch:assert>
      </sch:rule>
  
      <sch:rule context="ul">
          <sch:assert test="count(li) > 1" >
              A list must have more than one item.
          </sch:assert>
      </sch:rule>
  </sch:pattern>
  ```

- Elementet &quot;indexterm&quot; ska alltid finnas i en &quot;prolog&quot;

  ```
  <sch:pattern>
      <sch:rule context="*[contains(@class, ' topic/indexterm ')]">
          <sch:assert test="ancestor::node()/local-name() = 'prolog'">
              The indexterm element should be in a prolog.
          </sch:assert>
      </sch:rule>
  </sch:pattern>
  ```

#### Resurser

- Förstå  [Grundläggande om schematron](https://da2022.xatapult.com/#what-is-schematron)
- Mer om [Kontrollregler i schemat](https://www.xml.com/pub/a/2003/11/12/schematron.html#Assertions)
- [Exempel på schematron-fil](../../../assets/authoring/sample_schematron.sch)
