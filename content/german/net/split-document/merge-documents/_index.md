---
title: Word-Dokumente zusammenführen
linktitle: Dokumente zusammenführen
second_title: Aspose.Words-Dokumentverarbeitungs-API
description: Erfahren Sie, wie Sie mit Aspose.Words für .NET mehrere Word-Dokumente zusammenführen. Diese leistungsstarke API vereinfacht das Zusammenführen von Dokumenten und macht es effizient und unkompliziert.
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

## Abschluss

Glückwunsch! Sie haben gelernt, wie Sie mehrere Word-Dokumente mit der Funktion „Dokumente zusammenführen“ von Aspose.Words für .NET zusammenführen. Indem Sie dem bereitgestellten Quellcode folgen, können Sie separate Dokumente zu einem einzigen zusammengeführten Dokument kombinieren und dabei die Formatierung jedes Quelldokuments beibehalten.

Das Zusammenführen von Dokumenten kann nützlich sein, wenn Sie Informationen aus mehreren Quellen konsolidieren oder aus einzelnen Teilen ein einheitliches Dokument erstellen möchten. Aspose.Words für .NET bietet eine leistungsstarke API, die den Prozess des Zusammenführens von Dokumenten vereinfacht und ihn effizient und unkompliziert macht.

Entdecken Sie gerne weitere Funktionen von Aspose.Words für .NET, um Ihre Dokumentverarbeitungsmöglichkeiten zu verbessern und Ihren Arbeitsablauf zu optimieren.

### FAQs

#### Wie kann ich Dokumente mit unterschiedlicher Formatierung zusammenführen?

 Beim Zusammenführen von Dokumenten bietet Aspose.Words für .NET die Option, die Formatierung jedes Quelldokuments beizubehalten. Durch die Verwendung der`ImportFormatMode.KeepSourceFormatting` Option behält das zusammengeführte Dokument die Formatierung der Originaldokumente bei. Wenn Sie im gesamten zusammengeführten Dokument eine einheitliche Formatierung anwenden möchten, können Sie die Formatierung nach dem Zusammenführen der Dokumente mithilfe der Aspose.Words-API ändern.

#### Kann ich Dokumente in verschiedenen Formaten zusammenführen?

Ja, Aspose.Words für .NET unterstützt das Zusammenführen von Dokumenten in verschiedenen Formaten, einschließlich DOCX, DOC, RTF und mehr. Sie können Dokumente unterschiedlicher Formate in die Aspose.Words-API laden und sie unabhängig von ihren Originalformaten zu einem einzigen Dokument zusammenführen.

#### Kann ich Dokumente mit komplexen Strukturen wie Tabellen und Bildern zusammenführen?

Absolut! Aspose.Words für .NET ist in der Lage, Dokumente mit komplexen Strukturen, einschließlich Tabellen, Bildern, Kopf- und Fußzeilen und mehr, zusammenzuführen. Die API übernimmt den Zusammenführungsprozess und bewahrt gleichzeitig die Integrität und das Layout des Inhalts in jedem Dokument.

#### Ist es möglich, Dokumente mit unterschiedlichen Seitenausrichtungen oder -größen zusammenzuführen?

Ja, Aspose.Words für .NET verarbeitet während des Zusammenführungsprozesses Dokumente mit unterschiedlichen Seitenausrichtungen oder -größen. Das resultierende zusammengeführte Dokument berücksichtigt die unterschiedlichen Seitenausrichtungen und -größen der Quelldokumente.