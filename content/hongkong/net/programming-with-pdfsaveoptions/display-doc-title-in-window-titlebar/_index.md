---
title: 在視窗標題列中顯示文件標題
linktitle: 在視窗標題列中顯示文件標題
second_title: Aspose.Words 文件處理 API
description: 了解使用 Aspose.Words for .NET 轉換為 PDF 時如何在視窗標題列中顯示文件標題。
type: docs
weight: 10
url: /zh-hant/net/programming-with-pdfsaveoptions/display-doc-title-in-window-titlebar/
---

在本教學中，我們將引導您完成使用 Aspose.Words for .NET 在視窗標題列中顯示文件標題的步驟。此功能可讓您在開啟生成的 PDF 文件時在視窗標題列中顯示文件標題。請依照以下步驟操作：

## 第 1 步：載入文檔

首先上傳您想要轉換為 PDF 的文件：

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
Document doc = new Document(dataDir + "Rendering.docx");
```

請務必指定文件的正確路徑。

## 步驟 2：設定 PDF 儲存選項

建立 PdfSaveOptions 類別的實例並啟用在視窗標題列中顯示文件標題：

```csharp
PdfSaveOptions saveOptions = new PdfSaveOptions { DisplayDocTitle = true };
```

此選項允許在轉換為 PDF 時在視窗標題列中顯示文件標題。

## 步驟 3：將文件轉換為 PDF

使用`Save`將文件轉換為 PDF 的方法，指定轉換選項：

```csharp
doc.Save(dataDir + "WorkingWithPdfSaveOptions.DisplayDocTitleInWindowTitlebar.pdf", saveOptions);
```

確保指定正確的路徑來儲存轉換後的 PDF。

### 使用 Aspose.Words for .NET 在視窗標題列中顯示文件標題的範例原始碼

以下是使用 Aspose.Words for .NET 在 PDF 文件的視窗標題列中顯示文件標題的完整原始碼：

```csharp

	//文檔目錄的路徑。
	string dataDir = "YOUR DOCUMENT DIRECTORY";
	Document doc = new Document(dataDir + "Rendering.docx");

	PdfSaveOptions saveOptions = new PdfSaveOptions { DisplayDocTitle = true };

	doc.Save(dataDir + "WorkingWithPdfSaveOptions.DisplayDocTitleInWindowTitlebar.pdf", saveOptions);
        
```
透過執行下列步驟，當使用 Aspose.Words for .NET 轉換為 PDF 時，您可以輕鬆地在視窗標題列中顯示文件標題。

### 經常問的問題

#### Q：Aspose.Words for .NET 的「在視窗標題列中顯示文件標題」功能是什麼？
Aspose.Words for .NET 的「在視窗標題列中顯示文件標題」功能可讓您在開啟產生的 PDF 文件時在視窗標題列中顯示文件標題。這使得您可以在閱讀環境中更輕鬆地識別和區分 PDF 文件。

#### Q：如何在 Aspose.Words for .NET 中使用此功能？
若要將此功能與 Aspose.Words for .NET 結合使用，請依照下列步驟操作：

使用載入文檔`Document`方法並指定要轉換為 PDF 的文件的路徑。

透過建立實例來配置 PDF 儲存選項`PdfSaveOptions`類別並設定`DisplayDocTitle`財產給`true`。這使得在轉換為 PDF 時可以在視窗標題列中顯示文件標題。

使用`Save`將文件轉換為 PDF 的方法，指定轉換選項。

#### Q：此功能是否會更改文件本身的內容？
不，此功能不會修改文件本身的內容。當文件以 PDF 文件開啟時，它僅會影響視窗標題列中文件標題的顯示。文件內容不變。

#### Q：是否可以自訂視窗標題列中顯示的文件標題？
是的，您可以透過更改視窗標題列中顯示的文件標題來自訂`Document.Title`將文件轉換為 PDF 之前的屬性。您可以使用字串設定所需的標題。呼叫前請務必設定標題`Save`轉換為 PDF 的方法。

#### Q：Aspose.Words 也支援哪些其他輸出格式進行文件轉換？
Aspose.Words for .NET 支援多種文件轉換輸出格式，例如 PDF、XPS、HTML、EPUB、MOBI、映像（JPEG、PNG、BMP、TIFF、GIF）等。還有其他人。您可以根據您的特定需求選擇合適的輸出格式。