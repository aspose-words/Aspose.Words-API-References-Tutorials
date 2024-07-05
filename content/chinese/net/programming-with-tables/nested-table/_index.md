---
title: 嵌套表
linktitle: 嵌套表
second_title: Aspose.Words 文档处理 API
description: 了解如何使用 Aspose.Words for .NET 在 Word 文档中创建嵌套表。
type: docs
weight: 10
url: /zh/net/programming-with-tables/nested-table/
---

在本教程中，我们将学习如何使用 Aspose.Words for .NET 在 Word 文档中创建嵌套表格。我们将按照分步指南来理解代码并实现此功能。在本教程结束时，您将能够以编程方式在 Word 文档中创建嵌套表格。

## 步骤 1：项目设置
1. 启动 Visual Studio 并创建一个新的 C# 项目。
2. 添加对 Aspose.Words for .NET 库的引用。

## 第 2 步：创建文档并初始化文档生成器
要使用文档和文档生成器启动文字处理，请按照以下步骤操作：

```csharp
//文档目录的路径
string dataDir = "YOUR DOCUMENTS DIRECTORY";

//文档创建
Document doc = new Document();

//初始化文档生成器
DocumentBuilder builder = new DocumentBuilder(doc);
```

确保将“YOUR DOCUMENTS DIRECTORY”替换为您的文档目录的实际路径。

## 步骤 3：构建嵌套表
接下来，我们将通过在外部表格中插入单元格并在第一个单元格内创建新表格来构建嵌套表格。使用以下代码：

```csharp
//插入外部表格的第一个单元格
Cell cell = builder. InsertCell();
builder.Writeln("Cell 1 of the outer table");

//插入外表的第二个单元格
builder. InsertCell();
builder.Writeln("Cell 2 of the outer table");

//外表的终止
builder. EndTable();

//移至外表的第一个单元格
builder.MoveTo(cell.FirstParagraph);

//构建内表
builder. InsertCell();
builder.Writeln("Cell 1 of inner table");
builder. InsertCell();
builder.Writeln("Cell 2 of the inner table");

//内表结束
builder. EndTable();
```

这里我们使用文档生成器将单元格和内容插入到外部表格中。然后我们将文档生成器光标移动到外部表格的第一个单元格，并通过插入单元格和内容在内部构建一个新表格。

## 步骤 4：保存修改后的文档
最后，我们需要保存修改后的带有嵌套表的文档。使用以下代码：

```csharp
doc.Save(dataDir + "WorkingWithTables.NestedTable.docx");
```

确保为输出文档指定正确的路径和名称文件。

### 使用 Aspose.Words for .NET 的嵌套表示例源代码 

```csharp
	//文档目录的路径
	string dataDir = "YOUR DOCUMENT DIRECTORY";

	Document doc = new Document();
	DocumentBuilder builder = new DocumentBuilder(doc);
	Cell cell = builder.InsertCell();
	builder.Writeln("Outer Table Cell 1");
	builder.InsertCell();
	builder.Writeln("Outer Table Cell 2");
	//此调用对于在第一个表中创建嵌套表非常重要。
	//如果没有此调用，下面插入的单元格将被附加到外表。
	builder.EndTable();
	//移至外表的第一个单元格。
	builder.MoveTo(cell.FirstParagraph);
	//构建内表。
	builder.InsertCell();
	builder.Writeln("Inner Table Cell 1");
	builder.InsertCell();
	builder.Writeln("Inner Table Cell 2");
	builder.EndTable();
	doc.Save(dataDir + "WorkingWithTables.NestedTable.docx");
```

## 结论
在本教程中，我们学习了如何使用 Aspose.Words for .NET 在 Word 文档中创建嵌套表。通过遵循本分步指南并实现提供的 C# 代码，您可以根据您的特定需求以编程方式在 Word 文档中创建嵌套表。
