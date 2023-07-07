---
title: 多节
linktitle: 多节
second_title: Aspose.Words for .NET API 参考
description: 了解如何使用 Aspose.Words for .NET 检索和处理 Word 文档中的多部分结构化文档标签。
type: docs
weight: 10
url: /zh/net/programming-with-sdt/multi-section/
---

本教程介绍如何使用 Aspose.Words for .NET 在 Word 文档中处理多部分结构化文档标签。您可以检索和处理文档中存在的部分标签。

## 先决条件
要学习本教程，您需要具备以下条件：

- 已安装 Aspose.Words for .NET 库。
- C# 和使用 Word 文档的基本知识。

## 第 1 步：设置文档目录
首先设置文档目录的路径。代替`"YOUR DOCUMENT DIRECTORY"`与文档所在目录的实际路径。

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## 第 2 步：加载文档并检索多节标签
使用以下命令加载 Word 文档`Document`构造函数，将文档的路径作为参数传递。使用以下命令检索文档中所有结构化文档标签范围起始节点`GetChildNodes`方法。

```csharp
Document doc = new Document(dataDir + "Multi-section structured document tags.docx");
NodeCollection tags = doc.GetChildNodes(NodeType.StructuredDocumentTagRangeStart, true);
```

## 步骤 3：处理多节标签
迭代结构化文档标记范围起始节点的集合。在此示例中，我们只需将每个标签的标题打印到控制台。您可以根据您的要求进行进一步的处理。

```csharp
foreach (StructuredDocumentTagRangeStart tag in tags)
    Console.WriteLine(tag.Title);
```

### 使用 Aspose.Words for .NET 的多部分示例源代码 

```csharp
	//文档目录的路径
	string dataDir = "YOUR DOCUMENT DIRECTORY";

	Document doc = new Document(dataDir + "Multi-section structured document tags.docx");
	NodeCollection tags = doc.GetChildNodes(NodeType.StructuredDocumentTagRangeStart, true);
	foreach (StructuredDocumentTagRangeStart tag in tags)
		Console.WriteLine(tag.Title);
```

就是这样！您已使用 Aspose.Words for .NET 成功检索并处理了 Word 文档中的多节结构化文档标签。