---
title: Ajouter le document à vide
linktitle: Ajouter le document à vide
second_title: API de traitement de documents Aspose.Words
description: Découvrez comment ajouter un document à un document de destination vierge dans Aspose.Words for .NET.
type: docs
weight: 10
url: /fr/net/join-and-append-documents/append-document-to-blank/
---

Ce didacticiel explique comment utiliser Aspose.Words for .NET pour ajouter le contenu d'un document à un document de destination vierge. Le code source fourni montre comment créer un nouveau document, supprimer son contenu, puis y ajouter le document source.

## Étape 1 : Configurer le projet

Assurez-vous que vous disposez des conditions préalables suivantes :

- Bibliothèque Aspose.Words pour .NET installée. Vous pouvez le télécharger depuis[Aspose.Releases]https://releases.aspose.com/words/net/ ou utilisez le gestionnaire de packages NuGet pour l'installer.
- Un chemin de répertoire de documents où se trouvent les documents source et de destination.

## Étape 2 : Créer un nouveau document de destination

 Créer un nouveau`Document` objet pour le document de destination.

```csharp
// Chemin d'accès à votre répertoire de documents
string dataDir = "YOUR DOCUMENT DIRECTORY";

Document srcDoc = new Document(dataDir + "Document source.docx");
Document dstDoc = new Document();
```

## Étape 3 : Supprimer le contenu existant du document de destination

 Pour garantir un document de destination propre, supprimez tout le contenu existant du document à l'aide de l'outil`RemoveAllChildren` méthode.

```csharp
dstDoc.RemoveAllChildren();
```

## Étape 4 : Ajouter le document source au document de destination

 Ajoutez le contenu du document source au document de destination à l'aide du`AppendDocument` méthode avec`ImportFormatMode.KeepSourceFormatting` option.

```csharp
dstDoc.AppendDocument(srcDoc, ImportFormatMode.KeepSourceFormatting);
```

## Étape 5 : Enregistrez le document de destination

 Enfin, enregistrez le document de destination modifié à l'aide du`Save` méthode du`Document` objet.

```csharp
dstDoc.Save(dataDir + "JoinAndAppendDocuments.AppendDocumentToBlank.docx");
```

Ceci termine la mise en œuvre de l’ajout d’un document à un document de destination vierge à l’aide d’Aspose.Words pour .NET.

### Exemple de code source pour Ajouter un document à vide à l'aide d'Aspose.Words pour .NET 

```csharp
	//Chemin d'accès à votre répertoire de documents
	string dataDir = "YOUR DOCUMENT DIRECTORY";

	Document srcDoc = new Document(dataDir + "Document source.docx");
	Document dstDoc = new Document();
	//Le document de destination n'est pas vide, ce qui entraîne souvent l'apparition d'une page blanche avant le document annexé.
	// Cela est dû au fait que le document de base comporte une section vide et que le nouveau document démarre sur la page suivante.
	// Supprimez tout le contenu du document de destination avant de l'ajouter.
	dstDoc.RemoveAllChildren();
	dstDoc.AppendDocument(srcDoc, ImportFormatMode.KeepSourceFormatting);
	dstDoc.Save(dataDir + "JoinAndAppendDocuments.AppendDocumentToBlank.docx");

```