---
title: 移至 Word 文件中的頁首頁腳
linktitle: 移至 Word 文件中的頁首頁腳
second_title: Aspose.Words 文件處理 API
description: 透過此逐步指南，了解如何使用 Aspose.Words for .NET 導覽和修改 Word 文件中的頁首和頁尾。
type: docs
weight: 10
url: /zh-hant/net/add-content-using-documentbuilder/move-to-headers-footers/
---
在此範例中，我們將探索 Aspose.Words for .NET 的「移至頁首頁尾」功能。 Aspose.Words 是一個功能強大的文件操作庫，可讓開發人員以程式設計方式建立、修改和轉換 Word 文件。移動到頁首/頁腳功能使我們能夠導航到文件中的不同頁首和頁尾並向其中添加內容。

讓我們逐步瀏覽原始程式碼，了解如何使用 Aspose.Words for .NET 使用「移至頁首/頁尾」功能。

## 步驟 1：初始化文檔和文檔產生器

首先，初始化 Document 和 DocumentBuilder 物件：

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
```

## 第 2 步：設定頁首和頁尾

指定文件的頁首/頁尾設定。在此範例中，我們將首頁和奇數/偶數頁的頁首和頁尾設定為不同：

```csharp
builder.PageSetup.DifferentFirstPageHeaderFooter = true;
builder.PageSetup.OddAndEvenPagesHeaderFooter = true;
```

## 步驟 3：為不同頁面建立標題

移動到每個標題類型並添加內容。在此範例中，我們為第一頁、偶數頁和所有其他頁面建立標題：

```csharp
builder.MoveToHeaderFooter(HeaderFooterType.HeaderFirst);
builder.Write("Header for the first page");

builder.MoveToHeaderFooter(HeaderFooterType.HeaderEven);
builder.Write("Header for even pages");

builder.MoveToHeaderFooter(HeaderFooterType.HeaderPrimary);
builder.Write("Header for all other pages");
```

## 步驟 4：在文件中建立頁面
將內容新增至文件以建立多個頁面。例如：

```csharp
//在文件中建立兩個頁面。
builder.MoveToSection(0);
builder.Writeln("Page1");
builder.InsertBreak(BreakType.PageBreak);
builder.Writeln("Page2");
```
## 第 5 步：儲存文檔

將修改後的文件儲存到所需位置：

```csharp
doc.Save(ArtifactsDir + "AddContentUsingDocumentBuilder.MoveToHeadersFooters.docx");
```

確保指定適當的文件路徑和格式（例如 DOCX）。

### 使用 Aspose.Words for .NET 移至頁首/頁尾的範例原始碼

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

//指定我們希望首頁、偶數頁和奇數頁的頁首和頁尾不同。
builder.PageSetup.DifferentFirstPageHeaderFooter = true;
builder.PageSetup.OddAndEvenPagesHeaderFooter = true;

//建立標題。
builder.MoveToHeaderFooter(HeaderFooterType.HeaderFirst);
builder.Write("Header for the first page");
builder.MoveToHeaderFooter(HeaderFooterType.HeaderEven);
builder.Write("Header for even pages");
builder.MoveToHeaderFooter(HeaderFooterType.HeaderPrimary);
builder.Write("Header for all other pages");

//在文件中建立兩個頁面。
builder.MoveToSection(0);
builder.Writeln("Page1");
builder.InsertBreak(BreakType.PageBreak);
builder.Writeln("Page2");

doc.Save(ArtifactsDir + "AddContentUsingDocumentBuilder.MoveToHeadersFooters.docx");
```

## 結論

在此範例中，我們探索了 Aspose.Words for .NET 的「移至頁首/頁尾」功能。我們學習如何導覽至 Word 文件中的不同頁首和頁腳，並使用 DocumentBuilder 類別在其中新增內容。此功能允許開發人員自訂特定頁面或部分的頁首和頁腳，為建立專業和結構化文件提供了靈活性。 Aspose.Words for .NET 提供了一組功能強大的工具，用於以程式設計方式操作 Word 文檔，使其成為文檔處理應用程式的重要程式庫。

### 在 Word 文件中移至頁首頁尾的常見問題解答

#### Q：Aspose.Words for .NET 中的「移至頁首/頁尾」功能的用途是什麼？

答：Aspose.Words for .NET 中的「移至頁首/頁尾」功能可讓開發人員導覽至 Word 文件中的不同頁首和頁尾，並以程式設計方式新增內容。當您需要為文件中的不同頁面或部分自訂頁首和頁尾時，它非常有用。

#### Q：文件中的不同頁面可以使用不同的頁首和頁尾嗎？

答：是的，您可以分別使用 PageSetup.DifferentFirstPageHeaderFooter 和 PageSetup.OddAndEvenPagesHeaderFooter 屬性為首頁、偶數頁和奇數頁指定不同的頁首和頁尾。

#### Q：如何將內容新增到特定的頁首和頁尾？

答：若要將內容新增至特定的頁首和頁尾，請使用 DocumentBuilder 類別的 MoveToHeaderFooter 方法。您可以根據需要移動到 HeaderFirst、HeaderEven 和 HeaderPrimary 標頭或 FooterFirst、FooterEven 和 FooterPrimary 頁腳。

#### Q：我可以為文件中的特定部分建立頁首和頁尾嗎？

答：是的，您可以使用 DocumentBuilder 類別的 MoveToSection 方法移至文件中的特定部分，然後在該部分中建立頁首和頁尾。

#### Q：如何使用 Aspose.Words for .NET 將修改後的文件儲存到文件中？

答：您可以使用Document類別的Save方法將修改後的文件儲存到所需的位置和格式。確保指定適當的文件路徑和文件格式（例如 DOCX）。