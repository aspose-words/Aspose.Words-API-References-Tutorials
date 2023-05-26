---
title: 拆分表
linktitle: 拆分表
second_title: Aspose.Words for .NET API 参考
description: 了解如何使用 Aspose.Words for .NET 拆分 Word 文档中的表格。
type: docs
weight: 10
url: /zh/net/programming-with-tables/split-table/
---

在本教程中，我们将学习如何使用 Aspose.Words for .NET 在 Word 文档中拆分表格。我们将按照逐步指南来理解代码并实现此功能。在本教程结束时，您将能够从 Word 文档中的特定行拆分表格。

## 第 1 步：项目设置
1. 启动 Visual Studio 并创建一个新的 C# 项目。
2. 添加对 Aspose.Words for .NET 库的引用。

## 第 2 步：装入文档
要开始使用该文档，请执行以下步骤：

```csharp
//文档目录的路径
string dataDir = "YOUR DOCUMENTS DIRECTORY";

//装入文档
Document doc = new Document(dataDir + "Tables.docx");
```

请务必将“您的文档目录”替换为文档目录的实际路径并提供正确的文件名。

## 第三步：划分表格
接下来我们将从某一行拆分表格。使用以下代码：

```csharp
//检索第一个表
Table firstTable = (Table)doc.GetChild(NodeType.Table, 0, true);

//确定表格的分界线
Row row = firstTable.Rows[2];

//为拆分表创建一个新容器
Table table = (Table)firstTable.Clone(false);

//在原表后插入容器
firstTable.ParentNode.InsertAfter(table, firstTable);

//添加缓冲段落以保持表格之间的距离
firstTable.ParentNode.InsertAfter(new Paragraph(doc), firstTable);

//将行从原始表移动到拆分表
Row currentRow;
do
{
currentRow = firstTable.LastRow;
table. PrependChild(currentRow);
} while (currentRow != row);
```

这里我们使用文档从文档节点中检索第一个表。然后我们确定要从中拆分表的行，在本例中是第三行（索引 2）。然后我们通过克隆原始表来创建一个新容器，然后将其插入到原始表之后。我们还添加了一个缓冲段落来保持两个表之间的距离。然后我们使用 do-while 循环将行从原始表移动到拆分表，直到我们到达指定的行。

## 第 4 步：保存修改后的文档
最后，我们需要保存

  使用拆分表修改的文档。使用以下代码：

```csharp
doc.Save(dataDir + "WorkingWithTables.SplitTable.docx");
```

请务必为输出文档指定正确的路径和文件名。

### 使用 Aspose.Words for .NET 的拆分表示例源代码 

```csharp
//文档目录的路径
string dataDir = "YOUR DOCUMENT DIRECTORY";

Document doc = new Document(dataDir + "Tables.docx");
Table firstTable = (Table) doc.GetChild(NodeType.Table, 0, true);
//我们将在第三行（含）拆分表格。
Row row = firstTable.Rows[2];
//为拆分表创建一个新容器。
Table table = (Table) firstTable.Clone(false);
//在原件之后插入容器。
firstTable.ParentNode.InsertAfter(table, firstTable);
//添加一个缓冲段落以确保表格保持分开。
firstTable.ParentNode.InsertAfter(new Paragraph(doc), firstTable);
Row currentRow;
do
{
	currentRow = firstTable.LastRow;
	table.PrependChild(currentRow);
} while (currentRow != row);
doc.Save(dataDir + "WorkingWithTables.SplitTable.docx");
```

## 结论
在本教程中，我们学习了如何使用 Aspose.Words for .NET 在 Word 文档中拆分表格。通过遵循此分步指南并实施提供的 C# 代码，您可以轻松地从 Word 文档中的特定行拆分表格。