---
title: Ajouter avec les options de format d'importation
linktitle: Ajouter avec les options de format d'importation
second_title: Référence de l'API Aspose.Words pour .NET
description: Apprenez à ajouter un document avec des options de format d'importation à l'aide d'Aspose.Words pour .NET.
type: docs
weight: 10
url: /fr/net/join-and-append-documents/append-with-import-format-options/
---

Ce didacticiel explique comment utiliser Aspose.Words pour .NET pour ajouter le contenu d'un document à un autre avec des options de format d'importation. Le code source fourni montre comment ouvrir les documents source et de destination, spécifier les options de format d'importation et ajouter le document source au document de destination.

## Étape 1 : Configurer le projet

Assurez-vous que vous disposez des prérequis suivants :

- Bibliothèque Aspose.Words pour .NET installée. Vous pouvez le télécharger à partir du site Web officiel d'Aspose ou utiliser le gestionnaire de packages NuGet pour l'installer.
- Un chemin d'accès au répertoire de documents où se trouvent les documents source et de destination.

## Étape 2 : Ouvrez les documents source et destination

 Ouvrez les documents source et destination à l'aide de la`Document` constructeur de classe. Remplacer`"YOUR DOCUMENT DIRECTORY"` avec le chemin d'accès réel à votre répertoire de documents.

```csharp
// Chemin d'accès à votre répertoire de documents
string dataDir = "YOUR DOCUMENT DIRECTORY";

Document srcDoc = new Document(dataDir + "Document source with list.docx");
Document dstDoc = new Document(dataDir + "Document destination with list.docx");
```

## Étape 3 : Spécifiez les options de format d'importation

 Créer une instance de`ImportFormatOptions` classe pour spécifier les options de format d'importation. Dans cet exemple, nous utilisons le`KeepSourceNumbering` propriété pour garantir que la numérotation du document source est utilisée en cas de conflit avec le document de destination.

```csharp
ImportFormatOptions options = new ImportFormatOptions { KeepSourceNumbering = true };
```

## Étape 4 : Ajouter le document source au document de destination

 Utilisez le`AppendDocument` méthode du document de destination pour ajouter le document source. Passer`ImportFormatMode.UseDestinationStyles` comme deuxième paramètre pour utiliser les styles et la mise en forme du document de destination.

```csharp
dstDoc.AppendDocument(srcDoc, ImportFormatMode.UseDestinationStyles, options);
```

## Étape 5 : Enregistrer le document de destination

 Enfin, enregistrez le document de destination modifié à l'aide de la`Save` méthode de la`Document` objet.

```csharp
dstDoc.Save(dataDir + "JoinAndAppendDocuments.AppendWithImportFormatOptions.docx");
```

Ceci termine la mise en œuvre de l'ajout d'un document avec des options de format d'importation à l'aide d'Aspose.Words pour .NET.

### Exemple de code source pour Ajouter avec les options de format d'importation à l'aide de Aspose.Words pour .NET 

```csharp
	// Chemin d'accès à votre répertoire de documents
	string dataDir = "YOUR DOCUMENT DIRECTORY";

	Document srcDoc = new Document(dataDir + "Document source with list.docx");
	Document dstDoc = new Document(dataDir + "Document destination with list.docx");
	//Précisez qu'en cas de conflit de numérotation dans les documents source et de destination,
	// alors la numérotation du document source sera utilisée.
	ImportFormatOptions options = new ImportFormatOptions { KeepSourceNumbering = true };
	dstDoc.AppendDocument(srcDoc, ImportFormatMode.UseDestinationStyles, options);

```