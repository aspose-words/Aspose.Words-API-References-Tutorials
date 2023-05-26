---
title: 忽略页眉页脚
linktitle: 忽略页眉页脚
second_title: Aspose.Words for .NET API 参考
description: 了解如何使用 Aspose.Words for .NET 在忽略页眉和页脚内容的同时附加文档。
type: docs
weight: 10
url: /zh/net/join-and-append-documents/ignore-header-footer/
---

本教程解释了如何使用 Aspose.Words for .NET 在忽略页眉和页脚内容的同时附加文档。提供的源代码演示了如何设置导入格式选项以在附加过程中排除页眉和页脚。

## 第 1 步：设置项目

确保您具有以下先决条件：

- 安装了 Aspose.Words for .NET 库。您可以从 Aspose 官方网站下载或使用 NuGet 包管理器安装它。
- 源文档和目标文档所在的文档目录路径。

## 第 2 步：打开源文档和目标文档

使用打开源文档和目标文档`Document`类构造函数。代替`"YOUR DOCUMENT DIRECTORY"`使用文档目录的实际路径。

```csharp
//文档目录的路径
string dataDir = "YOUR DOCUMENT DIRECTORY";

Document srcDocument = new Document(dataDir + "Document source.docx");
Document dstDocument = new Document(dataDir + "Northwind traders.docx");
```

## 第 3 步：设置导入格式选项

创建一个实例`ImportFormatOptions`类并设置`IgnoreHeaderFooter`财产给`false`.这可确保在附加过程中包含页眉和页脚内容。

```csharp
ImportFormatOptions importFormatOptions = new ImportFormatOptions { IgnoreHeaderFooter = false };
```

## 第 4 步：将源文档附加到目标文档

使用`AppendDocument`附加源文档的目标文档的方法。经过`ImportFormatMode.KeepSourceFormatting`作为第二个参数，导入格式选项作为第三个参数。

```csharp
dstDocument.AppendDocument(srcDocument, ImportFormatMode.KeepSourceFormatting, importFormatOptions);
```

## 第 5 步：保存目标文档

最后，使用保存修改后的目标文档`Save`的方法`Document`目的。

```csharp
dstDocument.Save(dataDir + "JoinAndAppendDocuments.IgnoreHeaderFooter.docx");
```

这样就完成了使用 Aspose.Words for .NET 忽略页眉和页脚内容附加文档的实现。

### 使用 Aspose.Words for .NET 的忽略页眉页脚的示例源代码 

```csharp
	//文档目录的路径
	string dataDir = "YOUR DOCUMENT DIRECTORY";

	Document srcDocument = new Document(dataDir + "Document source.docx");
	Document dstDocument = new Document(dataDir + "Northwind traders.docx");
	ImportFormatOptions importFormatOptions = new ImportFormatOptions { IgnoreHeaderFooter = false };
	dstDocument.AppendDocument(srcDocument, ImportFormatMode.KeepSourceFormatting, importFormatOptions);
	dstDocument.Save(dataDir + "JoinAndAppendDocuments.IgnoreHeaderFooter.docx");
```