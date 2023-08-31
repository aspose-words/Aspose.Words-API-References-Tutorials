---
title: 创建表格样式
linktitle: 创建表格样式
second_title: Aspose.Words 文档处理 API
description: 使用 Aspose.Words for .NET 创建自定义表格样式的分步指南。
type: docs
weight: 10
url: /zh/net/programming-with-table-styles-and-formatting/create-table-style/
---

在本教程中，我们将引导您完成使用 Aspose.Words for .NET 创建表格样式的分步过程。我们将解释捆绑的 C# 源代码，并为您提供全面的指南，帮助您理解并在自己的项目中实现此功能。在本教程结束时，您将了解如何使用 Aspose.Words for .NET 为 Word 文档中的表格创建自定义样式。

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

## 第 3 步：创建一个新表格并添加单元格
要开始创建表，我们使用`StartTable()`文档生成器的方法，然后我们使用`InsertCell()`方法，我们将单元格的内容写入使用`Write()`方法。

```csharp
Table table = builder. StartTable();
builder. InsertCell();
builder.Write("Name");
builder. InsertCell();
builder.Write("Value");
builder. EndRow();
builder. InsertCell();
builder. InsertCell();
builder. EndTable();
```

## 第四步：创建表格样式
现在我们可以使用以下命令创建表格样式`TableStyle`类和`Add()`文档中的方法`s `风格的集合。我们定义样式的属性，例如边框、边距和填充。

```csharp
TableStyle tableStyle = (TableStyle)doc.Styles.Add(StyleType.Table, "MyTableStyle1");
tableStyle.Borders.LineStyle = LineStyle.Double;
tableStyle.Borders.LineWidth = 1;
tableStyle. LeftPadding = 18;
tableStyle. RightPadding = 18;
tableStyle.TopPadding = 12;
tableStyle.BottomPadding = 12;
```

## 第5步：将表格样式应用到表格
最后，我们使用创建的表格样式应用到表格`Style`表的属性。

```csharp
table.Style = tableStyle;
```

## 第六步：保存修改后的文档
最后将修改后的文档保存到文件中。您可以为输出文档选择适当的名称和位置。

```csharp


doc.Save(dataDir + "WorkingWithTableStylesAndFormatting.CreateTableStyle.docx");
```

恭喜！您现在已经使用 Aspose.Words for .NET 为表格创建了自定义样式。

### 使用 Aspose.Words for .NET 创建表格样式的示例源代码 

```csharp
	//文档目录的路径
	string dataDir = "YOUR DOCUMENT DIRECTORY";

	Document doc = new Document();
	DocumentBuilder builder = new DocumentBuilder(doc);
	Table table = builder.StartTable();
	builder.InsertCell();
	builder.Write("Name");
	builder.InsertCell();
	builder.Write("Value");
	builder.EndRow();
	builder.InsertCell();
	builder.InsertCell();
	builder.EndTable();
	TableStyle tableStyle = (TableStyle) doc.Styles.Add(StyleType.Table, "MyTableStyle1");
	tableStyle.Borders.LineStyle = LineStyle.Double;
	tableStyle.Borders.LineWidth = 1;
	tableStyle.LeftPadding = 18;
	tableStyle.RightPadding = 18;
	tableStyle.TopPadding = 12;
	tableStyle.BottomPadding = 12;
	table.Style = tableStyle;
	doc.Save(dataDir + "WorkingWithTableStylesAndFormatting.CreateTableStyle.docx");
```

## 结论
在本教程中，我们学习了如何使用 Aspose.Words for .NET 创建表格样式。通过遵循此分步指南，您可以轻松自定义 Word 文档中的表格样式。 Aspose.Words 提供了强大而灵活的 API，用于操作文档中的表格并设置其格式。有了这些知识，您就可以改进 Word 文档的视觉呈现并满足特定需求。