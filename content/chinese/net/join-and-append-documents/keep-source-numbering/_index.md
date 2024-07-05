---
title: 保留源编号
linktitle: 保留源编号
second_title: Aspose.Words 文档处理 API
description: 了解如何在 Aspose.Words for .NET 中附加文档同时保留源编号格式。
type: docs
weight: 10
url: /zh/net/join-and-append-documents/keep-source-numbering/
---

本教程介绍如何使用 Aspose.Words for .NET 将源文档附加到目标文档，同时保留编号段落的原始编号格式。

## 步骤 1：设置项目

确保您满足以下先决条件：

- 已安装 Aspose.Words for .NET 库。您可以从以下位置下载[Aspose.Releases]https://releases.aspose.com/words/net/ 或使用 NuGet 包管理器来安装。
- 保存源文档和目标文档的文档目录路径。

## 步骤 2：创建目标文档和源文档

创建实例`Document`用于目标文档和源文档。

```csharp
//文档目录的路径
string dataDir = "YOUR DOCUMENT DIRECTORY";

Document srcDoc = new Document(dataDir + "Document source.docx");
Document dstDoc = new Document(dataDir + "Northwind traders.docx");
```

## 步骤 3：导入时保留源编号

要保留源文档中编号段落的编号格式，请创建一个实例`ImportFormatOptions`并设置`KeepSourceNumbering`到`true`。 用一个`NodeImporter`要将源文档中的节点导入目标文档，请指定`ImportFormatMode.KeepSourceFormatting`和`importFormatOptions`.

```csharp
ImportFormatOptions importFormatOptions = new ImportFormatOptions { KeepSourceNumbering = true };
NodeImporter importer = new NodeImporter(srcDoc, dstDoc, ImportFormatMode.KeepSourceFormatting, importFormatOptions);
```

## 步骤 4：导入并附加段落

遍历源文档中的段落，并使用`importer`将导入的节点附加到目标文档的主体中。

```csharp
ParagraphCollection srcParas = srcDoc.FirstSection.Body.Paragraphs;
foreach (Paragraph srcPara in srcParas)
{
    Node importedNode = importer.ImportNode(srcPara, false);
    dstDoc.FirstSection.Body.AppendChild(importedNode);
}
```

## 步骤5：保存修改后的文档

使用保存修改后的文档`Save`方法`Document`目的。

```csharp
dstDoc.Save(dataDir + "JoinAndAppendDocuments.KeepSourceNumbering.docx");
```

这完成了使用 Aspose.Words for .NET 将源文档附加到目标文档同时保留原始编号格式的实现。

### 使用 Aspose.Words for .NET 保留源编号的示例源代码 

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