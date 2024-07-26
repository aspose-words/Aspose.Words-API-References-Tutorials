---
title: Rapport hauteur/largeur verrouillé
linktitle: Rapport hauteur/largeur verrouillé
second_title: API de traitement de documents Aspose.Words
description: Découvrez comment verrouiller ou déverrouiller les proportions d'une forme dans un document Word à l'aide d'Aspose.Words pour .NET.
type: docs
weight: 10
url: /fr/net/programming-with-shapes/aspect-ratio-locked/
---

Ce didacticiel explique comment verrouiller ou déverrouiller les proportions d'une forme dans un document Word à l'aide d'Aspose.Words pour .NET. En verrouillant les proportions, vous pouvez conserver les proportions d'origine de la forme lors de son redimensionnement.

## Conditions préalables
Pour suivre ce tutoriel, vous devez disposer des éléments suivants :

- Bibliothèque Aspose.Words pour .NET installée.
- Connaissance de base de C# et du traitement de mots avec des documents Word.

## Étape 1 : configurer le répertoire de documents
 Commencez par configurer le chemin d’accès à votre répertoire de documents. Remplacer`"YOUR DOCUMENT DIRECTORY"` avec le chemin réel du répertoire dans lequel vous souhaitez enregistrer le document.

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## Étape 2 : Créer un nouveau document et DocumentBuilder
 Créez une nouvelle instance du`Document` classe et un`DocumentBuilder` s'opposer à travailler avec le document.

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
```

## Étape 3 : Insérer une forme d'image
 Utilisez le`InsertImage` méthode du`DocumentBuilder` objet pour insérer une forme d’image dans le document. Fournissez le chemin d’accès au fichier image en tant que paramètre.

```csharp
Shape shape = builder.InsertImage(ImagesDir + "Transparent background logo.png");
```

## Étape 4 : verrouiller ou déverrouiller le rapport hauteur/largeur
 Met le`AspectRatioLocked` propriété de la forme à`true` ou`false` pour verrouiller ou déverrouiller le rapport hauteur/largeur, respectivement.

```csharp
shape.AspectRatioLocked = false; // Débloquez le rapport hauteur/largeur
```

## Étape 5 : Enregistrez le document
 Enregistrez le document dans le répertoire spécifié à l'aide du`Save` méthode. Fournissez le nom de fichier souhaité avec l'extension de fichier appropriée. Dans cet exemple, nous enregistrons le document sous le nom « WorkingWithShapes.AspectRatioLocked.docx ».

```csharp
doc.Save(dataDir + "WorkingWithShapes.AspectRatioLocked.docx");
```

### Exemple de code source pour Aspect Ratio Locked à l'aide d'Aspose.Words for .NET 

```csharp
	// Chemin d'accès à votre répertoire de documents
	string dataDir = "YOUR DOCUMENT DIRECTORY";

	Document doc = new Document();
	DocumentBuilder builder = new DocumentBuilder(doc);
	Shape shape = builder.InsertImage(ImagesDir + "Transparent background logo.png");
	shape.AspectRatioLocked = false;
	doc.Save(dataDir + "WorkingWithShapes.AspectRatioLocked.docx");
```

C'est ça! Vous avez réussi à verrouiller ou déverrouiller les proportions d'une forme dans votre document Word à l'aide d'Aspose.Words pour .NET.