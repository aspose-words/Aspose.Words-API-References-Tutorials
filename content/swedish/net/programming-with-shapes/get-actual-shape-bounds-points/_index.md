---
title: Få faktiska Shape Bounds-poäng
linktitle: Få faktiska Shape Bounds-poäng
second_title: Aspose.Words Document Processing API
description: Lär dig hur du hämtar de faktiska gränserna för en form i punkter (måttenhet) i ett Word-dokument med Aspose.Words för .NET.
type: docs
weight: 10
url: /sv/net/programming-with-shapes/get-actual-shape-bounds-points/
---

Denna handledning förklarar hur man hämtar de faktiska gränserna för en form i punkter (måttenhet) i ett Word-dokument med Aspose.Words för .NET. Gränserna representerar storleken och positionen för formen i dokumentet.

## Förutsättningar
För att följa denna handledning måste du ha följande:

- Aspose.Words för .NET-biblioteket installerat.
- Grundläggande kunskaper i C# och ordbehandling med Word-dokument.

## Steg 1: Skapa ett nytt dokument och DocumentBuilder
 Skapa en ny instans av`Document` klass och a`DocumentBuilder`objekt för att arbeta med dokumentet.

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
```

## Steg 2: Infoga en bildform
 Använd`InsertImage` metod för`DocumentBuilder` objekt för att infoga en bildform i dokumentet. Ange sökvägen till bildfilen som en parameter.

```csharp
Shape shape = builder.InsertImage(ImagesDir + "Transparent background logo.png");
shape.AspectRatioLocked = false;
```

## Steg 3: Hämta faktiska Shape Bounds Points
 Få tillgång till formens`ShapeRenderer` använda`GetShapeRenderer` metod. Hämta sedan formens faktiska gränser i punkter med hjälp av`BoundsInPoints` fast egendom.

```csharp
Console.Write("\nGets the actual bounds of the shape in points: ");
Console.WriteLine(shape.GetShapeRenderer().BoundsInPoints);
```


### Exempel på källkod för Get Actual Shape Bounds Points med Aspose.Words för .NET 

```csharp
	Document doc = new Document();
	DocumentBuilder builder = new DocumentBuilder(doc);
	Shape shape = builder.InsertImage(ImagesDir + "Transparent background logo.png");
	shape.AspectRatioLocked = false;
	Console.Write("\nGets the actual bounds of the shape in points: ");
	Console.WriteLine(shape.GetShapeRenderer().BoundsInPoints);
```

Det är allt! Du har framgångsrikt hämtat de faktiska gränserna för en form i punkter i ditt Word-dokument med Aspose.Words för .NET.