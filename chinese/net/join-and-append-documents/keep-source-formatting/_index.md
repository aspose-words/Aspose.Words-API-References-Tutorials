---
title: 保持源格式
linktitle: 保持源格式
second_title: Aspose.Words for .NET API 参考
description: 了解如何使用 Aspose.Words for .NET 将源文档附加到目标文档，同时保留原始格式。
type: docs
weight: 10
url: /zh/net/join-and-append-documents/keep-source-formatting/
---

本教程演示如何使用 Aspose.Words for .NET 将源文档附加到目标文档，同时保留源文档的原始格式。

## 第 1 步：设置项目

确保您具备以下先决条件：

- 已安装 Aspose.Words for .NET 库。您可以从 Aspose 官方网站下载它或使用 NuGet 包管理器来安装它。
- 将保存源文档和目标文档的文档目录路径。

## 步骤 2：创建目标文档和源文档

创建实例`Document`对于目标文档和源文档。

```csharp
//文档目录的路径
string dataDir = "YOUR DOCUMENT DIRECTORY";

Document dstDoc = new Document();
dstDoc.FirstSection.Body.AppendParagraph("Destination document text.");

Document srcDoc = new Document();
srcDoc.FirstSection.Body.AppendParagraph("Source document text.");
```

## 步骤 3：将源文档附加到目标文档

使用`AppendDocument`目标文档附加源文档的方法。经过`ImportFormatMode.KeepSourceFormatting`作为导入格式模式，保留源文档的原始格式。

```csharp
dstDoc.AppendDocument(srcDoc, ImportFormatMode.KeepSourceFormatting);
```

## 第四步：保存修改后的文档

使用以下命令保存修改后的文档`Save`的方法`Document`目的。

```csharp
dstDoc.Save(dataDir + "JoinAndAppendDocuments.KeepSourceFormatting.docx");
```

这样就完成了使用 Aspose.Words for .NET 将源文档附加到目标文档，同时保留原始格式的实现。

### 使用 Aspose.Words for .NET 保持源格式的示例源代码 

```csharp
	//文档目录的路径
	string dataDir = "YOUR DOCUMENT DIRECTORY";

	Document dstDoc = new Document();
	dstDoc.FirstSection.Body.AppendParagraph("Destination document text. ");
	Document srcDoc = new Document();
	srcDoc.FirstSection.Body.AppendParagraph("Source document text. ");
	//将源文档附加到目标文档。
	//通过格式模式以在导入时保留源文档的原始格式。
	dstDoc.AppendDocument(srcDoc, ImportFormatMode.KeepSourceFormatting);
	dstDoc.Save(dataDir + "JoinAndAppendDocuments.KeepSourceFormatting.docx");
```