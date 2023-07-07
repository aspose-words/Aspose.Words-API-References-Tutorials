---
title: 获取桌子位置
linktitle: 获取桌子位置
second_title: Aspose.Words for .NET API 参考
description: 了解如何使用 Aspose.Words for .NET 获取 Word 文档中表格的位置。
type: docs
weight: 10
url: /zh/net/programming-with-tables/get-table-position/
---

在本教程中，我们将学习如何使用 Aspose.Words for .NET 获取 Word 文档中表格的位置。我们将按照分步指南来理解代码并实现此功能。在本教程结束时，您将能够以编程方式获取 Word 文档中的表格定位属性。

## 第 1 步：项目设置
1. 启动 Visual Studio 并创建一个新的 C# 项目。
2. 添加对 Aspose.Words for .NET 库的引用。

## 第 2 步：加载文档并访问表
要开始使用该表，我们需要加载包含该表的文档并访问它。按着这些次序：

```csharp
//文档目录的路径
string dataDir = "YOUR DOCUMENTS DIRECTORY";

//加载文档
Document doc = new Document(dataDir + "Tables.docx");

//访问数组
Table table = (Table)doc.GetChild(NodeType.Table, 0, true);
```

请务必将“您的文档目录”替换为文档目录的实际路径。另外，请确保文档包含您想要获取其位置的表格。

## 第 3 步：获取数组定位属性
接下来，我们将检查数组的定位类型并获取适当的定位属性。使用以下代码：

```csharp
if (table.TextWrapping == TextWrapping.Around)
{
Console.WriteLine(table.RelativeHorizontalAlignment);
Console.WriteLine(table.RelativeVerticalAlignment);
}
else
{
Console.WriteLine(table.Alignment);
}
```

这里我们使用一个条件来检查数组是否是 float 类型。如果是这样，我们打印`RelativeHorizontalAlignment`和`RelativeVerticalAlignment`属性来获取表格的相对水平和垂直对齐方式。否则，我们打印`Alignment`属性来获取数组对齐方式。

### 使用 Aspose.Words for .NET 获取表格位置的示例源代码 

```csharp
	//文档目录的路径
	string dataDir = "YOUR DOCUMENT DIRECTORY";

	Document doc = new Document(dataDir + "Tables.docx");
	Table table = (Table) doc.GetChild(NodeType.Table, 0, true);
	if (table.TextWrapping == TextWrapping.Around)
	{
		Console.WriteLine(table.RelativeHorizontalAlignment);
		Console.WriteLine(table.RelativeVerticalAlignment);
	}
	else
	{
		Console.WriteLine(table.Alignment);
	}
```

## 结论
在本教程中，我们学习了如何使用 Aspose.Words for .NET 获取 Word 文档中表格的位置。通过遵循本分步指南并实现提供的 C# 代码，您可以通过编程方式获取 Word 文档中的表格定位属性。此功能允许您根据数组的特定位置来分析和操作数组。