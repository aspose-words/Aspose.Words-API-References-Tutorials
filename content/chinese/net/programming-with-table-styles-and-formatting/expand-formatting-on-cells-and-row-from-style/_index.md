---
title: 展开单元格的格式并从样式行
linktitle: 展开单元格的格式并从样式行
second_title: Aspose.Words 文档处理 API
description: 使用 Aspose.Words for .NET 将表格样式的格式扩展到单元格和行的分步指南。
type: docs
weight: 10
url: /zh/net/programming-with-table-styles-and-formatting/expand-formatting-on-cells-and-row-from-style/
---

在本教程中，我们将引导您逐步完成使用 Aspose.Words for .NET 将格式从样式扩展到单元格和行的过程。我们将解释捆绑的 C# 源代码，并为您提供全面的指南，帮助您理解并在自己的项目中实现此功能。在本教程结束时，您将了解如何使用 Aspose.Words for .NET 将表格样式格式应用于 Word 文档中的特定单元格和行。


## 第1步：定义文档目录
首先，您需要设置文档目录的路径。这是您的 Word 文档所在的位置。将“您的文档目录”替换为适当的路径。

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
```

## 第 2 步：加载现有文档
接下来，您需要将现有的 Word 文档加载到该实例中`Document`班级。

```csharp
Document doc = new Document(dataDir + "Tables.docx");
```

## 步骤 3：转到第一个表格的第一个单元格
首先，我们需要导航到文档中第一个表格的第一个单元格。我们使用`GetChild()`和`FirstRow.FirstCell`方法来获取对第一个单元格的引用。

```csharp
Table table = (Table)doc.GetChild(NodeType.Table, 0, true);
Cell firstCell = table.FirstRow.FirstCell;
```

## 步骤 4：显示初始单元格格式
在扩展表格的样式之前，我们显示单元格当前的背景颜色。该值应该为空，因为当前格式存储在表格的样式中。

```csharp
Color cellShadingBefore = firstCell.CellFormat.Shading.BackgroundPatternColor;
Console.WriteLine("Shading cell before style expansion: " + cellShadingBefore);
```

## 步骤 5：将表格样式扩展为直接格式化
现在我们将表格样式扩展为使用文档的直接格式`ExpandTableStylesToDirectFormatting()`方法。

```csharp
doc.ExpandTableStylesToDirectFormatting();
```

## 步骤 6：显示样式扩展后的单元格格式
现在我们在展开表格样式后显示单元格的背景颜色。应从表格样式应用蓝色背景颜色。

```csharp
Color cellShadingAfter = firstCell.CellFormat.Shading.BackgroundPatternColor;
Console.WriteLine("

Shading the cell after style expansion: " + cellShadingAfter);
```

### 使用 Aspose.Words for .NET 扩展单元格格式和从样式行的示例源代码 

```csharp
	//文档目录的路径
	string dataDir = "YOUR DOCUMENT DIRECTORY";

	Document doc = new Document(dataDir + "Tables.docx");
	//获取文档中第一个表格的第一个单元格。
	Table table = (Table) doc.GetChild(NodeType.Table, 0, true);
	Cell firstCell = table.FirstRow.FirstCell;
	//首先打印单元格底纹的颜色。
	//该值应该为空，因为当前着色存储在表格样式中。
	Color cellShadingBefore = firstCell.CellFormat.Shading.BackgroundPatternColor;
	Console.WriteLine("Cell shading before style expansion: " + cellShadingBefore);
	doc.ExpandTableStylesToDirectFormatting();
	//现在，在展开表格样式后打印单元格底纹。
	//应从表格样式应用蓝色背景图案颜色。
	Color cellShadingAfter = firstCell.CellFormat.Shading.BackgroundPatternColor;
	Console.WriteLine("Cell shading after style expansion: " + cellShadingAfter);
```

## 结论
在本教程中，我们学习了如何使用 Aspose.Words for .NET 将表格样式的格式扩展到单元格和行。通过遵循此分步指南，您可以轻松地将表格样式格式应用于 Word 文档中的特定单元格和行。 Aspose.Words 提供了强大而灵活的 API，用于操作文档中的表格并设置其格式。有了这些知识，您就可以进一步自定义 Word 文档的布局和演示文稿。