---
title: Mettre à jour le dessin Smart Art
linktitle: Mettre à jour le dessin Smart Art
second_title: API de traitement de documents Aspose.Words
description: Découvrez comment mettre à jour le dessin Smart Art dans un document Word à l'aide d'Aspose.Words pour .NET.
type: docs
weight: 10
url: /fr/net/programming-with-shapes/update-smart-art-drawing/
---

Ce didacticiel explique comment mettre à jour le dessin Smart Art dans un document Word à l'aide d'Aspose.Words for .NET. En parcourant les formes du document et en vérifiant si elles contiennent Smart Art, vous pouvez mettre à jour le dessin Smart Art pour refléter toutes les modifications apportées à ses données.

## Conditions préalables
Pour suivre ce tutoriel, vous devez disposer des éléments suivants :

- Bibliothèque Aspose.Words pour .NET installée.
- Connaissance de base de C# et du traitement de mots avec des documents Word.

## Étape 1 : configurer le répertoire de documents
 Commencez par configurer le chemin d’accès à votre répertoire de documents. Remplacer`"YOUR DOCUMENT DIRECTORY"` avec le chemin réel vers le répertoire où se trouve votre document.

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## Étape 2 : Charger le document
 Chargez le document Word contenant le dessin Smart Art à l'aide du`Document` constructeur de classe.

```csharp
Document doc = new Document(dataDir + "SmartArt.docx");
```

## Étape 3 : Mettre à jour le dessin Smart Art
 Parcourez les formes du document à l'aide de l'outil`GetChildNodes` méthode avec le`NodeType.Shape` paramètre. Vérifiez si chaque forme a Smart Art en utilisant le`HasSmartArt`propriété, et si c'est vrai, appelez le`UpdateSmartArtDrawing` méthode pour mettre à jour le dessin Smart Art.

```csharp
	foreach (Shape shape in doc.GetChildNodes(NodeType.Shape, true))
		if (shape.HasSmartArt)
			shape.UpdateSmartArtDrawing();
```


### Exemple de code source pour mettre à jour le dessin Smart Art à l'aide d'Aspose.Words pour .NET 

```csharp
	// Chemin d'accès à votre répertoire de documents
	string dataDir = "YOUR DOCUMENT DIRECTORY";

	Document doc = new Document(dataDir + "SmartArt.docx");
	foreach (Shape shape in doc.GetChildNodes(NodeType.Shape, true))
		if (shape.HasSmartArt)
			shape.UpdateSmartArtDrawing();
```

C'est ça! Vous avez mis à jour avec succès le dessin Smart Art dans votre document Word à l'aide d'Aspose.Words pour .NET.