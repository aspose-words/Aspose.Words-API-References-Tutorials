---
title: Slå samman dokument
linktitle: Slå samman dokument
second_title: Aspose.Words för .NET API Referens
description: Steg för steg guide för att förklara C#-källkoden för Merge Documents-funktionen i Aspose.Words för .NET
type: docs
weight: 10
url: /sv/net/split-document/merge-documents/
---

den här handledningen kommer vi att gå igenom hur du slår samman flera Word-dokument med funktionen Merge Documents i Aspose.Words för .NET. Följ stegen nedan för att förstå källkoden och få ett sammanslaget dokument som innehåller alla källdokument.

## Steg 1: Sök efter dokument som ska sammanfogas

Innan vi slår samman dokumenten måste vi hitta källdokumenten som ska slås samman. Här är hur:

```csharp
// Sökväg till dokumentkatalogen.
string dataDir = "YOUR DOCUMENTS DIRECTORY";
// Sök efter dokument som ska sammanfogas.
FileSystemInfo[] documentPaths = new DirectoryInfo(dataDir)
.GetFileSystemInfos("SplitDocument.PageParPage_*.docx").OrderBy(f => f.CreationTime).ToArray();
string sourceDocumentPath =
Directory.GetFiles(dataDir, "SplitDocument.PageParPage_1.docx", SearchOption.TopDirectoryOnly)[0];
```

## Steg 2: Slå samman dokument

Nu kommer vi att slå samman dokumenten ett efter ett för att skapa ett slutgiltigt sammanslaget dokument. Här är hur:

```csharp
// Öppna den första delen av det resulterande dokumentet.
Document sourceDoc = new Document(sourceDocumentPath);

// Skapa ett nytt resulterande dokument.
Document mergedDoc = new Document();
DocumentBuilder mergedDocBuilder = new DocumentBuilder(mergedDoc);

// Slå samman dokumenten ett efter ett.
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

### Exempel på källkod för Merge Documents med Aspose.Words för .NET

Här är den fullständiga källkoden för funktionen Merge Documents i Aspose.Words för .NET:

```csharp
// Sökvägen till dokumentkatalogen.
string dataDir = "YOUR DOCUMENT DIRECTORY";
// Hitta dokument med hjälp av för sammanfogning.
FileSystemInfo[] documentPaths = new DirectoryInfo(dataDir)
	.GetFileSystemInfos("SplitDocument.PageByPage_*.docx").OrderBy(f => f.CreationTime).ToArray();
string sourceDocumentPath =
	Directory.GetFiles(dataDir, "SplitDocument.PageByPage_1.docx", SearchOption.TopDirectoryOnly)[0];

// Öppna den första delen av det resulterande dokumentet.
Document sourceDoc = new Document(sourceDocumentPath);

// Skapa ett nytt resulterande dokument.
Document mergedDoc = new Document();
DocumentBuilder mergedDocBuilder = new DocumentBuilder(mergedDoc);

// Slå samman dokumentdelar en efter en.
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
