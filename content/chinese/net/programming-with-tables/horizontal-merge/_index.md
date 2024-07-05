---
title: 水平合并
linktitle: 水平合并
second_title: Aspose.Words 文档处理 API
description: 了解如何使用 Aspose.Words for .NET 在 Word 表中水平合并单元格。
type: docs
weight: 10
url: /zh/net/programming-with-tables/horizontal-merge/
---

在本教程中，我们将学习如何使用 Aspose.Words for .NET 在 Word 文档的表格中水平合并单元格。我们将按照分步指南来理解代码并实现此功能。在本教程结束时，您将能够以编程方式在 Word 表格中水平合并单元格。

## 步骤 1：项目设置
1. 启动 Visual Studio 并创建一个新的 C# 项目。
2. 添加对 Aspose.Words for .NET 库的引用。

## 第 2 步：创建文档并初始化文档生成器
要使用表格和单元格启动文字处理，我们需要创建一个新文档并初始化文档生成器。请按以下步骤操作：

```csharp
//文档目录的路径
string dataDir = "YOUR DOCUMENTS DIRECTORY";

//创建文档并初始化文档生成器
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
```

确保将“YOUR DOCUMENTS DIRECTORY”替换为您的文档目录的实际路径。

## 步骤 3：构建水平合并单元格的表格
接下来，我们将构建表格并使用 Aspose.Words for .NET 提供的属性应用水平单元格合并。使用以下代码：

```csharp
builder. InsertCell();
builder.CellFormat.HorizontalMerge = CellMerge.First;
builder.Write("Text in merged cells.");
builder. InsertCell();
builder.CellFormat.HorizontalMerge = CellMerge.Previous;
//此单元格与前一个单元格合并并且应为空。
builder. EndRow();

builder. InsertCell();
builder.CellFormat.HorizontalMerge = CellMerge.None;
builder.Write("Text in a cell.");
builder. InsertCell();
builder.Write("Text in another cell.");
builder. EndRow();
builder. EndTable();
```

这里我们使用文档生成器来构建表格并设置单元格水平合并属性。我们使用`HorizontalMerge`的财产`CellFormat`对象来指定应用于每个单元格的水平合并类型。使用`CellMerge.First`我们将第一个单元格与下一个单元格合并，同时使用`CellMerge.Previous`我们将当前单元格与前一个单元格合并。`CellMerge.None`表示该单元格不应合并。

## 步骤 4：保存修改后的文档
最后，我们需要保存修改后的文档，并将单元格水平合并。使用以下代码：

```csharp
doc.Save(data

Dir + "WorkingWithTables.HorizontalMerge.docx");
```

确保为输出文档指定正确的路径和文件名。

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
	//该单元格与前一个单元格合并并且应为空。
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
在本教程中，我们学习了如何使用 Aspose.Words for .NET 在 Word 文档中的表格中水平合并单元格。通过遵循本分步指南并实现提供的 C# 代码，您可以以编程方式在 Word 表中应用水平单元格合并。此功能允许您创建更复杂的表格布局并更好地组织数据。