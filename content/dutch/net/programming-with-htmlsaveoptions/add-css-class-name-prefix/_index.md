---
title: Voeg het voorvoegsel van de CSS-klassenaam toe
linktitle: Voeg het voorvoegsel van de CSS-klassenaam toe
second_title: Aspose.Words-API voor documentverwerking
description: Leer hoe u een CSS-klassenaamvoorvoegsel kunt toevoegen bij het opslaan van Word-documenten als HTML met Aspose.Words voor .NET. Inclusief stapsgewijze handleiding, codefragmenten en veelgestelde vragen.
type: docs
weight: 10
url: /nl/net/programming-with-htmlsaveoptions/add-css-class-name-prefix/
---
## Invoering

Welkom! Als je in de wereld van Aspose.Words voor .NET duikt, staat je iets lekkers te wachten. Vandaag onderzoeken we hoe u een CSS-klassenaamvoorvoegsel kunt toevoegen bij het opslaan van een Word-document als HTML met Aspose.Words voor .NET. Deze functie is superhandig als u klassenaamconflicten in uw HTML-bestanden wilt voorkomen.

## Vereisten

Voordat we beginnen, zorg ervoor dat u over het volgende beschikt:

-  Aspose.Words voor .NET: Als je het nog niet hebt geïnstalleerd,[download het hier](https://releases.aspose.com/words/net/).
- Ontwikkelomgeving: Visual Studio of een andere C# IDE.
-  Een Word-document: we gebruiken een document met de naam`Rendering.docx`. Plaats het in uw projectmap.

## Naamruimten importeren

Zorg er eerst voor dat de benodigde naamruimten in uw C#-project zijn geïmporteerd. Voeg deze toe bovenaan uw codebestand:

```csharp
using System;
using Aspose.Words;
using Aspose.Words.Saving;
```

Laten we nu eens in de stapsgewijze handleiding duiken!

## Stap 1: Stel uw project in

Voordat we kunnen beginnen met het toevoegen van een CSS-klassenaamvoorvoegsel, gaan we eerst ons project opzetten.

### Stap 1.1: Maak een nieuw project

 Start uw Visual Studio en maak een nieuw Console App-project. Noem het iets pakkends, bijvoorbeeld`AsposeCssPrefixExample`.

### Stap 1.2: Aspose.Words toevoegen voor .NET

Voeg Aspose.Words voor .NET toe aan uw project via NuGet als u dat nog niet heeft gedaan. Open eenvoudigweg de NuGet Package Manager Console en voer het volgende uit:

```bash
Install-Package Aspose.Words
```

Geweldig! Nu zijn we klaar om te beginnen met coderen.

## Stap 2: Laad uw document

Het eerste dat we moeten doen is het Word-document laden dat we naar HTML willen converteren.

### Stap 2.1: Definieer het documentpad

 Stel het pad naar uw documentmap in. Laten we voor deze zelfstudie aannemen dat uw document zich in een map met de naam bevindt`Documents` in uw projectmap.

```csharp
string dataDir = @"C:\YourProject\Documents\";
```

### Stap 2.2: Laad het document

Laten we nu het document laden met Aspose.Words:

```csharp
Document doc = new Document(dataDir + "Rendering.docx");
```

## Stap 3: Configureer HTML-opslagopties

Vervolgens moeten we de HTML-opslagopties configureren om een CSS-klassenaamvoorvoegsel op te nemen.

### Stap 3.1: Creëer HTML-opslagopties

 Instantieer de`HtmlSaveOptions` object en stel het CSS-stijlbladtype in op`External`.

```csharp
HtmlSaveOptions saveOptions = new HtmlSaveOptions
{
    CssStyleSheetType = CssStyleSheetType.External
};
```

### Stap 3.2: Stel het CSS-klassenaamvoorvoegsel in

 Laten we nu de`CssClassNamePrefix` eigenschap naar het gewenste voorvoegsel. Voor dit voorbeeld gebruiken we`"pfx_"`.

```csharp
saveOptions.CssClassNamePrefix = "pfx_";
```

## Stap 4: Sla het document op als HTML

Laten we ten slotte het document opslaan als een HTML-bestand met onze geconfigureerde opties.


Geef het HTML-uitvoerbestandspad op en sla het document op.

```csharp
doc.Save(dataDir + "WorkingWithHtmlSaveOptions.AddCssClassNamePrefix.html", saveOptions);
```

## Stap 5: Controleer de uitvoer

 Nadat u uw project hebt uitgevoerd, navigeert u naar uw`Documents` map. Je zou een HTML-bestand moeten vinden met de naam`WorkingWithHtmlSaveOptions.AddCssClassNamePrefix.html` . Open dit bestand in een teksteditor of browser om te controleren of de CSS-klassen het voorvoegsel hebben`pfx_`.

## Conclusie

En daar heb je het! Door deze stappen te volgen, hebt u met succes een CSS-klassenaamvoorvoegsel aan uw HTML-uitvoer toegevoegd met behulp van Aspose.Words voor .NET. Met deze eenvoudige maar krachtige functie kunt u schone en conflictvrije stijlen in uw HTML-documenten behouden.

## Veelgestelde vragen

### Kan ik voor elke opslagbewerking een ander voorvoegsel gebruiken?
 Ja, u kunt het voorvoegsel elke keer dat u een document opslaat, aanpassen door de`CssClassNamePrefix` eigendom.

### Ondersteunt deze methode inline CSS?
 De`CssClassNamePrefix`property werkt met externe CSS. Voor inline CSS heb je een andere aanpak nodig.

### Hoe kan ik andere HTML-opslagopties toevoegen?
 U kunt verschillende eigenschappen van configureren`HtmlSaveOptions` om uw HTML-uitvoer aan te passen. Controleer de[documentatie](https://reference.aspose.com/words/net/) voor meer details.

### Is het mogelijk om de HTML in een stream op te slaan?
 Absoluut! U kunt het document in een stream opslaan door het streamobject door te geven aan de`Save` methode.

### Hoe krijg ik ondersteuning als ik problemen tegenkom?
 U kunt ondersteuning krijgen van de[Aspose-forum](https://forum.aspose.com/c/words/8).