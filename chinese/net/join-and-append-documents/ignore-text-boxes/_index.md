---
title: 忽略文本框
linktitle: 忽略文本框
second_title: Aspose.Words for .NET API 参考
description: 了解如何使用 Aspose.Words for .NET 附加文档，同时忽略文本框格式。
type: docs
weight: 10
url: /zh/net/join-and-append-documents/ignore-text-boxes/
---

本教程介绍如何使用 Aspose.Words for .NET 附加文档，同时保留文本框的格式。提供的源代码演示了如何设置导入格式选项以在附加过程中包含文本框。

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

## 第 3 步：设置导入格式选项

创建一个实例`ImportFormatOptions`类并设置`IgnoreTextBoxes`财产给`false`。这可确保在附加过程中包含文本框，同时保留其格式。

```csharp
ImportFormatOptions importFormatOptions = new ImportFormatOptions { IgnoreTextBoxes = false };
```

## 第 4 步：附加文本框内容

创建一个`NodeImporter`对象并使用它将文本框节点从源文档导入到目标文档。迭代源文档中的每个段落并将其导入到目标文档。

```csharp
NodeImporter importer = new NodeImporter(srcDoc, dstDoc, ImportFormatMode.KeepSourceFormatting, importFormatOptions);
ParagraphCollection srcParas = srcDoc.FirstSection.Body.Paragraphs;
foreach (Paragraph srcPara in srcParas)
{
    Node importedNode = importer.ImportNode(srcPara, true);
    dstDoc.FirstSection.Body.AppendChild(importedNode);
}
```

## 步骤 5：保存目标文档

最后，使用以下命令保存修改后的目标文档`Save`的方法`Document`目的。

```csharp
dstDoc.Save(dataDir + "JoinAndAppendDocuments.IgnoreTextBoxes.docx");
```

这样就完成了使用 Aspose.Words for .NET 附加文档同时保留文本框格式的实现。

### 使用 Aspose.Words for .NET 忽略文本框的示例源代码 

```csharp
	//文档目录的路径
	string dataDir = "YOUR DOCUMENT DIRECTORY";

	Document srcDoc = new Document(dataDir + "Document source.docx");
	Document dstDoc = new Document(dataDir + "Northwind traders.docx");
	//导入时保持源文本框的格式。
	ImportFormatOptions importFormatOptions = new ImportFormatOptions { IgnoreTextBoxes = false };
	NodeImporter importer = new NodeImporter(srcDoc, dstDoc, ImportFormatMode.KeepSourceFormatting,
		importFormatOptions);
	ParagraphCollection srcParas = srcDoc.FirstSection.Body.Paragraphs;
	foreach (Paragraph srcPara in srcParas)
	{
		Node importedNode = importer.ImportNode(srcPara, true);
		dstDoc.FirstSection.Body.AppendChild(importedNode);
	}
	dstDoc.Save(dataDir + "JoinAndAppendDocuments.IgnoreTextBoxes.docx");
```