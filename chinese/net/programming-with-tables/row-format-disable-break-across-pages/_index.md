---
title: 行格式禁用跨页拆分
linktitle: 行格式禁用跨页拆分
second_title: Aspose.Words for .NET API 参考
description: 了解如何使用 Aspose.Words for .NET 为 Word 文档中的多页表格禁用换行符。
type: docs
weight: 10
url: /zh/net/programming-with-tables/row-format-disable-break-across-pages/
---

在本教程中，我们将学习如何使用 Aspose.Words for .NET 禁用 Word 文档中多页表格的换行符。我们将按照逐步指南来理解代码并实现此功能。在本教程结束时，您将能够为 Word 文档中表格中的所有行禁用换行。

## 第 1 步：项目设置
1. 启动 Visual Studio 并创建一个新的 C# 项目。
2. 添加对 Aspose.Words for .NET 库的引用。

## 第 2 步：装入文档
要开始使用该文档，请执行以下步骤：

```csharp
//文档目录的路径
string dataDir = "YOUR DOCUMENTS DIRECTORY";

//装入文档
Document doc = new Document(dataDir + "Table spanning two pages.docx");
```

请务必将“您的文档目录”替换为文档目录的实际路径并提供正确的文件名。

## 第 3 步：禁用表格换行符
接下来，我们将禁用表中所有行的换行。使用以下代码：

```csharp
//检索表
Table table = (Table) doc.GetChild(NodeType.Table, 0, true);

//禁用表中所有行的换行符
foreach(Row row in table.Rows)
row.RowFormat.AllowBreakAcrossPages = false;
```

这里我们使用文档来获取第一个表，然后使用 foreach 循环遍历表中的所有行。在循环内部，我们通过设置`RowFormat.AllowBreakAcrossPages`财产给`false`.

## 第 4 步：保存修改后的文档
最后，我们需要在禁用表格换行符的情况下保存修改后的文档。使用以下代码：

```csharp
doc.Save(dataDir + "WorkingWithTables.RowFormatDisableBreakAcrossPages.docx");
```

请务必为输出文档指定正确的路径和文件名。

### 使用 Aspose.Words for .NET 的行格式禁用跨页分隔的示例源代码 

```csharp
//文档目录的路径
string dataDir = "YOUR DOCUMENT DIRECTORY";

Document doc = new Document(dataDir + "Table spanning two pages.docx");
Table table = (Table) doc.GetChild(NodeType.Table, 0, true);
//禁用表格中所有行的分页。
foreach (Row row in table.Rows)
	row.RowFormat.AllowBreakAcrossPages = false;
doc.Save(dataDir + "WorkingWithTables.RowFormatDisableBreakAcrossPages.docx");
```

## 结论
在本教程中，我们学习了如何使用 Aspose.Words for .NET 禁用 Word 文档中多页表格的换行符。通过遵循此分步指南并实施提供的 C# 代码，您可以将此禁用应用于 Word 文档中的表格。