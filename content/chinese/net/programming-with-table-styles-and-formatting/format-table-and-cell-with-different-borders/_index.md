---
title: 设置具有不同边框的表格和单元格格式
linktitle: 设置具有不同边框的表格和单元格格式
second_title: Aspose.Words 文档处理 API
description: 使用 Aspose.Words for .NET 设置具有不同边框的表格和单元格格式的分步指南。
type: docs
weight: 10
url: /zh/net/programming-with-table-styles-and-formatting/format-table-and-cell-with-different-borders/
---

在本教程中，我们将引导您逐步使用 Aspose.Words for .NET 设置具有不同边框的表格和单元格格式。我们将解释捆绑的 C# 源代码，并为您提供全面的指南，帮助您理解并在自己的项目中实现此功能。在本教程结束时，您将了解如何使用 Aspose.Words for .NET 将自定义边框应用到 Word 文档中的特定表格和单元格。

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

## 第 3 步：创建一个新表格并添加单元格
要开始创建表，我们使用`StartTable()`文档生成器的方法，然后我们使用`InsertCell()`方法，我们将单元格的内容写入使用`Writeln()`方法。

```csharp
Table table = builder. StartTable();
builder. InsertCell();
//设置整个表格的边框。
table.SetBorders(LineStyle.Single, 2.0, Color.Black);
//设置该单元格的填充。
builder.CellFormat.Shading.BackgroundPatternColor = Color.Red;
builder.Writeln("Cell #1");
builder. InsertCell();
//为第二个单元格指定不同的单元格填充。
builder.CellFormat.Shading.BackgroundPatternColor = Color.Green;
builder.Writeln("Cell #2");
builder. EndRow();
//清除之前操作的单元格格式。
builder.CellFormat.ClearFormatting();
builder. InsertCell();
//为该行中的第一个单元格创建较粗的边框。将会有所不同
//相对于为表定义的边框。
builder.CellFormat.Borders.Left.LineWidth = 4.0;
builder.CellFormat.Borders.Right.LineWidth = 4.0;
builder.CellFormat.Borders.Top.LineWidth = 4.0;
builder.CellFormat.Borders.Bottom.LineWidth = 4.0;
builder.Writeln("Cell #3");
builder. InsertCell();
builder.CellFormat.ClearFormatting();
builder.Writeln("Cell #4");
```

## 步骤 4：保存文档

  修正的
最后将修改后的文档保存到文件中。您可以为输出文档选择适当的名称和位置。

```csharp
doc.Save(dataDir + "WorkingWithTableStylesAndFormatting.FormatTableAndCellWithDifferentBorders.docx");
```

恭喜！您现在已经使用 Aspose.Words for .NET 设置了具有不同边框的表格和单元格的格式。

### 使用 Aspose.Words for .NET 设置具有不同边框的表格和单元格格式的示例源代码 

```csharp
	//文档目录的路径
	string dataDir = "YOUR DOCUMENT DIRECTORY";

	Document doc = new Document();
	DocumentBuilder builder = new DocumentBuilder(doc);
	Table table = builder.StartTable();
	builder.InsertCell();
	//设置整个表格的边框。
	table.SetBorders(LineStyle.Single, 2.0, Color.Black);
	//设置该单元格的单元格底纹。
	builder.CellFormat.Shading.BackgroundPatternColor = Color.Red;
	builder.Writeln("Cell #1");
	builder.InsertCell();
	//为第二个单元格指定不同的单元格底纹。
	builder.CellFormat.Shading.BackgroundPatternColor = Color.Green;
	builder.Writeln("Cell #2");
	builder.EndRow();
	//清除之前操作中的单元格格式。
	builder.CellFormat.ClearFormatting();
	builder.InsertCell();
	//为该行的第一个单元格创建更大的边框。这将会有所不同
	//与为表格设置的边框相比。
	builder.CellFormat.Borders.Left.LineWidth = 4.0;
	builder.CellFormat.Borders.Right.LineWidth = 4.0;
	builder.CellFormat.Borders.Top.LineWidth = 4.0;
	builder.CellFormat.Borders.Bottom.LineWidth = 4.0;
	builder.Writeln("Cell #3");
	builder.InsertCell();
	builder.CellFormat.ClearFormatting();
	builder.Writeln("Cell #4");
	doc.Save(dataDir + "WorkingWithTableStylesAndFormatting.FormatTableAndCellWithDifferentBorders.docx");
```

## 结论
在本教程中，我们学习了如何使用 Aspose.Words for .NET 设置具有不同边框的表格和单元格的格式。通过遵循此分步指南，您可以轻松自定义 Word 文档中的表格和单元格边框。 Aspose.Words 提供了强大而灵活的 API，用于操作文档中的表格并设置其格式。有了这些知识，您就可以改进 Word 文档的视觉呈现并满足特定需求。