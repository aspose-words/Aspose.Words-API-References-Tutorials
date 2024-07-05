---
title: 透過縮減影像取樣來減少 PDF 文件大小
linktitle: 透過縮減影像取樣來減少 PDF 文件大小
second_title: Aspose.Words 文件處理 API
description: 了解在使用 Aspose.Words for .NET 轉換為 PDF 時如何透過縮減影像取樣來減少 pdf 文件大小。
type: docs
weight: 10
url: /zh-hant/net/programming-with-pdfsaveoptions/downsampling-images/
---

在本教學中，我們將引導您完成在使用 Aspose.Words for .NET 轉換為 PDF 時透過縮減影像取樣來減少 pdf 文件大小的步驟。這會減小產生的 PDF 檔案的大小。請依照以下步驟操作：

## 第 1 步：載入文檔

首先上傳您想要轉換為 PDF 的文件：

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
Document doc = new Document(dataDir + "Rendering.docx");
```

請務必指定文件的正確路徑。

## 步驟 2：設定 PDF 儲存選項

建立 PdfSaveOptions 類別的實例並設定映像縮小選項：

```csharp
PdfSaveOptions saveOptions = new PdfSaveOptions
{
DownsampleOptions = { Resolution = 36, ResolutionThreshold = 128 }
};
```

這`Resolution`屬性指定影像的目標解析度和`ResolutionThreshold`屬性指定最小分辨率，低於該分辨率影像將不會按比例縮小。

## 步驟 3：將文件轉換為 PDF

使用`Save`將文件轉換為 PDF 並指定儲存選項的方法：

```csharp
doc.Save(dataDir + "WorkingWithPdfSaveOptions.DownsamplingImages.pdf", saveOptions);
```

確保指定正確的路徑來儲存轉換後的 PDF。

### 使用 Aspose.Words for .NET 對影像進行下取樣的範例原始碼

```csharp

	//文檔目錄的路徑。
	string dataDir = "YOUR DOCUMENT DIRECTORY";
	Document doc = new Document(dataDir + "Rendering.docx");

	//我們可以設定下採樣的最小閾值。
	//該值將防止輸入文件中的第二個影像被下採樣。
	PdfSaveOptions saveOptions = new PdfSaveOptions
	{
		DownsampleOptions = { Resolution = 36, ResolutionThreshold = 128 }
	};

	doc.Save(dataDir + "WorkingWithPdfSaveOptions.DownsamplingImages.pdf", saveOptions);

```

透過執行這些步驟，您可以在使用 Aspose.Words for .NET 轉換為 PDF 時輕鬆降低影像解析度。

## 結論

在本教程中，我們解釋了在使用 Aspose.Words for .NET 轉換為 PDF 時如何透過圖像採樣來減少 PDF 文件的大小。透過執行所述步驟，您可以輕鬆降低影像的解析度和產生的 PDF 檔案的大小。請務必指定文件的正確路徑並根據需要配置影像採樣選項。減小 PDF 檔案大小可以更輕鬆地在不同平台上共用、儲存和快速載入檔案。使用 Aspose.Words for .NET 享受透過影像取樣減小 PDF 文件大小的好處。

### 經常問的問題

#### Q：什麼是透過影像採樣來減少 PDF 文件的大小？
答：透過影像取樣減小 PDF 文件大小是在轉換為 PDF 時透過降低影像的解析度來減少產生的 PDF 檔案的大小。這優化了儲存空間的使用，並使共享和傳輸 PDF 檔案變得更加容易。

#### Q：如何使用 Aspose.Words for .NET 透過影像取樣來減少 PDF 文件大小？
答：若要使用 Aspose.Words for .NET 透過影像取樣來減少 PDF 文件大小，請依照下列步驟操作：

透過替換設定文件所在的目錄路徑`"YOUR DOCUMENTS DIRECTORY"`與文檔目錄的實際路徑。

使用以下命令載入要轉換為 PDF 的文檔`Document` class 並指定指定文檔目錄中文檔的路徑。

透過建立一個實例來配置另存為 PDF 選項`PdfSaveOptions`類別並使用設定影像取樣選項`DownsampleOptions`財產。您可以使用以下命令指定影像的目標分辨率`Resolution`屬性並設定最小解析度閾值，超過該閾值影像將不會使用`ResolutionThreshold`財產。

使用以下命令將文件儲存為 PDF 格式`Save`的方法`Document`指定路徑和儲存選項的類別。

#### Q：透過影像採樣減小 PDF 文件大小有什麼好處？
答：透過影像採樣減小 PDF 文件大小的好處是：

減少 PDF 文件大小：影像採樣會降低 PDF 文件中影像的分辨率，從而顯著減少 PDF 文件大小。這使得共享和傳輸文件變得容易，尤其是透過電子郵件或線上。

優化儲存空間：縮小 PDF 檔案的大小有助於優化儲存空間的使用，尤其是當您有許多包含高解析度影像的 PDF 檔案時。

效能改進：較小的 PDF 檔案載入速度更快，並且可以在不同裝置上更快地開啟和檢視。