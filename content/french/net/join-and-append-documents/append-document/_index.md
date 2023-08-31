---
title: Ajouter un document
linktitle: Ajouter un document
second_title: API de traitement de documents Aspose.Words
description: Découvrez comment ajouter le contenu d'un document à un autre à l'aide d'Aspose.Words for .NET.
type: docs
weight: 10
url: /fr/net/join-and-append-documents/append-document/
---

Ce didacticiel explique comment utiliser Aspose.Words for .NET pour ajouter le contenu d'un document à un autre. Le code source fourni montre comment ouvrir les documents source et de destination, importer et ajouter des sections du document source au document de destination.

## Étape 1 : Configurer le projet

Assurez-vous que vous disposez des conditions préalables suivantes :

- Bibliothèque Aspose.Words pour .NET installée. Vous pouvez le télécharger depuis[Aspose.Releases]https://releases.aspose.com/words/net/ ou utilisez le gestionnaire de packages NuGet pour l'installer.
- Un chemin de répertoire de documents où se trouvent les documents source et de destination.

## Étape 2 : Ouvrir les documents source et destination

 Ouvrez les documents source et destination à l'aide du`Document` constructeur de classe. Remplacer`"YOUR DOCUMENT DIRECTORY"` avec le chemin réel vers votre répertoire de documents.

```csharp
// Chemin d'accès à votre répertoire de documents
string dataDir = "YOUR DOCUMENT DIRECTORY";

Document srcDoc = new Document(dataDir + "Document source.docx");
Document dstDoc = new Document(dataDir + "Northwind traders.docx");
```

## Étape 3 : Ajouter des sections du document source au document de destination

 Parcourez toutes les sections du document source et importez chaque section dans le document de destination à l'aide du`ImportNode` méthode. Ensuite, ajoutez la section importée au document de destination.

```csharp
foreach (Section srcSection in srcDoc)
{
    Node dstSection = dstDoc.ImportNode(srcSection, true, ImportFormatMode.KeepSourceFormatting);
    dstDoc.AppendChild(dstSection);
}
```

## Étape 4 : Enregistrez le document de destination

 Enfin, enregistrez le document de destination modifié à l'aide du`Save` méthode du`Document` objet.

```csharp
dstDoc.Save(dataDir + "JoinAndAppendDocuments.AppendDocument.docx");
```

Ceci termine la mise en œuvre de l’ajout d’un document à l’aide d’Aspose.Words pour .NET.

### Exemple de code source pour Append Document à l'aide d'Aspose.Words pour .NET 

```csharp
	//Chemin d'accès à votre répertoire de documents
	string dataDir = "YOUR DOCUMENT DIRECTORY";

	Document srcDoc = new Document(dataDir + "Document source.docx");
	Document dstDoc = new Document(dataDir + "Northwind traders.docx");
	// Parcourez toutes les sections du document source.
	// Les nœuds de section sont des enfants immédiats du nœud Document, nous pouvons donc simplement énumérer le document.
	foreach (Section srcSection in srcDoc)
	{
		// Parce que nous copions une section d'un document à un autre,
		// il est nécessaire d'importer le nœud Section dans le document de destination.
		// Cela ajuste toutes les références spécifiques au document aux styles, listes, etc.
		//
		// L'importation d'un nœud crée une copie du nœud d'origine, mais la copie
		// ss prêt à être inséré dans le document de destination.
		Node dstSection = dstDoc.ImportNode(srcSection, true, ImportFormatMode.KeepSourceFormatting);
		// Le nouveau nœud de section peut désormais être ajouté au document de destination.
		dstDoc.AppendChild(dstSection);
	}
	dstDoc.Save(dataDir + "JoinAndAppendDocuments.AppendDocument.docx");
```