---
title: 检索首选宽度类型
linktitle: 检索首选宽度类型
second_title: Aspose.Words for .NET API 参考
description: 了解如何使用 Aspose.Words for .NET 检索 Word 表格中单元格的类型和首选宽度值。
type: docs
weight: 10
url: /zh/net/programming-with-tables/retrieve-preferred-width-type/
---

在本教程中，我们将学习如何使用 Aspose.Words for .NET 从 Word 文档的表格单元格中检索首选宽度类型及其值。我们将按照分步指南来理解代码并实现此功能。在本教程结束时，您将能够检索 Word 文档表格中特定单元格的首选宽度类型（绝对、相对或自动）及其值。

## 第 1 步：项目设置
1. 启动 Visual Studio 并创建一个新的 C# 项目。
2. 添加对 Aspose.Words for .NET 库的引用。

## 第 2 步：加载文档
要开始使用该文档，请按照下列步骤操作：

```csharp
//文档目录的路径
string dataDir = "YOUR DOCUMENTS DIRECTORY";

//加载文档
Document doc = new Document(dataDir + "Tables.docx");
```

请务必将“您的文档目录”替换为文档目录的实际路径，并提供正确的文件名。

## 步骤 3：检索首选宽度类型和值
接下来，我们将检索特定表格单元格的首选宽度类型及其值。使用以下代码：

```csharp
//检索表
Table table = (Table) doc.GetChild(NodeType.Table, 0, true);

//激活自动工作台调整
table. AllowAutoFit = true;

//检索第一行的第一个单元格
Cell firstCell = table.FirstRow.FirstCell;

//检索首选宽度类型及其值
PreferredWidthType type = firstCell.CellFormat.PreferredWidth.Type;
double value = firstCell.CellFormat.PreferredWidth.Value;
```

这里我们使用文档来获取第一个表格，然后我们启用自动表格匹配`AllowAutoFit`财产。然后我们检索表格第一行的第一个单元格。从此单元格中，我们可以使用以下命令检索首选宽度类型`PreferredWidth.Type`财产及其价值`PreferredWidth.Value`财产。

### 使用 Aspose.Words for .NET 检索首选宽度类型的示例源代码 

```csharp
//文档目录的路径
string dataDir = "YOUR DOCUMENT DIRECTORY";

Document doc = new Document(dataDir + "Tables.docx");
Table table = (Table) doc.GetChild(NodeType.Table, 0, true);
table.AllowAutoFit = true;
Cell firstCell = table.FirstRow.FirstCell;
PreferredWidthType type = firstCell.CellFormat.PreferredWidth.Type;
double value = firstCell.CellFormat.PreferredWidth.Value;
```

## 结论
在本教程中，我们学习了如何使用 Aspose.Words for .NET 从 Word 文档中的表格单元格检索首选宽度类型及其值。通过遵循此分步指南并实施提供的 C# 代码，您可以检索 Word 文档表格中特定单元格的此信息。