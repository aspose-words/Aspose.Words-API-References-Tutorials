---
title: 分割表
linktitle: 分割表
second_title: Aspose.Words 文档处理 API
description: 了解如何使用 Aspose.Words for .NET 拆分 Word 文档中的表格。
type: docs
weight: 10
url: /zh/net/programming-with-tables/split-table/
---

在本教程中，我们将学习如何使用 Aspose.Words for .NET 拆分 Word 文档中的表格。我们将按照分步指南来理解代码并实现此功能。在本教程结束时，您将能够从 Word 文档中的特定行拆分表格。

## 第 1 步：项目设置
1. 启动 Visual Studio 并创建一个新的 C# 项目。
2. 添加对 Aspose.Words for .NET 库的引用。

## 第 2 步：加载文档
要启动文档的文字处理，请按照下列步骤操作：

```csharp
//文档目录的路径
string dataDir = "YOUR DOCUMENTS DIRECTORY";

//加载文档
Document doc = new Document(dataDir + "Tables.docx");
```

请务必将“您的文档目录”替换为文档目录的实际路径，并提供正确的文件名。

## 第三步：划分表格
接下来我们将从某一行拆分表。使用以下代码：

```csharp
//检索第一个表
Table firstTable = (Table)doc.GetChild(NodeType.Table, 0, true);

//确定表格的分割线
Row row = firstTable.Rows[2];

//为拆分表创建一个新容器
Table table = (Table)firstTable.Clone(false);

//将容器插入到原始表格之后
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

这里我们使用文档从文档节点检索第一个表。然后我们确定要从中拆分表的行，在本例中为第三行（索引 2）。然后，我们通过克隆原始表来创建一个新容器，然后将其插入到原始表之后。我们还添加了一个缓冲段落来保持两个表格之间的距离。然后，我们使用 do-while 循环将行从原始表移动到拆分表，直到到达指定的行。

## 第四步：保存修改后的文档
最后，我们需要保存

  使用拆分表修改的文档。使用以下代码：

```csharp
doc.Save(dataDir + "WorkingWithTables.SplitTable.docx");
```

请务必为输出文档指定正确的路径和文件名。

### 使用 Aspose.Words for .NET 的分割表示例源代码 

```csharp
//文档目录的路径
string dataDir = "YOUR DOCUMENT DIRECTORY";

Document doc = new Document(dataDir + "Tables.docx");
Table firstTable = (Table) doc.GetChild(NodeType.Table, 0, true);
//我们将在第三行（含）处拆分表格。
Row row = firstTable.Rows[2];
//为拆分表创建一个新容器。
Table table = (Table) firstTable.Clone(false);
//将容器插入原件之后。
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
在本教程中，我们学习了如何使用 Aspose.Words for .NET 拆分 Word 文档中的表格。通过遵循本分步指南并实现提供的 C# 代码，您可以轻松地从 Word 文档中的某一行拆分表格。