---
title: Image
linktitle: Image
second_title: API de traitement de documents Aspose.Words
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

 Nous pouvons insérer une image en utilisant le`Shape` class et en précisant le type d'image, ici`ShapeType.Image` . Nous définissons également le type d'habillage de l'image sur`WrapType.Inline`.

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


### FAQ

#### Q : Comment puis-je insérer une image à partir d'un fichier local dans Aspose.Words ?

 R : Pour insérer une image à partir d'un fichier local dans Aspose.Words, vous pouvez utiliser le`Shape` classe et la`InsertImage` méthode.

#### Q : Puis-je insérer une image à partir d'une URL dans Aspose.Words ?

 R : Oui, vous pouvez insérer une image à partir d'une URL dans Aspose.Words. Vous pouvez utiliser le même`InsertImage`méthode et spécifiez l'URL de l'image au lieu du chemin du fichier local.

#### Q : Comment puis-je redimensionner une image dans Aspose.Words ?

 R : Pour redimensionner une image dans Aspose.Words, vous pouvez utiliser le`Width` et`Height` propriétés de la`Shape` objet.

#### Q : Puis-je appliquer des filtres aux images dans Aspose.Words ?

 R : Oui, vous pouvez appliquer des filtres aux images dans Aspose.Words. Par exemple, vous pouvez appliquer un filtre de flou à une image à l'aide de la`ApplyGaussianBlur` méthode de la`Shape` objet.

#### Q : Comment puis-je remplacer une image par une autre dans Aspose.Words ?

 R : Pour remplacer une image par une autre dans Aspose.Words, vous pouvez utiliser le`Replace` méthode de la`Shape` classe. Cette méthode prend en paramètre le`Shape` l'objet de l'image à remplacer et le`Shape` objet de la nouvelle image.