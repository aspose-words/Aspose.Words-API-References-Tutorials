---
title: 把桌子放在一起
linktitle: 把桌子放在一起
second_title: Aspose.Words for .NET API 参考
description: 了解如何使用 Aspose.Words for .NET 在 Word 文档中将表格放在一起。
type: docs
weight: 10
url: /zh/net/programming-with-tables/keep-table-together/
---

在本教程中，我们将学习如何使用 Aspose.Words for .NET 在 Word 文档中将表格放在一起。我们将按照逐步指南来理解代码并实现此功能。到本教程结束时，您将能够保持表格完好无损，而不会在 Word 文档中将其拆分为多个页面。

## 第 1 步：项目设置
1. 启动 Visual Studio 并创建一个新的 C# 项目。
2. 添加对 Aspose.Words for .NET 库的引用。

## 第 2 步：加载文档并检索表格
要开始使用表格，我们需要加载文档并获取我们想要保存在一起的表格。按着这些次序：

```csharp
//文档目录的路径
string dataDir = "YOUR DOCUMENTS DIRECTORY";

//装入文档
Document doc = new Document(dataDir + "Table spanning two pages.docx");

//检索表
Table table = (Table)doc.GetChild(NodeType.Table, 0, true);
```

请务必将“您的文档目录”替换为您的文档目录的实际路径。

## 第 3 步：启用“KeepWithNext”选项
为了将表格保持在一起并防止它跨多个页面拆分，我们需要为表格中的每个段落启用“KeepWithNext”选项，表格最后一行的最后一段除外。使用以下代码：

```csharp
foreach(Cell cell in table.GetChildNodes(NodeType.Cell, true))
{
cell.EnsureMinimum();
foreach(Paragraph para in cell.Paragraphs)
if (!(cell.ParentRow.IsLastRow && para.IsEndOfCell))
para.ParagraphFormat.KeepWithNext = true;
}
```

在这里，我们遍历表格中的每个单元格，并为单元格中的每个段落启用“KeepWithNext”选项，表格中最后一行的最后一段除外。

## 第 4 步：保存修改后的文档
最后，我们需要将修改后的文档连同表格保存在一起。使用以下代码：

```csharp
doc.Save(dataDir + "WorkingWithTables.KeepTableTogether.docx");
```

请务必为输出文档指定正确的路径和文件名。

### 使用 Aspose.Words for .NET 将表格放在一起的示例源代码 

```csharp
	//文档目录的路径
	string dataDir = "YOUR DOCUMENT DIRECTORY";

	Document doc = new Document(dataDir + "Table spanning two pages.docx");
	Table table = (Table) doc.GetChild(NodeType.Table, 0, true);
	//我们需要为表格中的每个段落启用 KeepWithNext，以防止它跨页，
	//除了表格最后一行的最后一段。
	foreach (Cell cell in table.GetChildNodes(NodeType.Cell, true))
	{
		cell.EnsureMinimum();
		foreach (Paragraph para in cell.Paragraphs)
			if (!(cell.ParentRow.IsLastRow && para.IsEndOfCell))
				para.ParagraphFormat.KeepWithNext = true;
	}
	doc.Save(dataDir + "WorkingWithTables.KeepTableTogether.docx");
```

## 结论
在本教程中，我们学习了如何使用 Aspose.Words for .NET 在 Word 文档中将表格放在一起。通过遵循此分步指南并实施提供的 C# 代码，您可以保持表格完整并防止它在文档中跨多个页面拆分。此功能使您可以更好地控制文档中表格的外观和布局。