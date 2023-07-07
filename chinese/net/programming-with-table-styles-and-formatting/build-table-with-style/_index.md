---
title: 构建具有风格的表格
linktitle: 构建具有风格的表格
second_title: Aspose.Words for .NET API 参考
description: 使用 Aspose.Words for .NET 构建具有自定义样式的表格的分步指南。
type: docs
weight: 10
url: /zh/net/programming-with-table-styles-and-formatting/build-table-with-style/
---

在本教程中，我们将引导您逐步完成使用 Aspose.Words for .NET 构建样式表的过程。我们将解释捆绑的 C# 源代码，并为您提供全面的指南，帮助您理解并在自己的项目中实现此功能。在本教程结束时，您将了解如何使用 Aspose.Words for .NET 在 Word 文档中创建具有自定义样式的表格。

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

## 步骤 3：开始一个新表格并插入一个单元格
要开始构建表，我们使用`StartTable()`文档生成器的方法，然后我们使用`InsertCell()`方法。

```csharp
Table table = builder. StartTable();
builder. InsertCell();
```

## 第四步：定义表格的样式
现在我们可以使用以下命令设置表格样式`StyleIdentifier`财产。在此示例中，我们使用“MediumShading1Accent1”样式。

```csharp
table.StyleIdentifier = StyleIdentifier.MediumShading1Accent1;
```

## 步骤 5：将样式选项应用到表格
我们可以使用以下命令指定样式应格式化哪些特征`StyleOptions`数组的属性。在此示例中，我们应用以下选项：“FirstColumn”、“RowBands”和“FirstRow”。

```csharp
table.StyleOptions = TableStyleOptions.FirstColumn | TableStyleOptions.RowBands | TableStyleOptions.FirstRow;
```

## 第6步：自动调整表格大小
为了根据数组的内容自动调整数组的大小，我们使用`AutoFit()`方法与`AutoFitBehavior.AutoFitToContents`行为。

```csharp
table. AutoFit(AutoFitBehavior.AutoFitToContents);
```

## 步骤 7：向单元格添加内容
现在我们可以使用以下命令向单元格添加内容`Writeln()`和`InsertCell()`文档生成器的方法。在此示例中，我们添加“Item”和“Quantity”的标题（

kg）”和相应的数据。

```csharp
builder.Writeln("Item");
builder.CellFormat.RightPadding = 40;
builder. InsertCell();
builder. Writen("Quantity (kg)");
builder. EndRow();
builder. InsertCell();
builder.Writeln("Apples");
builder. InsertCell();
builder.Writeln("20");
builder. EndRow();
builder. InsertCell();
builder.Writeln("Bananas");
builder. InsertCell();
builder. Writen("40");
builder. EndRow();
builder. InsertCell();
builder.Writeln("Carrots");
builder. InsertCell();
builder.Writeln("50");
builder. EndRow();
```

## 步骤8：保存修改后的文档
最后，我们将修改后的文档保存到文件中。您可以为输出文档选择适当的名称和位置。

```csharp
doc.Save(dataDir + "WorkingWithTableStylesAndFormatting.BuildTableWithStyle.docx");
```

恭喜！您现在已经使用 Aspose.Words for .NET 构建了一个自定义样式的表格。

### 使用 Aspose.Words for .NET 构建带有样式的表格的示例源代码 

```csharp
	//文档目录的路径
	string dataDir = "YOUR DOCUMENT DIRECTORY";

	Document doc = new Document();
	DocumentBuilder builder = new DocumentBuilder(doc);
	Table table = builder.StartTable();
	//在设置任何表格格式之前，我们必须先插入至少一行。
	builder.InsertCell();
	//根据唯一样式标识符设置使用的表格样式。
	table.StyleIdentifier = StyleIdentifier.MediumShading1Accent1;
	//应用应按样式格式化哪些功能。
	table.StyleOptions =
		TableStyleOptions.FirstColumn | TableStyleOptions.RowBands | TableStyleOptions.FirstRow;
	table.AutoFit(AutoFitBehavior.AutoFitToContents);
	builder.Writeln("Item");
	builder.CellFormat.RightPadding = 40;
	builder.InsertCell();
	builder.Writeln("Quantity (kg)");
	builder.EndRow();
	builder.InsertCell();
	builder.Writeln("Apples");
	builder.InsertCell();
	builder.Writeln("20");
	builder.EndRow();
	builder.InsertCell();
	builder.Writeln("Bananas");
	builder.InsertCell();
	builder.Writeln("40");
	builder.EndRow();
	builder.InsertCell();
	builder.Writeln("Carrots");
	builder.InsertCell();
	builder.Writeln("50");
	builder.EndRow();
	doc.Save(dataDir + "WorkingWithTableStylesAndFormatting.BuildTableWithStyle.docx");
```

## 结论
在本教程中，我们学习了如何使用 Aspose.Words for .NET 构建样式表。通过遵循此分步指南，您可以轻松自定义 Word 文档中的表格样式。 Aspose.Words 提供了强大而灵活的 API，用于操作文档中的表格并设置其格式。有了这些知识，您就可以改进 Word 文档的视觉呈现并满足特定需求。