---
title: 首选宽度设置
linktitle: 首选宽度设置
second_title: Aspose.Words 文档处理 API
description: 了解如何使用 Aspose.Words for .NET 在 Word 文档中设置首选表格单元格宽度。
type: docs
weight: 10
url: /zh/net/programming-with-tables/preferred-width-settings/
---

在本教程中，我们将学习如何使用 Aspose.Words for .NET 设置 Word 文档中表格单元格的首选宽度设置。我们将按照分步指南来理解代码并实现此功能。在本教程结束时，您将能够为 Word 文档中的表格单元格指定不同的首选宽度。

## 第 1 步：项目设置
1. 启动 Visual Studio 并创建一个新的 C# 项目。
2. 添加对 Aspose.Words for .NET 库的引用。

## 第2步：创建文档并初始化文档生成器
要使用文档和文档生成器启动字处理，请按照下列步骤操作：

```csharp
//文档目录的路径
string dataDir = "YOUR DOCUMENTS DIRECTORY";

//文档创建
Document doc = new Document();

//初始化文档生成器
DocumentBuilder builder = new DocumentBuilder(doc);
```

请务必将“您的文档目录”替换为文档目录的实际路径。

## 第 3 步：构建具有首选宽度的表格
接下来，我们将构建一个包含三个具有不同首选宽度的单元格的表格。使用以下代码：

```csharp
//表的开头
builder. StartTable();

//插入绝对大小的单元格
builder. InsertCell();
builder.CellFormat.PreferredWidth = PreferredWidth.FromPoints(40);
builder.CellFormat.Shading.BackgroundPatternColor = Color.LightYellow;
builder.Writeln("Cell with a width of 40 points");

//插入相对大小的单元格（以百分比表示）
builder. InsertCell();
builder.CellFormat.PreferredWidth = PreferredWidth.FromPercent(20);
builder.CellFormat.Shading.BackgroundPatternColor = Color.LightBlue;
builder.Writeln("Cell with 20% width");

//插入自动调整大小的单元格
builder. InsertCell();
builder.CellFormat.PreferredWidth = PreferredWidth.Auto;
builder.CellFormat.Shading.BackgroundPatternColor = Color.LightGreen;
builder.Writeln("Auto-size cell. The size of this cell is calculated from the preferred width of the table. In this case, the cell will fill the rest of the available space.");

//表尾
builder. EndTable();
```

这里我们使用文档生成器来构建一个包含三个单元格的表格。第一个单元格的首选宽度为 40 磅，第二个单元格的首选宽度为表格宽度的 20%，第三个单元格的首选宽度可自动调整

  取决于可用空间。

## 第四步：保存修改后的文档
最后，我们需要使用为表格单元格定义的首选宽度设置来保存修改后的文档。使用以下代码：

```csharp
doc.Save(dataDir + "WorkingWithTables.PreferredWidthSettings.docx");
```

请务必为输出文档指定正确的路径和文件名。

### 使用 Aspose.Words for .NET 的首选宽度设置的示例源代码 

```csharp
	//文档目录的路径
	string dataDir = "YOUR DOCUMENT DIRECTORY";

	Document doc = new Document();
	DocumentBuilder builder = new DocumentBuilder(doc);
	//插入由三个具有不同首选宽度的单元格组成的表格行。
	builder.StartTable();
	//插入绝对大小的单元格。
	builder.InsertCell();
	builder.CellFormat.PreferredWidth = PreferredWidth.FromPoints(40);
	builder.CellFormat.Shading.BackgroundPatternColor = Color.LightYellow;
	builder.Writeln("Cell at 40 points width");
	//插入相对（百分比）大小的单元格。
	builder.InsertCell();
	builder.CellFormat.PreferredWidth = PreferredWidth.FromPercent(20);
	builder.CellFormat.Shading.BackgroundPatternColor = Color.LightBlue;
	builder.Writeln("Cell at 20% width");
	//插入自动调整大小的单元格。
	builder.InsertCell();
	builder.CellFormat.PreferredWidth = PreferredWidth.Auto;
	builder.CellFormat.Shading.BackgroundPatternColor = Color.LightGreen;
	builder.Writeln(
		"Cell automatically sized. The size of this cell is calculated from the table preferred width.");
	builder.Writeln("In this case the cell will fill up the rest of the available space.");
	doc.Save(dataDir + "WorkingWithTables.PreferredWidthSettings.docx");
```

## 结论
在本教程中，我们学习了如何使用 Aspose.Words for .NET 设置 Word 文档中表格单元格的首选宽度设置。通过遵循本分步指南并实施提供的 C# 代码，您可以根据您在 Word 文档中的特定需求自定义表格单元格宽度。