---
title: 允许单元格间距
linktitle: 允许单元格间距
second_title: Aspose.Words 文档处理 API
description: 使用 Aspose.Words for .NET 允许单元格间距的分步指南。
type: docs
weight: 10
url: /zh/net/programming-with-table-styles-and-formatting/allow-cell-spacing/
---

在本教程中，我们将引导您逐步使用 Aspose.Words for .NET 在表格中允许单元格间距。我们将解释完成此任务的 C# 源代码，并提供全面的指南来帮助您理解并在自己的项目中实现它。在本教程结束时，您将清楚地了解如何使用 Aspose.Words for .NET 在 Word 文档中操作表格格式。

## 步骤 1：设置文档目录
首先，您需要设置文档目录的路径。这是您的 Word 文档的存储位置。将“您的文档目录”替换为适当的路径。

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## 步骤 2：加载文档
接下来，您需要将 Word 文档加载到`Document`班级。

```csharp
Document doc = new Document(dataDir + "Tables.docx");
```

## 步骤 3：访问表
为了允许单元格间距，我们需要访问文档中的表格。`Table`该类代表 Aspose.Words 中的表。

```csharp
Table table = (Table)doc.GetChild(NodeType.Table, 0, true);
```

## 步骤 4：启用单元格间距
现在，我们可以通过设置`AllowCellSpacing`表的属性`true`。该属性决定表格是否可以有单元格间距。

```csharp
table.AllowCellSpacing = true;
```

## 步骤 5：设置单元格间距
为了指定单元格之间的空间量，我们使用`CellSpacing`表格的属性。在此示例中，我们将单元格间距设置为 2 磅。

```csharp
table. CellSpacing = 2;
```

## 步骤 6：保存修改后的文档
最后，我们将修改后的文档保存到文件中。您可以为输出文档选择合适的名称和位置。

```csharp
doc.Save(dataDir + "WorkingWithTableStylesAndFormatting.AllowCellSpacing.docx");
```

恭喜！您已成功使用 Aspose.Words for .NET 在表格中允许单元格间距。

### 使用 Aspose.Words for .NET 允许单元格间距的示例源代码 

```csharp
	//文档目录的路径
	string dataDir = "YOUR DOCUMENT DIRECTORY";

	Document doc = new Document(dataDir + "Tables.docx");
	Table table = (Table) doc.GetChild(NodeType.Table, 0, true);
	table.AllowCellSpacing = true;
	table.CellSpacing = 2;
	doc.Save(dataDir + "WorkingWithTableStylesAndFormatting.AllowCellSpacing.docx");
```

## 结论
在本教程中，我们学习了如何使用 Aspose.Words for .NET 在表格中启用单元格间距。通过遵循分步指南，您可以轻松地将此功能合并到您的 C# 项目中。操作表格格式是文档处理的一个重要方面，Aspose.Words 提供了强大而灵活的 API 来实现这一点。有了这些知识，您可以增强 Word 文档的视觉呈现效果并满足特定的格式要求。