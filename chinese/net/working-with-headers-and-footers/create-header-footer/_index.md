---
title: 创建页眉页脚
linktitle: 创建页眉页脚
second_title: Aspose.Words for .NET API 参考
description: 了解如何使用 Aspose.Words for .NET 在 Word 文档中创建页眉和页脚。为每个页面自定义页眉和页脚。
type: docs
weight: 10
url: /zh/net/working-with-headers-and-footers/create-header-footer/
---

以下分步指南解释了使用 Aspose.Words for .NET 功能创建页眉和页脚的以下 C# 源代码。在使用此代码之前，请确保您已在项目中包含 Aspose.Words 库。

## 第1步：设置文档目录路径

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

这里我们创建一个实例`Document`类和一个实例`DocumentBuilder`类，它允许我们操作文档并添加元素。

## 步骤3：设置页面参数和第一个标题

```csharp
Section currentSection = builder.CurrentSection;
PageSetup pageSetup = currentSection.PageSetup;

//指定我们是否希望首页的页眉/页脚与其他页面不同。
//您还可以使用 PageSetup.OddAndEvenPagesHeaderFooter 属性来指定
//奇数页和偶数页有不同的页眉/页脚。
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

我们设置页面参数，包括标题距离，然后移动到主标题（`HeaderPrimary`）。我们使用文档生成器添加文本并格式化标题。

## 步骤 4：在主标题中插入图像和文本

```csharp
builder.InsertImage(ImagesDir + "Graphics Interchange Format.gif", RelativeHorizontalPosition.Page, 10,
     RelativeVerticalPosition.Page, 10, 50, 50, WrapType.Through);

builder.ParagraphFormat.Alignment = ParagraphAlignment.Right;

builder.Write("Aspose.Words - Building headers/footers.");

builder. MoveToHeaderFooter(HeaderFooterType.FooterPrimary);
```

我们使用文档生成器在主标题的左上角插入图像，然后添加一些右对齐文本。

## 步骤 5：在主页脚中插入表格

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
//本节不需要为第一页使用不同的页眉/页脚，我们只需要文档中的一个标题页，
//并且该页面的页眉/页脚已在上一节中定义。
pageSetup.DifferentFirstPageHeaderFooter = false;

//本节默认显示上一节的页眉/页脚，调用 currentSection.HeadersFooters.LinkToPrevious(false) 来断开此链接，
//新部分的页面宽度不同，因此我们需要为页脚表格设置不同的单元格宽度。
currentSection.HeadersFooters.LinkToPrevious(false);

//如果我们想在本节中使用现有的页眉/页脚，
//但通过一些小的更改，复制页眉/页脚可能是有意义的
//从上一节中获取并在我们想要的地方应用必要的更改。
CopyHeadersFootersFromPreviousSection(currentSection);

HeaderFooter primaryFooter = currentSection.HeadersFooters[HeaderFooterType.FooterPrimary];

Row row = primaryFooter.Tables[0].FirstRow;
row.FirstCell.CellFormat.PreferredWidth = PreferredWidth.FromPercent(100 / 3);
row.LastCell.CellFormat.PreferredWidth = PreferredWidth.FromPercent(100 * 2 / 3);

//保存文档
doc.Save(dataDir + "WorkingWithHeadersAndFooters.CreateHeaderFooter.docx");
```

我们添加分页符和分节符来创建一个新页面，其中主页眉/页脚将可见。我们为新部分设置参数，然后使用`CopyHeadersFootersFromPreviousSection`方法从上一节复制页眉/页脚。最后，我们为主页脚表设置适当的单元格宽度并保存文档。

### 使用 Aspose.Words for .NET 创建页眉和页脚的示例源代码

```csharp
//文档目录的路径。
string dataDir = "YOUR_DIRECTORY_OF_DOCUMENTS";

Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

Section currentSection = builder.CurrentSection;
PageSetup pageSetup = currentSection.PageSetup;
//指定我们是否希望首页的页眉/页脚与其他页面不同。
//您还可以使用 PageSetup.OddAndEvenPagesHeaderFooter 属性来指定
//奇数页和偶数页有不同的页眉/页脚。
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

//将定位的图像插入标题的左上角/左上角。
//距页面上/左边缘的距离设置为 10 点。
builder.InsertImage(ImagesDir + "Graphics Interchange Format.gif", RelativeHorizontalPosition.Page, 10,
	RelativeVerticalPosition.Page, 10, 50, 50, WrapType.Through);

builder.ParagraphFormat.Alignment = ParagraphAlignment.Right;

builder.Write("Aspose.Words Header/Footer Creation Primer.");

builder.MoveToHeaderFooter(HeaderFooterType.FooterPrimary);

//我们使用一个包含两个单元格的表格来将文本的一部分放在该行上（带有页码）。
//左对齐，文本的其他部分（有版权）右对齐。
builder.StartTable();

builder.CellFormat.ClearFormatting();

builder.InsertCell();

builder.CellFormat.PreferredWidth = PreferredWidth.FromPercent(100 / 3);

//它使用 PAGE 和 NUMPAGES 字段自动计算当前页码和页数。
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

//进行分页以创建第二页，在该页上将看到主页眉/页脚。
builder.InsertBreak(BreakType.PageBreak);
builder.InsertBreak(BreakType.SectionBreakNewPage);

currentSection = builder.CurrentSection;
pageSetup = currentSection.PageSetup;
pageSetup.Orientation = Orientation.Landscape;
//本节不需要不同的首页页眉/页脚，我们只需要文档中的一个标题页，
//并且该页面的页眉/页脚已在上一节中定义。
pageSetup.DifferentFirstPageHeaderFooter = false;

//此部分显示上一部分的页眉/页脚
//默认调用 currentSection.HeadersFooters.LinkToPrevious(false) 取消此页面宽度
//新部分不同，因此我们需要为页脚表设置不同的单元格宽度。
currentSection.HeadersFooters.LinkToPrevious(false);

//如果我们想使用本节已经存在的页眉/页脚集。
//但通过一些小的修改，复制页眉/页脚可能会更方便
//从上一节中获取并在我们想要的地方应用必要的修改。
CopyHeadersFootersFromPreviousSection(currentSection);

HeaderFooter primaryFooter = currentSection.HeadersFooters[HeaderFooterType.FooterPrimary];

Row row = primaryFooter.Tables[0].FirstRow;
row.FirstCell.CellFormat.PreferredWidth = PreferredWidth.FromPercent(100 / 3);
row.LastCell.CellFormat.PreferredWidth = PreferredWidth.FromPercent(100 * 2 / 3);

doc.Save(dataDir + "WorkingWithHeadersAndFooters.CreateHeaderFooter.docx");
```

### 常见问题解答

#### 问：如何在 Aspose.Words 中向文档添加标题？

答：要在 Aspose.Words 中向文档添加标题，您可以使用`Document.FirstSection.HeadersFooters.Add(HeaderFooterType.HeaderPrimary)`方法。此方法将主标题添加到文档的第一部分。

#### 问：如何在 Aspose.Words 中向文档添加页脚？

答：要在 Aspose.Words 中向文档添加页脚，您可以使用`Document.FirstSection.HeadersFooters.Add(HeaderFooterType.FooterPrimary)`方法。此方法将主页脚添加到文档的第一部分。

#### 问：如何在 Aspose.Words 中向页眉或页脚添加文本？

答：要在 Aspose.Words 中添加文本到页眉或页脚，您可以使用`HeaderFooter.Paragraphs`属性来获取页眉或页脚的段落集合，然后使用以下命令将包含文本的段落添加到该集合中`ParagraphCollection.Add`方法。

#### 问：我可以在 Aspose.Words 中使用图像和页码自定义页眉或页脚内容吗？

答：是的，您可以在 Aspose.Words 中使用图像和页码自定义页眉或页脚内容。您可以使用类似的对象`Shape`添加图像和对象，例如`Field`将页码添加到页眉或页脚。

#### 问：我可以在 Aspose.Words 中更改页眉或页脚中文本的字体、大小和颜色吗？

答：是的，您可以在 Aspose.Words 中更改页眉或页脚中文本的字体、大小和颜色。您可以访问文本格式属性，例如`Font`更改字体，`Size`调整大小，以及`Color`设置文本颜色。