---
title: 导出到 Markdown 并对齐表格内容
linktitle: 导出到 Markdown 并对齐表格内容
second_title: Aspose.Words 文档处理 API
description: 了解如何使用 Aspose.Words for .NET 将具有不同对齐方式的表格内容导出到 Markdown 文件。
type: docs
weight: 10
url: /zh/net/programming-with-markdownsaveoptions/export-into-markdown-with-table-content-alignment/
---
以下是分步指南，用于解释以下 C# 源代码，该代码可帮助使用 .NET 的 Aspose.Words 库将内容导出到具有表格内容对齐的 Markdown 文件。在使用此代码之前，请确保已在项目中包含 Aspose.Words 库。

## 步骤 1：设置文档目录路径

```csharp
//文档目录的路径。
string dataDir = "YOUR_DIRECTORY_OF_DOCUMENTS";
```

确保指定将保存已编辑文档的文档目录的正确路径。

## 步骤 2：创建文档和文档生成器

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
```

在这里我们创建一个实例`Document`类和实例`DocumentBuilder`该类允许我们操作文档并添加元素。

## 步骤 3：在表格中插入具有不同段落对齐方式的单元格

```csharp
builder. InsertCell();
builder.ParagraphFormat.Alignment = ParagraphAlignment.Right;
builder.Write("Cell1");
builder. InsertCell();
builder.ParagraphFormat.Alignment = ParagraphAlignment.Center;
builder.Write("Cell2");
```

我们使用文档生成器在表中插入单元格，并为每个单元格设置不同的段落对齐方式。

## 步骤4：设置Markdown导出选项并保存修改后的文档

```csharp
MarkdownSaveOptions saveOptions = new MarkdownSaveOptions
{
     TableContentAlignment = TableContentAlignment.Left
};
doc.Save(dataDir + "Content_table_left_alignment.md", saveOptions);

saveOptions.TableContentAlignment = TableContentAlignment.Right;
doc.Save(dataDir + "Content_table_right_alignment.md", saveOptions);

saveOptions.TableContentAlignment = TableContentAlignment.Center;
doc.Save(dataDir + "Content_table_alignment_center.md", saveOptions);

saveOptions.TableContentAlignment = TableContentAlignment.Auto;
doc.Save(dataDir + "Content_table_auto_alignment.md", saveOptions);
```

我们设置不同表格内容对齐方式的 Markdown 导出选项，然后使用每个对齐选项保存修改后的文档。

### 使用 Aspose.Words for .NET 将表格内容对齐导出到 Markdown 的示例源代码

```csharp

            
	//文档目录的路径。
    string dataDir = "YOUR DOCUMENT DIRECTORY";
	
	Document doc = new Document();
	DocumentBuilder builder = new DocumentBuilder(doc);

	builder.InsertCell();
	builder.ParagraphFormat.Alignment = ParagraphAlignment.Right;
	builder.Write("Cell1");
	builder.InsertCell();
	builder.ParagraphFormat.Alignment = ParagraphAlignment.Center;
	builder.Write("Cell2");

	//使表格内的所有段落对齐。
	MarkdownSaveOptions saveOptions = new MarkdownSaveOptions
	{
		TableContentAlignment = TableContentAlignment.Left
	};
	doc.Save(ArtifactsDir + "WorkingWithMarkdownSaveOptions.LeftTableContentAlignment.md", saveOptions);

	saveOptions.TableContentAlignment = TableContentAlignment.Right;
	doc.Save(ArtifactsDir + "WorkingWithMarkdownSaveOptions.RightTableContentAlignment.md", saveOptions);

	saveOptions.TableContentAlignment = TableContentAlignment.Center;
	doc.Save(ArtifactsDir + "WorkingWithMarkdownSaveOptions.CenterTableContentAlignment.md", saveOptions);

	//在这种情况下，对齐将取自相应表格列中的第一个段落。
	saveOptions.TableContentAlignment = TableContentAlignment.Auto;
	
	//保存修改后的文档
	doc.Save(dataDir + "WorkingWithMarkdownSaveOptions.AutoTableContentAlignment.md", saveOptions);
            
        
```
