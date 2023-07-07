---
title: 设置表格行格式
linktitle: 设置表格行格式
second_title: Aspose.Words for .NET API 参考
description: 使用 Aspose.Words for .NET 设置表格行格式的分步指南。
type: docs
weight: 10
url: /zh/net/programming-with-table-styles-and-formatting/set-table-row-formatting/
---

在本教程中，我们将引导您完成使用 Aspose.Words for .NET 设置表格行格式的分步过程。我们将解释捆绑的 C# 源代码，并为您提供全面的指南，帮助您理解并在自己的项目中实现此功能。在本教程结束时，您将了解如何使用 Aspose.Words for .NET 调整 Word 文档中表格行的高度和填充。

## 第1步：定义文档目录
首先，您需要设置文档目录的路径。这是您要保存编辑的 Word 文档的位置。将“您的文档目录”替换为适当的路径。

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
```

## 步骤 2：创建新文档和文档生成器
接下来，您需要创建一个新的实例`Document`类和该文档的文档构造函数。

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
```

## 第 3 步：创建一个新表格并添加一个单元格
要开始创建表，我们使用`StartTable()`文档构造函数的方法，然后我们使用`InsertCell()`方法。

```csharp
Table table = builder. StartTable();
builder. InsertCell();
```

## 步骤 4：定义行格式
现在我们可以通过访问来设置行格式`RowFormat`的对象`DocumentBuilder`目的。我们可以使用相应的属性设置行高和边距（paddings）。

```csharp
RowFormat rowFormat = builder.RowFormat;
rowFormat. Height = 100;
rowFormat.HeightRule = HeightRule.Exactly;
```

## 第 5 步：设置表格边距
接下来，我们可以通过访问相应的属性来设置表格填充`Table`目的。这些边距将应用于表格的所有行。

```csharp
table. LeftPadding = 30;
table. RightPadding = 30;
table. TopPadding = 30;
table. BottomPadding = 30;
```

## 第 6 步：向行添加内容
最后，我们可以使用文档生成器将内容添加到该行`Writeln()`方法。

```csharp
builder.Writeln("I'm a beautifully formatted line.");
```

## 步骤 7：完成表格并保存文档
在

最后，我们使用以下命令完成表的创建`EndRow()`和`EndTable()`方法，然后我们将修改后的文档保存到文件中。

```csharp
builder. EndRow();
builder. EndTable();
doc.Save(dataDir + "WorkingWithTableStylesAndFormatting.DocumentBuilderSetTableRowFormatting.docx");
```

### 使用 Aspose.Words for .NET 设置表格行格式的示例源代码 

```csharp
	//文档目录的路径
	string dataDir = "YOUR DOCUMENT DIRECTORY";

	Document doc = new Document();
	DocumentBuilder builder = new DocumentBuilder(doc);
	Table table = builder.StartTable();
	builder.InsertCell();
	RowFormat rowFormat = builder.RowFormat;
	rowFormat.Height = 100;
	rowFormat.HeightRule = HeightRule.Exactly;
	//这些格式属性在表上设置并应用于表中的所有行。
	table.LeftPadding = 30;
	table.RightPadding = 30;
	table.TopPadding = 30;
	table.BottomPadding = 30;
	builder.Writeln("I'm a wonderful formatted row.");
	builder.EndRow();
	builder.EndTable();
	doc.Save(dataDir + "WorkingWithTableStylesAndFormatting.DocumentBuilderSetTableRowFormatting.docx");
```

## 结论
在本教程中，我们学习了如何使用 Aspose.Words for .NET 设置表格行格式。通过遵循此分步指南，您可以轻松调整 Word 文档中的表格行高和边距。 Aspose.Words 提供了强大而灵活的 API，用于操作文档中的表格并设置其格式。有了这些知识，您就可以根据您的特定需求自定义表格的视觉布局。