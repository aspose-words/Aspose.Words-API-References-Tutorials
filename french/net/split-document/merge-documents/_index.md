---
title: Fusionner des documents
linktitle: Fusionner des documents
second_title: Référence de l'API Aspose.Words pour .NET
description: Guide étape par étape pour expliquer le code source C # de la fonctionnalité de fusion de documents d'Aspose.Words pour .NET
type: docs
weight: 10
url: /fr/net/split-document/merge-documents/
---

Dans ce didacticiel, nous vous expliquerons comment fusionner plusieurs documents Word à l'aide de la fonctionnalité de fusion de documents d'Aspose.Words pour .NET. Suivez les étapes ci-dessous pour comprendre le code source et obtenir un document fusionné contenant tous les documents sources.

## Étape 1 : Rechercher des documents à fusionner

Avant de fusionner les documents, nous devons localiser les documents source à fusionner. Voici comment:

```csharp
// Chemin d'accès au répertoire des documents.
string dataDir = "YOUR DOCUMENTS DIRECTORY";
// Rechercher des documents à fusionner.
FileSystemInfo[] documentPaths = new DirectoryInfo(dataDir)
.GetFileSystemInfos("SplitDocument.PageParPage_*.docx").OrderBy(f => f.CreationTime).ToArray();
string sourceDocumentPath =
Directory.GetFiles(dataDir, "SplitDocument.PageParPage_1.docx", SearchOption.TopDirectoryOnly)[0];
```

## Étape 2 : fusionner des documents

Nous allons maintenant fusionner les documents un par un pour créer un document fusionné final. Voici comment:

```csharp
// Ouvrez la première partie du document résultant.
Document sourceDoc = new Document(sourceDocumentPath);

// Créez un nouveau document résultant.
Document mergedDoc = new Document();
DocumentBuilder mergedDocBuilder = new DocumentBuilder(mergedDoc);

// Fusionner les documents un par un.
foreach(FileSystemInfo documentPath in documentPaths)
{
if (documentPath.FullName == sourceDocumentPath)
keep on going;

mergedDocBuilder.MoveToDocumentEnd();
mergedDocBuilder.InsertDocument(sourceDoc, ImportFormatMode.KeepSourceFormatting);
sourceDoc = new Document(documentPath.FullName);
}

mergedDoc.Save(dataDir + "SplitDocument.MergeDocuments.docx");
```

### Exemple de code source pour fusionner des documents à l'aide d'Aspose.Words pour .NET

Voici le code source complet de la fonctionnalité de fusion de documents d'Aspose.Words pour .NET :

```csharp
// Chemin d'accès au répertoire des documents.
string dataDir = "YOUR DOCUMENT DIRECTORY";
// Rechercher des documents à l'aide de la fusion.
FileSystemInfo[] documentPaths = new DirectoryInfo(dataDir)
	.GetFileSystemInfos("SplitDocument.PageByPage_*.docx").OrderBy(f => f.CreationTime).ToArray();
string sourceDocumentPath =
	Directory.GetFiles(dataDir, "SplitDocument.PageByPage_1.docx", SearchOption.TopDirectoryOnly)[0];

// Ouvrez la première partie du document résultant.
Document sourceDoc = new Document(sourceDocumentPath);

// Créez un nouveau document résultant.
Document mergedDoc = new Document();
DocumentBuilder mergedDocBuilder = new DocumentBuilder(mergedDoc);

// Fusionnez les parties du document une par une.
foreach (FileSystemInfo documentPath in documentPaths)
{
	if (documentPath.FullName == sourceDocumentPath)
		continue;

	mergedDocBuilder.MoveToDocumentEnd();
	mergedDocBuilder.InsertDocument(sourceDoc, ImportFormatMode.KeepSourceFormatting);
	sourceDoc = new Document(documentPath.FullName);
}

mergedDoc.Save(dataDir + "SplitDocument.MergeDocuments.docx");
```
