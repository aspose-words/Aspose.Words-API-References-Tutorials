---
title: 获取浮动表位置
linktitle: 获取浮动表位置
second_title: Aspose.Words for .NET API 参考
description: 了解如何使用 Aspose.Words for .NET 获取 Word 文档中浮动表格的位置。
type: docs
weight: 10
url: /zh/net/programming-with-tables/get-floating-table-position/
---

在本教程中，我们将学习如何使用 Aspose.Words for .NET 获取 Word 文档中浮动表格的位置。我们将按照分步指南来理解代码并实现此功能。在本教程结束时，您将能够以编程方式获取 Word 文档中浮动表格的定位属性。

## 第 1 步：项目设置
1. 启动 Visual Studio 并创建一个新的 C# 项目。
2. 添加对 Aspose.Words for .NET 库的引用。

## 第 2 步：加载文档并访问表格
要开始使用表格，我们需要加载包含它们的文档并访问它们。按着这些次序：

```csharp
//文档目录的路径
string dataDir = "YOUR DOCUMENTS DIRECTORY";

//加载文档
Document doc = new Document(dataDir + "Table wrapped by text.docx");
```

请务必将“您的文档目录”替换为文档目录的实际路径。另外，请确保文档包含浮动表格。

## 第3步：获取浮动表定位属性
接下来，我们将循环遍历文档中的所有表格并获取浮动表格定位属性。使用以下代码：

```csharp
foreach(Table table in doc.FirstSection.Body.Tables)
{
//如果数组是浮点类型，则打印其定位属性。
if (table.TextWrapping == TextWrapping.Around)
{
Console.WriteLine(table.HorizontalAnchor);
Console.WriteLine(table.VerticalAnchor);
Console.WriteLine(table.AbsoluteHorizontalDistance);
Console.WriteLine(table.AbsoluteVerticalDistance);
Console.WriteLine(table.AllowOverlap);
Console.WriteLine(table.AbsoluteHorizontalDistance);
Console.WriteLine(table.RelativeVerticalAlignment);
Console.WriteLine("...............................");
}
}
```

这里我们使用的是`foreach`循环遍历文档中的所有数组。我们通过检查数组是否为 float 类型来检查`TextWrapping`财产。如果是这样，我们打印表格的定位属性，例如水平锚点、垂直锚点、绝对水平和垂直距离、重叠权限、绝对水平距离和相对垂直对齐。
 
### 使用 Aspose.Words for .NET 获取浮动表格位置的示例源代码 

```csharp
	//文档目录的路径
	string dataDir = "YOUR DOCUMENT DIRECTORY";

	Document doc = new Document(dataDir + "Table wrapped by text.docx");
	foreach (Table table in doc.FirstSection.Body.Tables)
	{
		//如果表格是浮动类型，则打印其定位属性。
		if (table.TextWrapping == TextWrapping.Around)
		{
			Console.WriteLine(table.HorizontalAnchor);
			Console.WriteLine(table.VerticalAnchor);
			Console.WriteLine(table.AbsoluteHorizontalDistance);
			Console.WriteLine(table.AbsoluteVerticalDistance);
			Console.WriteLine(table.AllowOverlap);
			Console.WriteLine(table.AbsoluteHorizontalDistance);
			Console.WriteLine(table.RelativeVerticalAlignment);
			Console.WriteLine("..............................");
		}
	}
```

## 结论
在本教程中，我们学习了如何使用 Aspose.Words for .NET 获取 Word 文档中浮动表格的位置。通过遵循本分步指南并实现提供的 C# 代码，您可以通过编程方式获取 Word 文档中浮动表格的定位属性。此功能允许您根据您的特定需求分析和操作浮动表。