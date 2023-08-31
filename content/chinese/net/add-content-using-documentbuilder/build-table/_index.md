---
title: 在Word文档中构建表格
linktitle: 在Word文档中构建表格
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

### Word文档中建表常见问题解答

#### 问：什么是 Aspose.Words for .NET？

答：Aspose.Words for .NET 是一个功能强大的文档处理库，允许开发人员在 .NET 应用程序中以编程方式创建、读取、编辑和转换 Microsoft Word 文档。它提供了广泛的处理 Word 文档的功能，例如文本操作、表格创建、文档保护、格式设置等。

#### 问：如何使用 Aspose.Words for .NET 在 Word 文档中构建表格？

答：要使用 Aspose.Words for .NET 在 Word 文档中构建表格，您可以按照以下步骤操作：
1. 创建一个新实例`Document`类和一个`DocumentBuilder`目的。
2. 使用`StartTable`的方法`DocumentBuilder`类开始建表。
3. 将单元格插入表格并使用`InsertCell`和`Write`的方法`DocumentBuilder`班级。
4. 使用以下命令结束该行`EndRow`的方法`DocumentBuilder`班级。
5. 通过设置行的属性来自定义行格式`RowFormat`和`CellFormat`对象。
6. 使用结束表`EndTable`的方法`DocumentBuilder`班级。
7. 保存文档。

#### 问：如何自定义表格及其单元格的格式？

答：您可以通过设置表格的各种属性来自定义表格及其单元格的格式。`RowFormat`和`CellFormat`对象。例如，您可以调整单元格对齐方式、垂直和水平文本方向、单元格高度、行高等。通过使用这些属性，您可以获得表及其内容所需的外观。

#### 问：我可以使用合并单元格和其他高级功能构建复杂的表格吗？

答：是的，Aspose.Words for .NET 提供了构建复杂表格的高级功能，包括对合并单元格、嵌套表格和复杂表格布局的支持。您可以使用`MergeCells`合并单元格的方法，`StartTable`方法创建嵌套表，以及其他方法来实现所需的表结构。

#### 问：Aspose.Words for .NET 是否与不同的 Word 文档格式兼容？

答：是的，Aspose.Words for .NET 与各种 Word 文档格式兼容，包括 DOC、DOCX、RTF 等。它支持传统格式 (DOC) 和现代基于 XML 的格式 (DOCX)，并允许您毫无问题地处理不同格式的文档。

#### 问：在哪里可以找到有关 Aspose.Words for .NET 的更多信息和文档？

答：您可以在以下位置找到全面的文档和代码示例[API参考](https://reference.aspose.com/words/net/)。该文档将提供有关该库的功能以及如何在 .NET 应用程序中使用它们的详细信息。