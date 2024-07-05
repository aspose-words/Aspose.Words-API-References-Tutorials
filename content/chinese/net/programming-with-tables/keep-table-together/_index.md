---
title: 保持桌子整齐
linktitle: 保持桌子整齐
second_title: Aspose.Words 文档处理 API
description: 了解如何使用 Aspose.Words for .NET 将 Word 文档中的表格合并在一起。
type: docs
weight: 10
url: /zh/net/programming-with-tables/keep-table-together/
---

在本教程中，我们将学习如何使用 Aspose.Words for .NET 将 Word 文档中的表格合并在一起。我们将按照分步指南来理解代码并实现此功能。在本教程结束时，您将能够保持表格完整，而不会将其拆分到 Word 文档中的多个页面中。

## 步骤 1：项目设置
1. 启动 Visual Studio 并创建一个新的 C# 项目。
2. 添加对 Aspose.Words for .NET 库的引用。

## 第 2 步：加载文档并检索表格
要使用表格启动文字处理，我们需要加载文档并获取要保存的表格。请按以下步骤操作：

```csharp
//文档目录的路径
string dataDir = "YOUR DOCUMENTS DIRECTORY";

//加载文档
Document doc = new Document(dataDir + "Table spanning two pages.docx");

//检索表
Table table = (Table)doc.GetChild(NodeType.Table, 0, true);
```

确保将“YOUR DOCUMENTS DIRECTORY”替换为您的文档目录的实际路径。

## 步骤 3：启用“KeepWithNext”选项
为了使表格保持连贯，防止其分裂到多个页面，我们需要为表格中除最后一行最后几段之外的每个段落启用“KeepWithNext”选项。使用以下代码：

```csharp
foreach(Cell cell in table.GetChildNodes(NodeType.Cell, true))
{
cell.EnsureMinimum();
foreach(Paragraph para in cell.Paragraphs)
if (!(cell.ParentRow.IsLastRow && para.IsEndOfCell))
para.ParagraphFormat.KeepWithNext = true;
}
```

这里我们循环遍历表格中的每个单元格，并为单元格中除表格最后一行的最后几段之外的每个段落启用“KeepWithNext”选项。

## 步骤 4：保存修改后的文档
最后，我们需要将修改后的文档与表格一起保存。使用以下代码：

```csharp
doc.Save(dataDir + "WorkingWithTables.KeepTableTogether.docx");
```

确保为输出文档指定正确的路径和文件名。

### 使用 Aspose.Words for .NET 实现“保持表格连贯”的示例源代码 

```csharp
	//文档目录的路径
	string dataDir = "YOUR DOCUMENT DIRECTORY";

	Document doc = new Document(dataDir + "Table spanning two pages.docx");
	Table table = (Table) doc.GetChild(NodeType.Table, 0, true);
	//我们需要为表格中的每个段落启用 KeepWithNext，以防止其跨页，
	//除了表格最后一行的最后几段之外。
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
在本教程中，我们学习了如何使用 Aspose.Words for .NET 将 Word 文档中的表格合并在一起。通过遵循本分步指南并实现提供的 C# 代码，您可以保持表格完整并防止其在文档中跨多页拆分。此功能使您可以更好地控制文档中表格的外观和布局。