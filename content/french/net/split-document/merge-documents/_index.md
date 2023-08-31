---
title: Fusionner des documents Word
linktitle: Fusionner des documents
second_title: API de traitement de documents Aspose.Words
description: Apprenez à fusionner plusieurs documents Word à l'aide d'Aspose.Words pour .NET. Cette puissante API simplifie le processus de fusion de documents, le rendant efficace et simple.
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

## Conclusion

Toutes nos félicitations! Vous avez appris à fusionner plusieurs documents Word à l'aide de la fonctionnalité de fusion de documents d'Aspose.Words pour .NET. En suivant le code source fourni, vous pouvez combiner des documents distincts en un seul document fusionné tout en préservant la mise en forme de chaque document source.

La fusion de documents peut être utile lorsque vous souhaitez consolider des informations provenant de plusieurs sources ou créer un document unifié à partir de parties individuelles. Aspose.Words pour .NET fournit une API puissante qui simplifie le processus de fusion de documents, le rendant efficace et simple.

N'hésitez pas à explorer d'autres fonctionnalités offertes par Aspose.Words pour .NET pour améliorer vos capacités de traitement de documents et rationaliser votre flux de travail.

### FAQ

#### Comment puis-je fusionner des documents avec un formatage différent ?

 Lors de la fusion de documents, Aspose.Words pour .NET offre la possibilité de conserver la mise en forme de chaque document source. En utilisant le`ImportFormatMode.KeepSourceFormatting` option, le document fusionné conservera le formatage des documents originaux. Si vous souhaitez appliquer une mise en forme cohérente dans tout le document fusionné, vous pouvez modifier la mise en forme à l'aide de l'API Aspose.Words après avoir fusionné les documents.

#### Puis-je fusionner des documents dans différents formats ?

Oui, Aspose.Words pour .NET prend en charge la fusion de documents dans différents formats, notamment DOCX, DOC, RTF, etc. Vous pouvez charger des documents de différents formats dans l'API Aspose.Words et les fusionner en un seul document, quels que soient leurs formats d'origine.

#### Puis-je fusionner des documents avec des structures complexes, telles que des tableaux et des images ?

Absolument! Aspose.Words pour .NET est capable de fusionner des documents avec des structures complexes, notamment des tableaux, des images, des en-têtes, des pieds de page, etc. L'API gère le processus de fusion tout en préservant l'intégrité et la mise en page du contenu de chaque document.

#### Est-il possible de fusionner des documents avec des orientations ou des tailles de page différentes ?

Oui, Aspose.Words pour .NET gère les documents avec différentes orientations ou tailles de page pendant le processus de fusion. Le document fusionné qui en résulte s'adaptera aux différentes orientations et tailles de page des documents source.