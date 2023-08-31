---
title: 设置单元格内边距
linktitle: 设置单元格内边距
second_title: Aspose.Words 文档处理 API
description: 使用 Aspose.Words for .NET 设置表格单元格边距的分步指南。
type: docs
weight: 10
url: /zh/net/programming-with-table-styles-and-formatting/set-cell-padding/
---

在本教程中，我们将引导您完成使用 Aspose.Words for .NET 设置表格单元格边距的分步过程。我们将解释捆绑的 C# 源代码，并为您提供全面的指南，帮助您理解并在自己的项目中实现此功能。在本教程结束时，您将了解如何使用 Aspose.Words for .NET 调整 Word 文档表格中单元格内容的左、上、右和下边距（空间）。

## 第1步：定义文档目录
首先，您需要设置文档目录的路径。这是您要保存编辑的 Word 文档的位置。将“您的文档目录”替换为适当的路径。

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
```

## 步骤 2：创建新文档和文档生成器
接下来，您需要创建一个新的实例`Document`类和该文档的文档构造函数。

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
```

## 第 3 步：创建一个新表格并添加一个单元格
要开始创建表，我们使用`StartTable()`文档构造函数的方法，然后我们使用`InsertCell()`方法。

```csharp
builder. StartTable();
builder. InsertCell();
```

## 第 4 步：设置单元格边距
现在我们可以使用以下命令设置单元格边距`SetPaddings()`的方法`CellFormat`目的。边距以磅为单位定义，并按左、上、右、下的顺序指定。

```csharp
builder.CellFormat.SetPaddings(30, 50, 30, 50);
```

## 步骤 5：向单元格添加内容
然后我们可以使用文档生成器向单元格添加内容`Writeln()`方法。

```csharp
builder.Writeln("I'm a beautifully formatted cell.");
```

## 步骤 6：完成表格并保存文档
最后，我们使用以下命令完成表的创建`EndRow()`方法和`EndTable()`，然后我们将修改后的文档保存到文件中。

```csharp
builder. EndRow();
builder. EndTable();
doc.Save(dataDir + "WorkingWithTableStylesAndFormatting.SetCellPadding.docx");
```
 
### 使用 Aspose.Words for .NET 设置单元格填充的示例源代码 

```csharp
	//文档目录的路径
	string dataDir = "YOUR DOCUMENT DIRECTORY";

	Document doc = new Document();
	DocumentBuilder builder = new DocumentBuilder(doc);
	builder.StartTable();
	builder.InsertCell();
	//设置添加到单元格内容的左侧/顶部/右侧/底部的空间量（以磅为单位）。
	builder.CellFormat.SetPaddings(30, 50, 30, 50);
	builder.Writeln("I'm a wonderful formatted cell.");
	builder.EndRow();
	builder.EndTable();
	doc.Save(dataDir + "WorkingWithTableStylesAndFormatting.SetCellPadding.docx");
```

## 结论
在本教程中，我们学习了如何使用 Aspose.Words for .NET 设置表格单元格的边距。通过遵循此分步指南，您可以轻松调整单元格边距，以便在 Word 文档表格内容的左侧、顶部、右侧和底部创建空格。 Aspose.Words 提供了强大而灵活的 API，用于操作文档中的表格并设置其格式。有了这些知识，您就可以根据您的特定需求自定义表格的格式。