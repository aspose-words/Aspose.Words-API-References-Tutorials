---
title: 更新 PDF 文件中最後列印的屬性
linktitle: 更新 PDF 文件中最後列印的屬性
second_title: Aspose.Words 文件處理 API
description: 使用 Aspose.Words for .NET 轉換為 PDF 時更新「上次列印」屬性的逐步指南。
type: docs
weight: 10
url: /zh-hant/net/programming-with-pdfsaveoptions/update-last-printed-property/
---

本文提供了有關如何透過 Aspose.Words for .NET 使用 PDF 文件更新功能中的「上次列印」屬性的逐步指南。我們將詳細解釋程式碼的每一部分。在本教學結束時，您將能夠了解如何配置選項以在轉換為 PDF 時更新「上次列印」屬性。

在開始之前，請確保您已在專案中安裝並設定了 Aspose.Words for .NET 程式庫。您可以在 Aspose 網站上找到庫和安裝說明。

## 步驟1：定義文檔目錄

首先，您需要定義文件所在目錄的路徑。代替`"YOUR DOCUMENT DIRECTORY"`與文檔目錄的實際路徑。

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## 第2步：上傳文件

接下來，我們需要載入我們想要處理的文檔。在此範例中，我們假設文件名稱為「Rendering.docx」並且位於指定的文件目錄中。

```csharp
Document doc = new Document(dataDir + "Rendering.docx");
```

## 步驟 3：使用更新的「上次列印」屬性配置另存為 PDF 選項

要在轉換為 PDF 時更新「上次列印」屬性，我們需要配置`PdfSaveOptions`對象並設定`UpdateLastPrintedProperty`財產給`true`.

```csharp
PdfSaveOptions saveOptions = new PdfSaveOptions { UpdateLastPrintedProperty = true };
```

## 步驟 4：將文件另存為 PDF，並更新「上次列印」屬性

最後，我們可以使用先前配置的儲存選項將文件儲存為 PDF 格式。

```csharp
doc.Save(dataDir + "WorkingWithPdfSaveOptions.UpdateIfLastPrinted.pdf", saveOptions);
```

就這樣 ！使用 Aspose.Words for .NET 將文件轉換為 PDF 時，您已成功啟用更新「上次列印」屬性。

### 使用 Aspose.Words for .NET 更新「上次列印」屬性的範例原始碼


```csharp

	//文檔目錄的路徑。
	string dataDir = "YOUR DOCUMENT DIRECTORY";
	Document doc = new Document(dataDir + "Rendering.docx");

	PdfSaveOptions saveOptions = new PdfSaveOptions { UpdateLastPrintedProperty = true };

	doc.Save(dataDir + "WorkingWithPdfSaveOptions.UpdateIfLastPrinted.pdf", saveOptions);

```
## 結論

在本教學中，我們說明如何使用 Aspose.Words for .NET 更新 PDF 文件中的「上次列印」屬性。透過執行給定的步驟，您可以輕鬆配置選項以在將文件轉換為 PDF 時更新「上次列印」屬性。使用此功能可以追蹤文件使用情況和相關資訊。

### 經常問的問題

#### Q：PDF 文件中的「最後列印」屬性是什麼？
答：PDF文件中的「上次列印」屬性是指文件上次列印的日期和時間。此屬性對於追蹤有關文件使用和管理的資訊非常有用。

#### Q：如何使用 Aspose.Words for .NET 更新 PDF 文件中的「上次列印」屬性？
答：若要使用 Aspose.Words for .NET 更新 PDF 文件中的「上次列印」屬性，請依照下列步驟操作：

建立一個實例`Document`指定 Word 文件路徑的類別。

建立一個實例`PdfSaveOptions`類別並設定`UpdateLastPrintedProperty`財產給`true`啟用更新“上次列印”屬性。

使用`Save`的方法`Document`類別透過指定儲存選項將文件儲存為 PDF 格式。

#### Q：如何檢查產生的 PDF 文件中的「上次列印」屬性是否已更新？
答：您可以透過使用相容的 PDF 檢視器（例如 Adobe Acrobat Reader）開啟 PDF 檔案並檢視文件資訊來檢查產生的 PDF 文件中的「上次列印」屬性是否已更新。最後列印的日期和時間應與產生 PDF 文件的日期和時間相對應。
