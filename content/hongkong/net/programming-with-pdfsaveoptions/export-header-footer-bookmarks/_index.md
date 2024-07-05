---
title: 將 Word 文件頁首頁腳書籤匯出至 PDF 文檔
linktitle: 將 Word 文件頁首頁腳書籤匯出至 PDF 文檔
second_title: Aspose.Words 文件處理 API
description: 使用 Aspose.Words for .NET 將 Word 文件頁首頁尾書籤匯出至 pdf 文件書籤的逐步指南。
type: docs
weight: 10
url: /zh-hant/net/programming-with-pdfsaveoptions/export-header-footer-bookmarks/
---

本文提供了有關如何使用 Aspose.Words for .NET 將 Word 文件頁眉頁腳書籤匯出至 pdf 文件功能的逐步指南。我們將詳細解釋程式碼的每一部分。在本教學結束時，您將能夠了解如何從文件的頁首和頁尾匯出書籤並產生具有適當書籤的 PDF。

在開始之前，請確保您已在專案中安裝並設定了 Aspose.Words for .NET 程式庫。您可以在 Aspose 網站上找到庫和安裝說明。

## 步驟1：定義文檔目錄

首先，您需要定義文件所在目錄的路徑。代替`"YOUR DOCUMENT DIRECTORY"`與文檔目錄的實際路徑。

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## 第2步：上傳文件

接下來，我們需要載入我們想要處理的文檔。在此範例中，我們假設文件名稱為「Bookmarks in headers and footers.docx」並且位於指定的文件目錄中。

```csharp
Document doc = new Document(dataDir + "Bookmarks in headers and footers.docx");
```

## 步驟 3：配置另存為 PDF 選項

要匯出頁首和頁尾書籤，我們需要配置`PdfSaveOptions`目的。在此範例中，我們將預設書籤大綱層級設為 1，並將頁首和頁尾書籤匯出模式設為「第一」。

```csharp
PdfSaveOptions saveOptions = new PdfSaveOptions();
saveOptions.OutlineOptions.DefaultBookmarksOutlineLevel = 1;
saveOptions.HeaderFooterBookmarksExportMode = HeaderFooterBookmarksExportMode.First;
```

## 步驟 4：將文件另存為帶有頁首和頁尾書籤的 PDF

最後，我們可以使用先前配置的儲存選項將文件儲存為 PDF 格式。

```csharp
doc.Save(dataDir + "WorkingWithPdfSaveOptions.ExportHeaderFooterBookmarks.pdf", saveOptions);
```

就這樣 ！您已成功從文件中匯出頁首和頁尾書籤，並使用 Aspose.Words for .NET 產生了具有適當書籤的 PDF。

### 使用 Aspose.Words for .NET 匯出頁首和頁尾書籤的範例原始碼

```csharp

	//文檔目錄的路徑。
	string dataDir = "YOUR DOCUMENT DIRECTORY";
	Document doc = new Document(dataDir + "Bookmarks in headers and footers.docx");

	PdfSaveOptions saveOptions = new PdfSaveOptions();
	saveOptions.OutlineOptions.DefaultBookmarksOutlineLevel = 1;
	saveOptions.HeaderFooterBookmarksExportMode = HeaderFooterBookmarksExportMode.First;

	doc.Save(dataDir + "WorkingWithPdfSaveOptions.ExportHeaderFooterBookmarks.pdf", saveOptions);

```

## 結論

在本教學中，我們說明如何使用 Aspose.Words for .NET 將頁首和頁尾書籤從 Word 文件匯出到 PDF 文件。匯出的書籤可以輕鬆導航並快速引用生成的 PDF 文件中對應的頁首和頁尾。依照所述的步驟從文件匯出頁首和頁尾書籤，並使用 Aspose.Words for .NET 產生適當書籤的 PDF。請務必指定文件的正確路徑並根據需要配置儲存選項。

### 經常問的問題

### Q：什麼是將頁首和頁尾書籤從 Word 文件匯出到 PDF 文件？
答：將Word文件中的頁首和頁尾書籤匯出至PDF文件是一項功能，可從頁首和頁尾保留並產生PDF文件中的書籤。原始 Word 文件的頁尾。這使得使用者可以使用與頁首和頁尾相對應的書籤快速輕鬆地瀏覽 PDF 文件。

### Q：如何使用 Aspose.Words for .NET 將頁首和頁尾書籤從 Word 文件匯出到 PDF 文件？
答：若要使用 Aspose.Words for .NET 將頁首和頁尾書籤從 Word 文檔匯出到 PDF 文檔，請依照下列步驟操作：

透過替換設定文件所在的目錄路徑`"YOUR DOCUMENT DIRECTORY"`與文檔目錄的實際路徑。

使用以下命令載入要處理的文檔`Document`類別並指定指定文檔目錄中Word文檔的路徑。

透過建立一個實例來配置另存為 PDF 選項`PdfSaveOptions`類別並設定適當的頁首和頁尾書籤選項。

使用以下命令將文件儲存為 PDF 格式`Save`的方法`Document`指定路徑和儲存選項的類別。

### Q：將頁首和頁尾書籤匯出到 PDF 文件有什麼好處？
答：將頁首和頁尾書籤匯出至 PDF 文件的優點是：

輕鬆導航：書籤允許使用者透過引用特定的頁首和頁尾輕鬆導航 PDF 文件。

快速參考：書籤允許使用者根據頁首和頁尾快速找到 PDF 文件的相關部分。