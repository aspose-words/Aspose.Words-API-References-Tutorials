---
title: 设置表格单元格格式
linktitle: 设置表格单元格格式
second_title: Aspose.Words for .NET API 参考
description: 使用 Aspose.Words for .NET 设置表格单元格格式的分步指南。
type: docs
weight: 10
url: /zh/net/programming-with-table-styles-and-formatting/set-table-cell-formatting/
---

在本教程中，我们将逐步引导您使用 Aspose.Words for .NET 定义表格单元格的格式。我们将解释捆绑的 C# 源代码，并为您提供全面的指南，以帮助您了解并在您自己的项目中实现此功能。在本教程结束时，您将了解如何使用 Aspose.Words for .NET 调整 Word 文档表格中单元格的宽度和边距（填充）。

## 第一步：定义文档目录
首先，您需要设置文档目录的路径。这是您要保存编辑后的 Word 文档的位置。用适当的路径替换“您的文档目录”。

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
```

## 第 2 步：创建新文档和文档生成器
接下来，您需要创建一个新的实例`Document`类和该文档的文档构造函数。

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
```

## 第 3 步：开始一个新表并添加一个单元格
要开始创建表，我们使用`StartTable()`文档构造函数的方法，然后我们使用`InsertCell()`方法。

```csharp
builder. StartTable();
builder. InsertCell();
```

## 第 4 步：设置单元格格式
现在我们可以通过访问来设置单元格格式`CellFormat`的对象`DocumentBuilder`目的。我们可以使用相应的属性设置单元格宽度和边距（填充）。

```csharp
CellFormat cellFormat = builder. CellFormat;
cellFormat. Width = 250;
cellFormat. LeftPadding = 30;
cellFormat. RightPadding = 30;
cellFormat. TopPadding = 30;
cellFormat.BottomPadding = 30;
```

## 第 5 步：向单元格添加内容
然后我们可以使用文档生成器的将内容添加到单元格`Writeln()`方法。

```csharp
builder.Writeln("I'm a beautifully formatted cell.");
```

## 第 6 步：完成表格并保存文档
最后，我们使用`EndRow()`方法和`EndTable()`，然后我们将修改后的文档保存到一个文件中。

```csharp
builder. EndRow();
builder. EndTable();
doc.Save(dataDir + "WorkingWithTableStylesAndFormatting.DocumentBuilderSetTableCellFormatting.docx");
```

### 使用 Aspose.Words for .NET 设置表格单元格格式的示例源代码 

```csharp
	//文档目录的路径
	string dataDir = "YOUR DOCUMENT DIRECTORY";

	Document doc = new Document();
	DocumentBuilder builder = new DocumentBuilder(doc);
	builder.StartTable();
	builder.InsertCell();
	CellFormat cellFormat = builder.CellFormat;
	cellFormat.Width = 250;
	cellFormat.LeftPadding = 30;
	cellFormat.RightPadding = 30;
	cellFormat.TopPadding = 30;
	cellFormat.BottomPadding = 30;
	builder.Writeln("I'm a wonderful formatted cell.");
	builder.EndRow();
	builder.EndTable();
	doc.Save(dataDir + "WorkingWithTableStylesAndFormatting.DocumentBuilderSetTableCellFormatting.docx");
```

## 结论
在本教程中，我们学习了如何使用 Aspose.Words for .NET 设置表格单元格的格式。按照此分步指南，您可以轻松调整 Word 文档中表格中单元格的宽度和边距。 Aspose.Words 提供了一个强大而灵活的 API，用于操作和格式化文档中的表格。有了这些知识，您就可以根据自己的特定需求自定义表格的视觉布局。