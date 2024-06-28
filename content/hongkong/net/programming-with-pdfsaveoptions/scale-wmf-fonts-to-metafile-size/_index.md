---
title: 透過將 Wmf 字體縮放到圖元檔案大小來減少 PDF 大小
linktitle: 透過將 Wmf 字體縮放到圖元檔案大小來減少 PDF 大小
second_title: Aspose.Words 文件處理 API
description: 使用 Aspose.Words for .NET 轉換為 PDF 時，透過將 wmf 字體縮放為圖元檔案大小來減少 pdf 大小的逐步指南。
type: docs
weight: 10
url: /zh-hant/net/programming-with-pdfsaveoptions/scale-wmf-fonts-to-metafile-size/
---

本文提供了有關如何使用 Aspose.Words for .NET 將 wmf 字體縮放到圖元檔案大小功能來減小 pdf 大小的逐步指南。我們將詳細解釋程式碼的每一部分。在本教程結束時，您將能夠了解如何在轉換為 PDF 時啟用或停用 WMF 字體縮放。

在開始之前，請確保您已在專案中安裝並設定了 Aspose.Words for .NET 程式庫。您可以在 Aspose 網站上找到庫和安裝說明。

## 步驟1：定義文檔目錄

首先，您需要定義文件所在目錄的路徑。代替`"YOUR DOCUMENT DIRECTORY"`與文檔目錄的實際路徑。

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## 第2步：上傳文件

接下來，我們需要載入我們想要處理的文檔。在此範例中，我們假設文件名稱為「WMF with text.docx」並且位於指定的文件目錄中。

```csharp
Document doc = new Document(dataDir + "WMF with text.docx");
```

## 步驟 3：設定圖元檔案渲染選項

要啟用或停用 WMF 字體縮放到圖元檔案大小，我們需要配置`MetafileRenderingOptions`目的。在此範例中，我們透過設定禁用字體縮放`ScaleWmfFontsToMetafileSize`財產給`false`.

```csharp
MetafileRenderingOptions metafileRenderingOptions = new MetafileRenderingOptions
{
     ScaleWmfFontsToMetafileSize=false
};
```

## 步驟 4：使用圖元檔案渲染選項配置另存為 PDF 選項

最後，我們可以使用先前配置的圖元檔案渲染選項來配置「儲存為 PDF」選項。

```csharp
PdfSaveOptions saveOptions = new PdfSaveOptions { MetafileRenderingOptions = metafileRenderingOptions };
```

## 步驟 5：使用圖元檔案渲染選項將文件另存為 PDF

使用先前配置的儲存選項將文件儲存為 PDF 格式。

```csharp
doc.Save(dataDir + "WorkingWithPdfSaveOptions.ScaleWmfFontsToMetafileSize.pdf", saveOptions);
```

就這樣 ！您已在轉換時成功啟用或停用 WMF 字體縮放至圖元檔案大小

使用 Aspose.Words for .NET 的 PDF 文件。

### 使用 Aspose.Words for .NET 將 WMF 字體縮放為圖元檔案大小的範例原始程式碼

```csharp

	//文檔目錄的路徑。
	string dataDir = "YOUR DOCUMENT DIRECTORY";
	Document doc = new Document(dataDir + "WMF with text.docx");

	MetafileRenderingOptions metafileRenderingOptions = new MetafileRenderingOptions
	{
		ScaleWmfFontsToMetafileSize = false
	};

	//如果 Aspose.Words 無法正確將某些圖元檔案記錄渲染為向量圖形
	//然後Aspose.Words 將此圖元檔案呈現為點陣圖。
	PdfSaveOptions saveOptions = new PdfSaveOptions { MetafileRenderingOptions = metafileRenderingOptions };

	doc.Save(dataDir + "WorkingWithPdfSaveOptions.ScaleWmfFontsToMetafileSize.pdf", saveOptions);
	
        
```

## 結論

在本教學中，我們解釋如何使用 Aspose.Words for .NET 在 PDF 文件中啟用或停用將 WMF 字體大小調整為圖元檔案大小。透過執行所述步驟，您可以輕鬆控制在轉換為 PDF 文件時是否應調整 WMF 字體大小以符合圖元檔案大小。這可以幫助您減少生成的 PDF 文件的大小並提高渲染效能。請務必指定文件的正確路徑並根據需要配置圖元文件渲染選項。

### 經常問的問題

#### Q：什麼是在 PDF 文件中將 WMF 字體大小調整為圖元檔案大小？
答：將 WMF 字體大小調整為 PDF 文件中的圖元文件大小是一項功能，用於控制在轉換為 PDF 文件時是否應縮放 WMF 字體以匹配圖元文件大小。啟用此功能後，WMF 字體將縮放以符合圖元檔案的大小，這可能會減少生成的 PDF 文件的大小。

#### Q：如何使用 Aspose.Words for .NET 啟用或停用將 PDF 文件中的 WMF 字體大小調整為圖元檔案大小？
答：若要使用 Aspose.Words for .NET 在 PDF 文件中啟用或停用將 WMF 字體大小調整為圖元檔案大小，請依照下列步驟操作：

透過替換設定文件所在的目錄路徑`"YOUR DOCUMENT DIRECTORY"`與文檔目錄的實際路徑。

使用以下命令載入要處理的文檔`Document`類別並指定指定文檔目錄中Word文檔的路徑。

透過建立圖元檔案的實例來配置圖元檔案渲染選項`MetafileRenderingOptions`類別並設定`ScaleWmfFontsToMetafileSize`財產給`true`啟用 WMF 字體縮放至圖元檔案大小，或`false`停用此功能。

透過建立一個實例來配置另存為 PDF 選項`PdfSaveOptions`類別並使用先前配置的圖元檔案渲染選項。

使用以下命令將文件儲存為 PDF 格式`Save`的方法`Document`類別指定路徑和儲存選項。

#### Q：在 PDF 文件中將 WMF 字體大小調整為圖元檔案大小有什麼好處？
答：在 PDF 文件中將 WMF 字體大小調整為圖元文件大小的優點是：

PDF 檔案大小減少：將 WMF 字體大小調整為圖元檔案大小可以透過將字體大小適應圖元檔案需求來減少生成的 PDF 文件的大小。

改進的效能：透過將 WMF 字體的大小調整為圖元檔案的尺寸，PDF 文件的渲染可以更快、更有效率。