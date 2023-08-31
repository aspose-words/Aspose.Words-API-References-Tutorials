---
title: 附加文档
linktitle: 附加文档
second_title: Aspose.Words 文档处理 API
description: 了解如何使用 Aspose.Words for .NET 将一个文档的内容附加到另一个文档。
type: docs
weight: 10
url: /zh/net/join-and-append-documents/append-document/
---

本教程介绍如何使用 Aspose.Words for .NET 将一个文档的内容附加到另一个文档。提供的源代码演示了如何打开源文档和目标文档，将源文档中的部分导入并附加到目标文档。

## 第 1 步：设置项目

确保您具备以下先决条件：

- 已安装 Aspose.Words for .NET 库。您可以从以下位置下载：[Aspose.Releases]https://releases.aspose.com/words/net/ 或使用 NuGet 包管理器来安装它。
- 源文档和目标文档所在的文档目录路径。

## 步骤 2：打开源文档和目标文档

使用以下命令打开源文档和目标文档`Document`类构造函数。代替`"YOUR DOCUMENT DIRECTORY"`与文档目录的实际路径。

```csharp
//文档目录的路径
string dataDir = "YOUR DOCUMENT DIRECTORY";

Document srcDoc = new Document(dataDir + "Document source.docx");
Document dstDoc = new Document(dataDir + "Northwind traders.docx");
```

## 步骤 3：将源文档中的部分附加到目标文档

循环遍历源文档中的所有部分，并使用以下命令将每个部分导入到目标文档中`ImportNode`方法。然后，将导入的部分附加到目标文档。

```csharp
foreach (Section srcSection in srcDoc)
{
    Node dstSection = dstDoc.ImportNode(srcSection, true, ImportFormatMode.KeepSourceFormatting);
    dstDoc.AppendChild(dstSection);
}
```

## 步骤 4：保存目标文档

最后，使用以下命令保存修改后的目标文档`Save`的方法`Document`目的。

```csharp
dstDoc.Save(dataDir + "JoinAndAppendDocuments.AppendDocument.docx");
```

这样就完成了使用 Aspose.Words for .NET 附加文档的实现。

### 使用 Aspose.Words for .NET 追加文档的示例源代码 

```csharp
	//文档目录的路径
	string dataDir = "YOUR DOCUMENT DIRECTORY";

	Document srcDoc = new Document(dataDir + "Document source.docx");
	Document dstDoc = new Document(dataDir + "Northwind traders.docx");
	//循环浏览源文档中的所有部分。
	//节节点是文档节点的直接子节点，因此我们可以枚举文档。
	foreach (Section srcSection in srcDoc)
	{
		//因为我们要将一个文档的一部分复制到另一个文档，
		//需要将Section节点导入到目标文档中。
		//这会调整任何特定于文档的样式、列表等引用。
		//
		//导入节点会创建原始节点的副本，但该副本
		//ss 准备插入到目标文档中。
		Node dstSection = dstDoc.ImportNode(srcSection, true, ImportFormatMode.KeepSourceFormatting);
		//现在可以将新的节节点附加到目标文档。
		dstDoc.AppendChild(dstSection);
	}
	dstDoc.Save(dataDir + "JoinAndAppendDocuments.AppendDocument.docx");
```