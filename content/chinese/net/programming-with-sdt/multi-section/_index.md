---
title: 多节
linktitle: 多节
second_title: Aspose.Words 文档处理 API
description: 了解如何使用 Aspose.Words for .NET 检索和处理 Word 文档中的多部分结构化文档标签。
type: docs
weight: 10
url: /zh/net/programming-with-sdt/multi-section/
---

本教程介绍如何使用 Aspose.Words for .NET 处理 Word 文档中的多节结构化文档标签。您可以检索和处理文档中存在的节标签。

## 先决条件
要遵循本教程，您需要满足以下条件：

- 已安装 Aspose.Words for .NET 库。
- 具备 C# 和 Word 文档文字处理的基本知识。

## 步骤 1：设置文档目录
首先设置文档目录的路径。替换`"YOUR DOCUMENT DIRECTORY"`使用您的文档所在目录的实际路径。

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## 步骤 2：加载文档并检索多部分标签
使用加载 Word 文档`Document`构造函数，将路径作为参数传递给文档。使用`GetChildNodes`方法。

```csharp
Document doc = new Document(dataDir + "Multi-section structured document tags.docx");
NodeCollection tags = doc.GetChildNodes(NodeType.StructuredDocumentTagRangeStart, true);
```

## 步骤 3：处理多部分标签
遍历结构化文档标签范围起始节点集合。本例中我们只是将每个标签的标题打印到控制台。您可以根据需要进行进一步处理。

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

就是这样！您已成功使用 Aspose.Words for .NET 检索和处理 Word 文档中的多节结构化文档标签。