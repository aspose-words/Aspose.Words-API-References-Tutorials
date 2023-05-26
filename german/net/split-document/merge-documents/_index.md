---
title: Dokumente zusammenführen
linktitle: Dokumente zusammenführen
second_title: Aspose.Words für .NET API-Referenz
description: Schritt-für-Schritt-Anleitung zur Erläuterung des C#-Quellcodes der Funktion „Dokumente zusammenführen“ von Aspose.Words für .NET
type: docs
weight: 10
url: /de/net/split-document/merge-documents/
---

In diesem Tutorial zeigen wir Ihnen, wie Sie mehrere Word-Dokumente mithilfe der Funktion „Dokumente zusammenführen“ von Aspose.Words für .NET zusammenführen. Führen Sie die folgenden Schritte aus, um den Quellcode zu verstehen und ein zusammengeführtes Dokument mit allen Quelldokumenten zu erhalten.

## Schritt 1: Suchen Sie nach zusammenzuführenden Dokumenten

Bevor wir die Dokumente zusammenführen, müssen wir die zusammenzuführenden Quelldokumente finden. Hier ist wie:

```csharp
// Pfad zum Dokumentenverzeichnis.
string dataDir = "YOUR DOCUMENTS DIRECTORY";
// Suchen Sie nach zusammenzuführenden Dokumenten.
FileSystemInfo[] documentPaths = new DirectoryInfo(dataDir)
.GetFileSystemInfos("SplitDocument.PageParPage_*.docx").OrderBy(f => f.CreationTime).ToArray();
string sourceDocumentPath =
Directory.GetFiles(dataDir, "SplitDocument.PageParPage_1.docx", SearchOption.TopDirectoryOnly)[0];
```

## Schritt 2: Dokumente zusammenführen

Jetzt führen wir die Dokumente einzeln zusammen, um ein endgültiges zusammengeführtes Dokument zu erstellen. Hier ist wie:

```csharp
// Öffnen Sie den ersten Teil des resultierenden Dokuments.
Document sourceDoc = new Document(sourceDocumentPath);

// Erstellen Sie ein neues resultierendes Dokument.
Document mergedDoc = new Document();
DocumentBuilder mergedDocBuilder = new DocumentBuilder(mergedDoc);

// Führen Sie die Dokumente einzeln zusammen.
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

### Beispielquellcode für Merge Documents mit Aspose.Words für .NET

Hier ist der vollständige Quellcode für die Funktion „Dokumente zusammenführen“ von Aspose.Words für .NET:

```csharp

	// Der Pfad zum Dokumentenverzeichnis.
	string dataDir = "YOUR DOCUMENT DIRECTORY";
	// Suchen Sie nach Dokumenten, die zum Zusammenführen verwendet werden.
	FileSystemInfo[] documentPaths = new DirectoryInfo(dataDir)
		.GetFileSystemInfos("SplitDocument.PageByPage_*.docx").OrderBy(f => f.CreationTime).ToArray();
	string sourceDocumentPath =
		Directory.GetFiles(dataDir, "SplitDocument.PageByPage_1.docx", SearchOption.TopDirectoryOnly)[0];

	// Öffnen Sie den ersten Teil des resultierenden Dokuments.
	Document sourceDoc = new Document(sourceDocumentPath);

	// Erstellen Sie ein neues resultierendes Dokument.
	Document mergedDoc = new Document();
	DocumentBuilder mergedDocBuilder = new DocumentBuilder(mergedDoc);

	// Dokumentteile einzeln zusammenführen.
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
