---
title: Obtenir les points de limites de forme réels
linktitle: Obtenir les points de limites de forme réels
second_title: API de traitement de documents Aspose.Words
description: Découvrez comment récupérer les limites réelles d'une forme en points (unité de mesure) dans un document Word à l'aide d'Aspose.Words pour .NET.
type: docs
weight: 10
url: /fr/net/programming-with-shapes/get-actual-shape-bounds-points/
---

Ce didacticiel explique comment récupérer les limites réelles d'une forme en points (unité de mesure) dans un document Word à l'aide d'Aspose.Words pour .NET. Les limites représentent la taille et la position de la forme dans le document.

## Conditions préalables
Pour suivre ce tutoriel, vous devez disposer des éléments suivants :

- Bibliothèque Aspose.Words pour .NET installée.
- Connaissance de base de C# et du traitement de mots avec des documents Word.

## Étape 1 : Créer un nouveau document et DocumentBuilder
 Créez une nouvelle instance du`Document` classe et un`DocumentBuilder`s'opposer à travailler avec le document.

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
```

## Étape 2 : Insérer une forme d'image
 Utilisez le`InsertImage` méthode du`DocumentBuilder` objet pour insérer une forme d’image dans le document. Fournissez le chemin d’accès au fichier image en tant que paramètre.

```csharp
Shape shape = builder.InsertImage(ImagesDir + "Transparent background logo.png");
shape.AspectRatioLocked = false;
```

## Étape 3 : Récupérer les points de limite de forme réels
 Accédez aux formes`ShapeRenderer` en utilisant le`GetShapeRenderer` méthode. Ensuite, récupérez les limites réelles de la forme en points à l'aide du`BoundsInPoints` propriété.

```csharp
Console.Write("\nGets the actual bounds of the shape in points: ");
Console.WriteLine(shape.GetShapeRenderer().BoundsInPoints);
```


### Exemple de code source pour obtenir les points de limites de forme réelles à l'aide d'Aspose.Words pour .NET 

```csharp
	Document doc = new Document();
	DocumentBuilder builder = new DocumentBuilder(doc);
	Shape shape = builder.InsertImage(ImagesDir + "Transparent background logo.png");
	shape.AspectRatioLocked = false;
	Console.Write("\nGets the actual bounds of the shape in points: ");
	Console.WriteLine(shape.GetShapeRenderer().BoundsInPoints);
```

C'est ça! Vous avez réussi à récupérer les limites réelles d'une forme en points dans votre document Word à l'aide d'Aspose.Words pour .NET.