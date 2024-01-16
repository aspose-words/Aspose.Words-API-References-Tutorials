---
title: Groepsvorm toevoegen
linktitle: Groepsvorm toevoegen
second_title: Aspose.Words-API voor documentverwerking
description: Leer hoe u een groepsvorm met meerdere vormen aan een Word-document kunt toevoegen met Aspose.Words voor .NET.
type: docs
weight: 10
url: /nl/net/programming-with-shapes/add-group-shape/
---

In deze zelfstudie wordt uitgelegd hoe u een groepsvorm met meerdere vormen aan een Word-document kunt toevoegen met Aspose.Words voor .NET. Met groepsvormen kunt u meerdere vormen als één geheel combineren en manipuleren.

## Vereisten
Om deze tutorial te volgen, heb je het volgende nodig:

- Aspose.Words voor .NET-bibliotheek geïnstalleerd.
- Basiskennis van C# en woordenverwerking met Word-documenten.

## Stap 1: Stel de documentmap in
 Begin met het instellen van het pad naar uw documentmap. Vervangen`"YOUR DOCUMENT DIRECTORY"` met het daadwerkelijke pad naar de map waar u het document wilt opslaan.

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## Stap 2: Maak een nieuw document en GroupShape
 Maak een nieuw exemplaar van de`Document` klasse en`GroupShape` bezwaar maken tegen het werken met het document.

```csharp
Document doc = new Document();
doc.EnsureMinimum();
GroupShape groupShape = new GroupShape(doc);
```

## Stap 3: Vormen maken en toevoegen aan de GroupShape
 Creëer individuele vormen zoals`accentBorderShape` En`actionButtonShape` de ... gebruiken`Shape` klas. Pas hun eigenschappen naar wens aan. Voeg deze vormen toe aan de`groupShape` voorwerp.

```csharp
Shape accentBorderShape = new Shape(doc, ShapeType.AccentBorderCallout1) { Width = 100, Height = 100 };
groupShape.AppendChild(accentBorderShape);

Shape actionButtonShape = new Shape(doc, ShapeType.ActionButtonBeginning)
{
    Left = 100,
    Width = 100,
    Height = 200
};
groupShape.AppendChild(actionButtonShape);
```

## Stap 4: Stel afmetingen in voor de GroupShape
 Stel de breedte, hoogte en coördinaatgrootte in voor de`groupShape`.

```csharp
groupShape.Width = 200;
groupShape.Height = 200;
groupShape.CoordSize = new Size(200, 200);
```

## Stap 5: Plaats de GroupShape in het document
 Maak een`DocumentBuilder` object en plaats de`groupShape` in het document met behulp van de`InsertNode` methode.

```csharp
DocumentBuilder builder = new DocumentBuilder(doc);
builder.InsertNode(groupShape);
```

## Stap 6: Sla het document op
 Sla het document op in de opgegeven map met behulp van de`Save`methode. Geef de gewenste bestandsnaam op met de juiste bestandsextensie. In dit voorbeeld slaan we het document op als "WorkingWithShapes.AddGroupShape.docx".

```csharp
doc.Save(dataDir + "WorkingWithShapes.AddGroupShape.docx");
```

### Voorbeeldbroncode voor het toevoegen van groepsvorm met Aspose.Words voor .NET 

```csharp
	// Pad naar uw documentmap
	string dataDir = "YOUR DOCUMENT DIRECTORY";

	Document doc = new Document();
	doc.EnsureMinimum();
	GroupShape groupShape = new GroupShape(doc);
	Shape accentBorderShape = new Shape(doc, ShapeType.AccentBorderCallout1) { Width = 100, Height = 100 };
	groupShape.AppendChild(accentBorderShape);
	Shape actionButtonShape = new Shape(doc, ShapeType.ActionButtonBeginning)
	{
		Left = 100, Width = 100, Height = 200
	};
	groupShape.AppendChild(actionButtonShape);
	groupShape.Width = 200;
	groupShape.Height = 200;
	groupShape.CoordSize = new Size(200, 200);
	DocumentBuilder builder = new DocumentBuilder(doc);
	builder.InsertNode(groupShape);
	doc.Save(dataDir + "WorkingWithShapes.AddGroupShape.docx");
```

Dat is het! U hebt met succes een groepsvorm met meerdere vormen aan uw Word-document toegevoegd met Aspose.W