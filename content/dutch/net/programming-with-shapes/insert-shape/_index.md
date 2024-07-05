---
title: Vorm invoegen
linktitle: Vorm invoegen
second_title: Aspose.Words-API voor documentverwerking
description: Leer hoe u vormen invoegt in een Word-document met Aspose.Words voor .NET.
type: docs
weight: 10
url: /nl/net/programming-with-shapes/insert-shape/
---

In deze zelfstudie wordt uitgelegd hoe u vormen in een Word-document kunt invoegen met Aspose.Words voor .NET. Vormen kunnen worden gebruikt om het visuele uiterlijk en de lay-out van uw documenten te verbeteren.

## Vereisten
Om deze tutorial te volgen, heb je het volgende nodig:

- Aspose.Words voor .NET-bibliotheek geïnstalleerd.
- Basiskennis van C# en woordenverwerking met Word-documenten.

## Stap 1: Stel de documentmap in
 Begin met het instellen van het pad naar uw documentmap. Vervangen`"YOUR DOCUMENT DIRECTORY"` met het daadwerkelijke pad naar de map waar u het document wilt opslaan.

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## Stap 2: Maak een nieuw document en DocumentBuilder
 Maak een nieuw exemplaar van de`Document` klasse en een`DocumentBuilder`bezwaar maken tegen het werken met het document.

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
```

## Stap 3: Vormen invoegen
 Gebruik de`InsertShape` werkwijze van de`DocumentBuilder`object om vormen in het document in te voegen. Geef het vormtype, de relatieve horizontale en verticale posities, de pagina-afmetingen, het formaat en het teruglooptype op. Indien gewenst kunt u ook de rotatiehoek van de vormen instellen.

```csharp
Shape shape = builder.InsertShape(ShapeType.TextBox, RelativeHorizontalPosition.Page, 100,
	RelativeVerticalPosition.Page, 100, 50, 50, WrapType.None);
shape.Rotation = 30.0;
builder.Writeln();
shape = builder.InsertShape(ShapeType.TextBox, 50, 50);
shape.Rotation = 30.0;
```

## Stap 4: Sla het document op
 Sla het document op in de opgegeven map met behulp van de`Save` methode. Geef de gewenste bestandsnaam op met de juiste bestandsextensie. In dit voorbeeld slaan we het document op als "WorkingWithShapes.InsertShape.docx".

```csharp
OoxmlSaveOptions saveOptions = new OoxmlSaveOptions(SaveFormat.Docx)
{
	Compliance = OoxmlCompliance.Iso29500_2008_Transitional
};
doc.Save(dataDir + "WorkingWithShapes.InsertShape.docx", saveOptions);
```

### Voorbeeldbroncode voor Shape invoegen met Aspose.Words voor .NET 

```csharp
	// Pad naar uw documentmap
	string dataDir = "YOUR DOCUMENT DIRECTORY";

	Document doc = new Document();
	DocumentBuilder builder = new DocumentBuilder(doc);
	Shape shape = builder.InsertShape(ShapeType.TextBox, RelativeHorizontalPosition.Page, 100,
		RelativeVerticalPosition.Page, 100, 50, 50, WrapType.None);
	shape.Rotation = 30.0;
	builder.Writeln();
	shape = builder.InsertShape(ShapeType.TextBox, 50, 50);
	shape.Rotation = 30.0;
	OoxmlSaveOptions saveOptions = new OoxmlSaveOptions(SaveFormat.Docx)
	{
		Compliance = OoxmlCompliance.Iso29500_2008_Transitional
	};
	doc.Save(dataDir + "WorkingWithShapes.InsertShape.docx", saveOptions);
```

Dat is het! U hebt met succes vormen in uw Word-document ingevoegd met Aspose.Words voor .NET.