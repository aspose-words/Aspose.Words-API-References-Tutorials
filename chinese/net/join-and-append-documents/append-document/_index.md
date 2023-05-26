---
title: 追加文件
linktitle: 追加文件
second_title: Aspose.Words for .NET API 参考
description: 了解如何使用 Aspose.Words for .NET 将一个文档的内容附加到另一个文档。
type: docs
weight: 10
url: /zh/net/join-and-append-documents/append-document/
---

本教程解释了如何使用 Aspose.Words for .NET 将一个文档的内容附加到另一个文档。提供的源代码演示了如何打开源文档和目标文档，将源文档中的部分导入和附加到目标文档。

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

## 第 3 步：将源文档中的部分附加到目标文档

循环遍历源文档中的所有部分，并使用`ImportNode`方法。然后，将导入的部分附加到目标文档。

```csharp
foreach (Section srcSection in srcDoc)
{
    Node dstSection = dstDoc.ImportNode(srcSection, true, ImportFormatMode.KeepSourceFormatting);
    dstDoc.AppendChild(dstSection);
}
```

## 第 4 步：保存目标文档

最后，使用保存修改后的目标文档`Save`的方法`Document`目的。

```csharp
dstDoc.Save(dataDir + "JoinAndAppendDocuments.AppendDocument.docx");
```

这样就完成了使用Aspose.Words for .NET 追加文档的实现。

### 使用 Aspose.Words for .NET 的 Append Document 示例源代码 

```csharp
	//文档目录的路径
	string dataDir = "YOUR DOCUMENT DIRECTORY";

	Document srcDoc = new Document(dataDir + "Document source.docx");
	Document dstDoc = new Document(dataDir + "Northwind traders.docx");
	//循环遍历源文档中的所有部分。
	// Section 节点是 Document 节点的直接子节点，因此我们可以枚举 Document。
	foreach (Section srcSection in srcDoc)
	{
		//因为我们正在将一个部分从一个文档复制到另一个文档，
		//需要将 Section 节点导入到目标文档中。
		//这会调整对样式、列表等的任何特定于文档的引用。
		//
		//导入节点会创建原始节点的副本，但副本
		//ss 准备好插入到目标文档中。
		Node dstSection = dstDoc.ImportNode(srcSection, true, ImportFormatMode.KeepSourceFormatting);
		//现在可以将新的节节点附加到目标文档。
		dstDoc.AppendChild(dstSection);
	}
	dstDoc.Save(dataDir + "JoinAndAppendDocuments.AppendDocument.docx");
```