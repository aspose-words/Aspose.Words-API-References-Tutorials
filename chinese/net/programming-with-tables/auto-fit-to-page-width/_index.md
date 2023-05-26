---
title: 自动适应页面宽度
linktitle: 自动适应页面宽度
second_title: Aspose.Words for .NET API 参考
description: 了解如何使用 Aspose.Words for .NET 使表格自动适应 Word 文档中的页面宽度。
type: docs
weight: 10
url: /zh/net/programming-with-tables/auto-fit-to-page-width/
---

在本教程中，我们将学习如何使用 Aspose.Words for .NET 使表格自动适应 Word 文档中的页面宽度。我们将按照逐步指南来理解代码并实现此功能。在本教程结束时，您将能够以编程方式操作 Word 文档中的表格。

## 第 1 步：项目设置
1. 启动 Visual Studio 并创建一个新的 C# 项目。
2. 添加对 Aspose.Words for .NET 库的引用。

## 第 2 步：创建和配置文档
要开始使用表格，我们需要创建一个文档并配置文档生成器。按着这些次序：

```csharp
//文档目录的路径
string dataDir = "YOUR DOCUMENTS DIRECTORY";

//创建文档和文档生成器
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
```

请务必将“您的文档目录”替换为您的文档目录的实际路径。

## 第 3 步：插入和配置表
接下来，我们将在文档中插入一个表格，表格的宽度占页面宽度的一半。使用以下代码：

```csharp
//插入表格并配置其宽度
Table table = builder. StartTable();
builder. InsertCell();
table. PreferredWidth = PreferredWidth. FromPercent(50);
builder.Writeln("Cell #1");
builder. InsertCell();
builder.Writeln("Cell #2");
builder. InsertCell();
builder.Writeln("Cell #3");
```

这里我们使用文档生成器开始创建表格，插入单元格，并将表格的首选宽度设置为页面宽度的 50%。然后我们在每个单元格中添加文本。

## 第 4 步：保存修改后的文档
最后，我们需要保存修改后的文档，表格调整到页面宽度。使用以下代码：

```csharp
//保存修改后的文件
doc.Save(dataDir + "WorkingWithTables.AutoFitToPageWidth.docx");
```

请务必为输出文档指定正确的路径和文件名。
  
### 使用 Aspose.Words for .NET 自动适应页面宽度的示例源代码 

```csharp
	//文档目录的路径
	string dataDir = "YOUR DOCUMENT DIRECTORY";

	Document doc = new Document();
	DocumentBuilder builder = new DocumentBuilder(doc);
	//插入一个宽度为页面宽度一半的表格。
	Table table = builder.StartTable();
	builder.InsertCell();
	table.PreferredWidth = PreferredWidth.FromPercent(50);
	builder.Writeln("Cell #1");
	builder.InsertCell();
	builder.Writeln("Cell #2");
	builder.InsertCell();
	builder.Writeln("Cell #3");
	doc.Save(dataDir + "WorkingWithTables.AutoFitToPageWidth.docx");
```

## 结论
在本教程中，我们学习了如何使用 Aspose.Words for .NET 使表格自动适应 Word 文档中的页面宽度。通过遵循此分步指南并实施提供的 C# 代码，您可以以编程方式操作 Word 文档中的表格。此功能允许您根据页面动态调整表格的宽度，从而提供专业且具有视觉吸引力的文档。