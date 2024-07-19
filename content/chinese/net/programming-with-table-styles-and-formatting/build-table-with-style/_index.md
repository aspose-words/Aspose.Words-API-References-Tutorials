---
title: 建立具有风格的表格
linktitle: 建立具有风格的表格
second_title: Aspose.Words 文档处理 API
description: 使用 Aspose.Words for .NET 构建具有自定义样式的表格的分步指南。
type: docs
weight: 10
url: /zh/net/programming-with-table-styles-and-formatting/build-table-with-style/
---

在本教程中，我们将引导您逐步使用 Aspose.Words for .NET 构建样式表。我们将解释捆绑的 C# 源代码并为您提供全面的指南，以帮助您理解并在自己的项目中实现此功能。在本教程结束时，您将了解如何使用 Aspose.Words for .NET 在 Word 文档中创建具有自定义样式的表格。

## 步骤1：定义文档目录
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

## 步骤 3：开始新表格并插入单元格
要开始构建表格，我们使用`StartTable()`方法，然后我们使用`InsertCell()`方法。

```csharp
Table table = builder. StartTable();
builder.InsertCell();
```

## 步骤 4：定义表格的样式
现在我们可以使用`StyleIdentifier`属性。在此示例中，我们使用“MediumShading1Accent1”样式。

```csharp
table.StyleIdentifier = StyleIdentifier.MediumShading1Accent1;
```

## 步骤 5：将样式选项应用到表格
我们可以使用以下方式指定哪些特征应按样式进行格式化`StyleOptions`数组的属性。在此示例中，我们应用以下选项：“FirstColumn”、“RowBands”和“FirstRow”。

```csharp
table.StyleOptions = TableStyleOptions.FirstColumn | TableStyleOptions.RowBands | TableStyleOptions.FirstRow;
```

## 步骤 6：自动调整表格大小
为了根据数组内容自动调整数组的大小，我们使用`AutoFit()`方法`AutoFitBehavior.AutoFitToContents`行为。

```csharp
table.AutoFit(AutoFitBehavior.AutoFitToContents);
```

## 步骤 7：向单元格添加内容
现在我们可以使用`Writeln()`和`InsertCell()`方法。在此示例中，我们添加了“项目”和“数量（

kg)”及其相应数据。

```csharp
builder.Writeln("Item");
builder.CellFormat.RightPadding = 40;
builder.InsertCell();
builder.Writen("Quantity (kg)");
builder.EndRow();
builder.InsertCell();
builder.Writeln("Apples");
builder.InsertCell();
builder.Writeln("20");
builder.EndRow();
builder.InsertCell();
builder.Writeln("Bananas");
builder.InsertCell();
builder.Writen("40");
builder.EndRow();
builder.InsertCell();
builder.Writeln("Carrots");
builder.InsertCell();
builder.Writeln("50");
builder.EndRow();
```

## 步骤8：保存修改后的文档
最后，我们将修改后的文档保存到文件中。您可以为输出文档选择合适的名称和位置。

```csharp
doc.Save(dataDir + "WorkingWithTableStylesAndFormatting.BuildTableWithStyle.docx");
```

恭喜！您现在已经使用 Aspose.Words for .NET 构建了自定义样式表。

### 使用 Aspose.Words for .NET 构建带样式表格的示例源代码 

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
//应用应按样式格式化的特征。
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
在本教程中，我们学习了如何使用 Aspose.Words for .NET 构建样式表。通过遵循本分步指南，您可以轻松自定义 Word 文档中表格的样式。Aspose.Words 提供了强大而灵活的 API，用于操作和格式化文档中的表格。有了这些知识，您可以改善 Word 文档的视觉呈现并满足特定需求。