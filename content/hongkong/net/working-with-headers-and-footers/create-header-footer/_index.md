---
title: 建立頁眉頁腳
linktitle: 建立頁眉頁腳
second_title: Aspose.Words 文件處理 API
description: 了解如何使用 Aspose.Words for .NET 在 Word 文件中建立頁首和頁尾。為每個頁面自訂頁首和頁尾。
type: docs
weight: 10
url: /zh-hant/net/working-with-headers-and-footers/create-header-footer/
---

以下逐步指南解釋了使用 Aspose.Words for .NET 功能建立頁首和頁尾的以下 C# 原始程式碼。在使用此程式碼之前，請確保您已在專案中包含 Aspose.Words 程式庫。

## 步驟1：設定文檔目錄路徑

```csharp
//文檔目錄的路徑。
string dataDir = "YOUR_DIRECTORY_OF_DOCUMENTS";
```

請務必指定儲存已編輯文件的文件目錄的正確路徑。

## 第 2 步：建立文件和文件產生器

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
```

這裡我們創建一個實例`Document`類別和一個實例`DocumentBuilder`類，它允許我們操作文件並添加元素。

## 步驟3：設定頁面參數和第一個標題

```csharp
Section currentSection = builder.CurrentSection;
PageSetup pageSetup = currentSection.PageSetup;

//指定我們是否希望首頁的頁首/頁尾與其他頁面不同。
//您也可以使用 PageSetup.OddAndEvenPagesHeaderFooter 屬性來指定
//奇數頁和偶數頁有不同的頁首/頁尾。
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

我們設定頁面參數，包括標題距離，然後移動到主標題（`HeaderPrimary`）。我們使用文檔生成器添加文字並格式化標題。

## 步驟 4：在主標題中插入圖像和文字

```csharp
builder.InsertImage(ImagesDir + "Graphics Interchange Format.gif", RelativeHorizontalPosition.Page, 10,
     RelativeVerticalPosition.Page, 10, 50, 50, WrapType.Through);

builder.ParagraphFormat.Alignment = ParagraphAlignment.Right;

builder.Write("Aspose.Words - Building headers/footers.");

builder. MoveToHeaderFooter(HeaderFooterType.FooterPrimary);
```

我們使用文件產生器在主標題的左上角插入圖像，然後添加一些右對齊文字。

## 步驟 5：在主頁腳中插入表格

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

## 第 6 步：新增頁面並設定頁首/頁尾

```csharp
builder. InsertBreak(BreakType.PageBreak);
builder.InsertBreak(BreakType.SectionBreakNewPage);

currentSection = builder. CurrentSection;
pageSetup = currentSection.PageSetup;
pageSetup.Orientation = Orientation.Landscape;
//本節不需要為第一頁使用不同的頁首/頁腳，我們只需要文件中的一個標題頁，
//並且該頁面的頁首/頁尾已在上一節中定義。
pageSetup.DifferentFirstPageHeaderFooter = false;

//本節預設顯示上一節的頁眉/頁腳，調用 currentSection.HeadersFooters.LinkToPrevious(false) 來斷開此鏈接，
//新部分的頁面寬度不同，因此我們需要為頁腳表格設定不同的儲存格寬度。
currentSection.HeadersFooters.LinkToPrevious(false);

//如果我們想在本節中使用現有的頁首/頁尾，
//但透過一些小的更改，複製頁首/頁尾可能是有意義的
//從上一節中取得並在我們想要的地方應用必要的變更。
CopyHeadersFootersFromPreviousSection(currentSection);

HeaderFooter primaryFooter = currentSection.HeadersFooters[HeaderFooterType.FooterPrimary];

Row row = primaryFooter.Tables[0].FirstRow;
row.FirstCell.CellFormat.PreferredWidth = PreferredWidth.FromPercent(100 / 3);
row.LastCell.CellFormat.PreferredWidth = PreferredWidth.FromPercent(100 * 2 / 3);

//儲存文件
doc.Save(dataDir + "WorkingWithHeadersAndFooters.CreateHeaderFooter.docx");
```

我們新增分頁符號和分節符號來建立一個新頁面，其中主頁眉/頁腳將可見。我們為新部分設定參數，然後使用`CopyHeadersFootersFromPreviousSection`方法從上一節複製頁首/頁尾。最後，我們為主頁腳表設定適當的儲存格寬度並儲存文件。

### 使用 Aspose.Words for .NET 建立頁首和頁尾的範例原始碼

```csharp
//文檔目錄的路徑。
string dataDir = "YOUR_DIRECTORY_OF_DOCUMENTS";

Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

Section currentSection = builder.CurrentSection;
PageSetup pageSetup = currentSection.PageSetup;
//指定我們是否希望首頁的頁首/頁尾與其他頁面不同。
//您也可以使用 PageSetup.OddAndEvenPagesHeaderFooter 屬性來指定
//奇數頁和偶數頁有不同的頁首/頁尾。
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

//將定位的圖像插入標題的左上角/左上角。
//距頁面上/左邊緣的距離設定為 10 點。
builder.InsertImage(ImagesDir + "Graphics Interchange Format.gif", RelativeHorizontalPosition.Page, 10,
	RelativeVerticalPosition.Page, 10, 50, 50, WrapType.Through);

builder.ParagraphFormat.Alignment = ParagraphAlignment.Right;

builder.Write("Aspose.Words Header/Footer Creation Primer.");

builder.MoveToHeaderFooter(HeaderFooterType.FooterPrimary);

//我們使用一個包含兩個單元格的表格來將文字的一部分放在該行上（帶有頁碼）。
//左對齊，文字的其他部分（有版權）右對齊。
builder.StartTable();

builder.CellFormat.ClearFormatting();

builder.InsertCell();

builder.CellFormat.PreferredWidth = PreferredWidth.FromPercent(100 / 3);

//它使用 PAGE 和 NUMPAGES 欄位自動計算當前頁碼和頁數。
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

//進行分頁以建立第二頁，在該頁上將看到主頁首/頁尾。
builder.InsertBreak(BreakType.PageBreak);
builder.InsertBreak(BreakType.SectionBreakNewPage);

currentSection = builder.CurrentSection;
pageSetup = currentSection.PageSetup;
pageSetup.Orientation = Orientation.Landscape;
//本節不需要不同的首頁頁首/頁腳，我們只需要文件中的一個標題頁，
//並且該頁面的頁首/頁尾已在上一節中定義。
pageSetup.DifferentFirstPageHeaderFooter = false;

//此部分顯示上一部分的頁首/頁尾
//預設呼叫 currentSection.HeadersFooters.LinkToPrevious(false) 取消此頁面寬度
//新部分不同，因此我們需要為頁腳表設定不同的儲存格寬度。
currentSection.HeadersFooters.LinkToPrevious(false);

//如果我們想要使用本節已經存在的頁首/頁尾集。
//但透過一些小的修改，複製頁首/頁尾可能會更方便
//從上一節中取得並在我們想要的地方應用必要的修改。
CopyHeadersFootersFromPreviousSection(currentSection);

HeaderFooter primaryFooter = currentSection.HeadersFooters[HeaderFooterType.FooterPrimary];

Row row = primaryFooter.Tables[0].FirstRow;
row.FirstCell.CellFormat.PreferredWidth = PreferredWidth.FromPercent(100 / 3);
row.LastCell.CellFormat.PreferredWidth = PreferredWidth.FromPercent(100 * 2 / 3);

doc.Save(dataDir + "WorkingWithHeadersAndFooters.CreateHeaderFooter.docx");
```

### 常見問題解答

#### Q：如何在 Aspose.Words 中為文件新增標題？

答：要在 Aspose.Words 中為文件新增標題，您可以使用`Document.FirstSection.HeadersFooters.Add(HeaderFooterType.HeaderPrimary)`方法。此方法將主標題新增至文件的第一部分。

#### Q：如何在 Aspose.Words 中新增頁尾頁？

答：要在 Aspose.Words 中新增頁腳，您可以使用`Document.FirstSection.HeadersFooters.Add(HeaderFooterType.FooterPrimary)`方法。此方法將主頁腳新增至文件的第一部分。

#### Q：如何在 Aspose.Words 中為頁首或頁尾新增文字？

答：要在 Aspose.Words 中為頁首或頁尾新增文本，您可以使用`HeaderFooter.Paragraphs`屬性來取得頁首或頁尾的段落集合，然後使用以下指令將包含文字的段落新增至該集合中`ParagraphCollection.Add`方法。

#### Q：我可以在 Aspose.Words 中使用圖片和頁碼自訂頁首或頁尾內容嗎？

答：是的，您可以在 Aspose.Words 中使用圖片和頁碼自訂頁首或頁尾內容。您可以使用類似的對象`Shape`新增圖像和對象，例如`Field`將頁碼新增至頁首或頁尾。

#### Q：我可以在 Aspose.Words 中更改頁首或頁尾中文字的字體、大小和顏色嗎？

答：是的，您可以在 Aspose.Words 中變更頁首或頁尾中文字的字體、大小和顏色。您可以存取文字格式屬性，例如`Font`更改字體，`Size`調整大小，以及`Color`設定文字顏色。