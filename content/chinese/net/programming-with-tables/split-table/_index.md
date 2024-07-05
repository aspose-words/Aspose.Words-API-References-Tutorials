---
title: 拆分表
linktitle: 拆分表
second_title: Aspose.Words 文档处理 API
description: 了解如何使用 Aspose.Words for .NET 拆分 Word 文档中的表格。
type: docs
weight: 10
url: /zh/net/programming-with-tables/split-table/
---

在本教程中，我们将学习如何使用 Aspose.Words for .NET 拆分 Word 文档中的表格。我们将按照分步指南来理解代码并实现此功能。在本教程结束时，您将能够从 Word 文档中的某一行拆分表格。

## 步骤 1：项目设置
1. 启动 Visual Studio 并创建一个新的 C# 项目。
2. 添加对 Aspose.Words for .NET 库的引用。

## 步骤 2：加载文档
要启动文档的文字处理，请按照以下步骤操作：

```csharp
//文档目录的路径
string dataDir = "YOUR DOCUMENTS DIRECTORY";

//加载文档
Document doc = new Document(dataDir + "Tables.docx");
```

请务必将“您的文档目录”替换为您的文档目录的实际路径，并提供正确的文件名。

## 步骤 3：划分表格
接下来我们将从某一行开始拆分表格。使用以下代码：

```csharp
//检索第一个表
Table firstTable = (Table)doc.GetChild(NodeType.Table, 0, true);

//确定表格的划分线
Row row = firstTable.Rows[2];

//为拆分表创建一个新的容器
Table table = (Table)firstTable.Clone(false);

//将容器插入到原表之后
firstTable.ParentNode.InsertAfter(table, firstTable);

//添加缓冲段落以保持表格之间的距离
firstTable.ParentNode.InsertAfter(new Paragraph(doc), firstTable);

//将原始表中的行移动到拆分表
Row currentRow;
do
{
currentRow = firstTable.LastRow;
table. PrependChild(currentRow);
} while (currentRow != row);
```

这里我们使用文档从文档节点检索第一个表。然后我们确定要从哪一行拆分表，在本例中是第三行（索引 2）。然后我们通过克隆原始表创建一个新容器，然后将其插入原始表之后。我们还添加了一个缓冲段落以保持两个表之间的距离。然后我们使用 do-while 循环将行从原始表移动到拆分表，直到到达指定的行。

## 步骤 4：保存修改后的文档
最后，我们需要保存

  使用拆分表修改的文档。使用以下代码：

```csharp
doc.Save(dataDir + "WorkingWithTables.SplitTable.docx");
```

确保为输出文档指定正确的路径和文件名。

### 使用 Aspose.Words for .NET 进行拆分表的示例源代码 

```csharp
//文档目录的路径
string dataDir = "YOUR DOCUMENT DIRECTORY";

Document doc = new Document(dataDir + "Tables.docx");
Table firstTable = (Table) doc.GetChild(NodeType.Table, 0, true);
//我们将在第三行（含第三行）处拆分表格。
Row row = firstTable.Rows[2];
//为拆分表创建一个新的容器。
Table table = (Table) firstTable.Clone(false);
//将容器插入原件后面。
firstTable.ParentNode.InsertAfter(table, firstTable);
//添加缓冲段落以确保表格保持分开。
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