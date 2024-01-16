---
title: 將 Word 文檔結構匯出為 PDF 文檔
linktitle: 將 Word 文檔結構匯出為 PDF 文檔
second_title: Aspose.Words 文件處理 API
description: 使用 Aspose.Words for .NET 將 Word 文件結構匯出為 PDF 文件的逐步指南。
type: docs
weight: 10
url: /zh-hant/net/programming-with-pdfsaveoptions/export-document-structure/
---

本文提供了有關如何透過 Aspose.Words for .NET 使用「將 Word 文件結構匯出為 PDF 文件」功能的逐步指南。我們將詳細解釋程式碼的每一部分。在本教學結束時，您將能夠了解如何匯出文件結構並產生文件結構可見的 PDF。

在開始之前，請確保您已在專案中安裝並設定了 Aspose.Words for .NET 程式庫。您可以在 Aspose 網站上找到庫和安裝說明。

## 步驟1：定義文檔目錄

首先，您需要定義文件所在目錄的路徑。代替`"YOUR DOCUMENT DIRECTORY"`與文檔目錄的實際路徑。

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## 第2步：上傳文件

接下來，我們需要載入我們想要處理的文檔。在此範例中，我們假設文件名稱為「Paragraphs.docx」並且位於指定的文件目錄中。

```csharp
Document doc = new Document(dataDir + "Paragraphs.docx");
```

## 步驟 3：配置另存為 PDF 選項

要匯出文件結構並在編輯 PDF 文件時使該結構在 Adobe Acrobat Pro 的「內容」導覽窗格中可見，我們需要配置`PdfSaveOptions`對象與`ExportDocumentStructure`屬性設定為`true`.

```csharp
PdfSaveOptions saveOptions = new PdfSaveOptions { ExportDocumentStructure = true };
```

## 步驟 4：將文件儲存為具有文件結構的 PDF

最後，我們可以使用先前配置的儲存選項將文件儲存為 PDF 格式。

```csharp
doc.Save(dataDir + "WorkingWithPdfSaveOptions.ExportDocumentStructure.pdf", saveOptions);
```

就這樣 ！您已成功匯出文件結構並使用 Aspose.Words for .NET 產生了文件結構可見的 PDF。

### 使用 Aspose.Words for .NET 匯出文件結構的範例原始碼


```csharp

            //文檔目錄的路徑。
			string dataDir = "YOUR DOCUMENT DIRECTORY";
            Document doc = new Document(dataDir + "Paragraphs.docx");

            //文件大小將增加，並且結構將在「內容」導覽窗格中可見
            //Adobe Acrobat Pro，同時編輯 .pdf。
            PdfSaveOptions saveOptions = new PdfSaveOptions { ExportDocumentStructure = true };

            doc.Save(dataDir + "WorkingWithPdfSaveOptions.ExportDocumentStructure.pdf", saveOptions);
        
```


## 結論

在本教學中，我們解釋如何使用 Aspose.Words for .NET 將 Word 文件的結構匯出到 PDF 文件。透過依照概述的步驟操作，您可以輕鬆產生文件結構可見的 PDF，從而更輕鬆地瀏覽和搜尋文件。使用 Aspose.Words for .NET 的功能匯出 Word 文件的結構並建立結構良好的 PDF。

### 經常問的問題

#### Q：什麼是將Word文檔的結構匯出為PDF文檔？
答：將 Word 文件的結構匯出到 PDF 文件會建立具有可見文件結構的 PDF。文件結構通常包括標題、章節、段落和文件的其他結構化元素。此結構對於在 PDF 文件中進行導航和搜尋非常有用。

#### Q：如何使用 Aspose.Words for .NET 將 Word 文件的結構匯出為 PDF 文件？
答：要使用 Aspose.Words for .NET 將 Word 文檔的結構匯出為 PDF 文檔，請依照下列步驟操作：

建立一個實例`Document`指定 Word 文件路徑的類別。

建立一個實例`PdfSaveOptions`類別並設定`ExportDocumentStructure`財產給`true`。這將匯出文件結構並使其在編輯 PDF 文件時在 Adobe Acrobat Pro 的「內容」導覽窗格中可見。

使用`Save`的方法`Document`類別透過指定儲存選項將文件儲存為 PDF 格式。

#### Q：如何使用 Adobe Acrobat Pro 查看 PDF 文件的結構？
答：要使用 Adobe Acrobat Pro 檢視 PDF 文件的結構，請依照下列步驟操作：

在 Adobe Acrobat Pro 中開啟 PDF 文件。

在左側導覽列中，按一下「內容」圖標，顯示「內容」導覽窗格。

在「內容」導覽窗格中，您將看到包含標題、部分和其他結構化元素的文件結構。