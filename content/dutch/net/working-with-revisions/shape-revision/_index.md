---
title: Vormrevisie
linktitle: Vormrevisie
second_title: Aspose.Words-API voor documentverwerking
description: Herzie vormen in een Word-document met Aspose.Words voor .NET.
type: docs
weight: 10
url: /nl/net/working-with-revisions/shape-revision/
---

In deze stapsgewijze handleiding laten we u zien hoe u revisies kunt aanbrengen in vormen in een Word-document met Aspose.Words voor .NET. We voorzien u van de volledige broncode en laten u zien hoe u de markdown-uitvoer kunt formatteren.

## Stap 1: Het document maken en vormen toevoegen

De eerste stap is het maken van een nieuw document en het toevoegen van vormen.

```csharp
Document doc = new Document();
Assert.False(doc.TrackRevisions);

Shape shape = new Shape(doc, ShapeType.Cube);
shape. WrapType = WrapType. Inline;
shape. Width = 100.0;
shape. Height = 100.0;
doc.FirstSection.Body.FirstParagraph.AppendChild(shape);
```

## Stap 2: Houd revisies bij en voeg een andere vorm toe

We schakelen het bijhouden van revisies in en voegen een andere vorm toe.

```csharp
doc.StartTrackRevisions("John Doe");

shape = new Shape(doc, ShapeType.Sun);
shape. WrapType = WrapType. Inline;
shape. Width = 100.0;
shape. Height = 100.0;
doc.FirstSection.Body.FirstParagraph.AppendChild(shape);
```

## Stap 3: Haal de vormcollectie op en controleer op herzieningen

We halen de verzameling vormen uit het document en controleren de revisies die aan elke vorm zijn gekoppeld.

```csharp
List<Shape> shapes = doc.GetChildNodes(NodeType.Shape, true).Cast<Shape>().ToList();
Assert.AreEqual(2, shapes.Count);

Assert.AreEqual(ShapeType.Cube, shapes[0].ShapeType);
Assert.True(shapes[0].IsDeleteRevision);

Assert.AreEqual(ShapeType.Sun, shapes[1].ShapeType);
Assert.True(shapes[1].IsInsertRevision);
```

## Stap 4: Revisies van vormverplaatsingen controleren

We gaan een bestaand document laden dat revisies van vormverplaatsingen bevat en de bijbehorende revisies controleren.

```csharp
doc = new Document(MyDir + "Revision shape.docx");

shapes = doc.GetChildNodes(NodeType.Shape, true).Cast<Shape>().ToList();
Assert.AreEqual(2, shapes.Count);

Assert. False(shapes[0].IsMoveFromRevision);
Assert.True(shapes[0].IsMoveToRevision);

Assert.True(shapes[1].IsMoveFromRevision);
Assert. False(shapes[1].IsMoveToRevision);
```

### Voorbeeldbroncode voor Shape Revision met Aspose.Words voor .NET

Hier is de volledige broncode voor het maken van herzieningen van vormen in een document met Aspose.Words voor .NET:

```csharp
Document doc = new Document();

//Voeg een inlinevorm in zonder revisies bij te houden.
Assert.False(doc.TrackRevisions);
Shape shape = new Shape(doc, ShapeType.Cube);
shape.WrapType = WrapType.Inline;
shape.Width = 100.0;
shape.Height = 100.0;
doc.FirstSection.Body.FirstParagraph.AppendChild(shape);

// Begin met het bijhouden van revisies en voeg vervolgens een andere vorm in.
doc.StartTrackRevisions("John Doe");
shape = new Shape(doc, ShapeType.Sun);
shape.WrapType = WrapType.Inline;
shape.Width = 100.0;
shape.Height = 100.0;
doc.FirstSection.Body.FirstParagraph.AppendChild(shape);

// Haal de vormencollectie van het document op, die alleen de twee vormen bevat die we hebben toegevoegd.
List<Shape> shapes = doc.GetChildNodes(NodeType.Shape, true).Cast<Shape>().ToList();
Assert.AreEqual(2, shapes.Count);

// Verwijder de eerste vorm.
shapes[0].Remove();

// Omdat we die vorm hebben verwijderd terwijl de wijzigingen werden bijgehouden, telt de vorm als een verwijderingsrevisie.
Assert.AreEqual(ShapeType.Cube, shapes[0].ShapeType);
Assert.True(shapes[0].IsDeleteRevision);

// En we hebben een andere vorm ingevoegd terwijl we de wijzigingen bijhielden, zodat die vorm telt als een invoegrevisie.
Assert.AreEqual(ShapeType.Sun, shapes[1].ShapeType);
Assert.True(shapes[1].IsInsertRevision);

// Het document heeft één vorm die is verplaatst, maar revisies van vormverplaatsingen zullen twee exemplaren van die vorm bevatten.
// De ene is de vorm op de aankomstbestemming en de andere is de vorm op de oorspronkelijke locatie.
doc = new Document(MyDir + "Revision shape.docx");

shapes = doc.GetChildNodes(NodeType.Shape, true).Cast<Shape>().ToList();
Assert.AreEqual(2, shapes.Count);

// Dit is de stap naar herziening, ook de vorm op de aankomstbestemming.
Assert.False(shapes[0].IsMoveFromRevision);
Assert.True(shapes[0].IsMoveToRevision);

// Dit is de stap van revisie, namelijk de vorm op de oorspronkelijke locatie.
Assert.True(shapes[1].IsMoveFromRevision);
Assert.False(shapes[1].IsMoveToRevision);
```

## Conclusie

In deze zelfstudie hebben we geleerd hoe u vormen in een Word-document kunt wijzigen met behulp van Aspose.Words voor .NET. Door de stappen te volgen voor het maken van het document, het bijhouden van revisies in te schakelen, de revisies te controleren die aan elke vorm zijn gekoppeld en de revisies te controleren op het verplaatsen van de vormen, konden we de revisies met succes beheren. Aspose.Words voor .NET biedt een krachtige API voor woordenverwerking met recensies en formulieren in Word-documenten.

### Veelgestelde vragen

#### Vraag: Hoe kan ik een nieuw document maken en vormen toevoegen in Aspose.Words voor .NET?

A: Om een nieuw document te maken en vormen toe te voegen in Aspose.Words voor .NET, kunt u de volgende code gebruiken. Hier voegen we twee vormen, een kubus en een zon, toe aan het eerste gedeelte van het document:

```csharp
Document doc = new Document();
Assert.False(doc.TrackRevisions);

Shape shape = new Shape(doc, ShapeType.Cube);
shape. WrapType = WrapType. Inline;
shape. Width = 100.0;
shape. Height = 100.0;
doc.FirstSection.Body.FirstParagraph.AppendChild(shape);
```

#### Vraag: Hoe schakel ik het bijhouden van revisies in Aspose.Words voor .NET in?

 A: Om het bijhouden van revisies in Aspose.Words voor .NET in te schakelen, kunt u de`StartTrackRevisions` werkwijze van de`Document` voorwerp. Deze methode gebruikt de naam van de auteur van de revisies als parameter:

```csharp
doc.StartTrackRevisions("John Doe");
```

#### Vraag: Hoe kan ik de revisies controleren die aan elke vorm in een Aspose.Words voor .NET-document zijn gekoppeld?

A: Om de revisies te controleren die aan elke vorm in een Aspose.Words voor .NET-document zijn gekoppeld, kunt u de verzameling vormen van het document ophalen met behulp van de`GetChildNodes` methode met de`NodeType.Shape` knooppunttype. Vervolgens hebt u toegang tot de vormen van elke vorm`IsDeleteRevision`, `IsInsertRevision`, `IsMoveFromRevision` , En`IsMoveToRevision` eigenschappen om te bepalen welk type revisie aan de vorm is gekoppeld:

```csharp
List<Shape> shapes = doc.GetChildNodes(NodeType.Shape, true).Cast<Shape>().ToList();
Assert.AreEqual(2, shapes.Count);

Assert.AreEqual(ShapeType.Cube, shapes[0].ShapeType);
Assert.True(shapes[0].IsDeleteRevision);

Assert.AreEqual(ShapeType.Sun, shapes[1].ShapeType);
Assert.True(shapes[1].IsInsertRevision);
```

#### Vraag: Hoe kan ik controleren op verplaatsingsrevisies van vormen in een Aspose.Words voor .NET-document?

 A: Om te controleren op revisies van vormverplaatsingen in een Aspose.Words voor .NET-document, kunt u een bestaand document laden dat revisies van vormverplaatsingen bevat. Vervolgens hebt u toegang tot de vormen van elke vorm`IsMoveFromRevision`En`IsMoveToRevision` eigenschappen om te bepalen of het wordt verplaatst en zo ja, van waar en naar waar:

```csharp
doc = new Document(MyDir + "Revision shape.docx");

shapes = doc.GetChildNodes(NodeType.Shape, true).Cast<Shape>().ToList();
Assert.AreEqual(2, shapes.Count);

Assert. False(shapes[0].IsMoveFromRevision);
Assert.True(shapes[0].IsMoveToRevision);

Assert.True(shapes[1].IsMoveFromRevision);
Assert. False(shapes[1].IsMoveToRevision);
```