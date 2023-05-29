---
title: Unisci documenti
linktitle: Unisci documenti
second_title: Riferimento all'API Aspose.Words per .NET
description: Guida passo passo per spiegare il codice sorgente C# della funzionalità Unisci documenti di Aspose.Words per .NET
type: docs
weight: 10
url: /it/net/split-document/merge-documents/
---

In questo tutorial, ti illustreremo come unire più documenti di Word utilizzando la funzione Unisci documenti di Aspose.Words per .NET. Segui i passaggi seguenti per comprendere il codice sorgente e ottenere un documento unito contenente tutti i documenti di origine.

## Passaggio 1: cerca i documenti da unire

Prima di unire i documenti, dobbiamo individuare i documenti di origine da unire. Ecco come:

```csharp
// Percorso della directory dei documenti.
string dataDir = "YOUR DOCUMENTS DIRECTORY";
// Cerca i documenti da unire.
FileSystemInfo[] documentPaths = new DirectoryInfo(dataDir)
.GetFileSystemInfos("SplitDocument.PageParPage_*.docx").OrderBy(f => f.CreationTime).ToArray();
string sourceDocumentPath =
Directory.GetFiles(dataDir, "SplitDocument.PageParPage_1.docx", SearchOption.TopDirectoryOnly)[0];
```

## Passaggio 2: unisci i documenti

Ora uniremo i documenti uno per uno per creare un documento unito finale. Ecco come:

```csharp
// Apri la prima parte del documento risultante.
Document sourceDoc = new Document(sourceDocumentPath);

// Crea un nuovo documento risultante.
Document mergedDoc = new Document();
DocumentBuilder mergedDocBuilder = new DocumentBuilder(mergedDoc);

// Unire i documenti uno per uno.
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

### Esempio di codice sorgente per Merge Documents utilizzando Aspose.Words per .NET

Ecco il codice sorgente completo per la funzione Merge Documents di Aspose.Words per .NET:

```csharp
// Il percorso della directory dei documenti.
string dataDir = "YOUR DOCUMENT DIRECTORY";
// Trova i documenti usando per unire.
FileSystemInfo[] documentPaths = new DirectoryInfo(dataDir)
	.GetFileSystemInfos("SplitDocument.PageByPage_*.docx").OrderBy(f => f.CreationTime).ToArray();
string sourceDocumentPath =
	Directory.GetFiles(dataDir, "SplitDocument.PageByPage_1.docx", SearchOption.TopDirectoryOnly)[0];

// Apri la prima parte del documento risultante.
Document sourceDoc = new Document(sourceDocumentPath);

// Crea un nuovo documento risultante.
Document mergedDoc = new Document();
DocumentBuilder mergedDocBuilder = new DocumentBuilder(mergedDoc);

// Unisci le parti del documento una per una.
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
