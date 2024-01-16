---
title: 透過跳過嵌入的 Arial 和 Times Roman 字體優化 PDF 大小
linktitle: 透過跳過嵌入的 Arial 和 Times Roman 字體優化 PDF 大小
second_title: Aspose.Words 文件處理 API
description: 使用 Aspose.Words for .NET 產生優化 PDF 且無需嵌入 Arial 和 Times Roman 字體的逐步指南。
type: docs
weight: 10
url: /zh-hant/net/programming-with-pdfsaveoptions/skip-embedded-arial-and-times-roman-fonts/
---

本文提供了有關如何使用該功能透過 Aspose.Words for .NET 將嵌入的 Arial 和 Times Roman 字體跳過到圖元檔案大小來優化 PDF 大小的逐步指南。我們將詳細解釋程式碼的每一部分。在本教學結束時，您將能夠了解如何在文件中配置字體嵌入模式選項並產生 PDF，而不嵌入 Arial 和 Times Roman 字體。

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

## 步驟 3：配置帶有字體嵌入的另存為 PDF 選項

要跳過在生成的 PDF 中嵌入 Arial 和 Times Roman 字體，我們需要配置`PdfSaveOptions`對象並設定`FontEmbeddingMode`財產給`PdfFontEmbeddingMode.EmbedAll`.

```csharp
PdfSaveOptions saveOptions = new PdfSaveOptions { FontEmbeddingMode = PdfFontEmbeddingMode.EmbedAll };
```

## 步驟 4：將文件儲存為不嵌入字體的 PDF

最後，我們可以使用先前配置的儲存選項將文件儲存為 PDF 格式。

```csharp
doc.Save(dataDir + "WorkingWithPdfSaveOptions.SkipEmbeddedArialAndTimesRomanFonts.pdf", saveOptions);
```

就這樣 ！您已使用 Aspose.Words for .NET 成功產生了 PDF，無需嵌入 Arial 和 Times Roman 字體。

### 使用 Aspose.Words for .NET 以圖元檔案大小跳過嵌入的 Arial 和 Times Roman 字體的範例原始程式碼

```csharp

	//文檔目錄的路徑。
	string dataDir = "YOUR DOCUMENT DIRECTORY";
	Document doc = new Document(dataDir + "Rendering.docx");

	PdfSaveOptions saveOptions = new PdfSaveOptions { FontEmbeddingMode = PdfFontEmbeddingMode.EmbedAll };

	doc.Save(dataDir + "WorkingWithPdfSaveOptions.SkipEmbeddedArialAndTimesRomanFonts.pdf", saveOptions);
   
```

## 結論

在本教學中，我們說明如何使用 Aspose.Words for .NET 在 PDF 文件中停用 Arial 和 Times Roman 字體的嵌入。透過執行概述的步驟，您可以產生 PDF 文件，而無需嵌入這些特定字體，這有助於減小文件大小並確保文件在不同平台之間具有更好的兼容性。使用此功能時，請務必考慮停用字體嵌入的後果。請隨意探索 Aspose.Words for .NET 的更多功能來優化 PDF 檔案的產生。

### 經常問的問題

#### Q：什麼是停用 PDF 文件中的 Arial 和 Times Roman 字體嵌入？為什麼它很重要？
答：在 PDF 文件中停用 Arial 和 Times Roman 字體的嵌入是指在產生的 PDF 文件中不包含這些字體的過程。透過避免包含 PDF 閱讀器系統上已經常見的字體，這對於減少 PDF 檔案的大小非常重要。它還可以幫助確保 PDF 文件在不同設備和平台上具有更好的兼容性和一致的外觀。

#### Q：如何設定 Aspose.Words for .NET 不在 PDF 文件中嵌入 Arial 和 Times Roman 字型？
答：要將 Aspose.Words for .NET 配置為不在 PDF 文件中嵌入 Arial 和 Times Roman 字體，請依照下列步驟操作：

透過替換設定文件所在的目錄路徑`"YOUR DOCUMENT DIRECTORY"`與文檔目錄的實際路徑。

使用以下命令載入要處理的文檔`Document`類別和指定的文檔路徑。

建立一個實例`PdfSaveOptions`類別並設定`FontEmbeddingMode`財產給`PdfFontEmbeddingMode.EmbedAll`。這將在生成的 PDF 文件中嵌入除 Arial 和 Times Roman 之外的所有字體。

使用`Save`的方法`Document`物件以 PDF 格式儲存文檔，指定先前配置的儲存選項。

#### Q：在 PDF 文件中停用 Arial 和 Times Roman 字體嵌入有什麼好處？
答：在 PDF 文件中停用 Arial 和 Times Roman 字體嵌入的好處是：

縮小 PDF 檔案大小：透過避免嵌入 Arial 和 Times Roman 等常用字體，可以減少 PDF 檔案大小，從而更輕鬆地儲存、共享和傳輸檔案。

更好的相容性：透過使用 PDF 閱讀器系統上常用的字體，您可以確保文件在不同裝置和平台上具有更好的相容性和外觀。

#### Q：在 PDF 文件中停用 Arial 和 Times Roman 字體嵌入會產生什麼後果？
答：在 PDF 文件中停用 Arial 和 Times Roman 字體嵌入的後果如下：

外觀不同：如果開啟 PDF 的系統上沒有 Arial 和 Times Roman 字體，則將使用替代字體，這可能會導致外觀與預期不同。

可讀性問題：使用的替代字體可能不如原始字體可讀，這可能會影響文件的可讀性。