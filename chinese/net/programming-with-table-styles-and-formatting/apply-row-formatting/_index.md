---
title: 应用行格式
linktitle: 应用行格式
second_title: Aspose.Words for .NET API 参考
description: 使用 Aspose.Words for .NET 将行格式应用于表格的分步指南。
type: docs
weight: 10
url: /zh/net/programming-with-table-styles-and-formatting/apply-row-formatting/
---

在本教程中，我们将逐步引导您使用 Aspose.Words for .NET 将行格式应用于表格。我们将解释捆绑的 C# 源代码，并为您提供全面的指南，以帮助您了解并在您自己的项目中实现此功能。在本教程结束时，您将清楚地了解如何使用 Aspose.Words for .NET 格式化 Word 文档中的表格行。

## 第一步：定义文档目录
首先，您需要设置文档目录的路径。这是您要保存编辑后的 Word 文档的位置。用适当的路径替换“您的文档目录”。

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
```

## 第 2 步：创建新文档和文档生成器
接下来，您需要创建一个新的实例`Document`类和该文档的文档构造函数。

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
```

## 第 3 步：启动新板
要应用行格式，我们必须首先使用`StartTable()`文档构造函数的方法。

```csharp
Table table = builder. StartTable();
```

## 第 4 步：插入单元格并转到行格式
现在我们可以将一个单元格插入表格并使用文档生成器的访问该单元格的行格式`InsertCell()`和`RowFormat`方法。

```csharp
builder. InsertCell();
RowFormat rowFormat = builder.RowFormat;
```

## 第五步：设置行高
要设置行高，我们使用`Height`和`HeightRule`行格式的属性。在此示例中，我们将行高设置为 100 磅并使用`Exactly`规则。

```csharp
rowFormat. Height = 100;
rowFormat.HeightRule = HeightRule.Exactly;
```

## 步骤 6：定义表格格式
一些格式化属性可以在表格本身上设置并应用于所有表格行。在此示例中，我们使用`LeftPadding`, `RightPadding`, `TopPadding`和`BottomPadding`特性。

```csharp
table. LeftPadding = 30;
table. RightPadding = 30;
table. TopPadding = 30;
table. BottomPadding = 30;
```

## 第 7 步：向行添加内容
现在我们可以

我们将使用文档构造函数的方法向该行添加内容。在这个例子中，我们使用`Writeln()`向行中添加文本的方法。

```csharp
builder.Writeln("I'm a beautifully formatted line.");
```

## 第八步：完成线条和表格
一旦我们将内容添加到行中，我们就可以使用`EndRow()`方法，然后使用结束表`EndTable()`方法。

```csharp
builder. EndRow();
builder. EndTable();
```

## 第 9 步：保存修改后的文件
最后，我们将修改后的文档保存到一个文件中。您可以为输出文档选择合适的名称和位置。

```csharp
doc.Save(dataDir + "WorkingWithTableStylesAndFormatting.ApplyRowFormatting.docx");
```

恭喜！您现在已经使用 Aspose.Words for .NET 将行格式应用于表格。

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
	//这些格式化属性在表上设置并应用于表中的所有行。
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
在本教程中，我们学习了如何使用 Aspose.Words for .NET 将行格式应用于表格。按照这个分步指南，您可以轻松地将此功能集成到您的 C# 项目中。操作表格行格式是文档处理的一个重要方面，Aspose.Words 提供了一个强大而灵活的 API 来实现这一点。有了这些知识，您可以改进 Word 文档的视觉呈现并满足特定要求。