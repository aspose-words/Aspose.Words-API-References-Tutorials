---
title: 使用生成器插入文档
linktitle: 使用生成器插入文档
second_title: Aspose.Words 文档处理 API
description: 了解如何使用 Aspose.Words for .NET 在另一个文档的末尾插入一个文档。
type: docs
weight: 10
url: /zh/net/join-and-append-documents/insert-document-with-builder/
---

本教程介绍如何使用 Aspose.Words for .NET 将一个文档插入到另一个文档中`DocumentBuilder`班级。提供的源代码演示了如何在另一个文档的末尾插入一个文档，同时保留源格式。

## 第 1 步：设置项目

确保您具备以下先决条件：

- 已安装 Aspose.Words for .NET 库。您可以从 Aspose 官方网站下载它或使用 NuGet 包管理器来安装它。
- 源文档和目标文档所在的文档目录路径。

## 步骤 2：打开源文档和目标文档

使用以下命令打开源文档和目标文档`Document`类构造函数。代替`"YOUR DOCUMENT DIRECTORY"`与文档目录的实际路径。

```csharp
//文档目录的路径
string dataDir = "YOUR DOCUMENT DIRECTORY";

Document srcDoc = new Document(dataDir + "Document source.docx");
Document dstDoc = new Document(dataDir + "Northwind traders.docx");
```

## 第 3 步：初始化 DocumentBuilder

创建一个新实例`DocumentBuilder`类并将目标文档作为参数传递。

```csharp
DocumentBuilder builder = new DocumentBuilder(dstDoc);
```

## 第 4 步：定位 DocumentBuilder

移动`DocumentBuilder`到文档末尾，使用`MoveToDocumentEnd`方法。插入分页符以将现有内容与插入的文档分开。

```csharp
builder.MoveToDocumentEnd();
builder.InsertBreak(BreakType.PageBreak);
```

## 第5步：插入源文档

使用`InsertDocument`的方法`DocumentBuilder`类将源文档插入到目标文档中。将导入格式模式设置为`ImportFormatMode.KeepSourceFormatting`保留源格式。

```csharp
builder.InsertDocument(srcDoc, ImportFormatMode.KeepSourceFormatting);
```

## 第六步：保存修改后的文档

最后，使用以下命令保存修改后的目标文档`Save`的方法`Document`目的。

```csharp
builder.Document.Save(dataDir + "JoinAndAppendDocuments.InsertDocumentWithBuilder.docx");
```

这样就完成了使用 Aspose.Words for .NET 将一个文档插入另一个文档的实现。

### 使用 Aspose.Words for .NET 插入文档与生成器的示例源代码 

```csharp
	//文档目录的路径
	string dataDir = "YOUR DOCUMENT DIRECTORY";

	Document srcDoc = new Document(dataDir + "Document source.docx");
	Document dstDoc = new Document(dataDir + "Northwind traders.docx");
	DocumentBuilder builder = new DocumentBuilder(dstDoc);
	builder.MoveToDocumentEnd();
	builder.InsertBreak(BreakType.PageBreak);
	builder.InsertDocument(srcDoc, ImportFormatMode.KeepSourceFormatting);
	builder.Document.Save(dataDir + "JoinAndAppendDocuments.InsertDocumentWithBuilder.docx");
```