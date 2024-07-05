---
title: 浮动表位置
linktitle: 浮动表位置
second_title: Aspose.Words 文档处理 API
description: 了解如何使用 Aspose.Words for .NET 将表格置于 Word 文档中的浮动位置。
type: docs
weight: 10
url: /zh/net/programming-with-tables/floating-table-position/
---

在本教程中，我们将学习如何使用 Aspose.Words for .NET 将表格定位在 Word 文档中的浮动位置。我们将按照分步指南来理解代码并实现此功能。在本教程结束时，您将能够以编程方式控制 Word 文档中浮动表格的位置和对齐方式。

## 步骤 1：项目设置
1. 启动 Visual Studio 并创建一个新的 C# 项目。
2. 添加对 Aspose.Words for .NET 库的引用。

## 第 2 步：加载文档并访问表格
要使用表格启动文字处理，我们需要加载包含该表格的文档并访问它。请按以下步骤操作：

```csharp
//文档目录的路径
string dataDir = "YOUR DOCUMENTS DIRECTORY";

//加载文档
Document doc = new Document(dataDir + "Table wrapped by text.docx");

//访问数组
Table table = doc.FirstSection.Body.Tables[0];
```

请务必将“您的文档目录”替换为您的文档目录的实际路径。此外，请确保文档包含将定位在浮动位置的表格。

## 步骤 3：定位浮板
接下来，我们将使用 Aspose.Words for .NET 提供的属性将表格置于浮动位置。使用以下代码：

```csharp
//定位浮动表
table. AbsoluteHorizontalDistance = 10;
table. RelativeVerticalAlignment = VerticalAlignment. Center;
```

在这里我们使用`AbsoluteHorizontalDistance`属性来设置表格与页面左边缘的绝对水平距离。我们还使用`RelativeVerticalAlignment`属性来设置表与周围内容的相对垂直对齐方式。

## 步骤 4：保存修改后的文档
最后，我们需要保存修改后的文档，并将表格置于浮动位置。使用以下代码：

```csharp
//保存修改后的文档
doc.Save(dataDir + "WorkingWithTables.FloatingTablePosition.docx");
```

确保为输出文档指定正确的路径和文件名。

### 使用 Aspose.Words for .NET 的浮动表格位置示例源代码 

```csharp
	//文档目录的路径
	string dataDir = "YOUR DOCUMENT DIRECTORY";

	Document doc = new Document(dataDir + "Table wrapped by text.docx");
	Table table = doc.FirstSection.Body.Tables[0];
	table.AbsoluteHorizontalDistance = 10;
	table.RelativeVerticalAlignment = VerticalAlignment.Center;
	doc.Save(dataDir + "WorkingWithTables.FloatingTablePosition.docx");
```

## 结论
在本教程中，我们学习了如何使用 Aspose.Words for .NET 将表格定位在 Word 文档中的浮动位置。通过遵循本分步指南并实现提供的 C# 代码，您可以以编程方式控制 Word 文档中浮动表格的位置和对齐方式。