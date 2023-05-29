---
title: Révision de la forme
linktitle: Révision de la forme
second_title: Référence de l'API Aspose.Words pour .NET
description: Révisez les formes dans un document Word avec Aspose.Words pour .NET.
type: docs
weight: 10
url: /fr/net/working-with-revisions/shape-revision/
---

Dans ce guide étape par étape, nous vous expliquerons comment apporter des modifications aux formes dans un document Word à l'aide de Aspose.Words pour .NET. Nous vous fournirons le code source complet et vous montrerons comment formater la sortie Markdown.

## Étape 1 : création du document et ajout de formes

La première étape consiste à créer un nouveau document et à ajouter des formes.

```csharp
Document doc = new Document();
Assert.False(doc.TrackRevisions);

Shape shape = new Shape(doc, ShapeType.Cube);
shape. WrapType = WrapType. Inline;
shape. Width = 100.0;
shape. Height = 100.0;
doc.FirstSection.Body.FirstParagraph.AppendChild(shape);
```

## Étape 2 : Suivre les révisions et ajouter une autre forme

Nous allons activer le suivi des révisions et ajouter une autre forme.

```csharp
doc.StartTrackRevisions("John Doe");

shape = new Shape(doc, ShapeType.Sun);
shape. WrapType = WrapType. Inline;
shape. Width = 100.0;
shape. Height = 100.0;
doc.FirstSection.Body.FirstParagraph.AppendChild(shape);
```

## Étape 3 : Obtenir la collection de formes et vérifier les révisions

Nous allons récupérer la collection de formes du document et vérifier les révisions associées à chaque forme.

```csharp
List<Shape> shapes = doc.GetChildNodes(NodeType.Shape, true).Cast<Shape>().ToList();
Assert.AreEqual(2, shapes.Count);

Assert.AreEqual(ShapeType.Cube, shapes[0].ShapeType);
Assert.True(shapes[0].IsDeleteRevision);

Assert.AreEqual(ShapeType.Sun, shapes[1].ShapeType);
Assert.True(shapes[1].IsInsertRevision);
```

## Étape 4 : Vérification des révisions de déplacement de forme

Nous allons charger un document existant contenant des révisions de déplacement de forme et vérifier les révisions associées.

```csharp
doc = new Document(MyDir + "Revision shape.docx");

shapes = doc.GetChildNodes(NodeType.Shape, true).Cast<Shape>().ToList();
Assert.AreEqual(2, shapes.Count);

Assert. False(shapes[0].IsMoveFromRevision);
Assert.True(shapes[0].IsMoveToRevision);

Assert.True(shapes[1].IsMoveFromRevision);
Assert. False(shapes[1].IsMoveToRevision);
```

### Exemple de code source pour Shape Revision utilisant Aspose.Words pour .NET

Voici le code source complet pour apporter des révisions aux formes dans un document en utilisant Aspose.Words pour .NET :

```csharp
Document doc = new Document();

// Insérez une forme en ligne sans suivre les révisions.
Assert.False(doc.TrackRevisions);
Shape shape = new Shape(doc, ShapeType.Cube);
shape.WrapType = WrapType.Inline;
shape.Width = 100.0;
shape.Height = 100.0;
doc.FirstSection.Body.FirstParagraph.AppendChild(shape);

// Commencez à suivre les révisions, puis insérez une autre forme.
doc.StartTrackRevisions("John Doe");
shape = new Shape(doc, ShapeType.Sun);
shape.WrapType = WrapType.Inline;
shape.Width = 100.0;
shape.Height = 100.0;
doc.FirstSection.Body.FirstParagraph.AppendChild(shape);

// Obtenez la collection de formes du document qui comprend uniquement les deux formes que nous avons ajoutées.
List<Shape> shapes = doc.GetChildNodes(NodeType.Shape, true).Cast<Shape>().ToList();
Assert.AreEqual(2, shapes.Count);

// Supprimez la première forme.
shapes[0].Remove();

// Étant donné que nous avons supprimé cette forme pendant le suivi des modifications, la forme compte comme une révision de suppression.
Assert.AreEqual(ShapeType.Cube, shapes[0].ShapeType);
Assert.True(shapes[0].IsDeleteRevision);

// Et nous avons inséré une autre forme lors du suivi des modifications, de sorte que cette forme comptera comme une révision d'insertion.
Assert.AreEqual(ShapeType.Sun, shapes[1].ShapeType);
Assert.True(shapes[1].IsInsertRevision);

//Le document a une forme qui a été déplacée, mais les révisions de déplacement de forme auront deux instances de cette forme.
// L'un sera la forme à sa destination d'arrivée et l'autre sera la forme à son emplacement d'origine.
doc = new Document(MyDir + "Revision shape.docx");

shapes = doc.GetChildNodes(NodeType.Shape, true).Cast<Shape>().ToList();
Assert.AreEqual(2, shapes.Count);

// C'est le passage à la révision, ainsi que la forme à sa destination d'arrivée.
Assert.False(shapes[0].IsMoveFromRevision);
Assert.True(shapes[0].IsMoveToRevision);

// Il s'agit du déplacement de la révision, qui est la forme à son emplacement d'origine.
Assert.True(shapes[1].IsMoveFromRevision);
Assert.False(shapes[1].IsMoveToRevision);
```

