---
title: 在后续页面上重复行
linktitle: 在后续页面上重复行
second_title: Aspose.Words for .NET API 参考
description: 了解如何使用 Aspose.Words for .NET 在 Word 文档的后续页面上重复表格行。
type: docs
weight: 10
url: /zh/net/programming-with-tables/repeat-rows-on-subsequent-pages/
---

在本教程中，我们将学习如何使用 Aspose.Words for .NET 在 Word 文档的后续页面上重复表格的行。我们将按照分步指南来理解代码并实现此功能。在本教程结束时，您将能够指定在 Word 文档中表格的后续页面上重复的行。

## 第 1 步：项目设置
1. 启动 Visual Studio 并创建一个新的 C# 项目。
2. 添加对 Aspose.Words for .NET 库的引用。

## 第2步：创建文档并初始化文档生成器
要开始使用文档和文档生成器，请按照下列步骤操作：

```csharp
//文档目录的路径
string dataDir = "YOUR DOCUMENTS DIRECTORY";

//文档创建
Document doc = new Document();

//初始化文档生成器
DocumentBuilder builder = new DocumentBuilder(doc);
```

请务必将“您的文档目录”替换为文档目录的实际路径。

## 步骤 3：构建包含重复行的表
接下来，我们将构建一个在后续页面上包含重复行的表格。使用以下代码：

```csharp
//表的开头
builder. StartTable();

//第一行参数的配置（标题行）
builder.RowFormat.HeadingFormat = true;
builder.ParagraphFormat.Alignment = ParagraphAlignment.Center;
builder.CellFormat.Width = 100;

//插入第一行的第一个单元格
builder. InsertCell();
builder.Writeln("Header line 1");
builder. EndRow();

//插入第一行的第二个单元格
builder. InsertCell();
builder.Writeln("Header line 2");
builder. EndRow();

//配置以下几行参数
builder.CellFormat.Width = 50;
builder.ParagraphFormat.ClearFormatting();

//循环插入以下行中的单元格
for (int i = 0; i < 50; i++)
{
builder. InsertCell();
builder.RowFormat.HeadingFormat = false;
builder.Write("Text column 1");
builder. InsertCell();
builder.Write("Text column 2");
builder. EndRow();
}

//表尾
builder. EndTable();
```

这里我们使用文档构建器构建一个包含两个标题行和多个数据行的表格。这`RowFormat.HeadingFormat`参数用于标记应在后续页面上重复的标题行。

## 第四步：保存修改后的文档
终于美国了

  需要保存修改后的文档，并在表格的后续页面上重复标题行。使用以下代码：

```csharp
doc.Save(dataDir + "WorkingWithTables.RepeatRowsOnSubsequentPages.docx");
```

请务必为输出文档指定正确的路径和文件名。

### 使用 Aspose.Words for .NET 在后续页面上重复行的示例源代码 

```csharp
//文档目录的路径
string dataDir = "YOUR DOCUMENT DIRECTORY";

Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
builder.StartTable();
builder.RowFormat.HeadingFormat = true;
builder.ParagraphFormat.Alignment = ParagraphAlignment.Center;
builder.CellFormat.Width = 100;
builder.InsertCell();
builder.Writeln("Heading row 1");
builder.EndRow();
builder.InsertCell();
builder.Writeln("Heading row 2");
builder.EndRow();
builder.CellFormat.Width = 50;
builder.ParagraphFormat.ClearFormatting();
for (int i = 0; i < 50; i++)
{
	builder.InsertCell();
	builder.RowFormat.HeadingFormat = false;
	builder.Write("Column 1 Text");
	builder.InsertCell();
	builder.Write("Column 2 Text");
	builder.EndRow();
}
doc.Save(dataDir + "WorkingWithTables.RepeatRowsOnSubsequentPages.docx");
```

## 结论
在本教程中，我们学习了如何使用 Aspose.Words for .NET 在 Word 文档的后续页面上重复表格的行。通过遵循本分步指南并实现提供的 C# 代码，您可以根据您在 Word 文档中的特定需要指定要重复的行。