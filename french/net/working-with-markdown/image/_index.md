---
title: Image
linktitle: Image
second_title: Référence de l'API Aspose.Words pour .NET
description: Apprenez à insérer et personnaliser une image avec le guide étape par étape Aspose.Words pour .NET.
type: docs
weight: 10
url: /fr/net/working-with-markdown/image/
---

Dans cet exemple, nous expliquerons comment utiliser la fonctionnalité d'image avec Aspose.Words pour .NET. Les images vous permettent d'insérer des illustrations et des graphiques dans un document.

## Étape 1 : Utiliser un générateur de documents

Tout d'abord, nous allons utiliser un générateur de document pour ajouter du contenu à notre document.

```csharp
DocumentBuilder builder = new DocumentBuilder();
```

## Étape 2 : Insertion d'une image

 Nous pouvons insérer une image en utilisant le`Shape` class et en précisant le type d'image, ici`ShapeType.Image` Nous définissons également le type d'habillage de l'image sur`WrapType.Inline`.

```csharp
Shape shape = new Shape(builder.Document, ShapeType.Image);
shape. WrapType = WrapType. Inline;
```

## Étape 3 : Personnalisation de l'image

 Nous personnalisons l'image en spécifiant son chemin complet, par exemple`"/attachment/1456/pic001.png"`, et en ajoutant un titre à l'image.

```csharp
shape.ImageData.SourceFullName = "/attachment/1456/pic001.png";
shape.ImageData.Title = "Title";
```

### Exemple de code source pour les images avec Aspose.Words pour .NET

```csharp
// Utilisez un générateur de document pour ajouter du contenu au document.
DocumentBuilder builder = new DocumentBuilder();

// Insérer une image.
Shape shape = new Shape(builder.Document, ShapeType.Image);
shape.WrapType = WrapType.Inline;
shape.ImageData.SourceFullName = "/attachment/1456/pic001.png";
shape.ImageData.Title = "title";
builder.InsertNode(shape);
```

Félicitation ! Vous avez maintenant appris à utiliser la fonctionnalité d'images avec Aspose.Words pour .NET.

