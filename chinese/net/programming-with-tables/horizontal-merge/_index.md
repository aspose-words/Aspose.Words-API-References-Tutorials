---
title: 水平合并
linktitle: 水平合并
second_title: Aspose.Words for .NET API 参考
description: 了解如何使用 Aspose.Words for .NET 水平合并 Word 表格中的单元格。
type: docs
weight: 10
url: /zh/net/programming-with-tables/horizontal-merge/
---

在本教程中，我们将学习如何使用 Aspose.Words for .NET 水平合并 Word 文档中表格中的单元格。我们将按照分步指南来理解代码并实现此功能。在本教程结束时，您将能够以编程方式水平合并 Word 表格中的单元格。

## 第 1 步：项目设置
1. 启动 Visual Studio 并创建一个新的 C# 项目。
2. 添加对 Aspose.Words for .NET 库的引用。

## 第2步：创建文档并初始化文档生成器
要开始使用表格和单元格，我们需要创建一个新文档并初始化文档生成器。按着这些次序：

```csharp
//文档目录的路径
string dataDir = "YOUR DOCUMENTS DIRECTORY";

//创建文档并初始化文档生成器
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
```

请务必将“您的文档目录”替换为文档目录的实际路径。

## 步骤 3：通过水平合并单元格构建表格
接下来，我们将使用 Aspose.Words for .NET 提供的属性构建表格并应用水平单元格合并。使用以下代码：

```csharp
builder. InsertCell();
builder.CellFormat.HorizontalMerge = CellMerge.First;
builder.Write("Text in merged cells.");
builder. InsertCell();
builder.CellFormat.HorizontalMerge = CellMerge.Previous;
//该单元格已与前一个单元格合并，并且应该为空。
builder. EndRow();

builder. InsertCell();
builder.CellFormat.HorizontalMerge = CellMerge.None;
builder.Write("Text in a cell.");
builder. InsertCell();
builder.Write("Text in another cell.");
builder. EndRow();
builder. EndTable();
```

这里我们使用文档生成器来构建表格并设置单元格水平合并属性。我们使用`HorizontalMerge`的财产`CellFormat`对象来指定要应用于每个单元格的水平合并的类型。使用`CellMerge.First`我们将第一个单元格与下一个单元格合并，同时使用`CellMerge.Previous`我们将当前单元格与前一个单元格合并。`CellMerge.None`指示不应合并单元格。

## 第四步：保存修改后的文档
最后，我们需要保存修改后的文档，并水平合并单元格。使用以下代码：

```csharp
doc.Save(data

Dir + "WorkingWithTables.HorizontalMerge.docx");
```

请务必为输出文档指定正确的路径和文件名。

### 使用 Aspose.Words for .NET 进行水平合并的示例源代码 

```csharp
	//文档目录的路径
	string dataDir = "YOUR DOCUMENT DIRECTORY";

	Document doc = new Document();
	DocumentBuilder builder = new DocumentBuilder(doc);
	builder.InsertCell();
	builder.CellFormat.HorizontalMerge = CellMerge.First;
	builder.Write("Text in merged cells.");
	builder.InsertCell();
	//该单元格已合并到前一个单元格，并且应该为空。
	builder.CellFormat.HorizontalMerge = CellMerge.Previous;
	builder.EndRow();
	builder.InsertCell();
	builder.CellFormat.HorizontalMerge = CellMerge.None;
	builder.Write("Text in one cell.");
	builder.InsertCell();
	builder.Write("Text in another cell.");
	builder.EndRow();
	builder.EndTable();
	doc.Save(dataDir + "WorkingWithTables.HorizontalMerge.docx");
```

## 结论
在本教程中，我们学习了如何使用 Aspose.Words for .NET 水平合并 Word 文档中表格中的单元格。通过遵循本分步指南并实现提供的 C# 代码，您可以以编程方式在 Word 表格中应用水平单元格合并。此功能允许您创建更复杂的表格布局并更好地组织数据。