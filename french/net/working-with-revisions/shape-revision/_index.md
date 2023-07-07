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

//Insérez une forme en ligne sans suivre les révisions.
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

// Le document a une forme qui a été déplacée, mais les révisions de déplacement de forme auront deux instances de cette forme.
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

## Conclusion

Dans ce didacticiel, nous avons appris à apporter des modifications aux formes d'un document Word à l'aide de Aspose.Words pour .NET. En suivant les étapes de création du document, en activant le suivi des révisions, en vérifiant les révisions associées à chaque forme et en vérifiant les révisions pour déplacer les formes, nous avons pu gérer les révisions avec succès. Aspose.Words pour .NET offre une API puissante pour travailler avec des révisions et des formulaires dans des documents Word.

### FAQ

#### Q : Comment puis-je créer un nouveau document et ajouter des formes dans Aspose.Words pour .NET ?

R : Pour créer un nouveau document et ajouter des formes dans Aspose.Words pour .NET, vous pouvez utiliser le code suivant. Ici, nous ajoutons deux formes, un cube et un soleil, à la première section du document :

```csharp
Document doc = new Document();
Assert.False(doc.TrackRevisions);

Shape shape = new Shape(doc, ShapeType.Cube);
shape. WrapType = WrapType. Inline;
shape. Width = 100.0;
shape. Height = 100.0;
doc.FirstSection.Body.FirstParagraph.AppendChild(shape);
```

#### Q : Comment activer le suivi des révisions dans Aspose.Words pour .NET ?

 R : Pour activer le suivi des révisions dans Aspose.Words pour .NET, vous pouvez utiliser le`StartTrackRevisions` méthode de la`Document` objet. Cette méthode prend le nom de l'auteur des révisions en paramètre :

```csharp
doc.StartTrackRevisions("John Doe");
```

#### Q : Comment puis-je vérifier les révisions associées à chaque forme dans un document Aspose.Words pour .NET ?

R : Pour vérifier les révisions associées à chaque forme dans un document Aspose.Words pour .NET, vous pouvez obtenir la collection de formes du document à l'aide de la commande`GetChildNodes` méthode avec la`NodeType.Shape` type de nœud. Ensuite, vous pouvez accéder à chaque forme`IsDeleteRevision`, `IsInsertRevision`, `IsMoveFromRevision` , et`IsMoveToRevision` properties pour déterminer quel type de révision est associé à la forme :

```csharp
List<Shape> shapes = doc.GetChildNodes(NodeType.Shape, true).Cast<Shape>().ToList();
Assert.AreEqual(2, shapes.Count);

Assert.AreEqual(ShapeType.Cube, shapes[0].ShapeType);
Assert.True(shapes[0].IsDeleteRevision);

Assert.AreEqual(ShapeType.Sun, shapes[1].ShapeType);
Assert.True(shapes[1].IsInsertRevision);
```

#### Q : Comment puis-je vérifier les révisions de déplacement des formes dans un document Aspose.Words pour .NET ?

 R : Pour vérifier les révisions de déplacement de forme dans un document Aspose.Words pour .NET, vous pouvez charger un document existant qui contient des révisions de déplacement de forme. Ensuite, vous pouvez accéder à chaque forme`IsMoveFromRevision` et`IsMoveToRevision` properties pour déterminer s'il est déplacé et si oui, d'où et vers où :

```csharp
doc = new Document(MyDir + "Revision shape.docx");

shapes = doc.GetChildNodes(NodeType.Shape, true).Cast<Shape>().ToList();
Assert.AreEqual(2, shapes.Count);

Assert. False(shapes[0].IsMoveFromRevision);
Assert.True(shapes[0].IsMoveToRevision);

Assert.True(shapes[1].IsMoveFromRevision);
Assert. False(shapes[1].IsMoveToRevision);
```