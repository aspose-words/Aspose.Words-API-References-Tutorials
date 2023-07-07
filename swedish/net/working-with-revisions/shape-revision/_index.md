---
title: Formrevision
linktitle: Formrevision
second_title: Aspose.Words för .NET API Referens
description: Revidera former i ett Word-dokument med Aspose.Words för .NET.
type: docs
weight: 10
url: /sv/net/working-with-revisions/shape-revision/
---

den här steg-för-steg-guiden går vi igenom hur du gör ändringar av former i ett Word-dokument med Aspose.Words för .NET. Vi kommer att förse dig med den fullständiga källkoden och visa dig hur du formaterar markdown-utdata.

## Steg 1: Skapa dokumentet och lägga till former

Det första steget är att skapa ett nytt dokument och lägga till former.

```csharp
Document doc = new Document();
Assert.False(doc.TrackRevisions);

Shape shape = new Shape(doc, ShapeType.Cube);
shape. WrapType = WrapType. Inline;
shape. Width = 100.0;
shape. Height = 100.0;
doc.FirstSection.Body.FirstParagraph.AppendChild(shape);
```

## Steg 2: Spåra revisioner och lägg till ytterligare en form

Vi aktiverar revisionsspårning och lägger till ytterligare en form.

```csharp
doc.StartTrackRevisions("John Doe");

shape = new Shape(doc, ShapeType.Sun);
shape. WrapType = WrapType. Inline;
shape. Width = 100.0;
shape. Height = 100.0;
doc.FirstSection.Body.FirstParagraph.AppendChild(shape);
```

## Steg 3: Skaffa formsamlingen och leta efter ändringar

Vi hämtar samlingen av former från dokumentet och kontrollerar de ändringar som är kopplade till varje form.

```csharp
List<Shape> shapes = doc.GetChildNodes(NodeType.Shape, true).Cast<Shape>().ToList();
Assert.AreEqual(2, shapes.Count);

Assert.AreEqual(ShapeType.Cube, shapes[0].ShapeType);
Assert.True(shapes[0].IsDeleteRevision);

Assert.AreEqual(ShapeType.Sun, shapes[1].ShapeType);
Assert.True(shapes[1].IsInsertRevision);
```

## Steg 4: Kontrollera Shape Move-revisioner

Vi kommer att ladda ett befintligt dokument som innehåller formförskjutningsrevisioner och kontrollera de associerade revisionerna.

```csharp
doc = new Document(MyDir + "Revision shape.docx");

shapes = doc.GetChildNodes(NodeType.Shape, true).Cast<Shape>().ToList();
Assert.AreEqual(2, shapes.Count);

Assert. False(shapes[0].IsMoveFromRevision);
Assert.True(shapes[0].IsMoveToRevision);

Assert.True(shapes[1].IsMoveFromRevision);
Assert. False(shapes[1].IsMoveToRevision);
```

### Exempel på källkod för Shape Revision med Aspose.Words för .NET

Här är den fullständiga källkoden för att göra ändringar av former i ett dokument med Aspose.Words för .NET:

```csharp
Document doc = new Document();

//Infoga en inline-form utan att spåra revisioner.
Assert.False(doc.TrackRevisions);
Shape shape = new Shape(doc, ShapeType.Cube);
shape.WrapType = WrapType.Inline;
shape.Width = 100.0;
shape.Height = 100.0;
doc.FirstSection.Body.FirstParagraph.AppendChild(shape);

// Börja spåra revisioner och infoga sedan en annan form.
doc.StartTrackRevisions("John Doe");
shape = new Shape(doc, ShapeType.Sun);
shape.WrapType = WrapType.Inline;
shape.Width = 100.0;
shape.Height = 100.0;
doc.FirstSection.Body.FirstParagraph.AppendChild(shape);

// Skaffa dokumentets formsamling som bara innehåller de två formerna vi har lagt till.
List<Shape> shapes = doc.GetChildNodes(NodeType.Shape, true).Cast<Shape>().ToList();
Assert.AreEqual(2, shapes.Count);

// Ta bort den första formen.
shapes[0].Remove();

// Eftersom vi tog bort den formen medan ändringar spårades, räknas formen som en raderingsrevision.
Assert.AreEqual(ShapeType.Cube, shapes[0].ShapeType);
Assert.True(shapes[0].IsDeleteRevision);

// Och vi infogade en annan form när vi spårade ändringar, så den formen kommer att räknas som en insättningsrevision.
Assert.AreEqual(ShapeType.Sun, shapes[1].ShapeType);
Assert.True(shapes[1].IsInsertRevision);

// Dokumentet har en form som flyttades, men formflyttningsrevisioner kommer att ha två instanser av den formen.
// En kommer att vara formen vid ankomstdestinationen och den andra kommer att vara formen på sin ursprungliga plats.
doc = new Document(MyDir + "Revision shape.docx");

shapes = doc.GetChildNodes(NodeType.Shape, true).Cast<Shape>().ToList();
Assert.AreEqual(2, shapes.Count);

// Detta är övergången till revidering, även formen vid ankomstdestinationen.
Assert.False(shapes[0].IsMoveFromRevision);
Assert.True(shapes[0].IsMoveToRevision);

// Detta är övergången från revision, som är formen på sin ursprungliga plats.
Assert.True(shapes[1].IsMoveFromRevision);
Assert.False(shapes[1].IsMoveToRevision);
```

## Slutsats

den här handledningen lärde vi oss hur man gör ändringar av former i ett Word-dokument med Aspose.Words för .NET. Genom att följa stegen för att skapa dokumentet, aktivera revisionsspårning, kontrollera revisionerna som är associerade med varje form och kontrollera revisionerna för att flytta formerna, kunde vi hantera revisionerna framgångsrikt. Aspose.Words för .NET erbjuder ett kraftfullt API för att arbeta med recensioner och formulär i Word-dokument.

### FAQ's

#### F: Hur kan jag skapa ett nytt dokument och lägga till former i Aspose.Words för .NET?

S: För att skapa ett nytt dokument och lägga till former i Aspose.Words för .NET kan du använda följande kod. Här lägger vi till två former, en kub och en sol, till den första delen av dokumentet:

```csharp
Document doc = new Document();
Assert.False(doc.TrackRevisions);

Shape shape = new Shape(doc, ShapeType.Cube);
shape. WrapType = WrapType. Inline;
shape. Width = 100.0;
shape. Height = 100.0;
doc.FirstSection.Body.FirstParagraph.AppendChild(shape);
```

#### F: Hur aktiverar jag revisionsspårning i Aspose.Words för .NET?

 S: För att aktivera revisionsspårning i Aspose.Words för .NET kan du använda`StartTrackRevisions` metod för`Document` objekt. Denna metod tar namnet på författaren av revisionerna som en parameter:

```csharp
doc.StartTrackRevisions("John Doe");
```

#### F: Hur kan jag kontrollera revisionerna som är associerade med varje form i ett Aspose.Words för .NET-dokument?

S: För att kontrollera revisionerna som är kopplade till varje form i ett Aspose.Words för .NET-dokument kan du hämta dokumentets samling av former med hjälp av`GetChildNodes` metod med`NodeType.Shape` nodtyp. Sedan kan du komma åt varje form`IsDeleteRevision`, `IsInsertRevision`, `IsMoveFromRevision` , och`IsMoveToRevision` egenskaper för att avgöra vilken typ av revision som är associerad med formen:

```csharp
List<Shape> shapes = doc.GetChildNodes(NodeType.Shape, true).Cast<Shape>().ToList();
Assert.AreEqual(2, shapes.Count);

Assert.AreEqual(ShapeType.Cube, shapes[0].ShapeType);
Assert.True(shapes[0].IsDeleteRevision);

Assert.AreEqual(ShapeType.Sun, shapes[1].ShapeType);
Assert.True(shapes[1].IsInsertRevision);
```

#### F: Hur kan jag kontrollera om det finns förskjutningsrevisioner av former i ett Aspose.Words för .NET-dokument?

 S: För att leta efter formförskjutningsrevisioner i ett Aspose.Words för .NET-dokument, kan du ladda ett befintligt dokument som innehåller formförskjutningsrevisioner. Sedan kan du komma åt varje form`IsMoveFromRevision` och`IsMoveToRevision` egenskaper för att avgöra om den flyttas och i så fall varifrån och var:

```csharp
doc = new Document(MyDir + "Revision shape.docx");

shapes = doc.GetChildNodes(NodeType.Shape, true).Cast<Shape>().ToList();
Assert.AreEqual(2, shapes.Count);

Assert. False(shapes[0].IsMoveFromRevision);
Assert.True(shapes[0].IsMoveToRevision);

Assert.True(shapes[1].IsMoveFromRevision);
Assert. False(shapes[1].IsMoveToRevision);
```