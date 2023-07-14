---
title: 建表
linktitle: 建表
second_title: Aspose.Words 文档处理 API
description: 了解如何使用 Aspose.Words for .NET 在 Word 文档中构建表格。
type: docs
weight: 10
url: /zh/net/add-content-using-documentbuilder/build-table/
---

在本分步教程中，您将学习如何使用 Aspose.Words for .NET 在 Word 文档中构建表格。我们将指导您完成整个过程，并为您提供必要的 C# 代码片段。在本指南结束时，您将能够使用 DocumentBuilder 类创建具有自定义格式和内容的表格。

## 先决条件
在我们开始之前，请确保您满足以下先决条件：
- Aspose.Words for .NET 库安装在您的系统上。

## 第 1 步：创建一个新文档
首先，使用 Document 类创建一个新文档：

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
```

## 第 2 步：启动表格
接下来，使用 DocumentBuilder 类的 StartTable 方法开始建表：

```csharp
Table table = builder.StartTable();
```

## 第 3 步：插入单元格并添加内容
现在，您可以使用 DocumentBuilder 类的 InsertCell 和 Write 方法将单元格插入表中并向其中添加内容。根据需要自定义单元格格式：

```csharp
builder.InsertCell();
builder.CellFormat.VerticalAlignment = CellVerticalAlignment.Center;
builder.Write("This is row 1 cell 1");

builder.InsertCell();
builder.Write("This is row 1 cell 2");
```

## 第四步：结束行
将内容添加到第一行的单元格后，使用 DocumentBuilder 类的 EndRow 方法结束该行：

```csharp
builder.EndRow();
```

## 第 5 步：自定义行格式
您可以通过设置 RowFormat 和 CellFormat 对象的属性来自定义行的格式：

```csharp
builder.InsertCell();
builder.RowFormat.Height = 100;
builder.RowFormat.HeightRule = HeightRule.Exactly;
builder.CellFormat.Orientation = TextOrientation.Upward;
builder.Writeln("This is row 2 cell 1");

builder.InsertCell();
builder.CellFormat.Orientation = TextOrientation.Downward;
builder.Writeln("This is row 2 cell 2");
```

## 第六步：结束桌子
要完成表格，请使用 DocumentBuilder 类的 EndTable 方法：

```csharp
builder.EndTable();
```

### 使用 Aspose.Words for .NET 构建表格的示例源代码
以下是使用 Aspose.Words for .NET 构建表格的完整源代码：

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

Table table = builder.StartTable();
builder.InsertCell();
table.AutoFit(AutoFitBehavior.FixedColumnWidths);

builder.CellFormat.VerticalAlignment = CellVerticalAlignment.Center;
builder.Write("This is row 1 cell 1");

builder.InsertCell();
builder.Write("This is row 1 cell 2");

builder.EndRow();

builder.InsertCell();

builder.RowFormat.Height = 100;
builder.RowFormat.HeightRule = HeightRule.Exactly;
builder.CellFormat.Orientation = TextOrientation.Upward;
builder.Writeln("This is row 2 cell 1");

builder.InsertCell();
builder.CellFormat.Orientation = TextOrientation.Downward;
builder.Writeln("This is row 2 cell 2");

builder.EndRow();
builder.EndTable();

doc.Save(ArtifactsDir + "AddContentUsingDocumentBuilder.BuildTable.docx");
```

## 结论
恭喜！您已成功学习如何使用 Aspose.Words for .NET 在 Word 文档中构建表格。通过遵循分步指南并利用提供的源代码，您现在可以创建具有自定义格式的表格。