---
title: 克隆完整表
linktitle: 克隆完整表
second_title: Aspose.Words 文档处理 API
description: 了解如何使用 Aspose.Words for .NET 将整个表格克隆到 Word 文档中。
type: docs
weight: 10
url: /zh/net/programming-with-tables/clone-complete-table/
---

在本教程中，我们将学习如何使用 Aspose.Words for .NET 将整个表格克隆到 Word 文档中。我们将按照分步指南来理解代码并实现此功能。在本教程结束时，您将能够以编程方式将表格克隆到 Word 文档中。

## 第 1 步：项目设置
1. 启动 Visual Studio 并创建一个新的 C# 项目。
2. 添加对 Aspose.Words for .NET 库的引用。

## 第 2 步：加载文档并访问表
要对表启动文字处理，我们需要加载包含该表的文档并访问它。按着这些次序：

```csharp
//文档目录的路径
string dataDir = "YOUR DOCUMENTS DIRECTORY";

//加载文档
Document doc = new Document(dataDir + "Tables.docx");

//访问数组
Table table = (Table)doc.GetChild(NodeType.Table, 0, true);
```

请务必将“您的文档目录”替换为文档目录的实际路径。

## 第 3 步：全阵列克隆
接下来，我们将克隆整个表格并将其插入到文档中原始表格之后。使用以下代码：

```csharp
//克隆数组
Table tableClone = (Table)table.Clone(true);

//将克隆的表格插入到文档中原始表格之后
table.ParentNode.InsertAfter(tableClone, table);

//在两个表格之间插入一个空段落
//否则它们将在保存时合并为一个（这是由于文档验证）
table.ParentNode.InsertAfter(new Paragraph(doc), table);
```

这里我们使用的是`Clone`方法创建数组的完整副本。然后我们使用`InsertAfter`将克隆的表格插入文档中原始表格之后。我们还在两个表之间添加一个空段落，以防止保存时它们被合并。

## 第四步：保存修改后的文档
最后，我们需要将修改后的文档与克隆的表一起保存。使用以下代码：

```csharp
//保存修改后的文档
doc.Save(dataDir + "WorkingWithTables.CloneCompleteTable.docx");
```

请务必为输出文档指定正确的路径和文件名。
  
### 使用 Aspose.Words for .NET 克隆完整表的示例源代码 

```csharp
	//文档目录的路径
	string dataDir = "YOUR DOCUMENT DIRECTORY";

	Document doc = new Document(dataDir + "Tables.docx");
	Table table = (Table) doc.GetChild(NodeType.Table, 0, true);
	//克隆表格并将其插入到文档中的原始表格之后。
	Table tableClone = (Table) table.Clone(true);
	table.ParentNode.InsertAfter(tableClone, table);
	//在两个表格之间插入一个空段落，
	//否则它们将在保存时合并为一个，这与文档验证有关。
	table.ParentNode.InsertAfter(new Paragraph(doc), table);
	doc.Save(dataDir + "WorkingWithTables.CloneCompleteTable.docx");
```

## 结论
在本教程中，我们学习了如何使用 Aspose.Words for .NET 将整个表格克隆到 Word 文档中。通过遵循本分步指南并实现提供的 C# 代码，您可以通过编程方式克隆 Word 文档中的表格。此功能允许您对数组执行高级操作以满足您的特定需求。