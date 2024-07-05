---
title: Ontvang werkelijke vormgrenspunten
linktitle: Ontvang werkelijke vormgrenspunten
second_title: Aspose.Words-API voor documentverwerking
description: Leer hoe u de werkelijke grenzen van een vorm in punten (meeteenheid) kunt ophalen in een Word-document met behulp van Aspose.Words voor .NET.
type: docs
weight: 10
url: /nl/net/programming-with-shapes/get-actual-shape-bounds-points/
---

In deze tutorial wordt uitgelegd hoe u de werkelijke grenzen van een vorm in punten (meeteenheid) in een Word-document kunt ophalen met behulp van Aspose.Words voor .NET. De grenzen vertegenwoordigen de grootte en positie van de vorm in het document.

## Vereisten
Om deze tutorial te volgen, heb je het volgende nodig:

- Aspose.Words voor .NET-bibliotheek geïnstalleerd.
- Basiskennis van C# en woordenverwerking met Word-documenten.

## Stap 1: Maak een nieuw document en DocumentBuilder
 Maak een nieuw exemplaar van de`Document` klasse en een`DocumentBuilder`bezwaar maken tegen het werken met het document.

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
```

## Stap 2: Voeg een afbeeldingsvorm in
 Gebruik de`InsertImage` werkwijze van de`DocumentBuilder` object om een afbeeldingsvorm in het document in te voegen. Geef het pad naar het afbeeldingsbestand op als parameter.

```csharp
Shape shape = builder.InsertImage(ImagesDir + "Transparent background logo.png");
shape.AspectRatioLocked = false;
```

## Stap 3: Haal de werkelijke vormgrenspunten op
 Toegang tot de vorm`ShapeRenderer` de ... gebruiken`GetShapeRenderer` methode. Haal vervolgens de werkelijke grenzen van de vorm op in punten met behulp van de`BoundsInPoints` eigendom.

```csharp
Console.Write("\nGets the actual bounds of the shape in points: ");
Console.WriteLine(shape.GetShapeRenderer().BoundsInPoints);
```


### Voorbeeldbroncode voor Get Actual Shape Bounds Points met Aspose.Words voor .NET 

```csharp
	Document doc = new Document();
	DocumentBuilder builder = new DocumentBuilder(doc);
	Shape shape = builder.InsertImage(ImagesDir + "Transparent background logo.png");
	shape.AspectRatioLocked = false;
	Console.Write("\nGets the actual bounds of the shape in points: ");
	Console.WriteLine(shape.GetShapeRenderer().BoundsInPoints);
```

Dat is het! U hebt met succes de werkelijke grenzen van een vorm in punten in uw Word-document opgehaald met Aspose.Words voor .NET.