---
title: 修改行格式
linktitle: 修改行格式
second_title: Aspose.Words for .NET API 参考
description: 使用 Aspose.Words for .NET 更改表格行格式的分步指南。
type: docs
weight: 10
url: /zh/net/programming-with-table-styles-and-formatting/modify-row-formatting/
---

在本教程中，我们将引导您完成使用 Aspose.Words for .NET 更改表格行格式的分步过程。我们将解释捆绑的 C# 源代码，并为您提供全面的指南，帮助您理解并在自己的项目中实现此功能。在本教程结束时，您将了解如何使用 Aspose.Words for .NET 更改 Word 文档中表格行的边框、高度和换行符。

## 第1步：定义文档目录
首先，您需要设置文档目录的路径。这是您的 Word 文档所在的位置。将“您的文档目录”替换为适当的路径。

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
```

## 第 2 步：加载现有文档
接下来，您需要将现有的 Word 文档加载到该实例中`Document`班级。

```csharp
Document doc = new Document(dataDir + "Tables.docx");
```

## 第三步：访问要修改的行
要更改表行的格式，我们需要导航到表中的特定行。我们使用`GetChild()`和`FirstRow`方法来获取对表第一行的引用。

```csharp
Table table = (Table)doc.GetChild(NodeType.Table, 0, true);
Row firstRow = table.FirstRow;
```

## 步骤 4：更改行格式
现在我们可以使用属性来更改行格式`RowFormat`班级。例如，我们可以删除线边框、设置自动高度并允许换行。

```csharp
firstRow.RowFormat.Borders.LineStyle = LineStyle.None;
firstRow.RowFormat.HeightRule = HeightRule.Auto;
firstRow.RowFormat.AllowBreakAcrossPages = true;
```

### 使用 Aspose.Words for .NET 修改行格式的示例源代码 

```csharp
	//文档目录的路径
	string dataDir = "YOUR DOCUMENT DIRECTORY";

	Document doc = new Document(dataDir + "Tables.docx");
	Table table = (Table) doc.GetChild(NodeType.Table, 0, true);
	//检索表中的第一行。
	Row firstRow = table.FirstRow;
	firstRow.RowFormat.Borders.LineStyle = LineStyle.None;
	firstRow.RowFormat.HeightRule = HeightRule.Auto;
	firstRow.RowFormat.AllowBreakAcrossPages = true;
```

## 结论
在本教程中，我们学习了如何使用 Aspose.Words for .NET 更改表格行的格式。通过遵循此分步指南，您可以轻松调整 Word 文档中表格的边框、高度和行换行符。 Aspose.Words 提供了强大而灵活的 API，用于操作文档中的表格并设置其格式。有了这些知识，您就可以根据您的特定需求自定义表格的视觉布局。