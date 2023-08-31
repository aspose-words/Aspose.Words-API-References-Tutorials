---
title: 自动适应页面宽度
linktitle: 自动适应页面宽度
second_title: Aspose.Words 文档处理 API
description: 了解如何使用 Aspose.Words for .NET 自动调整 Word 文档中表格的页面宽度。
type: docs
weight: 10
url: /zh/net/programming-with-tables/auto-fit-to-page-width/
---

在本教程中，我们将学习如何使用 Aspose.Words for .NET 自动调整表格以适应 Word 文档中的页面宽度。我们将按照分步指南来理解代码并实现此功能。在本教程结束时，您将能够以编程方式操作 Word 文档中的表格。

## 第 1 步：项目设置
1. 启动 Visual Studio 并创建一个新的 C# 项目。
2. 添加对 Aspose.Words for .NET 库的引用。

## 第 2 步：创建和配置文档
要使用表格启动文字处理，我们需要创建一个文档并配置文档生成器。按着这些次序：

```csharp
//文档目录的路径
string dataDir = "YOUR DOCUMENTS DIRECTORY";

//创建文档和文档生成器
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
```

请务必将“您的文档目录”替换为文档目录的实际路径。

## 第 3 步：插入并配置表
接下来，我们将在文档中插入一个表格，其宽度占页面宽度的一半。使用以下代码：

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

## 第四步：保存修改后的文档
最后，我们需要保存修改后的文档，并将表格调整为页面宽度。使用以下代码：

```csharp
//保存修改后的文档
doc.Save(dataDir + "WorkingWithTables.AutoFitToPageWidth.docx");
```

请务必为输出文档指定正确的路径和文件名。
  
### 使用 Aspose.Words for .NET 自动适应页面宽度的示例源代码 

```csharp
	//文档目录的路径
	string dataDir = "YOUR DOCUMENT DIRECTORY";

	Document doc = new Document();
	DocumentBuilder builder = new DocumentBuilder(doc);
	//插入宽度占页面宽度一半的表格。
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
在本教程中，我们学习了如何使用 Aspose.Words for .NET 在 Word 文档中自动调整表格的页面宽度。通过遵循本分步指南并实现提供的 C# 代码，您可以以编程方式操作 Word 文档中的表格。此功能允许您根据页面动态调整表格的宽度，从而提供专业且具有视觉吸引力的文档。