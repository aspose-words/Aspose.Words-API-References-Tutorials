---
title: 获取表格周围文本之间的距离
linktitle: 获取表格周围文本之间的距离
second_title: Aspose.Words for .NET API 参考
description: 使用 Aspose.Words for .NET 获取 Word 文档中文本和表格之间的距离的分步指南。
type: docs
weight: 10
url: /zh/net/programming-with-table-styles-and-formatting/get-distance-between-table-surrounding-text/
---

在本教程中，我们将引导您逐步使用 Aspose.Words for .NET 获取表格中周围文本之间的距离。我们将解释捆绑的 C# 源代码，并为您提供全面的指南，帮助您理解并在自己的项目中实现此功能。在本教程结束时，您将了解如何使用 Aspose.Words for .NET 访问 Word 文档中表格与周围文本之间的各种距离。

## 第1步：定义文档目录
首先，您需要设置文档目录的路径。这是您的 Word 文档所在的位置。将“您的文档目录”替换为适当的路径。

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
```

## 第 2 步：加载现有文档
接下来，您需要将现有的 Word 文档加载到该实例中`Document`班级。

```csharp
Document doc = new Document(dataDir + "Tables.docx");
```

## 第三步：获取表格与周围文本之间的距离
要获取表格与周围文本之间的距离，我们需要使用以下命令访问文档中的表格`GetChild()`方法和`NodeType.Table`财产。然后我们可以使用数组属性显示不同的距离`DistanceTop`, `DistanceBottom`, `DistanceRight`和`DistanceLeft`.

```csharp
Table table = (Table)doc.GetChild(NodeType.Table, 0, true);
Console.WriteLine("Distance between table and top text: " + table.DistanceTop);
Console.WriteLine("Distance between table and bottom text: " + table.DistanceBottom);
Console.WriteLine("Distance between the table and the text on the right: " + table.DistanceRight);
Console.WriteLine("Distance between the table and the text on the left: " + table.DistanceLeft);
```

### 使用 Aspose.Words for .NET 获取表格周围文本之间的距离的示例源代码 

```csharp
	//文档目录的路径
	string dataDir = "YOUR DOCUMENT DIRECTORY";

	Document doc = new Document(dataDir + "Tables.docx");
	Console.WriteLine("\nGet distance between table left, right, bottom, top and the surrounding text.");
	Table table = (Table) doc.GetChild(NodeType.Table, 0, true);
	Console.WriteLine(table.DistanceTop);
	Console.WriteLine(table.DistanceBottom);
	Console.WriteLine(table.DistanceRight);
	Console.WriteLine(table.DistanceLeft);
```

## 结论
在本教程中，我们学习了如何使用 Aspose.Words for .NET 获取表格中周围文本之间的距离。通过遵循此分步指南，您可以轻松了解 Word 文档中表格与周围文本之间的各种距离。 Aspose.Words 提供了强大而灵活的 API，用于操作文档中的表格并设置其格式。有了这些知识，您就可以分析与文本相关的表格布局并满足特定需求。