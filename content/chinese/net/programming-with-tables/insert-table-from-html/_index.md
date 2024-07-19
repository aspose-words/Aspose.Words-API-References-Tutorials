---
title: 从 HTML 插入表格
linktitle: 从 HTML 插入表格
second_title: Aspose.Words 文档处理 API
description: 了解如何使用 Aspose.Words for .NET 将 HTML 表格插入 Word 文档。
type: docs
weight: 10
url: /zh/net/programming-with-tables/insert-table-from-html/
---

在本教程中，我们将学习如何使用 Aspose.Words for .NET 将表格从 HTML 插入 Word 文档。我们将按照分步指南来理解代码并实现此功能。在本教程结束时，您将能够以编程方式将表格从 HTML 插入 Word 文档。

## 步骤 1：项目设置
1. 启动 Visual Studio 并创建一个新的 C# 项目。
2. 添加对 Aspose.Words for .NET 库的引用。

## 第 2 步：创建文档并初始化文档生成器
要使用文档和文档生成器启动文字处理，请按照以下步骤操作：

```csharp
//文档目录的路径
string dataDir = "YOUR DOCUMENTS DIRECTORY";

//文档创建
Document doc = new Document();

//初始化文档生成器
DocumentBuilder builder = new DocumentBuilder(doc);
```

确保将“YOUR DOCUMENTS DIRECTORY”替换为您的文档目录的实际路径。

## 步骤 3：从 HTML 插入表格
接下来，我们将使用 HTML 代码将表格插入文档。使用以下代码：

```csharp
builder.InsertHtml("<table>" +
"<tr>" +
"<td>Line 1, Cell 1</td>" +
"<td>Line 1, Cell 2</td>" +
"</tr>" +
"<tr>" +
"<td>Line 2, Cell 1</td>" +
"<td>Line 2, Cell 2</td>" +
"</tr>" +
"</table>");
```

在这里我们使用`InsertHtml`文档生成器的方法插入包含表格的 HTML。指定的 HTML 会创建一个包含两行、每行两个单元格的表格。您可以根据需要修改 HTML 代码来自定义表格的内容。

## 步骤 4：保存修改后的文档
最后，我们需要保存修改后的文档，其中包含从 HTML 插入的表格。使用以下代码：

```csharp
doc.Save(dataDir + "WorkingWithTables.InsertTableFromHtml.docx");
```

确保为输出文档指定正确的路径和文件名。

### 使用 Aspose.Words for .NET 从 Html 插入表格的示例源代码 

```csharp
	//文档目录的路径
	string dataDir = "YOUR DOCUMENT DIRECTORY";

	Document doc = new Document();
	DocumentBuilder builder = new DocumentBuilder(doc);
	//请注意，AutoFitSettings 不适用于从 HTML 插入的表格。
	builder.InsertHtml("<table>" +
					   "<tr>" +
					   "<td>Row 1, Cell 1</td>" +
					   "<td>Row 1, Cell 2</td>" +
					   "</tr>" +
					   "<tr>" +
					   "<td>Row 2, Cell 2</td>" +
					   "<td>Row 2, Cell 2</td>" +
					   "</tr>" +
					   "</table>");
	doc.Save(dataDir + "WorkingWithTables.InsertTableFromHtml.docx");
```

## 结论
在本教程中，我们学习了如何使用 Aspose.Words for .NET 将表格从 HTML 插入 Word 文档。通过遵循本分步指南并实现提供的 C# 代码，您可以以编程方式将表格从 HTML 插入 Word 文档。此功能允许您将表格数据从 HTML 源转换并导入到 Word 文档中。
