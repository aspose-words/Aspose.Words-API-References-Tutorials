---
title: 合并Word文档
linktitle: 合并文档
second_title: Aspose.Words 文档处理 API
description: 了解如何使用 Aspose.Words for .NET 合并多个 Word 文档。这个强大的 API 简化了合并文档的过程，使其高效且简单。
type: docs
weight: 10
url: /zh/net/split-document/merge-documents/
---

在本教程中，我们将引导您了解如何使用 Aspose.Words for .NET 的合并文档功能合并多个 Word 文档。按照以下步骤了解源代码并获得包含所有源文档的合并文档。

## 第 1 步：搜索要合并的文档

在合并文档之前，我们需要找到要合并的源文档。就是这样：

```csharp
//文档目录的路径。
string dataDir = "YOUR DOCUMENTS DIRECTORY";
//搜索要合并的文档。
FileSystemInfo[] documentPaths = new DirectoryInfo(dataDir)
.GetFileSystemInfos("SplitDocument.PageParPage_*.docx").OrderBy(f => f.CreationTime).ToArray();
string sourceDocumentPath =
Directory.GetFiles(dataDir, "SplitDocument.PageParPage_1.docx", SearchOption.TopDirectoryOnly)[0];
```

## 第 2 步：合并文档

现在我们将逐个合并文档以创建最终的合并文档。就是这样：

```csharp
//打开生成的文档的第一部分。
Document sourceDoc = new Document(sourceDocumentPath);

//创建一个新的结果文档。
Document mergedDoc = new Document();
DocumentBuilder mergedDocBuilder = new DocumentBuilder(mergedDoc);

//将文档一一合并。
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

### 使用 Aspose.Words for .NET 合并文档的示例源代码

以下是 Aspose.Words for .NET 合并文档功能的完整源代码：

```csharp
//文档目录的路径。
string dataDir = "YOUR DOCUMENT DIRECTORY";
//查找用于合并的文档。
FileSystemInfo[] documentPaths = new DirectoryInfo(dataDir)
	.GetFileSystemInfos("SplitDocument.PageByPage_*.docx").OrderBy(f => f.CreationTime).ToArray();
string sourceDocumentPath =
	Directory.GetFiles(dataDir, "SplitDocument.PageByPage_1.docx", SearchOption.TopDirectoryOnly)[0];

//打开生成的文档的第一部分。
Document sourceDoc = new Document(sourceDocumentPath);

//创建一个新的结果文档。
Document mergedDoc = new Document();
DocumentBuilder mergedDocBuilder = new DocumentBuilder(mergedDoc);

//将文档部分逐一合并。
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

## 结论

恭喜！您已经学习了如何使用 Aspose.Words for .NET 的合并文档功能来合并多个 Word 文档。通过遵循提供的源代码，您可以将单独的文档合并为单个合并文档，同时保留每个源文档的格式。

当您想要合并多个来源的信息或从各个部分创建统一的文档时，合并文档会很有用。 Aspose.Words for .NET 提供了强大的 API，可以简化合并文档的过程，使其高效且简单。

请随意探索 Aspose.Words for .NET 提供的其他功能，以增强您的文档处理能力并简化您的工作流程。

### 常见问题解答

#### 如何合并不同格式的文档？

合并文档时，Aspose.Words for .NET 提供保留每个源文档格式的选项。通过使用`ImportFormatMode.KeepSourceFormatting`选项，合并的文档将保留原始文档的格式。如果您想在整个合并文档中应用一致的格式，您可以在合并文档后使用 Aspose.Words API 修改格式。

#### 我可以合并不同格式的文档吗？

是的，Aspose.Words for .NET 支持合并各种格式的文档，包括 DOCX、DOC、RTF 等。您可以将不同格式的文档加载到Aspose.Words API中并将它们合并到一个文档中，无论其原始格式如何。

#### 我可以合并具有复杂结构的文档，例如表格和图像吗？

绝对地！ Aspose.Words for .NET 能够合并具有复杂结构的文档，包括表格、图像、页眉、页脚等。 API 处理合并过程，同时保留每个文档中内容的完整性和布局。

#### 是否可以合并具有不同页面方向或尺寸的文档？

是的，Aspose.Words for .NET 在合并过程中处理具有不同页面方向或大小的文档。生成的合并文档将适应源文档的不同页面方向和大小。