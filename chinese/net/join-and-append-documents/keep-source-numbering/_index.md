---
title: 保留来源编号
linktitle: 保留来源编号
second_title: Aspose.Words for .NET API 参考
description: 了解如何在 Aspose.Words for .NET 中保留源编号格式的同时附加文档。
type: docs
weight: 10
url: /zh/net/join-and-append-documents/keep-source-numbering/
---

本教程解释了如何使用 Aspose.Words for .NET 将源文档附加到目标文档，同时保留编号段落的原始编号格式。

## 第 1 步：设置项目

确保您具备以下先决条件：

- 安装了 Aspose.Words for .NET 库。您可以从 Aspose 官方网站下载或使用 NuGet 包管理器安装它。
- 将保存源文档和目标文档的文档目录路径。

## 第 2 步：创建目标文档和源文档

创建实例`Document`对于目标文件和源文件。

```csharp
//文档目录的路径
string dataDir = "YOUR DOCUMENT DIRECTORY";

Document srcDoc = new Document(dataDir + "Document source.docx");
Document dstDoc = new Document(dataDir + "Northwind traders.docx");
```

## 第 3 步：导入时保留来源编号

要保留源文档中编号段落的编号格式，请创建一个实例`ImportFormatOptions`并设置`KeepSourceNumbering`到`true`.用一个`NodeImporter`将节点从源文档导入到目标文档，指定`ImportFormatMode.KeepSourceFormatting`和`importFormatOptions`.

```csharp
ImportFormatOptions importFormatOptions = new ImportFormatOptions { KeepSourceNumbering = true };
NodeImporter importer = new NodeImporter(srcDoc, dstDoc, ImportFormatMode.KeepSourceFormatting, importFormatOptions);
```

## 第 4 步：导入和附加段落

遍历源文档中的段落并使用`importer`.将导入的节点附加到目标文档的主体。

```csharp
ParagraphCollection srcParas = srcDoc.FirstSection.Body.Paragraphs;
foreach (Paragraph srcPara in srcParas)
{
    Node importedNode = importer.ImportNode(srcPara, false);
    dstDoc.FirstSection.Body.AppendChild(importedNode);
}
```

## 第五步：保存修改后的文件

使用`Save`的方法`Document`目的。

```csharp
dstDoc.Save(dataDir + "JoinAndAppendDocuments.KeepSourceNumbering.docx");
```

这样就完成了使用 Aspose.Words for .NET 在保持原始编号格式的同时将源文档附加到目标文档的实现。

### 使用 Aspose.Words for .NET 的 Keep Source Numbering 示例源代码 

```csharp
	//文档目录的路径
	string dataDir = "YOUR DOCUMENT DIRECTORY";

	Document srcDoc = new Document(dataDir + "Document source.docx");
	Document dstDoc = new Document(dataDir + "Northwind traders.docx");
	//导入编号段落时保留源列表格式。
	ImportFormatOptions importFormatOptions = new ImportFormatOptions { KeepSourceNumbering = true };
	NodeImporter importer = new NodeImporter(srcDoc, dstDoc, ImportFormatMode.KeepSourceFormatting,
		importFormatOptions);
	ParagraphCollection srcParas = srcDoc.FirstSection.Body.Paragraphs;
	foreach (Paragraph srcPara in srcParas)
	{
		Node importedNode = importer.ImportNode(srcPara, false);
		dstDoc.FirstSection.Body.AppendChild(importedNode);
	}
	dstDoc.Save(dataDir + "JoinAndAppendDocuments.KeepSourceNumbering.docx");
```