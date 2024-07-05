---
title: 更改 Word 文件中的目錄製表位
linktitle: 更改 Word 文件中的目錄製表位
second_title: Aspose.Words 文件處理 API
description: 了解如何使用 Aspose.Words for .NET 變更 Word 文件中的目錄標籤。
type: docs
weight: 10
url: /zh-hant/net/programming-with-table-of-content/change-toc-tab-stops/
---
Aspose.Words for .NET 是一個功能強大的程式庫，用於在 C# 應用程式中建立、編輯和操作 Word 文件。在 Aspose.Words 提供的功能中，可以修改 Word 文件目錄中使用的選項卡。在本指南中，我們將向您展示如何使用 Aspose.Words for .NET 的 C# 原始程式碼來變更文件目錄中的標籤。

## 了解 Aspose.Words 函式庫

在深入研究程式碼之前，了解 .NET 的 Aspose.Words 函式庫非常重要。 Aspose.Words 是一個受歡迎的函式庫，它讓 Word 文件的文字處理變得簡單有效率。它提供了用於建立、編輯和操作 Word 文件的廣泛功能，包括更改目錄標籤。

## 載入包含目錄的文檔

第一步是載入包含要修改目錄的 Word 文件。使用 Document 類別從來源檔案載入文件。這是一個例子：

```csharp
Document doc = new Document(dataDir + "Table of contents.docx");
```

在此範例中，我們載入位於文件目錄中的文件「Table ofcontents.docx」。

## 更改目錄中的選項卡

載入文件後，我們將瀏覽文件的每個段落並檢查是否使用目錄 (TOC) 結果樣式進行格式化。如果是這樣，我們修改用於對齊頁碼的選項卡。就是這樣：

```csharp
foreach(Paragraph para in doc.GetChildNodes(NodeType.Paragraph, true))
{
     if (para.ParagraphFormat.Style.StyleIdentifier >= StyleIdentifier.Toc1 &&
         para.ParagraphFormat.Style.StyleIdentifier <= StyleIdentifier.Toc9)
     {
         TabStop tab = para.ParagraphFormat.TabStops[0];
         para.ParagraphFormat.TabStops.RemoveByPosition(tab.Position);
         para.ParagraphFormat.TabStops.Add(tab.Position - 50, tab.Alignment, tab.Leader);
     }
}
```

在此範例中，我們使用循環來循環遍歷文件中的每個段落。然後，我們檢查該段落是否使用目錄結果 (TOC) 樣式進行格式化。如果是這樣，我們存取本段中使用的第一個選項卡，並透過刪除舊選項卡並新增具有修改位置的新選項卡來修改它。

## 儲存修改後的文檔

對目錄中的選項卡進行必要的變更後，可以使用 Document 類別的 Save 方法儲存修改後的文件。這是一個例子：

```csharp
doc.Save(dataDir + "WorkingWithTableOfContent.ChangeTocTabStops.docx");
```

在此範例中，我們將修改後的文件儲存為「WorkingWithTableOfContent.ChangeTocTabStops.docx」。

### Aspose.Words for .NET 的「編輯目錄標籤」功能的範例原始碼

```csharp
//文檔目錄的路徑
string dataDir = "YOUR DOCUMENTS DIRECTORY";

//載入包含目錄的文檔
Document doc = new Document(dataDir + "Table of contents.docx");

//修改目錄的選項卡
foreach(Paragraph para in doc.GetChildNodes(NodeType.Paragraph, true))
{
     if (para.ParagraphFormat.Style.StyleIdentifier >= StyleIdentifier.Toc1 &&
         para.ParagraphFormat.Style.StyleIdentifier <= StyleIdentifier.Toc9)
     {
         TabStop tab = para.ParagraphFormat.TabStops[0];
         para.ParagraphFormat.TabStops.RemoveByPosition(tab.Position);
         para.ParagraphFormat.TabStops.Add(tab.Position - 50, tab.Alignment, tab.Leader);
     }
}

//儲存修改後的文檔
doc.Save(dataDir + "WorkingWithTableOfContent.ChangeTocTabStops.docx");
```

## 結論

在本指南中，我們介紹如何使用 Aspose.Words for .NET 使用提供的 C# 原始程式碼變更 Word 文件目錄中的標籤。透過按照提供的步驟操作，您可以輕鬆地在 C# 應用程式中自訂 Word 文件中的目錄標籤。 Aspose.Words 提供了巨大的靈活性和強大的功能來處理文件的樣式和格式，使您能夠創建有吸引力且專業的 Word 文件。

### Word 文件中更改目錄製表位的常見問題解答

#### Q：Aspose.Words for .NET 中「更改 Word 文件中的目錄製表位」功能的用途是什麼？

答：Aspose.Words for .NET 中的「更改 Word 文件中的目錄製表位」功能可讓您修改 Word 文件目錄中使用的製表位。它使您能夠自訂頁碼和目錄中相應標題的對齊方式和位置。

#### Q：什麼是 Aspose.Words for .NET？

答：Aspose.Words for .NET 是一個功能強大的程式庫，專為 .NET 應用程式中的 Word 文件進行文字處理而設計。它提供了使用 C# 或其他 .NET 語言以程式設計方式建立、編輯、操作和轉換 Word 文件的全面功能。

#### Q：如何使用 Aspose.Words for .NET 載入包含目錄的 Word 文件？

答：要使用 Aspose.Words for .NET 載入包含目錄的 Word 文檔，您可以使用`Document`類別及其建構函數。透過提供文件的文件路徑，您可以將其載入到`Document`目的。這是一個例子：

```csharp
Document doc = new Document(dataDir + "Table of contents.docx");
```

此程式碼片段載入位於指定目錄中的文件「Table ofcontents.docx」。

#### Q：如何使用 Aspose.Words for .NET 更改目錄中使用的選項卡？

答：文件載入後，您可以遍歷文件的每個段落並檢查是否使用目錄 (TOC) 結果樣式進行格式化。如果段落格式為目錄樣式，您可以修改用於對齊頁碼的標籤。在 Aspose.Words for .NET 中，您可以訪問`ParagraphFormat`每個段落的屬性來檢索和修改製表位。這是一個例子：

```csharp
foreach(Paragraph para in doc.GetChildNodes(NodeType.Paragraph, true))
{
    if (para.ParagraphFormat.Style.StyleIdentifier >= StyleIdentifier.Toc1 &&
        para.ParagraphFormat.Style.StyleIdentifier <= StyleIdentifier.Toc9)
    {
        TabStop tab = para.ParagraphFormat.TabStops[0];
        para.ParagraphFormat.TabStops.RemoveByPosition(tab.Position);
        para.ParagraphFormat.TabStops.Add(tab.Position - 50, tab.Alignment, tab.Leader);
    }
}
```

在此程式碼中，循環遍歷文件中的每個段落。如果段落具有目錄樣式，它將存取該段落中使用的第一個製表位，將其刪除，並新增具有修改位置的新製表位。

#### Q：我可以使用 Aspose.Words for .NET 更改目錄中多個層級的選項卡嗎？

答：是的，您可以使用 Aspose.Words for .NET 來變更目錄中多個層級的標籤。透過迭代每個段落並檢查目錄樣式，您可以單獨修改每個層級的標籤。您可以存取所需等級的目錄並相應地調整製表位。

#### Q：使用 Aspose.Words for .NET 更改目錄中的選項卡後，如何儲存修改後的文件？

答：對目錄中的選項卡進行必要的更改後，您可以使用以下命令儲存修改後的文件：`Save`的方法`Document`班級。提供輸出文件所需的文件路徑和名稱作為參數`Save`方法。這是一個例子：

```csharp
doc.Save(dataDir + "WorkingWithTableOfContent.ChangeTocTabStops.docx");
```

此程式碼將修改後的文件儲存為「WorkingWithTableOfContent.ChangeTocTabStops.docx」。

#### Q：我可以使用 Aspose.Words for .NET 自訂目錄的其他方面嗎？

答：是的，使用 Aspose.Words for .NET，您可以自訂目錄的各個方面。除了變更標籤之外，您還可以修改目錄條目和頁碼的字型樣式、大小、對齊方式以及其他格式屬性。此外，您還可以調整對應標題的縮排、間距和格式。

#### 問：。我可以使用 Aspose.Words for .NET 更改目錄的製表符對齊方式和前導字元嗎？

答：是的，您可以使用 Aspose.Words for .NET 來變更目錄的製表符對齊方式和前導字元。透過存取製表位並調整其對齊方式和引線屬性，您可以控制頁碼和目錄中相應標題的對齊方式和視覺外觀。

#### Q：Aspose.Words for .NET 是否支援更改 Word 文件中的其他樣式和格式？

答：是的，Aspose.Words for .NET 為更改 Word 文件中的各種樣式和格式提供了廣泛的支援。它允許您修改不同元素的樣式，例如段落、標題、表格、清單等。您可以根據您的要求變更字體、顏色、對齊方式、縮排、間距和其他格式設定。

#### Q：我可以使用 Aspose.Words for .NET 修改現有 Word 文件目錄中的選項卡嗎？

答：是的，您可以使用 Aspose.Words for .NET 修改現有 Word 文件目錄中的標籤。透過載入文件、迭代段落並對製表位進行必要的更改，您可以更新目錄中的選項卡。最後，儲存文件以套用修改。