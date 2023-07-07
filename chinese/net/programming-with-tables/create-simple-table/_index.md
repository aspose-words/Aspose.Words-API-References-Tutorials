---
title: 创建简单表
linktitle: 创建简单表
second_title: Aspose.Words for .NET API 参考
description: 了解如何使用 Aspose.Words for .NET 在 Word 文档中创建简单的表格。
type: docs
weight: 10
url: /zh/net/programming-with-tables/create-simple-table/
---

在本教程中，我们将学习如何使用 Aspose.Words for .NET 在 Word 文档中创建简单的表格。我们将按照分步指南来理解代码并实现此功能。在本教程结束时，您将能够以编程方式在 Word 文档中创建自定义表格。

## 第 1 步：项目设置
1. 启动 Visual Studio 并创建一个新的 C# 项目。
2. 添加对 Aspose.Words for .NET 库的引用。

## 第2步：创建文档并初始化文档生成器
要开始构建表，我们需要创建一个新文档并初始化文档构建器。按着这些次序：

```csharp
//文档目录的路径
string dataDir = "YOUR DOCUMENTS DIRECTORY";

//创建文档并初始化文档生成器
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
```

请务必将“您的文档目录”替换为文档目录的实际路径。

## 第 3 步：构建阵列
接下来，我们将使用文档构建器提供的方法构建表。使用以下代码：

```csharp
//开始数组构建
builder. StartTable();

//构建第一行第一个单元格
builder. InsertCell();
builder.Write("Contents of cell 1 of row 1.");

//第一行第二个单元格的构造
builder. InsertCell();
builder.Write("Contents of cell 2 of row 1.");

//调用以下方法结束第一行并开始新行
builder. EndRow();

//第二行第一个单元格的构造
builder. InsertCell();
builder.Write("Contents of cell 1 of row 2.");

//第二排第二个单元的构造
builder. InsertCell();
builder.Write("Contents of cell 2 of row 2.");

//调用next方法结束第二行
builder. EndRow();

//表明表的构建完成
builder. EndTable();
```

这里我们使用文档构建器来一步步构建表格。我们首先调用`StartTable()`初始化表，然后使用`InsertCell()`插入细胞和`Write()`向每个单元格添加内容。我们还使用`EndRow()`结束一行并开始新行。最后，我们调用`EndTable()`表明表构建完成。

## 步骤 4：保存文档
最后，我们需要保存

  包含创建的表格的文档。使用以下代码：

```csharp
//保存文档
doc.Save(dataDir + "WorkingWithTables.CreateSimpleTable.docx");
```

请务必为输出文档指定正确的路径和文件名。

### 使用 Aspose.Words for .NET 创建简单表的示例源代码 

```csharp
	//文档目录的路径
	string dataDir = "YOUR DOCUMENT DIRECTORY";

	Document doc = new Document();
	DocumentBuilder builder = new DocumentBuilder(doc);
	//开始建表。
	builder.StartTable();
	builder.InsertCell();
	builder.Write("Row 1, Cell 1 Content.");
	//构建第二个单元格。
	builder.InsertCell();
	builder.Write("Row 1, Cell 2 Content.");
	//调用以下方法结束该行并开始新行。
	builder.EndRow();
	//构建第二行的第一个单元格。
	builder.InsertCell();
	builder.Write("Row 2, Cell 1 Content");
	//构建第二个单元格。
	builder.InsertCell();
	builder.Write("Row 2, Cell 2 Content.");
	builder.EndRow();
	//表明我们已经完成了表格的构建。
	builder.EndTable();
	doc.Save(dataDir + "WorkingWithTables.CreateSimpleTable.docx");
```

## 结论
在本教程中，我们学习了如何使用 Aspose.Words for .NET 在 Word 文档中创建简单的表格。通过遵循本分步指南并实施提供的 C# 代码，您可以以编程方式在 Word 文档中创建自定义表格。此功能允许您以结构化且清晰的方式格式化和组织数据。