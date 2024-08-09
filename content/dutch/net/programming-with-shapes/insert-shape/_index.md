---
title: Vorm invoegen
linktitle: Vorm invoegen
second_title: Aspose.Words-API voor documentverwerking
description: Leer hoe u vormen in Word-documenten kunt invoegen en manipuleren met Aspose.Words voor .NET met onze stapsgewijze handleiding.
type: docs
weight: 10
url: /nl/net/programming-with-shapes/insert-shape/
---
## Invoering

Als het gaat om het maken van visueel aantrekkelijke en goed gestructureerde Word-documenten, kunnen vormen een cruciale rol spelen. Of u nu pijlen, kaders of zelfs complexe aangepaste vormen toevoegt, de mogelijkheid om deze elementen programmatisch te manipuleren biedt ongeëvenaarde flexibiliteit. In deze zelfstudie onderzoeken we hoe u vormen in Word-documenten kunt invoegen en manipuleren met Aspose.Words voor .NET.

## Vereisten

Voordat u in de zelfstudie duikt, moet u ervoor zorgen dat u aan de volgende vereisten voldoet:

1.  Aspose.Words voor .NET: Download en installeer de nieuwste versie van de[Aspose-releasespagina](https://releases.aspose.com/words/net/).
2. Ontwikkelomgeving: Een geschikte .NET-ontwikkelomgeving zoals Visual Studio.
3. Basiskennis van C#: Bekendheid met de programmeertaal C# en basisconcepten.

## Naamruimten importeren

Om aan de slag te gaan, moet u de benodigde naamruimten in uw C#-project importeren:

```csharp
using Aspose.Words;
using Aspose.Words.Drawing;
```

## Stap 1: Stel uw project in

Voordat u kunt beginnen met het invoegen van vormen, moet u uw project instellen en de Aspose.Words voor .NET-bibliotheek toevoegen.

1. Maak een nieuw project: Open Visual Studio en maak een nieuw C# Console Application-project.
2. Aspose.Words voor .NET toevoegen: Installeer de Aspose.Words voor .NET-bibliotheek via NuGet Package Manager.

```bash
Install-Package Aspose.Words
```

## Stap 2: Initialiseer het document

Eerst moet u een nieuw document en een documentbuilder initialiseren, die u zullen helpen bij het samenstellen van het document.

```csharp
// Pad naar uw documentmap
string dataDir = "YOUR DOCUMENT DIRECTORY";

// Initialiseer een nieuw document
Document doc = new Document();

// Initialiseer een DocumentBuilder om het document te helpen bouwen
DocumentBuilder builder = new DocumentBuilder(doc);
```

## Stap 3: Voeg een vorm in

Laten we nu een vorm in het document invoegen. We beginnen met het toevoegen van een eenvoudig tekstvak.

```csharp
// Voeg een tekstvakvorm in het document in
Shape shape = builder.InsertShape(ShapeType.TextBox, RelativeHorizontalPosition.Page, 100, RelativeVerticalPosition.Page, 100, 50, 50, WrapType.None);

// Draai de vorm
shape.Rotation = 30.0;
```

In dit voorbeeld voegen we een tekstvak in op de positie (100, 100) met een breedte en hoogte van elk 50 eenheden. We roteren de vorm ook 30 graden.

## Stap 4: Voeg nog een vorm toe

Laten we nog een vorm aan het document toevoegen, dit keer zonder de positie op te geven.

```csharp
// Voeg nog een tekstvakvorm toe
Shape secondShape = builder.InsertShape(ShapeType.TextBox, 50, 50);

// Draai de vorm
secondShape.Rotation = 30.0;
```

Dit codefragment voegt een ander tekstvak in met dezelfde afmetingen en rotatie als het eerste, maar zonder de positie ervan te specificeren.

## Stap 5: Bewaar het document

 Na het toevoegen van de vormen is de laatste stap het opslaan van het document. Wij gebruiken de`OoxmlSaveOptions` om het opslagformaat op te geven.

```csharp
// Definieer opslagopties met naleving
OoxmlSaveOptions saveOptions = new OoxmlSaveOptions(SaveFormat.Docx)
{
    Compliance = OoxmlCompliance.Iso29500_2008_Transitional
};

// Bewaar het document
doc.Save(dataDir + "WorkingWithShapes.InsertShape.docx", saveOptions);
```

## Conclusie

En daar heb je het! U hebt met succes vormen in een Word-document ingevoegd en gemanipuleerd met Aspose.Words voor .NET. In deze zelfstudie werd de basis behandeld, maar Aspose.Words biedt nog veel meer geavanceerde functies voor het werken met vormen, zoals aangepaste stijlen, verbindingslijnen en groepsvormen.

 Voor meer gedetailleerde informatie, bezoek de[Aspose.Words voor .NET-documentatie](https://reference.aspose.com/words/net/).

## Veelgestelde vragen

### Hoe voeg ik verschillende soorten vormen in?
 kunt de`ShapeType` in de`InsertShape` methode om verschillende soorten vormen in te voegen, zoals cirkels, rechthoeken en pijlen.

### Kan ik tekst toevoegen aan de vormen?
 Ja, u kunt gebruik maken van de`builder.Write` methode om tekst in de vormen toe te voegen nadat ze zijn ingevoegd.

### Is het mogelijk om de vormen te stylen?
 Ja, u kunt de vormen opmaken door eigenschappen in te stellen, zoals`FillColor`, `StrokeColor` , En`StrokeWeight`.

### Hoe positioneer ik vormen ten opzichte van andere elementen?
 Gebruik de`RelativeHorizontalPosition`En`RelativeVerticalPosition` eigenschappen om vormen ten opzichte van andere elementen in het document te positioneren.

### Kan ik meerdere vormen groeperen?
 Ja, met Aspose.Words voor .NET kunt u vormen groeperen met behulp van de`GroupShape` klas.