---
title: Ajouter le document au blanc
linktitle: Ajouter le document au blanc
second_title: Référence de l'API Aspose.Words pour .NET
description: Apprenez à ajouter un document à un document de destination vide dans Aspose.Words pour .NET.
type: docs
weight: 10
url: /fr/net/join-and-append-documents/append-document-to-blank/
---

Ce didacticiel explique comment utiliser Aspose.Words pour .NET pour ajouter le contenu d'un document à un document de destination vierge. Le code source fourni montre comment créer un nouveau document, supprimer son contenu, puis y ajouter le document source.

## Étape 1 : Configurer le projet

Assurez-vous que vous disposez des prérequis suivants :

- Bibliothèque Aspose.Words pour .NET installée. Vous pouvez le télécharger à partir du site Web officiel d'Aspose ou utiliser le gestionnaire de packages NuGet pour l'installer.
- Un chemin d'accès au répertoire de documents où se trouvent les documents source et de destination.

## Étape 2 : créer un nouveau document de destination

 Créer un nouveau`Document` objet pour le document de destination.

```csharp
// Chemin d'accès à votre répertoire de documents
string dataDir = "YOUR DOCUMENT DIRECTORY";

Document srcDoc = new Document(dataDir + "Document source.docx");
Document dstDoc = new Document();
```

## Étape 3 : supprimer le contenu existant du document de destination

Pour garantir un document de destination propre, supprimez tout le contenu existant du document à l'aide de la`RemoveAllChildren` méthode.

```csharp
dstDoc.RemoveAllChildren();
```

## Étape 4 : Ajouter le document source au document de destination

 Ajoutez le contenu du document source au document de destination à l'aide de la`AppendDocument` méthode avec`ImportFormatMode.KeepSourceFormatting` option.

```csharp
dstDoc.AppendDocument(srcDoc, ImportFormatMode.KeepSourceFormatting);
```

## Étape 5 : Enregistrer le document de destination

 Enfin, enregistrez le document de destination modifié à l'aide de la`Save` méthode de la`Document` objet.

```csharp
dstDoc.Save(dataDir + "JoinAndAppendDocuments.AppendDocumentToBlank.docx");
```

Ceci termine l'implémentation de l'ajout d'un document à un document de destination vierge à l'aide de Aspose.Words pour .NET.

### Exemple de code source pour Append Document To Blank en utilisant Aspose.Words pour .NET 

```csharp
	// Chemin d'accès à votre répertoire de documents
	string dataDir = "YOUR DOCUMENT DIRECTORY";

	Document srcDoc = new Document(dataDir + "Document source.docx");
	Document dstDoc = new Document();
	// Le document de destination n'est pas vide, ce qui provoque souvent l'apparition d'une page vierge avant le document ajouté.
	// Cela est dû au fait que le document de base a une section vide et que le nouveau document commence à la page suivante.
	// Supprimez tout le contenu du document de destination avant de l'ajouter.
	dstDoc.RemoveAllChildren();
	dstDoc.AppendDocument(srcDoc, ImportFormatMode.KeepSourceFormatting);
	dstDoc.Save(dataDir + "JoinAndAppendDocuments.AppendDocumentToBlank.docx");

```