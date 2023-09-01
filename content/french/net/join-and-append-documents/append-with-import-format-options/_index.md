---
title: Ajouter avec les options de format d'importation
linktitle: Ajouter avec les options de format d'importation
second_title: API de traitement de documents Aspose.Words
description: Découvrez comment ajouter un document avec des options de format d'importation à l'aide d'Aspose.Words pour .NET.
type: docs
weight: 10
url: /fr/net/join-and-append-documents/append-with-import-format-options/
---

Ce didacticiel explique comment utiliser Aspose.Words for .NET pour ajouter le contenu d'un document à un autre avec des options de format d'importation. Le code source fourni montre comment ouvrir les documents source et de destination, spécifier les options de format d'importation et ajouter le document source au document de destination.

## Étape 1 : Configurer le projet

Assurez-vous que vous disposez des conditions préalables suivantes :

-  Bibliothèque Aspose.Words pour .NET installée. Vous pouvez le télécharger depuis[Aspose.Releases]https://releases.aspose.com/words/net/ ou utilisez le gestionnaire de packages NuGet pour l'installer.
- Un chemin de répertoire de documents où se trouvent les documents source et de destination.

## Étape 2 : Ouvrir les documents source et destination

 Ouvrez les documents source et destination à l'aide du`Document` constructeur de classe. Remplacer`"YOUR DOCUMENT DIRECTORY"` avec le chemin réel vers votre répertoire de documents.

```csharp
// Chemin d'accès à votre répertoire de documents
string dataDir = "YOUR DOCUMENT DIRECTORY";

Document srcDoc = new Document(dataDir + "Document source with list.docx");
Document dstDoc = new Document(dataDir + "Document destination with list.docx");
```

## Étape 3 : Spécifier les options de format d'importation

 Créez une instance du`ImportFormatOptions` classe pour spécifier les options de format d’importation. Dans cet exemple, nous utilisons le`KeepSourceNumbering` propriété pour garantir que la numérotation du document source est utilisée en cas de conflits avec le document de destination.

```csharp
ImportFormatOptions options = new ImportFormatOptions { KeepSourceNumbering = true };
```

## Étape 4 : Ajouter le document source au document de destination

 Utilisez le`AppendDocument` méthode du document de destination pour ajouter le document source. Passer`ImportFormatMode.UseDestinationStyles` comme deuxième paramètre pour utiliser les styles et le formatage du document de destination.

```csharp
dstDoc.AppendDocument(srcDoc, ImportFormatMode.UseDestinationStyles, options);
```

## Étape 5 : Enregistrez le document de destination

 Enfin, enregistrez le document de destination modifié à l'aide du`Save` méthode du`Document` objet.

```csharp
dstDoc.Save(dataDir + "JoinAndAppendDocuments.AppendWithImportFormatOptions.docx");
```

Ceci termine la mise en œuvre de l’ajout d’un document avec des options de format d’importation à l’aide d’Aspose.Words pour .NET.

### Exemple de code source pour les options d'ajout avec format d'importation à l'aide d'Aspose.Words pour .NET 

```csharp
	// Chemin d'accès à votre répertoire de documents
	string dataDir = "YOUR DOCUMENT DIRECTORY";

	Document srcDoc = new Document(dataDir + "Document source with list.docx");
	Document dstDoc = new Document(dataDir + "Document destination with list.docx");
	// Spécifiez que si la numérotation entre en conflit dans les documents source et de destination,
	// alors la numérotation du document source sera utilisée.
	ImportFormatOptions options = new ImportFormatOptions { KeepSourceNumbering = true };
	dstDoc.AppendDocument(srcDoc, ImportFormatMode.UseDestinationStyles, options);

```