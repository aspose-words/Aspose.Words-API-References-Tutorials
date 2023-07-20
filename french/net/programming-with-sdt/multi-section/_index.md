---
title: Multi-section
linktitle: Multi-section
second_title: API de traitement de documents Aspose.Words
description: Découvrez comment récupérer et traiter des balises de document structurées à plusieurs sections dans un document Word à l'aide d'Aspose.Words pour .NET.
type: docs
weight: 10
url: /fr/net/programming-with-sdt/multi-section/
---

Ce didacticiel explique comment utiliser des balises de document structurées à plusieurs sections dans un document Word à l'aide de Aspose.Words pour .NET. Vous pouvez récupérer et traiter les balises de section présentes dans le document.

## Conditions préalables
Pour suivre ce tutoriel, vous devez disposer des éléments suivants :

- Bibliothèque Aspose.Words pour .NET installée.
- Connaissance de base de C# et du traitement de texte avec des documents Word.

## Étape 1 : Configurer le répertoire de documents
 Commencez par configurer le chemin d'accès à votre répertoire de documents. Remplacer`"YOUR DOCUMENT DIRECTORY"` avec le chemin d'accès réel au répertoire où se trouve votre document.

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## Étape 2 : Chargez le document et récupérez les balises multi-sections
 Chargez le document Word à l'aide du`Document` constructeur, en passant le chemin d'accès au document en tant que paramètre. Récupérez tous les nœuds de début de plage de balises de document structuré dans le document à l'aide de la`GetChildNodes` méthode.

```csharp
Document doc = new Document(dataDir + "Multi-section structured document tags.docx");
NodeCollection tags = doc.GetChildNodes(NodeType.StructuredDocumentTagRangeStart, true);
```

## Étape 3 : Traiter les balises multi-sections
Parcourez la collection de nœuds de début de plage de balises de document structuré. Dans cet exemple, nous imprimons simplement le titre de chaque balise sur la console. Vous pouvez effectuer un traitement supplémentaire en fonction de vos besoins.

```csharp
foreach (StructuredDocumentTagRangeStart tag in tags)
    Console.WriteLine(tag.Title);
```

### Exemple de code source pour Multi Section utilisant Aspose.Words pour .NET 

```csharp
	//Chemin d'accès à votre répertoire de documents
	string dataDir = "YOUR DOCUMENT DIRECTORY";

	Document doc = new Document(dataDir + "Multi-section structured document tags.docx");
	NodeCollection tags = doc.GetChildNodes(NodeType.StructuredDocumentTagRangeStart, true);
	foreach (StructuredDocumentTagRangeStart tag in tags)
		Console.WriteLine(tag.Title);
```

C'est ça! Vous avez récupéré et traité avec succès les balises de document structuré à plusieurs sections dans votre document Word à l'aide d'Aspose.Words pour .NET.