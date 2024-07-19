---
title: 使用不同的边框格式化表格和单元格
linktitle: 使用不同的边框格式化表格和单元格
second_title: Aspose.Words 文档处理 API
description: 使用 Aspose.Words for .NET 一步一步指导如何用不同的边框格式化表格和单元格。
type: docs
weight: 10
url: /zh/net/programming-with-table-styles-and-formatting/format-table-and-cell-with-different-borders/
---

在本教程中，我们将引导您逐步使用 Aspose.Words for .NET 格式化具有不同边框的表格和单元格。我们将解释捆绑的 C# 源代码并为您提供全面的指南，以帮助您理解并在自己的项目中实现此功能。在本教程结束时，您将了解如何使用 Aspose.Words for .NET 将自定义边框应用于 Word 文档中的特定表格和单元格。

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

## 步骤 3：开始新表格并添加单元格
要开始创建表，我们使用`StartTable()`方法，然后我们使用`InsertCell()`方法，我们将单元格的内容写入使用`Writeln()`方法。

```csharp
Table table = builder. StartTable();
builder.InsertCell();
//为整个表格设置边框。
table.SetBorders(LineStyle.Single, 2.0, Color.Black);
//设置该单元格的填充。
builder.CellFormat.Shading.BackgroundPatternColor = Color.Red;
builder.Writeln("Cell #1");
builder.InsertCell();
//为第二个单元格指定不同的单元格填充。
builder.CellFormat.Shading.BackgroundPatternColor = Color.Green;
builder.Writeln("Cell #2");
builder.EndRow();
//清除先前操作的单元格格式。
builder.CellFormat.ClearFormatting();
builder.InsertCell();
//为该行中的第一个单元格创建更粗的边框。它将有所不同
//相对于表格定义的边框。
builder.CellFormat.Borders.Left.LineWidth = 4.0;
builder.CellFormat.Borders.Right.LineWidth = 4.0;
builder.CellFormat.Borders.Top.LineWidth = 4.0;
builder.CellFormat.Borders.Bottom.LineWidth = 4.0;
builder.Writeln("Cell #3");
builder.InsertCell();
builder.CellFormat.ClearFormatting();
builder.Writeln("Cell #4");
```

## 步骤 4：保存文档

  修正
最后将修改后的文档保存为文件。您可以为输出文档选择合适的名称和位置。

```csharp
doc.Save(dataDir + "WorkingWithTableStylesAndFormatting.FormatTableAndCellWithDifferentBorders.docx");
```

恭喜！现在，您已使用 Aspose.Words for .NET 格式化了具有不同边框的表格和单元格。

### 使用 Aspose.Words for .NET 格式化表格和具有不同边框的单元格的示例源代码 

```csharp
//文档目录的路径
string dataDir = "YOUR DOCUMENT DIRECTORY";

Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
Table table = builder.StartTable();
builder.InsertCell();
//设置整个表格的边框。
table.SetBorders(LineStyle.Single, 2.0, Color.Black);
//设置此单元格的单元格阴影。
builder.CellFormat.Shading.BackgroundPatternColor = Color.Red;
builder.Writeln("Cell #1");
builder.InsertCell();
//为第二个单元格指定不同的单元格阴影。
builder.CellFormat.Shading.BackgroundPatternColor = Color.Green;
builder.Writeln("Cell #2");
builder.EndRow();
//清除以前操作的单元格格式。
builder.CellFormat.ClearFormatting();
builder.InsertCell();
//为该行的第一个单元格创建更大的边框。这将有所不同
//与表格设置的边框相比。
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
在本教程中，我们学习了如何使用 Aspose.Words for .NET 格式化具有不同边框的表格和单元格。通过遵循本分步指南，您可以轻松地自定义 Word 文档中的表格和单元格边框。Aspose.Words 提供了强大而灵活的 API，用于操作和格式化文档中的表格。有了这些知识，您可以改善 Word 文档的视觉呈现并满足特定需求。