---
title: 合并文档
linktitle: 合并文档
second_title: Aspose.Words for .NET API 参考
description: 分步指南解释 Aspose.Words for .NET 的合并文档功能的 C# 源代码
type: docs
weight: 10
url: /zh/net/split-document/merge-documents/
---

在本教程中，我们将向您介绍如何使用 Aspose.Words for .NET 的合并文档功能合并多个 Word 文档。按照以下步骤了解源代码并获得包含所有源文档的合并文档。

## 第 1 步：搜索要合并的文档

在合并文档之前，我们需要定位到要合并的源文档。就是这样：

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

现在我们将一个一个地合并文档以创建最终的合并文档。就是这样：

```csharp
//打开生成的文档的第一部分。
Document sourceDoc = new Document(sourceDocumentPath);

//创建一个新的结果文档。
Document mergedDoc = new Document();
DocumentBuilder mergedDocBuilder = new DocumentBuilder(mergedDoc);

//一张一张合并文件。
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

以下是 Aspose.Words for .NET 的合并文档功能的完整源代码：

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

//一个接一个地合并文档部分。
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
