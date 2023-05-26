---
title: Joindre le document
linktitle: Joindre le document
second_title: Référence de l'API Aspose.Words pour .NET
description: Apprenez à ajouter le contenu d'un document à un autre en utilisant Aspose.Words pour .NET.
type: docs
weight: 10
url: /fr/net/join-and-append-documents/append-document/
---

Ce didacticiel explique comment utiliser Aspose.Words pour .NET pour ajouter le contenu d'un document à un autre. Le code source fourni montre comment ouvrir les documents source et de destination, importer et ajouter des sections du document source au document de destination.

## Étape 1 : Configurer le projet

Assurez-vous que vous disposez des prérequis suivants :

- Bibliothèque Aspose.Words pour .NET installée. Vous pouvez le télécharger à partir du site Web officiel d'Aspose ou utiliser le gestionnaire de packages NuGet pour l'installer.
- Un chemin d'accès au répertoire de documents où se trouvent les documents source et de destination.

## Étape 2 : Ouvrez les documents source et destination

 Ouvrez les documents source et destination à l'aide de la`Document` constructeur de classe. Remplacer`"YOUR DOCUMENT DIRECTORY"` avec le chemin d'accès réel à votre répertoire de documents.

```csharp
// Chemin d'accès à votre répertoire de documents
string dataDir = "YOUR DOCUMENT DIRECTORY";

Document srcDoc = new Document(dataDir + "Document source.docx");
Document dstDoc = new Document(dataDir + "Northwind traders.docx");
```

## Étape 3 : Ajouter des sections du document source au document de destination

 Parcourez toutes les sections du document source et importez chaque section dans le document de destination à l'aide de la`ImportNode` méthode. Ensuite, ajoutez la section importée au document de destination.

```csharp
foreach (Section srcSection in srcDoc)
{
    Node dstSection = dstDoc.ImportNode(srcSection, true, ImportFormatMode.KeepSourceFormatting);
    dstDoc.AppendChild(dstSection);
}
```

## Étape 4 : Enregistrer le document de destination

 Enfin, enregistrez le document de destination modifié à l'aide de la`Save` méthode de la`Document` objet.

```csharp
dstDoc.Save(dataDir + "JoinAndAppendDocuments.AppendDocument.docx");
```

Ceci termine l'implémentation de l'ajout d'un document à l'aide de Aspose.Words pour .NET.

### Exemple de code source pour Append Document utilisant Aspose.Words pour .NET 

```csharp
	// Chemin d'accès à votre répertoire de documents
	string dataDir = "YOUR DOCUMENT DIRECTORY";

	Document srcDoc = new Document(dataDir + "Document source.docx");
	Document dstDoc = new Document(dataDir + "Northwind traders.docx");
	// Parcourez toutes les sections du document source.
	// Les nœuds de section sont des enfants immédiats du nœud Document, nous pouvons donc simplement énumérer le document.
	foreach (Section srcSection in srcDoc)
	{
		//Parce que nous copions une section d'un document à un autre,
		// il est nécessaire d'importer le nœud Section dans le document de destination.
		// Cela ajuste toutes les références spécifiques au document aux styles, listes, etc.
		//
		// L'importation d'un nœud crée une copie du nœud d'origine, mais la copie
		// ss prêt à être inséré dans le document de destination.
		Node dstSection = dstDoc.ImportNode(srcSection, true, ImportFormatMode.KeepSourceFormatting);
		// Maintenant, le nouveau nœud de section peut être ajouté au document de destination.
		dstDoc.AppendChild(dstSection);
	}
	dstDoc.Save(dataDir + "JoinAndAppendDocuments.AppendDocument.docx");
```