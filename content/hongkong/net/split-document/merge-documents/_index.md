---
title: 合併Word文檔
linktitle: 合併文檔
second_title: Aspose.Words 文件處理 API
description: 了解如何使用 Aspose.Words for .NET 合併多個 Word 文件。這個強大的 API 簡化了合併文件的過程，使其高效且簡單。
type: docs
weight: 10
url: /zh-hant/net/split-document/merge-documents/
---

在本教學中，我們將引導您了解如何使用 Aspose.Words for .NET 的合併文件功能合併多個 Word 文件。請按照以下步驟了解原始程式碼並取得包含所有來源文件的合併文件。

## 第 1 步：搜尋要合併的文檔

在合併文件之前，我們需要找到要合併的來源文件。就是這樣：

```csharp
//文檔目錄的路徑。
string dataDir = "YOUR DOCUMENTS DIRECTORY";
//搜尋要合併的文檔。
FileSystemInfo[] documentPaths = new DirectoryInfo(dataDir)
.GetFileSystemInfos("SplitDocument.PageParPage_*.docx").OrderBy(f => f.CreationTime).ToArray();
string sourceDocumentPath =
Directory.GetFiles(dataDir, "SplitDocument.PageParPage_1.docx", SearchOption.TopDirectoryOnly)[0];
```

## 第 2 步：合併文檔

現在我們將逐一合併文件以建立最終的合併文件。就是這樣：

```csharp
//開啟產生的文件的第一部分。
Document sourceDoc = new Document(sourceDocumentPath);

//建立一個新的結果文件。
Document mergedDoc = new Document();
DocumentBuilder mergedDocBuilder = new DocumentBuilder(mergedDoc);

//將文檔一一合併。
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

### 使用 Aspose.Words for .NET 合併文件的範例原始碼

以下是 Aspose.Words for .NET 合併文件功能的完整原始碼：

```csharp
//文檔目錄的路徑。
string dataDir = "YOUR DOCUMENT DIRECTORY";
//尋找用於合併的文檔。
FileSystemInfo[] documentPaths = new DirectoryInfo(dataDir)
	.GetFileSystemInfos("SplitDocument.PageByPage_*.docx").OrderBy(f => f.CreationTime).ToArray();
string sourceDocumentPath =
	Directory.GetFiles(dataDir, "SplitDocument.PageByPage_1.docx", SearchOption.TopDirectoryOnly)[0];

//開啟產生的文件的第一部分。
Document sourceDoc = new Document(sourceDocumentPath);

//建立一個新的結果文件。
Document mergedDoc = new Document();
DocumentBuilder mergedDocBuilder = new DocumentBuilder(mergedDoc);

//將文件部分逐一合併。
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

## 結論

恭喜！您已經學習如何使用 Aspose.Words for .NET 的合併文件功能來合併多個 Word 文件。透過遵循提供的原始程式碼，您可以將單獨的文檔合併為單一合併文檔，同時保留每個來源文檔的格式。

當您想要合併多個來源的資訊或從各個部分建立統一的文件時，合併文件會很有用。 Aspose.Words for .NET 提供了強大的 API，可以簡化合併文件的流程，使其高效且簡單。

請隨意探索 Aspose.Words for .NET 提供的其他功能，以增強您的文件處理能力並簡化您的工作流程。

### 常見問題解答

#### 如何合併不同格式的文件？

合併文件時，Aspose.Words for .NET 提供保留每個來源文件格式的選項。透過使用`ImportFormatMode.KeepSourceFormatting`選項，合併的文檔將保留原始文檔的格式。如果您想要在整個合併文件中套用一致的格式，您可以在合併文件後使用 Aspose.Words API 修改格式。

#### 我可以合併不同格式的文件嗎？

是的，Aspose.Words for .NET 支援合併各種格式的文檔，包括 DOCX、DOC、RTF 等。您可以將不同格式的文件載入到Aspose.Words API中並將它們合併到一個文件中，無論其原始格式為何。

#### 我可以合併具有複雜結構的文檔，例如表格和圖像嗎？

絕對地！ Aspose.Words for .NET 能夠合併具有複雜結構的文檔，包括表格、圖像、頁首、頁尾等。 API 處理合併過程，同時保留每個文件中內容的完整性和佈局。

#### 是否可以合併具有不同頁面方向或尺寸的文件？

是的，Aspose.Words for .NET 在合併過程中處理具有不同頁面方向或大小的文件。產生的合併文件將適應來源文件的不同頁面方向和大小。