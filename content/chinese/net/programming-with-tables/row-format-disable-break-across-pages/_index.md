---
title: 行格式禁用跨页拆分
linktitle: 行格式禁用跨页拆分
second_title: Aspose.Words 文档处理 API
description: 了解如何使用 Aspose.Words for .NET 禁用 Word 文档中跨多页表格的换行符。
type: docs
weight: 10
url: /zh/net/programming-with-tables/row-format-disable-break-across-pages/
---

在本教程中，我们将学习如何使用 Aspose.Words for .NET 禁用 Word 文档中多页表的换行符。我们将按照分步指南来理解代码并实现此功能。在本教程结束时，您将能够禁用 Word 文档中表格中所有行的换行符。

## 步骤 1：项目设置
1. 启动 Visual Studio 并创建一个新的 C# 项目。
2. 添加对 Aspose.Words for .NET 库的引用。

## 步骤 2：加载文档
要启动文档的文字处理，请按照以下步骤操作：

```csharp
//文档目录的路径
string dataDir = "YOUR DOCUMENTS DIRECTORY";

//加载文档
Document doc = new Document(dataDir + "Table spanning two pages.docx");
```

请务必将“您的文档目录”替换为您的文档目录的实际路径，并提供正确的文件名。

## 步骤 3：禁用表格行分隔符
接下来，我们将禁用表中的所有行的换行。使用以下代码：

```csharp
//检索表
Table table = (Table) doc.GetChild(NodeType.Table, 0, true);

//禁用表格中所有行的换行
foreach(Row row in table.Rows)
row.RowFormat.AllowBreakAcrossPages = false;
```

这里我们使用文档获取第一个表，然后使用 foreach 循环遍历表中的所有行。在循环中，我们通过设置`RowFormat.AllowBreakAcrossPages`财产`false`.

## 步骤 4：保存修改后的文档
最后，我们需要保存修改后的文档并禁用表格换行符。使用以下代码：

```csharp
doc.Save(dataDir + "WorkingWithTables.RowFormatDisableBreakAcrossPages.docx");
```

确保为输出文档指定正确的路径和文件名。

### 使用 Aspose.Words for .NET 禁用跨页行格式的示例源代码 

```csharp
//文档目录的路径
string dataDir = "YOUR DOCUMENT DIRECTORY";

Document doc = new Document(dataDir + "Table spanning two pages.docx");
Table table = (Table) doc.GetChild(NodeType.Table, 0, true);
//禁用表格中所有行的跨页分页。
foreach (Row row in table.Rows)
	row.RowFormat.AllowBreakAcrossPages = false;
doc.Save(dataDir + "WorkingWithTables.RowFormatDisableBreakAcrossPages.docx");
```

## 结论
在本教程中，我们学习了如何使用 Aspose.Words for .NET 禁用 Word 文档中多页表的换行符。通过遵循本分步指南并实现提供的 C# 代码，您可以将此禁用功能应用于 Word 文档中的表格。