---
title: 使用生成器插入文档
linktitle: 使用生成器插入文档
second_title: Aspose.Words for .NET API 参考
description: 了解如何使用 Aspose.Words for .NET 在另一个文档的末尾插入一个文档。
type: docs
weight: 10
url: /zh/net/join-and-append-documents/insert-document-with-builder/
---

本教程解释了如何使用 Aspose.Words for .NET 将一个文档插入到另一个文档中，使用`DocumentBuilder`班级。提供的源代码演示了如何在保留源格式的同时将一个文档插入另一个文档的末尾。

## 第 1 步：设置项目

确保您具有以下先决条件：

- 安装了 Aspose.Words for .NET 库。您可以从 Aspose 官方网站下载或使用 NuGet 包管理器安装它。
- 源文档和目标文档所在的文档目录路径。

## 第 2 步：打开源文档和目标文档

使用打开源文档和目标文档`Document`类构造函数。代替`"YOUR DOCUMENT DIRECTORY"`使用文档目录的实际路径。

```csharp
//文档目录的路径
string dataDir = "YOUR DOCUMENT DIRECTORY";

Document srcDoc = new Document(dataDir + "Document source.docx");
Document dstDoc = new Document(dataDir + "Northwind traders.docx");
```

## 第 3 步：初始化 DocumentBuilder

创建一个新的实例`DocumentBuilder`类并将目标文档作为参数传递。

```csharp
DocumentBuilder builder = new DocumentBuilder(dstDoc);
```

## 第 4 步：定位 DocumentBuilder

移动`DocumentBuilder`到文档末尾使用`MoveToDocumentEnd`方法。插入分页符以将现有内容与插入的文档分开。

```csharp
builder.MoveToDocumentEnd();
builder.InsertBreak(BreakType.PageBreak);
```

## 第五步：插入源文档

使用`InsertDocument`的方法`DocumentBuilder`将源文档插入目标文档的类。设置导入格式模式为`ImportFormatMode.KeepSourceFormatting`保留源格式。

```csharp
builder.InsertDocument(srcDoc, ImportFormatMode.KeepSourceFormatting);
```

## 第 6 步：保存修改后的文件

最后，使用保存修改后的目标文档`Save`的方法`Document`目的。

```csharp
builder.Document.Save(dataDir + "JoinAndAppendDocuments.InsertDocumentWithBuilder.docx");
```

这样就完成了使用Aspose.Words for .NET 将一个文档插入另一个文档的实现。

### 使用 Aspose.Words for .NET 的 Insert Document With Builder 的示例源代码 

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