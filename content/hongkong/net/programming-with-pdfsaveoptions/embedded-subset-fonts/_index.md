---
title: 在 PDF 文件中嵌入子集字體
linktitle: 在 PDF 文件中嵌入子集字體
second_title: Aspose.Words 文件處理 API
description: 使用 Aspose.Words for .NET 在 PDF 文件中嵌入字體子集的逐步指南。
type: docs
weight: 10
url: /zh-hant/net/programming-with-pdfsaveoptions/embedded-subset-fonts/
---

本文提供了有關如何將字體子集嵌入功能與 Aspose.Words for .NET 結合使用的逐步指南。我們將詳細解釋程式碼的每一部分。在本教學結束時，您將能夠了解如何在文件中嵌入字體子集並產生僅包含文件中使用的字形的 PDF。

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

## 步驟 3：配置另存為 PDF 選項

要建立僅包含文件中使用的字體子集的 PDF，我們需要配置`PdfSaveOptions`對象與`EmbedFullFonts`屬性設定為`false`.

```csharp
PdfSaveOptions saveOptions = new PdfSaveOptions { EmbedFullFonts = false };
```

## 步驟 4：將文件儲存為帶有字型子集的 PDF

最後，我們可以使用字型子集將文件另存為 PDF。指定輸出檔名和`saveOptions`我們在上一步中配置的物件。

```csharp
doc.Save(dataDir + "WorkingWithPdfSaveOptions.EmbeddSubsetFonts.pdf", saveOptions);
```

就這樣 ！您已成功將字體子集嵌入到文件中，並使用 Aspose.Words for .NET 產生了僅包含文件中使用的字形的 PDF。

### 使用 Aspose.Words for .NET 嵌入字體子集的範例原始程式碼

```csharp

	//文檔目錄的路徑。
	string dataDir = "YOUR DOCUMENT DIRECTORY";
	Document doc = new Document(dataDir + "Rendering.docx");

	//輸出 PDF 將包含文件中字體的子集。
	// PDF 字型中僅包含文件中使用的字形。
	PdfSaveOptions saveOptions = new PdfSaveOptions { EmbedFullFonts = false };
	
	doc.Save(dataDir + "WorkingWithPdfSaveOptions.EmbeddSubsetFonts.pdf", saveOptions);

```

## 結論

在本教程中，我們學習如何使用 Aspose.Words for .NET 在 PDF 文件中嵌入字體子集。嵌入字體子集有助於減小 PDF 文件的大小，同時僅使用實際使用的字元來保留文件的外觀。這可確保查看和列印 PDF 時更好的相容性和效能。請隨意進一步探索 Aspose.Words for .NET 的功能，以優化帶有嵌入字體子集的 PDF 文件的生成。

### 經常問的問題

#### Q：什麼是在 PDF 文件中嵌入字體子集？
答：在 PDF 文件中嵌入字型子集是僅包含文件中使用的字形的過程，而不是包含所有完整的字型。這樣可以僅包含顯示文件中實際使用的字元所需的字體數據，從而減少 PDF 文件的大小。

#### Q：嵌入完整字體和嵌入字體子集有什麼不同？
答：完整字體嵌入是指將文件中使用的所有字體包含在 PDF 文件中，這可以確保文件完全按照設計顯示，但會增加 PDF 文件的大小。相較之下，嵌入字體子集僅包含文件中使用的字形，從而減小了 PDF 文件的大小，但如果稍後添加其他字符，則限制了精確複製文件外觀的能力。

#### Q：如何使用 Aspose.Words for .NET 在 PDF 文件中嵌入字型子集？
答：若要使用 Aspose.Words for .NET 在 PDF 文件中嵌入字型子集，請依照下列步驟操作：

透過替換設定文檔目錄路徑`"YOUR DOCUMENT DIRECTORY"`與文檔目錄的實際路徑。

使用以下命令載入要處理的文檔`Document`類和文檔路徑。

透過建立實例來配置 PDF 儲存選項`PdfSaveOptions`類別並設定`EmbedFullFonts`財產給`false`。這可確保只有文件中使用的字型子集才會包含在 PDF 檔案中。

將文件儲存為 PDF 格式，並使用嵌入的字型子集`Save`的方法`Document`對象，指定輸出檔案的名稱和先前配置的儲存選項。

#### Q：在 PDF 文件中嵌入字體子集有什麼好處？
答：在 PDF 文件中嵌入字體子集的好處是：

減少 PDF 文件大小：與嵌入完整字體相比，透過僅包含文件中使用的字形，可以減少 PDF 文件大小。

保留文件的外觀：PDF 文件中包含的字型子集使得僅使用實際使用的字元即可重現文件的外觀。

與許可證限制的兼容性：在由於許可證限製而無法合法嵌入完整字體的情況下，可能會首選嵌入字體子集。