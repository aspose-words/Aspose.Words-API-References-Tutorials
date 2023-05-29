---
title: Formrevision
linktitle: Formrevision
second_title: Aspose.Words för .NET API Referens
description: Revidera former i ett Word-dokument med Aspose.Words för .NET.
type: docs
weight: 10
url: /sv/net/working-with-revisions/shape-revision/
---

I den här steg-för-steg-guiden går vi igenom hur du gör ändringar av former i ett Word-dokument med Aspose.Words för .NET. Vi kommer att förse dig med den fullständiga källkoden och visa dig hur du formaterar markdown-utdata.

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

// Infoga en inline-form utan att spåra revisioner.
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

//Dokumentet har en form som flyttades, men formflyttningsrevisioner kommer att ha två instanser av den formen.
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

