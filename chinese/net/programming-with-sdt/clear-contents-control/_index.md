---
title: 清除内容控制
linktitle: 清除内容控制
second_title: Aspose.Words for .NET API 参考
description: 了解如何使用 Aspose.Words for .NET 清除 Word 文档中控件的内容。
type: docs
weight: 10
url: /zh/net/programming-with-sdt/clear-contents-control/
---

本教程演示如何使用 Aspose.Words for .NET 清除 Word 文档中 SDT 的内容。清除 SDT 的内容会删除内容控件中的任何文本或子节点。

## 先决条件
要学习本教程，您需要具备以下条件：

- 安装了 Aspose.Words for .NET 库。
- C# 的基本知识和使用 Word 文档。

## 第 1 步：设置文档目录
首先设置文档目录的路径。代替`"YOUR DOCUMENT DIRECTORY"`使用文档所在目录的实际路径。

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## 第 2 步：加载文档并获取 StructuredDocumentTag
使用`Document`构造函数，将文档的路径作为参数传递。然后，检索所需的`StructuredDocumentTag`从文档中。在此示例中，我们假设 SDT 是文档中的第一个子节点。

```csharp
Document doc = new Document(dataDir + "Structured document tags.docx");
StructuredDocumentTag sdt = (StructuredDocumentTag)doc.GetChild(NodeType.StructuredDocumentTag, 0, true);
```

## 第 3 步：清除 StructuredDocumentTag 的内容
使用清除 SDT 的内容`Clear`方法。这将删除内容控件中的任何文本或子节点。

```csharp
sdt.Clear();
```

## 第 4 步：保存文档
使用`Save`方法。提供具有适当文件扩展名的所需文件名。在本例中，我们将文档保存为“WorkingWithSdt.ClearContentsControl.doc”。

```csharp
doc.Save(dataDir + "WorkingWithSdt.ClearContentsControl.doc");
```

### 使用 Aspose.Words for .NET 的清除内容控件示例源代码 

```csharp
	//文档目录的路径
	string dataDir = "YOUR DOCUMENT DIRECTORY";

	Document doc = new Document(dataDir + "Structured document tags.docx");
	StructuredDocumentTag sdt = (StructuredDocumentTag) doc.GetChild(NodeType.StructuredDocumentTag, 0, true);
	sdt.Clear();
	doc.Save(dataDir + "WorkingWithSdt.ClearContentsControl.doc");
```

就是这样！您已经使用 Aspose.Words for .NET 成功清除了 Word 文档中 StructuredDocumentTag 的内容。