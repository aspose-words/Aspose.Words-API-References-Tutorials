---
title: 保留源格式
linktitle: 保留源格式
second_title: Aspose.Words 文档处理 API
description: 了解如何使用 Aspose.Words for .NET 将源文档附加到目标文档，同时保留原始格式。
type: docs
weight: 10
url: /zh/net/join-and-append-documents/keep-source-formatting/
---

本教程演示如何使用 Aspose.Words for .NET 将源文档附加到目标文档，同时保留源文档的原始格式。

## 步骤 1：设置项目

确保您满足以下先决条件：

- 已安装 Aspose.Words for .NET 库。您可以从以下位置下载[Aspose.Releases]https://releases.aspose.com/words/net/ 或使用 NuGet 包管理器来安装。
- 保存源文档和目标文档的文档目录路径。

## 步骤 2：创建目标文档和源文档

创建实例`Document`用于目标文档和源文档。

```csharp
//文档目录的路径
string dataDir = "YOUR DOCUMENT DIRECTORY";

Document dstDoc = new Document();
dstDoc.FirstSection.Body.AppendParagraph("Destination document text.");

Document srcDoc = new Document();
srcDoc.FirstSection.Body.AppendParagraph("Source document text.");
```

## 步骤 3：将源文档附加到目标文档

使用`AppendDocument`方法来追加源文档。传递`ImportFormatMode.KeepSourceFormatting`作为导入格式模式以保留源文档的原始格式。

```csharp
dstDoc.AppendDocument(srcDoc, ImportFormatMode.KeepSourceFormatting);
```

## 步骤 4：保存修改后的文档

使用保存修改后的文档`Save`方法`Document`目的。

```csharp
dstDoc.Save(dataDir + "JoinAndAppendDocuments.KeepSourceFormatting.docx");
```

这完成了使用 Aspose.Words for .NET 将源文档附加到目标文档同时保留原始格式的实现。

### 使用 Aspose.Words for .NET 保留源格式的示例源代码 

```csharp
	//文档目录的路径
	string dataDir = "YOUR DOCUMENT DIRECTORY";

	Document dstDoc = new Document();
	dstDoc.FirstSection.Body.AppendParagraph("Destination document text. ");
	Document srcDoc = new Document();
	srcDoc.FirstSection.Body.AppendParagraph("Source document text. ");
	//将源文档附加到目标文档。
	//传递格式模式在导入时保留源文档的原始格式。
	dstDoc.AppendDocument(srcDoc, ImportFormatMode.KeepSourceFormatting);
	dstDoc.Save(dataDir + "JoinAndAppendDocuments.KeepSourceFormatting.docx");
```