---
title: 应用行格式
linktitle: 应用行格式
second_title: Aspose.Words 文档处理 API
description: 使用 Aspose.Words for .NET 将行格式应用于表格的分步指南。
type: docs
weight: 10
url: /zh/net/programming-with-table-styles-and-formatting/apply-row-formatting/
---

在本教程中，我们将引导您逐步使用 Aspose.Words for .NET 将行格式应用于表格。我们将解释捆绑的 C# 源代码并为您提供全面的指南，以帮助您理解并在自己的项目中实现此功能。在本教程结束时，您将清楚地了解如何使用 Aspose.Words for .NET 在 Word 文档中格式化表格行。

## 步骤1：定义文档目录
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

## 步骤 3：开始新的董事会
要应用行格式，我们必须首先使用`StartTable()`文档构造函数的方法。

```csharp
Table table = builder. StartTable();
```

## 步骤 4：插入单元格并转到行格式
现在我们可以在表中插入一个单元格，并使用文档生成器的`InsertCell()`和`RowFormat`方法。

```csharp
builder. InsertCell();
RowFormat rowFormat = builder.RowFormat;
```

## 步骤 5：设置行高
要设置行高，我们使用`Height`和`HeightRule`行格式的属性。在此示例中，我们将行高设置为 100 点，并使用`Exactly`规则。

```csharp
rowFormat. Height = 100;
rowFormat.HeightRule = HeightRule.Exactly;
```

## 步骤 6：定义表格格式
一些格式属性可以在表格本身上设置，并应用于所有表格行。在此示例中，我们使用`LeftPadding`, `RightPadding`, `TopPadding`和`BottomPadding`特性。

```csharp
table. LeftPadding = 30;
table. RightPadding = 30;
table. TopPadding = 30;
table. BottomPadding = 30;
```

## 步骤 7：向行添加内容
现在我们可以

我们将使用文档构造函数的方法向行中添加内容。在此示例中，我们使用`Writeln()`方法将文本添加到行中。

```csharp
builder.Writeln("I'm a beautifully formatted line.");
```

## 步骤 8：完成线条和表格
一旦我们将内容添加到行中，我们就可以使用`EndRow()`方法，然后使用`EndTable()`方法。

```csharp
builder. EndRow();
builder. EndTable();
```

## 步骤 9：保存修改后的文档
最后，我们将修改后的文档保存到文件中。您可以为输出文档选择合适的名称和位置。

```csharp
doc.Save(dataDir + "WorkingWithTableStylesAndFormatting.ApplyRowFormatting.docx");
```

恭喜！您现在已使用 Aspose.Words for .NET 将行格式应用于表格。

### 使用 Aspose.Words for .NET 应用行格式的示例源代码 

```csharp
	//文档目录的路径
	string dataDir = "YOUR DOCUMENT DIRECTORY";

	Document doc = new Document();
	DocumentBuilder builder = new DocumentBuilder(doc);
	Table table = builder.StartTable();
	builder.InsertCell();
	RowFormat rowFormat = builder.RowFormat;
	rowFormat.Height = 100;
	rowFormat.HeightRule = HeightRule.Exactly;
	//这些格式属性是在表上设置的，并应用于表中的所有行。
	table.LeftPadding = 30;
	table.RightPadding = 30;
	table.TopPadding = 30;
	table.BottomPadding = 30;
	builder.Writeln("I'm a wonderful formatted row.");
	builder.EndRow();
	builder.EndTable();
	doc.Save(dataDir + "WorkingWithTableStylesAndFormatting.ApplyRowFormatting.docx");
```

## 结论
在本教程中，我们学习了如何使用 Aspose.Words for .NET 将行格式应用于表格。通过遵循本分步指南，您可以轻松地将此功能集成到您的 C# 项目中。操作表格行格式是文档处理的一个重要方面，Aspose.Words 提供了强大而灵活的 API 来实现这一点。有了这些知识，您可以改善 Word 文档的视觉呈现并满足特定要求。