---
title: 将文档附加到空白处
linktitle: 将文档附加到空白处
second_title: Aspose.Words 文档处理 API
description: 了解如何在 Aspose.Words for .NET 中将文档附加到空白目标文档。
type: docs
weight: 10
url: /zh/net/join-and-append-documents/append-document-to-blank/
---

本教程介绍如何使用 Aspose.Words for .NET 将一个文档的内容附加到空白目标文档。提供的源代码演示了如何创建新文档、删除其内容，然后将源文档附加到该文档。

## 步骤 1：设置项目

确保您满足以下先决条件：

- 已安装 Aspose.Words for .NET 库。您可以从以下位置下载[Aspose.Releases]https://releases.aspose.com/words/net/ 或使用 NuGet 包管理器来安装。
- 源文档和目标文档所在的文档目录路径。

## 步骤 2：创建新的目标文档

创建一个新的`Document`目标文档的对象。

```csharp
//文档目录的路径
string dataDir = "YOUR DOCUMENT DIRECTORY";

Document srcDoc = new Document(dataDir + "Document source.docx");
Document dstDoc = new Document();
```

## 步骤 3：从目标文档中删除现有内容

为了确保目标文档干净，请使用`RemoveAllChildren`方法。

```csharp
dstDoc.RemoveAllChildren();
```

## 步骤 4：将源文档附加到目标文档

使用将源文档的内容附加到目标文档`AppendDocument`方法`ImportFormatMode.KeepSourceFormatting`选项。

```csharp
dstDoc.AppendDocument(srcDoc, ImportFormatMode.KeepSourceFormatting);
```

## 步骤 5：保存目标文档

最后，使用`Save`方法`Document`目的。

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
	//目标文档不为空，经常导致附加文档前出现空白页。
	//这是因为基础文档有一个空白部分并且新文档从下一页开始。
	//附加之前从目标文档中删除所有内容。
	dstDoc.RemoveAllChildren();
	dstDoc.AppendDocument(srcDoc, ImportFormatMode.KeepSourceFormatting);
	dstDoc.Save(dataDir + "JoinAndAppendDocuments.AppendDocumentToBlank.docx");

```