---
title: 直接插入表格
linktitle: 直接插入表格
second_title: Aspose.Words for .NET API 参考
description: 了解如何使用 Aspose.Words for .NET 将表格直接插入到 Word 文档中。
type: docs
weight: 10
url: /zh/net/programming-with-tables/insert-table-directly/
---

在本教程中，我们将学习如何使用 Aspose.Words for .NET 将表格直接插入到 Word 文档中。我们将按照分步指南来理解代码并实现此功能。在本教程结束时，您将能够以编程方式将表格直接插入到 Word 文档中。

## 第 1 步：项目设置
1. 启动 Visual Studio 并创建一个新的 C# 项目。
2. 添加对 Aspose.Words for .NET 库的引用。

## 第2步：创建文档和表格
要开始使用数组，我们需要创建一个新文档并初始化数组。按着这些次序：

```csharp
//文档目录的路径
string dataDir = "YOUR DOCUMENTS DIRECTORY";

//文档创建
Document doc = new Document();

//创建数组
Table table = new Table(doc);
doc.FirstSection.Body.AppendChild(table);
```

请务必将“您的文档目录”替换为文档目录的实际路径。

## 第 3 步：构建阵列
接下来，我们将通过添加行和单元格来构建表格。使用以下代码为例：

```csharp
//创建第一行
Row row = new Row(doc);
row.RowFormat.AllowBreakAcrossPages = true;
table.AppendChild(row);

//创建第一个单元格
Cell cell = new Cell(doc);
cell.CellFormat.Shading.BackgroundPatternColor = Color.LightBlue;
cell.CellFormat.Width = 80;
cell.AppendChild(new Paragraph(doc));
cell.FirstParagraph.AppendChild(new Run(doc, "Text in row 1, cell 1"));
row.AppendChild(cell);

//复制该单元格作为行中的第二个单元格
row.AppendChild(cell.Clone(false));
row.LastCell.AppendChild(new Paragraph(doc));
row.LastCell.FirstParagraph.AppendChild(new Run(doc, "Text in row 1, cell 2"));
```

这里我们创建一行`AllowBreakAcrossPages`属性设置为`true`允许行之间分页。然后，我们创建一个具有彩色背景、固定宽度和指定文本内容的单元格。然后，我们复制该单元格以创建该行中的第二个单元格。

## 第 4 步：自动调整表格
我们可以对表格应用自动调整以正确设置其格式。使用以下代码：

```csharp
table. AutoFit(AutoFitBehavior.FixedColumnWidths);
```

这行代码应用基于固定列宽的自动调整。

## 第 5 步：注册

  修改后的文件
最后，我们需要将修改后的文档与直接插入的表格一起保存。使用以下代码：

```csharp
doc.Save(dataDir + "WorkingWithTables.InsertTableDirectly.docx");
```

请务必为输出文档指定正确的路径和文件名。

### 使用 Aspose.Words for .NET 直接插入表格的示例源代码 

```csharp
	//文档目录的路径
	string dataDir = "YOUR DOCUMENT DIRECTORY";

	Document doc = new Document();
	//我们首先创建表对象。注意我们必须传递文档对象
	//到每个节点的构造函数。这是因为我们创建的每个节点都必须属于
	//到某个文档。
	Table table = new Table(doc);
	doc.FirstSection.Body.AppendChild(table);
	//在这里，我们可以调用 EnsureMinimum 为我们创建行和单元格。使用这个方法
	//确保指定的节点有效。在这种情况下，有效的表格应至少具有一行和一个单元格。
	//相反，我们将自己处理创建行和表。
	//如果我们在算法中创建表，这将是最好的方法。
	Row row = new Row(doc);
	row.RowFormat.AllowBreakAcrossPages = true;
	table.AppendChild(row);
	//我们现在可以应用任何自动调整设置。
	table.AutoFit(AutoFitBehavior.FixedColumnWidths);
	Cell cell = new Cell(doc);
	cell.CellFormat.Shading.BackgroundPatternColor = Color.LightBlue;
	cell.CellFormat.Width = 80;
	cell.AppendChild(new Paragraph(doc));
	cell.FirstParagraph.AppendChild(new Run(doc, "Row 1, Cell 1 Text"));
	row.AppendChild(cell);
	//然后，我们将对表中的其他单元格和行重复该过程。
	//我们还可以通过克隆现有的单元格和行来加快速度。
	row.AppendChild(cell.Clone(false));
	row.LastCell.AppendChild(new Paragraph(doc));
	row.LastCell.FirstParagraph.AppendChild(new Run(doc, "Row 1, Cell 2 Text"));
	doc.Save(dataDir + "WorkingWithTables.InsertTableDirectly.docx");
```

## 结论
在本教程中，我们学习了如何使用 Aspose.Words for .NET 将表格直接插入到 Word 文档中。通过遵循本分步指南并实现提供的 C# 代码，您可以通过编程方式将表格直接插入到 Word 文档中。此功能允许您根据您的特定需求创建和自定义表格。