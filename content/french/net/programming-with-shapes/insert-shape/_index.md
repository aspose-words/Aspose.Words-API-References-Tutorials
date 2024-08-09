---
title: Insérer une forme
linktitle: Insérer une forme
second_title: API de traitement de documents Aspose.Words
description: Découvrez comment insérer et manipuler des formes dans des documents Word à l'aide d'Aspose.Words for .NET grâce à notre guide étape par étape.
type: docs
weight: 10
url: /fr/net/programming-with-shapes/insert-shape/
---
## Introduction

Lorsqu’il s’agit de créer des documents Word visuellement attrayants et bien structurés, les formes peuvent jouer un rôle essentiel. Que vous ajoutiez des flèches, des cases ou même des formes personnalisées complexes, la possibilité de manipuler ces éléments par programmation offre une flexibilité inégalée. Dans ce didacticiel, nous explorerons comment insérer et manipuler des formes dans des documents Word à l'aide d'Aspose.Words pour .NET.

## Conditions préalables

Avant de plonger dans le didacticiel, assurez-vous d'avoir les prérequis suivants :

1.  Aspose.Words pour .NET : téléchargez et installez la dernière version à partir du[Page des versions d'Aspose](https://releases.aspose.com/words/net/).
2. Environnement de développement : un environnement de développement .NET approprié tel que Visual Studio.
3. Connaissance de base de C# : Familiarité avec le langage de programmation C# et les concepts de base.

## Importer des espaces de noms

Pour commencer, vous devrez importer les espaces de noms nécessaires dans votre projet C# :

```csharp
using Aspose.Words;
using Aspose.Words.Drawing;
```

## Étape 1 : Configurez votre projet

Avant de pouvoir commencer à insérer des formes, vous devez configurer votre projet et ajouter la bibliothèque Aspose.Words for .NET.

1. Créer un nouveau projet : ouvrez Visual Studio et créez un nouveau projet d'application console C#.
2. Ajoutez Aspose.Words pour .NET : installez la bibliothèque Aspose.Words pour .NET via NuGet Package Manager.

```bash
Install-Package Aspose.Words
```

## Étape 2 : initialiser le document

Tout d’abord, vous devrez initialiser un nouveau document et un générateur de documents, qui vous aideront à construire le document.

```csharp
// Chemin d'accès à votre répertoire de documents
string dataDir = "YOUR DOCUMENT DIRECTORY";

// Initialiser un nouveau document
Document doc = new Document();

// Initialisez un DocumentBuilder pour aider à créer le document
DocumentBuilder builder = new DocumentBuilder(doc);
```

## Étape 3 : Insérer une forme

Maintenant, insérons une forme dans le document. Nous allons commencer par ajouter une simple zone de texte.

```csharp
// Insérer une forme de zone de texte dans le document
Shape shape = builder.InsertShape(ShapeType.TextBox, RelativeHorizontalPosition.Page, 100, RelativeVerticalPosition.Page, 100, 50, 50, WrapType.None);

// Faire pivoter la forme
shape.Rotation = 30.0;
```

Dans cet exemple, nous insérons une zone de texte à la position (100, 100) avec une largeur et une hauteur de 50 unités chacune. Nous faisons également pivoter la forme de 30 degrés.

## Étape 4 : ajouter une autre forme

Ajoutons une autre forme au document, cette fois sans préciser la position.

```csharp
// Ajouter une autre forme de zone de texte
Shape secondShape = builder.InsertShape(ShapeType.TextBox, 50, 50);

// Faire pivoter la forme
secondShape.Rotation = 30.0;
```

Cet extrait de code insère une autre zone de texte avec les mêmes dimensions et rotation que la première mais sans préciser sa position.

## Étape 5 : Enregistrez le document

 Après avoir ajouté les formes, la dernière étape consiste à enregistrer le document. Nous utiliserons le`OoxmlSaveOptions` pour spécifier le format de sauvegarde.

```csharp
// Définir les options de sauvegarde en toute conformité
OoxmlSaveOptions saveOptions = new OoxmlSaveOptions(SaveFormat.Docx)
{
    Compliance = OoxmlCompliance.Iso29500_2008_Transitional
};

// Enregistrez le document
doc.Save(dataDir + "WorkingWithShapes.InsertShape.docx", saveOptions);
```

## Conclusion

Et voilà ! Vous avez réussi à insérer et à manipuler des formes dans un document Word à l'aide d'Aspose.Words pour .NET. Ce didacticiel couvre les bases, mais Aspose.Words propose de nombreuses fonctionnalités plus avancées pour travailler avec des formes, telles que des styles personnalisés, des connecteurs et des formes de groupe.

 Pour des informations plus détaillées, visitez le[Documentation Aspose.Words pour .NET](https://reference.aspose.com/words/net/).

## FAQ

### Comment insérer différents types de formes ?
Vous pouvez changer le`ShapeType` dans le`InsertShape` méthode pour insérer différents types de formes telles que des cercles, des rectangles et des flèches.

### Puis-je ajouter du texte à l’intérieur des formes ?
 Oui, vous pouvez utiliser le`builder.Write` méthode pour ajouter du texte à l’intérieur des formes après les avoir insérées.

### Est-il possible de styliser les formes ?
 Oui, vous pouvez styliser les formes en définissant des propriétés telles que`FillColor`, `StrokeColor` , et`StrokeWeight`.

### Comment positionner les formes par rapport à d’autres éléments ?
 Utilisez le`RelativeHorizontalPosition`et`RelativeVerticalPosition` propriétés pour positionner les formes par rapport aux autres éléments du document.

### Puis-je regrouper plusieurs formes ?
 Oui, Aspose.Words for .NET vous permet de regrouper des formes à l'aide de l'option`GroupShape` classe.