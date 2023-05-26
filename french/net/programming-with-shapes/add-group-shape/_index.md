---
title: Ajouter une forme de groupe
linktitle: Ajouter une forme de groupe
second_title: Référence de l'API Aspose.Words pour .NET
description: Apprenez à ajouter une forme de groupe avec plusieurs formes à un document Word à l'aide de Aspose.Words pour .NET.
type: docs
weight: 10
url: /fr/net/programming-with-shapes/add-group-shape/
---

Ce didacticiel explique comment ajouter une forme de groupe contenant plusieurs formes à un document Word à l'aide de Aspose.Words pour .NET. Les formes de groupe vous permettent de combiner et de manipuler plusieurs formes en une seule entité.

## Conditions préalables
Pour suivre ce tutoriel, vous devez disposer des éléments suivants :

- Bibliothèque Aspose.Words pour .NET installée.
- Connaissance de base de C# et travail avec des documents Word.

## Étape 1 : Configurer le répertoire de documents
 Commencez par configurer le chemin d'accès à votre répertoire de documents. Remplacer`"YOUR DOCUMENT DIRECTORY"`avec le chemin d'accès réel au répertoire où vous souhaitez enregistrer le document.

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## Étape 2 : créer un nouveau document et une forme de groupe
 Créez une nouvelle instance de`Document` classe et`GroupShape` objet de travailler avec le document.

```csharp
Document doc = new Document();
doc.EnsureMinimum();
GroupShape groupShape = new GroupShape(doc);
```

## Étape 3 : créer et ajouter des formes au GroupShape
 Créez des formes individuelles telles que`accentBorderShape` et`actionButtonShape` en utilisant le`Shape` classe. Personnalisez leurs propriétés comme vous le souhaitez. Ajoutez ces formes à la`groupShape` objet.

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

## Étape 4 : définir les dimensions de la forme de groupe
 Définissez la largeur, la hauteur et la taille des coordonnées pour le`groupShape`.

```csharp
groupShape.Width = 200;
groupShape.Height = 200;
groupShape.CoordSize = new Size(200, 200);
```

## Étape 5 : Insérez le GroupShape dans le document
 Créer un`DocumentBuilder` objet et insérez le`groupShape` dans le document à l'aide de`InsertNode` méthode.

```csharp
DocumentBuilder builder = new DocumentBuilder(doc);
builder.InsertNode(groupShape);
```

## Étape 6 : Enregistrer le document
 Enregistrez le document dans le répertoire spécifié à l'aide de la`Save`méthode. Indiquez le nom de fichier souhaité avec l'extension de fichier appropriée. Dans cet exemple, nous enregistrons le document sous "WorkingWithShapes.AddGroupShape.docx".

```csharp
doc.Save(dataDir + "WorkingWithShapes.AddGroupShape.docx");
```

### Exemple de code source pour Ajouter une forme de groupe à l'aide de Aspose.Words pour .NET 

```csharp
	// Chemin d'accès à votre répertoire de documents
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

C'est ça! Vous avez ajouté avec succès une forme de groupe contenant plusieurs formes à votre document Word à l'aide d'Aspose.W