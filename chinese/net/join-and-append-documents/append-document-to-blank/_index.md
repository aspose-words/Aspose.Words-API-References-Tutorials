---
title: 将文档附加到空白
linktitle: 将文档附加到空白
second_title: Aspose.Words for .NET API 参考
description: 了解如何在 Aspose.Words for .NET 中将文档附加到空白目标文档。
type: docs
weight: 10
url: /zh/net/join-and-append-documents/append-document-to-blank/
---

本教程解释了如何使用 Aspose.Words for .NET 将一个文档的内容附加到一个空白的目标文档中。提供的源代码演示了如何创建新文档、删除其内容，然后将源文档附加到其中。

## 第 1 步：设置项目

确保您具有以下先决条件：

- 安装了 Aspose.Words for .NET 库。您可以从 Aspose 官方网站下载或使用 NuGet 包管理器安装它。
- 源文档和目标文档所在的文档目录路径。

## 第 2 步：创建新的目标文档

创建一个新的`Document`目标文档的对象。

```csharp
//文档目录的路径
string dataDir = "YOUR DOCUMENT DIRECTORY";

Document srcDoc = new Document(dataDir + "Document source.docx");
Document dstDoc = new Document();
```

## 第 3 步：从目标文档中删除现有内容

为确保目标文档干净，请使用`RemoveAllChildren`方法。

```csharp
dstDoc.RemoveAllChildren();
```

## 第 4 步：将源文档附加到目标文档

使用将源文档的内容附加到目标文档`AppendDocument`方法与`ImportFormatMode.KeepSourceFormatting`选项。

```csharp
dstDoc.AppendDocument(srcDoc, ImportFormatMode.KeepSourceFormatting);
```

## 第 5 步：保存目标文档

最后，使用保存修改后的目标文档`Save`的方法`Document`目的。

```csharp
dstDoc.Save(dataDir + "JoinAndAppendDocuments.AppendDocumentToBlank.docx");
```

这样就完成了使用 Aspose.Words for .NET 将文档附加到空白目标文档的实现。

### 使用 Aspose.Words for .NET 将文档附加到空白的示例源代码 

```csharp
	//文档目录的路径
	string dataDir = "YOUR DOCUMENT DIRECTORY";

	Document srcDoc = new Document(dataDir + "Document source.docx");
	Document dstDoc = new Document();
	//目标文档不为空，通常会导致在附加文档之前出现空白页。
	//这是因为基础文档有一个空白部分，而新文档在下一页开始。
	//在附加之前从目标文档中删除所有内容。
	dstDoc.RemoveAllChildren();
	dstDoc.AppendDocument(srcDoc, ImportFormatMode.KeepSourceFormatting);
	dstDoc.Save(dataDir + "JoinAndAppendDocuments.AppendDocumentToBlank.docx");

```