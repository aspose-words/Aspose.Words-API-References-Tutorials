---
title: 設定註腳和尾註位置
linktitle: 設定註腳和尾註位置
second_title: Aspose.Words 文件處理 API
description: 了解如何使用 Aspose.Words for .NET 在 Word 文件中設定腳註和尾註的位置。
type: docs
weight: 10
url: /zh-hant/net/working-with-footnote-and-endnote/set-footnote-and-end-note-position/
---

在本逐步教學中，我們將指導您如何使用 Aspose.Words for .NET 在 Word 文件中設定腳註和尾註的位置。我們將解釋提供的 C# 原始程式碼，並向您展示如何在您自己的專案中實現它。

首先，請確保您已在開發環境中安裝並設定了 Aspose.Words for .NET。如果您還沒有這樣做，請從以下位置下載並安裝該程式庫[Aspose.Releases]https://releases.aspose.com/words/net/。

## 第 1 步：初始化文檔對象

首先，初始化`Document`透過提供來源文檔的路徑來物件：

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";     
Document doc = new Document(dataDir + "Document.docx");
```

## 步驟2：設定註腳和尾註位置

接下來，訪問`FootnoteOptions`和`EndnoteOptions`文檔的屬性來設定腳註和尾註的位置。在此範例中，我們將腳註的位置設為文字下方，將尾註的位置設定為該節的末尾：

```csharp
doc.FootnoteOptions.Position = FootnotePosition.BeneathText;
doc.EndnoteOptions.Position = EndnotePosition.EndOfSection;
```

## 第 3 步：儲存文檔

最後儲存修改後的文件：

```csharp
doc.Save(dataDir + "WorkingWithFootnotes.SetFootnoteAndEndNotePosition.docx");
```

就是這樣！您已使用 Aspose.Words for .NET 成功設定了 Word 文件中註腳和尾註的位置。

### 使用 Aspose.Words for .NET 設定腳註和尾註位置的範例原始碼

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";     
Document doc = new Document(dataDir + "Document.docx");

doc.FootnoteOptions.Position = FootnotePosition.BeneathText;
doc.EndnoteOptions.Position = EndnotePosition.EndOfSection;

doc.Save(dataDir + "WorkingWithFootnotes.SetFootnoteAndEndNotePosition.docx");
```

請隨意在您自己的專案中使用此程式碼，並根據您的特定要求進行修改。

### 常見問題解答

#### Q：如何在 Aspose.Words 中放置腳註和尾註？

答：要在 Aspose.Words 中定位腳註和尾註，您需要使用`FootnoteOptions`類和`Position`財產。您可以將此屬性設定為您想要的任何值，例如`BottomOfPage`（在頁面底部）或`EndOfSection`（在本節的末尾）。

#### Q：是否可以自訂文件每頁或每節的腳註和尾註的位置？

答：是的，可以自訂文件每頁或每節的腳註和尾註的位置。您可以使用 Aspose.Words 部分和頁面操作方法來定義腳註和尾註的特定位置。

#### Q：如何從文件中刪除腳註或尾註？

答：要在 Aspose.Words 中刪除文件中的腳註或尾註，您可以使用適當的方法，例如`RemoveAllFootnotes`刪除所有腳註或`RemoveAllEndnotes`刪除所有尾註。執行這些操作後請務必儲存文件。

#### Q：註腳和尾註可以位於頁邊距之外嗎？

不可以，預設情況下，腳註和尾註不能位於 Aspose.Words 的頁邊距之外。但是，如果需要，您可以調整文件頁邊距，以便為腳註和尾註留出更多空間。

#### Q：腳註和尾註可以使用特定字體或格式樣式進行自訂嗎？

答：是的，您可以在 Aspose.Words 中使用特定字體或格式樣式自訂腳註和尾註。您可以使用可用的方法和屬性來套用字體樣式、顏色、字體大小等腳註和尾註。