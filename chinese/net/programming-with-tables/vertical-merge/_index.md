---
title: 垂直合并
linktitle: 垂直合并
second_title: Aspose.Words 文档处理 API
description: 了解如何使用 Aspose.Words for .NET 垂直合并 Word 文档表格中的单元格。
type: docs
weight: 10
url: /zh/net/programming-with-tables/vertical-merge/
---

在本教程中，我们将学习如何使用 Aspose.Words for .NET 垂直合并 Word 文档中表格中的单元格。我们将按照分步指南来理解代码并实现此功能。在本教程结束时，您将能够垂直合并 Word 文档中表格中的单元格。

## 第 1 步：项目设置
1. 启动 Visual Studio 并创建一个新的 C# 项目。
2. 添加对 Aspose.Words for .NET 库的引用。

## 第 2 步：加载文档
要启动文档的文字处理，请按照下列步骤操作：

```csharp
//文档目录的路径
string dataDir = "YOUR DOCUMENTS DIRECTORY";

//创建一个新文档
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
```

请务必将“您的文档目录”替换为文档目录的实际路径。

## 步骤 3：垂直合并单元格
接下来我们将合并表格中的垂直单元格。使用以下代码：

```csharp
//插入一个单元格
builder. InsertCell();

//将垂直合并应用于第一个单元格
builder.CellFormat.VerticalMerge = CellMerge.First;
builder.Write("Text in merged cells.");

//插入另一个单元格
builder. InsertCell();

//不对单元格应用垂直合并
builder.CellFormat.VerticalMerge = CellMerge.None;
builder.Write("Text in a cell");
builder. EndRow();

//插入一个单元格
builder. InsertCell();

//应用与前一个单元格的垂直合并
builder.CellFormat.VerticalMerge = CellMerge.Previous;

//插入另一个单元格
builder. InsertCell();

//不对单元格应用垂直合并
builder.CellFormat.VerticalMerge = CellMerge.None;
builder.Write("Text in another cell");
builder. EndRow();

//结束表的创建
builder. EndTable();
```

在此代码中，我们使用 DocumentBuilder 构造函数将单元格插入表中。我们使用 CellFormat.VerticalMerge 属性对单元格应用垂直合并。我们使用 CellMerge.First 进行第一次单元格合并，使用 CellMerge.Previous 与前一个单元格合并，使用 CellMerge.None 进行非垂直合并。

## 第四步：保存修改后的文档
最后，我们需要保存修改后的文档和合并的单元格。使用以下代码：

```csharp
doc.Save(dataDir + "WorkingWithTables.VerticalMerge.docx");
```

请务必为输出文档指定正确的路径和文件名。

### 使用 Aspose.Words for .NET 进行垂直合并的示例源代码 
```csharp
	//文档目录的路径
	string dataDir = "YOUR DOCUMENT DIRECTORY";

	Document doc = new Document();
	DocumentBuilder builder = new DocumentBuilder(doc);
	builder.InsertCell();
	builder.CellFormat.VerticalMerge = CellMerge.First;
	builder.Write("Text in merged cells.");
	builder.InsertCell();
	builder.CellFormat.VerticalMerge = CellMerge.None;
	builder.Write("Text in one cell");
	builder.EndRow();
	builder.InsertCell();
	//该单元格垂直合并到上面的单元格，并且应该为空。
	builder.CellFormat.VerticalMerge = CellMerge.Previous;
	builder.InsertCell();
	builder.CellFormat.VerticalMerge = CellMerge.None;
	builder.Write("Text in another cell");
	builder.EndRow();
	builder.EndTable();
	doc.Save(dataDir + "WorkingWithTables.VerticalMerge.docx");
```

## 结论
在本教程中，我们学习了如何使用 Aspose.Words for .NET 垂直合并 Word 文档中表格中的单元格。通过遵循此分步指南并实现提供的 C# 代码，您可以轻松合并表格中的垂直单元格。