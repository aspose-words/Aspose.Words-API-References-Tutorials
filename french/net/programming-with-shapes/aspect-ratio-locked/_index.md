---
title: Format d'image verrouillé
linktitle: Format d'image verrouillé
second_title: Référence de l'API Aspose.Words pour .NET
description: Découvrez comment verrouiller ou déverrouiller les proportions d'une forme dans un document Word à l'aide d'Aspose.Words pour .NET.
type: docs
weight: 10
url: /fr/net/programming-with-shapes/aspect-ratio-locked/
---

Ce didacticiel explique comment verrouiller ou déverrouiller les proportions d'une forme dans un document Word à l'aide de Aspose.Words pour .NET. En verrouillant le rapport d'aspect, vous pouvez conserver les proportions d'origine de la forme lors du redimensionnement.

## Conditions préalables
Pour suivre ce tutoriel, vous devez disposer des éléments suivants :

- Bibliothèque Aspose.Words pour .NET installée.
- Connaissance de base de C# et travail avec des documents Word.

## Étape 1 : Configurer le répertoire de documents
 Commencez par configurer le chemin d'accès à votre répertoire de documents. Remplacer`"YOUR DOCUMENT DIRECTORY"`avec le chemin d'accès réel au répertoire où vous souhaitez enregistrer le document.

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## Étape 2 : Créer un nouveau document et DocumentBuilder
 Créez une nouvelle instance de`Document` classe et une`DocumentBuilder` objet de travailler avec le document.

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
```

## Étape 3 : Insérer une forme d'image
 Utilisez le`InsertImage` méthode de la`DocumentBuilder` objet pour insérer une forme d'image dans le document. Indiquez le chemin d'accès au fichier image en tant que paramètre.

```csharp
Shape shape = builder.InsertImage(ImagesDir + "Transparent background logo.png");
```

## Étape 4 : Verrouiller ou déverrouiller le format d'image
 Met le`AspectRatioLocked` propriété de la forme à`true` ou`false`pour verrouiller ou déverrouiller le format d'image, respectivement.

```csharp
shape.AspectRatioLocked = false; // Déverrouiller le rapport hauteur/largeur
```

## Étape 5 : Enregistrer le document
 Enregistrez le document dans le répertoire spécifié à l'aide de la`Save` méthode. Indiquez le nom de fichier souhaité avec l'extension de fichier appropriée. Dans cet exemple, nous enregistrons le document sous "WorkingWithShapes.AspectRatioLocked.docx".

```csharp
doc.Save(dataDir + "WorkingWithShapes.AspectRatioLocked.docx");
```

### Exemple de code source pour Aspect Ratio Locked en utilisant Aspose.Words pour .NET 

```csharp
	// Chemin d'accès à votre répertoire de documents
	string dataDir = "YOUR DOCUMENT DIRECTORY";

	Document doc = new Document();
	DocumentBuilder builder = new DocumentBuilder(doc);
	Shape shape = builder.InsertImage(ImagesDir + "Transparent background logo.png");
	shape.AspectRatioLocked = false;
	doc.Save(dataDir + "WorkingWithShapes.AspectRatioLocked.docx");
```

C'est ça! Vous avez verrouillé ou déverrouillé avec succès le rapport d'aspect d'une forme dans votre document Word à l'aide de Aspose.Words pour .NET.