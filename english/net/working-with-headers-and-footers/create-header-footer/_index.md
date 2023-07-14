---
title: Create Header Footer
linktitle: Create Header Footer
second_title: Aspose.Words Document Processing API
description: Learn how to create headers and footers in your Word documents with Aspose.Words for .NET. Customize headers and footers for each page.
type: docs
weight: 10
url: /net/working-with-headers-and-footers/create-header-footer/
---

Here is a step-by-step guide to explain the following C# source code to create headers and footers using Aspose.Words for .NET functionality. Make sure you have included the Aspose.Words library in your project before using this code.

## Step 1: Set document directory path

```csharp
// The path to the documents directory.
string dataDir = "YOUR_DIRECTORY_OF_DOCUMENTS";
```

Be sure to specify the correct path to your documents directory where the edited document will be saved.

## Step 2: Create a document and a document generator

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
```

Here we create an instance of the `Document` class and an instance of the `DocumentBuilder` class which will allow us to manipulate the document and add elements.

## Step 3: Set page parameters and first header

```csharp
Section currentSection = builder.CurrentSection;
PageSetup pageSetup = currentSection.PageSetup;

// Specify if we want the headers/footers of the first page to be different from the other pages.
// You can also use the PageSetup.OddAndEvenPagesHeaderFooter property to specify
// different headers/footers for odd and even pages.
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

We set the page parameters, including the header distance, and then move to the main header (`HeaderPrimary`). We use the document generator to add text and format the header.

## Step 4: Insert an image and text in the main header

```csharp
builder.InsertImage(ImagesDir + "Graphics Interchange Format.gif", RelativeHorizontalPosition.Page, 10,
     RelativeVerticalPosition.Page, 10, 50, 50, WrapType.Through);

builder.ParagraphFormat.Alignment = ParagraphAlignment.Right;

builder.Write("Aspose.Words - Building headers/footers.");

builder. MoveToHeaderFooter(HeaderFooterType.FooterPrimary);
```

We use the document generator to insert an image in the upper left corner of the main header, then we add some right-aligned text.

## Step 5: Insert a table in the main footer

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

## Step 6: Add a new page and set headers/footers

```csharp
builder. InsertBreak(BreakType.PageBreak);
builder.InsertBreak(BreakType.SectionBreakNewPage);

currentSection = builder. CurrentSection;
pageSetup = currentSection.PageSetup;
pageSetup.Orientation = Orientation.Landscape;
// This section doesn't need a different header/footer for the first page, we only need one title page in the document,
// and the header/footer for this page has already been defined in the previous section.
pageSetup.DifferentFirstPageHeaderFooter = false;

// This section displays the headers/footers of the previous section by default, call currentSection.HeadersFooters.LinkToPrevious(false) to break this link,
// the page width is different for the new section, so we need to set different cell widths for a footer table.
currentSection.HeadersFooters.LinkToPrevious(false);

// If we want to use the already existing headers/footers for this section,
// but with a few minor changes, it might make sense to copy the headers/footers
// from the previous section and apply the necessary changes where we want them.
CopyHeadersFootersFromPreviousSection(currentSection);

HeaderFooter primaryFooter = currentSection.HeadersFooters[HeaderFooterType.FooterPrimary];

Row row = primaryFooter.Tables[0].FirstRow;
row.FirstCell.CellFormat.PreferredWidth = PreferredWidth.FromPercent(100 / 3);
row.LastCell.CellFormat.PreferredWidth = PreferredWidth.FromPercent(100 * 2 / 3);

// Save the document
doc.Save(dataDir + "WorkingWithHeadersAndFooters.CreateHeaderFooter.docx");
```

We add a page break and a section break to create a new page where the primary headers/footers will be visible. We set the parameters for the new section, then we use the `CopyHeadersFootersFromPreviousSection` method to copy the headers/footers from the previous section. Finally, we set the appropriate cell widths for the main footer table and save the document.

### Example source code to create headers and footers with Aspose.Words for .NET

```csharp
// The path to the documents directory.
string dataDir = "YOUR_DIRECTORY_OF_DOCUMENTS";

Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

Section currentSection = builder.CurrentSection;
PageSetup pageSetup = currentSection.PageSetup;
// Specify if we want headers/footers of the first page to be different from other pages.
// You can also use PageSetup.OddAndEvenPagesHeaderFooter property to specify
// different headers/footers for odd and even pages.
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

// Insert a positioned image into the top/left corner of the header.
// Distance from the top/left edges of the page is set to 10 points.
builder.InsertImage(ImagesDir + "Graphics Interchange Format.gif", RelativeHorizontalPosition.Page, 10,
	RelativeVerticalPosition.Page, 10, 50, 50, WrapType.Through);

builder.ParagraphFormat.Alignment = ParagraphAlignment.Right;

builder.Write("Aspose.Words Header/Footer Creation Primer.");

builder.MoveToHeaderFooter(HeaderFooterType.FooterPrimary);

// We use a table with two cells to make one part of the text on the line (with page numbering).
// To be aligned left, and the other part of the text (with copyright) to be aligned right.
builder.StartTable();

builder.CellFormat.ClearFormatting();

builder.InsertCell();

builder.CellFormat.PreferredWidth = PreferredWidth.FromPercent(100 / 3);

// It uses PAGE and NUMPAGES fields to auto calculate the current page number and many pages.
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

// Make a page break to create a second page on which the primary headers/footers will be seen.
builder.InsertBreak(BreakType.PageBreak);
builder.InsertBreak(BreakType.SectionBreakNewPage);

currentSection = builder.CurrentSection;
pageSetup = currentSection.PageSetup;
pageSetup.Orientation = Orientation.Landscape;
// This section does not need a different first-page header/footer we need only one title page in the document,
// and the header/footer for this page has already been defined in the previous section.
pageSetup.DifferentFirstPageHeaderFooter = false;

// This section displays headers/footers from the previous section
// by default call currentSection.HeadersFooters.LinkToPrevious(false) to cancel this page width
// is different for the new section, and therefore we need to set different cell widths for a footer table.
currentSection.HeadersFooters.LinkToPrevious(false);

// If we want to use the already existing header/footer set for this section.
// But with some minor modifications, then it may be expedient to copy headers/footers
// from the previous section and apply the necessary modifications where we want them.
CopyHeadersFootersFromPreviousSection(currentSection);

HeaderFooter primaryFooter = currentSection.HeadersFooters[HeaderFooterType.FooterPrimary];

Row row = primaryFooter.Tables[0].FirstRow;
row.FirstCell.CellFormat.PreferredWidth = PreferredWidth.FromPercent(100 / 3);
row.LastCell.CellFormat.PreferredWidth = PreferredWidth.FromPercent(100 * 2 / 3);

doc.Save(dataDir + "WorkingWithHeadersAndFooters.CreateHeaderFooter.docx");
```

### FAQ's

#### Q: How can I add a header to my document in Aspose.Words?

A: To add a header to your document in Aspose.Words, you can use the `Document.FirstSection.HeadersFooters.Add(HeaderFooterType.HeaderPrimary)` method. This method adds a primary heading to the first section of your document.

#### Q: How can I add a footer to my document in Aspose.Words?

A: To add a footer to your document in Aspose.Words, you can use the `Document.FirstSection.HeadersFooters.Add(HeaderFooterType.FooterPrimary)` method. This method adds a primary footer to the first section of your document.

#### Q: How can I add text to my header or footer in Aspose.Words?

A: To add text to your header or footer in Aspose.Words, you can use the `HeaderFooter.Paragraphs` property to get the paragraph collection of the header or footer, then add a paragraph containing your text to this collection using the `ParagraphCollection.Add` method.

#### Q: Can I customize header or footer content with images and page numbers in Aspose.Words?

A: Yes, you can customize header or footer content with images and page numbers in Aspose.Words. You can use objects like `Shape` to add images and objects like `Field` to add page numbers to your header or footer.

#### Q: Can I change the font, size and color of text in my header or footer in Aspose.Words?

A: Yes, you can change the font, size and color of text in your header or footer in Aspose.Words. You can access text formatting properties such as `Font` to change the font, `Size` to adjust the size, and `Color` to set the text color.
