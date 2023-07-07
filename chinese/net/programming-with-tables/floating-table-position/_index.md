---
title: 浮动工作台位置
linktitle: 浮动工作台位置
second_title: Aspose.Words for .NET API 参考
description: 了解如何使用 Aspose.Words for .NET 将表格放置在 Word 文档中的浮动位置。
type: docs
weight: 10
url: /zh/net/programming-with-tables/floating-table-position/
---

在本教程中，我们将学习如何使用 Aspose.Words for .NET 将表格放置在 Word 文档中的浮动位置。我们将按照分步指南来理解代码并实现此功能。在本教程结束时，您将能够以编程方式控制 Word 文档中浮动表格的位置和对齐方式。

## 第 1 步：项目设置
1. 启动 Visual Studio 并创建一个新的 C# 项目。
2. 添加对 Aspose.Words for .NET 库的引用。

## 第 2 步：加载文档并访问表
要开始使用该表，我们需要加载包含该表的文档并访问它。按着这些次序：

```csharp
//文档目录的路径
string dataDir = "YOUR DOCUMENTS DIRECTORY";

//加载文档
Document doc = new Document(dataDir + "Table wrapped by text.docx");

//访问数组
Table table = doc.FirstSection.Body.Tables[0];
```

请务必将“您的文档目录”替换为文档目录的实际路径。另外，请确保文档包含将位于浮动位置的表格。

## 第三步：定位浮板
接下来，我们将使用 Aspose.Words for .NET 提供的属性将表格定位在浮动位置。使用以下代码：

```csharp
//定位浮动台
table. AbsoluteHorizontalDistance = 10;
table. RelativeVerticalAlignment = VerticalAlignment. Center;
```

这里我们使用`AbsoluteHorizontalDistance`属性设置表格距页面左边缘的绝对水平距离。我们还使用`RelativeVerticalAlignment`属性来设置表格与周围内容的相对垂直对齐方式。

## 第四步：保存修改后的文档
最后，我们需要保存修改后的文档，并将表格放置在浮动位置。使用以下代码：

```csharp
//保存修改后的文档
doc.Save(dataDir + "WorkingWithTables.FloatingTablePosition.docx");
```

请务必为输出文档指定正确的路径和文件名。

### 使用 Aspose.Words for .NET 浮动表格位置的示例源代码 

```csharp
	//文档目录的路径
	string dataDir = "YOUR DOCUMENT DIRECTORY";

	Document doc = new Document(dataDir + "Table wrapped by text.docx");
	Table table = doc.FirstSection.Body.Tables[0];
	table.AbsoluteHorizontalDistance = 10;
	table.RelativeVerticalAlignment = VerticalAlignment.Center;
	doc.Save(dataDir + "WorkingWithTables.FloatingTablePosition.docx");
```

## 结论
在本教程中，我们学习了如何使用 Aspose.Words for .NET 将表格放置在 Word 文档中的浮动位置。通过遵循本分步指南并实现提供的 C# 代码，您可以通过编程方式控制 Word 文档中浮动表格的位置和对齐方式。