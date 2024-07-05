---
title: 透過停用嵌入字體來減少 PDF 大小
linktitle: 透過停用嵌入字體來減少 PDF 大小
second_title: Aspose.Words 文件處理 API
description: 了解在使用 Aspose.Words for .NET 將文件轉換為 PDF 時如何透過停用 Windows 字體嵌入來減少 PDF 大小。
type: docs
weight: 10
url: /zh-hant/net/programming-with-pdfsaveoptions/disable-embed-windows-fonts/
---

在本教學中，我們將引導您完成使用 Aspose.Words for .NET 在 PDF 文件中停用 Windows 字體嵌入來減少 PDF 大小的步驟。透過停用字體嵌入，您可以減小生成的 PDF 檔案的大小。請依照以下步驟操作：

## 第 1 步：載入文檔

首先上傳您想要轉換為 PDF 的文件：

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
Document doc = new Document(dataDir + "Rendering.docx");
```

請務必指定文件的正確路徑。

## 第 2 步：設定 PDF 儲存選項

建立 PdfSaveOptions 類別的實例並指定如何嵌入字型：

```csharp
PdfSaveOptions saveOptions = new PdfSaveOptions { FontEmbeddingMode = PdfFontEmbeddingMode.EmbedNone };
```

此選項可讓您在生成的 PDF 檔案中停用 Windows 字體的整合。

## 步驟 3：將文件轉換為 PDF

使用`Save`將文件轉換為 PDF 的方法，指定轉換選項：

```csharp
doc.Save(dataDir + "WorkingWithPdfSaveOptions.DisableEmbedWindowsFonts.pdf", saveOptions);
```

確保指定正確的路徑來儲存轉換後的 PDF。

### 使用 Aspose.Words for .NET 停用嵌入 Windows 字體的範例原始碼

以下是使用 Aspose.Words for .NET 在 PDF 文件中停用嵌入 Windows 字體的完整原始碼：

```csharp

	//文檔目錄的路徑。
	string dataDir = "YOUR DOCUMENT DIRECTORY";
	Document doc = new Document(dataDir + "Rendering.docx");

	//儲存輸出的 PDF 時不會嵌入標準 Windows 字型。
	PdfSaveOptions saveOptions = new PdfSaveOptions { FontEmbeddingMode = PdfFontEmbeddingMode.EmbedNone };
	
	doc.Save(dataDir + "WorkingWithPdfSaveOptions.DisableEmbedWindowsFonts.pdf", saveOptions);

```
透過執行下列步驟，您可以使用 Aspose.Words for .NET 輕鬆停用在 PDF 文件中嵌入 Windows 字型。


## 結論

在本教學中，我們學習如何透過使用 Aspose.Words for .NET 停用嵌入 Windows 字體來減少 PDF 檔案的大小。透過停用字體嵌入，您可以減少生成的 PDF 文件的大小，從而更輕鬆地儲存、共享和傳輸文件。但是，請務必注意，停用 Windows 字型嵌入可能會導致最終 PDF 文件的外觀和格式變更。使用此功能時請務必考慮這些後果。請隨意探索 Aspose.Words for .NET 的更多功能來優化 PDF 檔案的產生。

### 經常問的問題

#### Q：什麼是在 PDF 文件中禁用 Windows 字體嵌入？
答：在 PDF 文件中停用 Windows 字型嵌入是防止 Windows 字型包含在產生的 PDF 文件中的過程。這可以透過刪除嵌入的 Windows 字型資料來減少 PDF 檔案的大小。這對於減小 PDF 檔案的大小非常重要，使它們更容易儲存、共享和更快地傳輸。

#### Q：如何使用 Aspose.Words for .NET 在 PDF 文件中停用 Windows 字型嵌入？
答：若要使用 Aspose.Words for .NET 在 PDF 文件中停用嵌入 Windows 字體，請依照下列步驟操作：

使用以下命令載入要轉換為 PDF 的文檔`Document`類和文檔路徑。

建立一個實例`PdfSaveOptions`類別並設定`FontEmbeddingMode`財產給`PdfFontEmbeddingMode.EmbedNone`。這會停用在產生的 PDF 檔案中嵌入 Windows 字型。

使用`Save`的方法`Document`將文件轉換為 PDF 的對象，指定先前配置的轉換選項。

#### Q：在 PDF 文件中停用 Windows 字型嵌入有什麼好處？
答：在 PDF 文件中停用 Windows 字型嵌入的好處是：

減小 PDF 檔案大小：透過停用 Windows 字型嵌入，嵌入的 Windows 字型資料將會被刪除，從而減少產生的 PDF 檔案的大小。

更容易儲存：較小的 PDF 檔案更容易儲存、儲存和傳輸。

更快的共享和傳輸：較小的 PDF 文件可以更快地共享和傳輸，從而節省時間和資源。

#### Q：在 PDF 文件中停用 Windows 字型嵌入會產生什麼後果？
答：在 PDF 文件中停用 Windows 字型嵌入可能會導致以下後果：

外觀和格式遺失：如果文件中指定的 Windows 字體在開啟 PDF 的系統上不可用，則將使用替代字體，這可能會導致外觀和格式不正確。形狀與預期不同。

可讀性問題：如果使用的替代字體不如原始字體可讀，可能會影響 PDF 文件中文字的可讀性。