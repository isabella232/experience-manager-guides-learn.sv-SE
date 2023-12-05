---
title: Skapa kartor baserade på anpassade mallar
description: Lär dig att skapa en egen mall, använda dem för att skapa nya kartfiler och skicka den definierade titeln till en DITA-karta i AEM.
source-git-commit: 880cd344ceb65ea339be699ebcad41c0d62e168a
workflow-type: tm+mt
source-wordcount: '1103'
ht-degree: 0%

---

# Skapa kartor baserade på anpassade mallar {#id225VF0808MP}

Du kan skapa anpassade mappningsmallar och använda dem för att skapa DITA-kartor tillsammans med ämnesmallarna och mappningsmallarna som refereras i kartmallen

Du kan referera till andra mappningsmallar och ämnesmallar från den anpassade mappningsmallen. De refererade mappningsmallarna kan hänvisa till olika mappningsmallar, ämnesmallar, ämnen, kartor, bilder, videor och andra resurser. Den anpassade mappningsmallen kan hjälpa dig att enkelt replikera mappningsmallarna och hela den refererade mappstrukturen. Dessa anpassade mallar är särskilt användbara när du vill skapa och återskapa flera kartor med rekursiva strukturer och referenser.

>[!NOTE]
>
> Ämnesmallar skapas inte rekursivt. Det är bara ämnesmallar som är direkt inuti mappningsmallen som genereras och alla ämnesmallar i en ämnesmall som refereras direkt till i den överordnade mallen.

## Skapa anpassade mallar

Med AEM Guides kan du skapa anpassade kartor och ämnen från mappen Dita-templates. Du kan använda de här anpassade mallarna för att skapa en karta och ett ämne. Du kan också dela mallarna med författarna och de kan använda dem för att skapa sina filer. Med hjälp av de här mallarna kan du tillåta författarna att behålla separata kopior av vissa resurser som finns i mallmappen.

>[!NOTE]
>
> Alla resurser som bara ska refereras och behållas över måste hållas utanför mallmappen.


Du kan skapa mappnings- och ämnesmallar på följande sätt:
1. Mallrutan i [Vänster panel](./web-editor-features.md#left-panel-id2051ea0m0hs)
1. [Mallar i resursgränssnitt](#templates-assets-ui)
1. [Alternativ-menyn](#templates-in-assets-ui)

### Mallar i resursgränssnitt {#templates-assets-ui}

**Ämnesmall**

Så här skapar du en ämnesmall:

1. I **Resursgränssnitt** navigera till mappen Dita-templates.

   ![](images/dita-templates.png){width="800" align="left"}

1. Klicka **ämnen** mapp att öppna.Klicka på **Skapa \> DITA-mall**.
1. På sidan för utkast väljer du **Ämne** och sedan klicka **Nästa.**
1. På sidan Egenskaper anger du ämnesmallen **Titel**.
1. Ange filen **Namn**

   >[!NOTE]
   >
   > Filnamnet måste ha filtillägget .dita.

1. \(Valfritt\) Lägg till en beskrivning.
1. Klicka **Skapa**. Meddelandet Ämnesmallen som skapas visas. Du kan sedan öppna ämnesmallen och redigera den.

**Kartmall**

Så här skapar du en mappningsmall:

1. I **Resursgränssnitt** navigera till mappen Dita-templates.
1. Klicka **kartor** för att öppna den.
1. Klicka **Skapa DITA-mall \>.**

   ![](images/create-dita-template.png){width="300" align="left"}

1. På sidan för utkast väljer du **Karta** och klicka **Nästa**.
1. Ange kartmallen på sidan Egenskaper **Titel**.
1. Ange filen **Namn**.

   >[!NOTE]
   >
   > Filnamnet måste ha filtillägget .ditamap.

1. (Valfritt\) Lägg till en beskrivning.Klicka på **Skapa**. Meddelandet som du skapade med kartmallen visas. Du kan sedan öppna mappningsmallen och redigera den. Du kan lägga till referenser för ämnesmallarna, mappningsmallarna och andra resurser i mappningsmallen.

### Alternativ-menyn {#options-menu}

Så här skapar du en karta eller ämnesmall:

1. Välj **Karta** eller **Ämne** i den aktuella mallmappen. Till exempel, mappen `dita-templates`.
1. Från **Alternativ** meny, välja **Skapa kartmall** eller **Skapa ämnesmall**.

   The **Skapa ny mappningsmall** eller **Skapa ny ämnesmall** öppnas.
1. Ange den nya mallens rubrik och namn.
1. Välj den typ av mall som du vill skapa från **Mall** listruta.

Meddelandet som du skapade med kartmallen visas. Du kan lägga till mallen i din globala profil eller mappnivåprofil. Den nya mallen visas sedan i processen för att skapa avsnitt eller kartor och du kan skapa kartor eller ämnen med hjälp av den.


Administratören kan också skapa en mapp och konfigurera den så att den blir den mapp där du kan skapa och spara mallarna.

Lär dig hur du konfigurerar en anpassad sökväg till en DITA-mallmapp baserat på konfigurationen:
<details>
    <summary> Cloud Service </summary>

Lär dig hur [konfigurera anpassad sökväg till DITA-mallmapp](../install-guide/conf-template-tags-custom-dita-topic-template.md#configure-custom-dita-template-folder-path-id191lcf0095z) i Cloud Servicens installations- och konfigureringshandbok.
</details>

<details>
    <summary> Lokal programvara</summary>

Lär dig hur [konfigurera anpassad sökväg till DITA-mallmapp](../cs-install-guide/conf-template-tags-custom-dita-topic-template.md#configure-custom-dita-template-folder-path-id191lcf0095z) i Installations- och konfigureringshandboken på plats.
</details>

## Skicka den titel som definieras i mallarna

Om du vill skicka titeln för det ämne eller den karta som används i mallen till DITA-kartor som skapats med den mallen använder du klammerparenteser runt titeln.

Exempel

```XML
<pubtitle>
   <mainpubtitle outputclass="booktitle">
   {title}
   </mainpubtitle>
   <subtitle>Subtitle</subtitle>
</pubtitle>

The resultant DITA map with title "Rootmap1" will look like as follows:
<pubtitle>
   <mainpubtitle outputclass="booktitle">Rootmap1
   </mainpubtitle>
   <subtitle>Subtitle</subtitle>
</pubtitle>
```

>[!NOTE]
> Endast den första förekomsten av klammerparenteser ersätts med rubrik.

Om du inte använder klammerparenteser runt titeln kommer den resulterande DITA-kartan endast att plockas ut med det första elementet och kapslingen av titeln kommer inte att plockas från mallen och ser ut så här:

```XML
<pubtitle> Rootmap1 </pubtitle>
```

>[!NOTE]
> Du kan också använda klammerparenteserna runt texten för att överföra den kapslade strukturen från de anpassade mallarna till dina DITA-kartor.

Exempel

```XML
<title>    
    <sub>        
        <b>{title}</b>    
    </sub>
</title>
```




## Använd kartmallen för att skapa nya kartor

>[!NOTE]
>
> Kartmallen måste konfigureras och göras tillgänglig för redigering av administratören. Mer information finns i *Konfigurera redigeringsmallar* i avsnittet Installera och konfigurera Adobe Experience Manager Guides as a Cloud Service.

Så här skapar du en karta med hjälp av den anpassade mappningsmallen:

1. I **Resursgränssnitt,** navigera till den mapp där du vill skapa kartan.
1. Klicka **Skapa \> DITA-karta**.
1. På sidan Design väljer du den kartmall som du vill använda och klickar på **Nästa**. Om du t.ex. har skapat en mappningsmall som är &quot;test-template&quot;, markerar du den.
1. Ange kartan på sidan Egenskaper **Titel**.
1. Ange filen **Namn**.

   >[!NOTE]
   >
   > Filnamnet måste ha filtillägget .ditamap.

1. Klicka **Skapa**. Det meddelande som kartan skapade visas.


Kartan genererar alla resurser som refereras till inuti mallmappen. En del typer av tillgångar som refereras till på en karta kan vara följande:

- Om kartan innehåller referensen till en ämnesmall skapas en kopia av den i mappen, i samma hierarki som i ämnesmappen i `dita-templates` mapp.
- Om kartan innehåller referensen till en mappningsmall skapas en kopia av den i mappen, i samma hierarki som i mappningsmappen i `dita-templates` mapp.
- Om kartan innehåller den generiska referensen till ett ämne eller en karta utanför `dita-templates/topics` eller `dita-templates/maps` mapp, det är bara samma som refereras och ingen kopia skapas.

  >[!NOTE]
  >
  > `dita-templates/topics` och `dita-templates/maps` är standardsökvägarna i stödlinjerna och kan konfigureras.


  Om det finns en ämnesmallnyckeldefinition inuti mappningsmallen skapas en ny nyckel \(därför nytt ämne\) som refereras till på kartan.

- Om en annan karta eller ett annat ämne skapas på samma nivå i mappen läggs namnen på de nyskapade resurserna till med 0,1,2 och så vidare. Du kan välja att öppna kartan för redigering eller spara kartfilen i databasen.

**Överordnat ämne:**[ Arbeta med kartredigeraren](map-editor.md)
