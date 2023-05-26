---
title: 创建页眉页脚
linktitle: 创建页眉页脚
second_title: Aspose.Words for .NET API 参考
description: 了解如何使用 Aspose.Words for .NET 在您的 Word 文档中创建页眉和页脚。为每个页面自定义页眉和页脚。
type: docs
weight: 10
url: /zh/net/working-with-headers-and-footers/create-header-footer/
---

这是一个分步指南，用于解释以下使用 Aspose.Words for .NET 功能创建页眉和页脚的 C# 源代码。在使用此代码之前，请确保您已将 Aspose.Words 库包含在您的项目中。

## 第一步：设置文档目录路径

```csharp
//文档目录的路径。
string dataDir = "YOUR_DIRECTORY_OF_DOCUMENTS";
```

请务必指定保存已编辑文档的文档目录的正确路径。

## 第 2 步：创建文档和文档生成器

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
```

这里我们创建一个实例`Document`类和一个实例`DocumentBuilder`允许我们操作文档和添加元素的类。

## 第三步：设置页面参数和第一个页眉

```csharp
Section currentSection = builder.CurrentSection;
PageSetup pageSetup = currentSection.PageSetup;

//指定我们是否希望第一页的页眉/页脚与其他页面不同。
//您还可以使用 PageSetup.OddAndEvenPagesHeaderFooter 属性来指定
//奇数页和偶数页的不同页眉/页脚。
pageSetup.DifferentFirstPageHeaderFooter = true;
pageSetup.HeaderDistance = 20;

builder.MoveToHeaderFooter(HeaderFooterType.HeaderFirst);
builder.ParagraphFormat.Alignment = ParagraphAlignment.Center;

builder.Font.Name = "Arial";
builder.Font.Bold = true;
builder.Font.Size = 14;

builder.Write("Aspose.Words - Creating Headers/Footers - Title Page.");

pageSetup.HeaderDistance = 20;
builder. MoveToHeaderFooter(HeaderFooterType.HeaderPrimary);
```

我们设置页面参数，包括页眉距离，然后移动到主页眉（`HeaderPrimary`).我们使用文档生成器来添加文本和格式化标题。

## 第 4 步：在主标题中插入图像和文本

```csharp
builder.InsertImage(ImagesDir + "Graphics Interchange Format.gif", RelativeHorizontalPosition.Page, 10,
     RelativeVerticalPosition.Page, 10, 50, 50, WrapType.Through);

builder.ParagraphFormat.Alignment = ParagraphAlignment.Right;

builder.Write("Aspose.Words - Building headers/footers.");

builder. MoveToHeaderFooter(HeaderFooterType.FooterPrimary);
```

我们使用文档生成器在主标题的左上角插入一个图像，然后我们添加一些右对齐的文本。

## 第 5 步：在主页脚中插入表格

```csharp
builder.StartTable();

builder.CellFormat.ClearFormatting();

builder.InsertCell();

builder.CellFormat.PreferredWidth = PreferredWidth.FromPercent(100 / 3);

builder.Write("Page ");
builder.InsertField("PAGE", "");
builder.Write(" of ");
builder.InsertField("NUMPAGES", "");

builder.CurrentParagraph.ParagraphFormat.Alignment = ParagraphAlignment.Left;

builder.InsertCell();

builder.CellFormat.PreferredWidth = PreferredWidth.FromPercent(100 * 2 / 3);

builder.Write("(C) 2001 Aspose Pty Ltd. All rights reserved.");

builder.CurrentParagraph.ParagraphFormat.Alignment = ParagraphAlignment.Right;

builder.EndRow();
builder.EndTable();

builder.MoveToDocumentEnd();
```

## 第 6 步：添加新页面并设置页眉/页脚

```csharp
builder. InsertBreak(BreakType.PageBreak);
builder.InsertBreak(BreakType.SectionBreakNewPage);

currentSection = builder. CurrentSection;
pageSetup = currentSection.PageSetup;
pageSetup.Orientation = Orientation.Landscape;
//本节的第一页不需要不同的页眉/页脚，我们只需要文档中的一个标题页，
//并且此页面的页眉/页脚已在上一节中定义。
pageSetup.DifferentFirstPageHeaderFooter = false;

//本节默认显示上一节的页眉/页脚，调用 currentSection.HeadersFooters.LinkToPrevious(false) 断开此链接，
//新部分的页面宽度不同，因此我们需要为页脚表格设置不同的单元格宽度。
currentSection.HeadersFooters.LinkToPrevious(false);

//如果我们想为本节使用已经存在的页眉/页脚，
//但有一些小的变化，复制页眉/页脚可能是有意义的
//从上一节开始，并在我们需要的地方应用必要的更改。
CopyHeadersFootersFromPreviousSection(currentSection);

HeaderFooter primaryFooter = currentSection.HeadersFooters[HeaderFooterType.FooterPrimary];

Row row = primaryFooter.Tables[0].FirstRow;
row.FirstCell.CellFormat.PreferredWidth = PreferredWidth.FromPercent(100 / 3);
row.LastCell.CellFormat.PreferredWidth = PreferredWidth.FromPercent(100 * 2 / 3);

//保存文件
doc.Save(dataDir + "WorkingWithHeadersAndFooters.CreateHeaderFooter.docx");
```

我们添加一个分页符和一个分节符以创建一个新页面，其中主要页眉/页脚将可见。我们为新部分设置参数，然后使用`CopyHeadersFootersFromPreviousSection`从上一节复制页眉/页脚的方法。最后，我们为主页脚表格设置适当的单元格宽度并保存文档。

### 使用 Aspose.Words for .NET 创建页眉和页脚的示例源代码

```csharp
	//文档目录的路径。
	string dataDir = "YOUR_DIRECTORY_OF_DOCUMENTS";
	
	Document doc = new Document();
	DocumentBuilder builder = new DocumentBuilder(doc);

	Section currentSection = builder.CurrentSection;
	PageSetup pageSetup = currentSection.PageSetup;
	//指定我们是否希望第一页的页眉/页脚与其他页面不同。
	//您还可以使用 PageSetup.OddAndEvenPagesHeaderFooter 属性来指定
	//奇数页和偶数页的不同页眉/页脚。
	pageSetup.DifferentFirstPageHeaderFooter = true;
	pageSetup.HeaderDistance = 20;

	builder.MoveToHeaderFooter(HeaderFooterType.HeaderFirst);
	builder.ParagraphFormat.Alignment = ParagraphAlignment.Center;

	builder.Font.Name = "Arial";
	builder.Font.Bold = true;
	builder.Font.Size = 14;

	builder.Write("Aspose.Words Header/Footer Creation Primer - Title Page.");

	pageSetup.HeaderDistance = 20;
	builder.MoveToHeaderFooter(HeaderFooterType.HeaderPrimary);

	//将定位图像插入页眉的上/左角。
	//距页面上/左边缘的距离设置为 10 磅。
	builder.InsertImage(ImagesDir + "Graphics Interchange Format.gif", RelativeHorizontalPosition.Page, 10,
		RelativeVerticalPosition.Page, 10, 50, 50, WrapType.Through);

	builder.ParagraphFormat.Alignment = ParagraphAlignment.Right;

	builder.Write("Aspose.Words Header/Footer Creation Primer.");

	builder.MoveToHeaderFooter(HeaderFooterType.FooterPrimary);

	//我们使用一个带有两个单元格的表格来使行中的一部分文本（带有页码）。
	//左对齐，文本的另一部分（有版权）右对齐。
	builder.StartTable();

	builder.CellFormat.ClearFormatting();

	builder.InsertCell();

	builder.CellFormat.PreferredWidth = PreferredWidth.FromPercent(100 / 3);

	//它使用 PAGE 和 NUMPAGES 字段来自动计算当前页码和页数。
	builder.Write("Page ");
	builder.InsertField("PAGE", "");
	builder.Write(" of ");
	builder.InsertField("NUMPAGES", "");

	builder.CurrentParagraph.ParagraphFormat.Alignment = ParagraphAlignment.Left;

	builder.InsertCell();

	builder.CellFormat.PreferredWidth = PreferredWidth.FromPercent(100 * 2 / 3);

	builder.Write("(C) 2001 Aspose Pty Ltd. All rights reserved.");

	builder.CurrentParagraph.ParagraphFormat.Alignment = ParagraphAlignment.Right;

	builder.EndRow();
	builder.EndTable();

	builder.MoveToDocumentEnd();

	//进行分页以创建第二页，在该页上可以看到主要的页眉/页脚。
	builder.InsertBreak(BreakType.PageBreak);
	builder.InsertBreak(BreakType.SectionBreakNewPage);

	currentSection = builder.CurrentSection;
	pageSetup = currentSection.PageSetup;
	pageSetup.Orientation = Orientation.Landscape;
	//本节不需要不同的首页页眉/页脚我们只需要文档中的一个标题页，
	//并且此页面的页眉/页脚已在上一节中定义。
	pageSetup.DifferentFirstPageHeaderFooter = false;

	//此部分显示上一节中的页眉/页脚
	//默认调用 currentSection.HeadersFooters.LinkToPrevious(false) 取消此页宽
	//对于新的部分是不同的，因此我们需要为页脚表设置不同的单元格宽度。
	currentSection.HeadersFooters.LinkToPrevious(false);

	//如果我们想为此部分使用现有的页眉/页脚集。
	//但是经过一些小的修改，复制页眉/页脚可能是方便的
	//从上一节中提取并在我们需要的地方应用必要的修改。
	CopyHeadersFootersFromPreviousSection(currentSection);

	HeaderFooter primaryFooter = currentSection.HeadersFooters[HeaderFooterType.FooterPrimary];

	Row row = primaryFooter.Tables[0].FirstRow;
	row.FirstCell.CellFormat.PreferredWidth = PreferredWidth.FromPercent(100 / 3);
	row.LastCell.CellFormat.PreferredWidth = PreferredWidth.FromPercent(100 * 2 / 3);

	doc.Save(dataDir + "WorkingWithHeadersAndFooters.CreateHeaderFooter.docx");
```
