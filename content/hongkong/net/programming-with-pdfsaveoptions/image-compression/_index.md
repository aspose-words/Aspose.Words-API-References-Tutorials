---
title: PDF 文件中的影像壓縮
linktitle: PDF 文件中的影像壓縮
second_title: Aspose.Words 文件處理 API
description: 使用 Aspose.Words for .NET 壓縮 PDF 文件中的影像的逐步指南。
type: docs
weight: 10
url: /zh-hant/net/programming-with-pdfsaveoptions/image-compression/
---

本文提供了有關如何透過 Aspose.Words for .NET 使用 PDF 文件中的影像壓縮功能的逐步指南。我們將詳細解釋程式碼的每一部分。在本教程結束時，您將能夠了解如何壓縮文件中的圖像並使用適當的圖像壓縮生成 PDF。

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

## 步驟 3：配置帶有影像壓縮的另存為 PDF 選項

要在轉換為 PDF 時壓縮影像，我們需要配置`PdfSaveOptions`目的。如果需要，我們可以設定影像壓縮類型、JPEG 品質和其他 PDF 合規性選項。

```csharp
PdfSaveOptions saveOptions = new PdfSaveOptions
{
ImageCompression = PdfImageCompression.Jpeg,
PreserveFormFields = true
};
```

## 步驟 4：使用影像壓縮將文件另存為 PDF

最後，我們可以使用先前配置的儲存選項將文件儲存為 PDF 格式。

```csharp
doc.Save(dataDir + "WorkingWithPdfSaveOptions.PdfImageCompression.pdf", saveOptions);
```

## 步驟 5：設定使用影像壓縮儲存為 PDF/A-2u 的選項

如果您想透過影像壓縮產生符合 PDF/A-2u 標準的 PDF，您可以設定其他儲存選項。

```csharp
PdfSaveOptions saveOptionsA2U = new PdfSaveOptions
{
Compliance = PdfCompliance.PdfA2u,
ImageCompression = PdfImageCompression.Jpeg,
JpegQuality=100, //使用 50% 質量的 JPEG 壓縮來減少檔案大小。
};
```

## 步驟 6：使用影像壓縮將文件另存為 PDF/A-2u

使用先前配置的其他儲存選項以 PDF/A-2u 格式儲存文件。

```csharp
doc.Save(dataDir + "WorkingWithPdfSaveOptions.PdfImageCompression_A2u.pdf", saveOptionsA2U);
```



就這樣 ！您已成功壓縮文件中的圖像，並使用 Aspose.Words for .NET 產生了具有正確圖像壓縮的 PDF。

### 使用 Aspose.Words for .NET 壓縮映像的範例原始程式碼

```csharp

	//文檔目錄的路徑。
	string dataDir = "YOUR DOCUMENT DIRECTORY";
	Document doc = new Document(dataDir + "Rendering.docx");

	PdfSaveOptions saveOptions = new PdfSaveOptions
	{
		ImageCompression = PdfImageCompression.Jpeg, PreserveFormFields = true
	};

	doc.Save(dataDir + "WorkingWithPdfSaveOptions.PdfImageCompression.pdf", saveOptions);

	PdfSaveOptions saveOptionsA2U = new PdfSaveOptions
	{
		Compliance = PdfCompliance.PdfA2u,
		ImageCompression = PdfImageCompression.Jpeg,
		JpegQuality = 100, //使用 50% 質量的 JPEG 壓縮來減少檔案大小。
	};

	

	doc.Save(dataDir + "WorkingWithPdfSaveOptions.PdfImageCompression_A2u.pdf", saveOptionsA2U);
	
```

## 結論

在本教學中，我們說明如何使用 Aspose.Words for .NET 壓縮 PDF 文件中的圖片。透過執行所述步驟，您可以輕鬆縮小 PDF 文件中影像的大小，並產生具有適當影像壓縮的 PDF。使用 Aspose.Words for .NET 的圖片壓縮功能來最佳化 PDF 文件的大小，同時保持影像品質。

### 經常問的問題

#### Q：什麼是 PDF 文件中的影像壓縮？
答：壓縮PDF文件中的圖片是縮小PDF文件中包含的圖片的大小，以減少PDF文件的整體大小。這減少了載入和查看 PDF 時所需的儲存空間並提高了效能。

#### Q：如何使用 Aspose.Words for .NET 壓縮 PDF 文件中的映像？
答：若要使用 Aspose.Words for .NET 壓縮 PDF 文件中的影像，請依照下列步驟操作：

建立一個實例`Document`指定 Word 文件路徑的類別。

建立一個實例`PdfSaveOptions`類別並設定`ImageCompression`財產給`PdfImageCompression.Jpeg`使用 JPEG 壓縮。

您也可以根據需要設定其他影像壓縮選項，例如 JPEG 品質。

使用`Save`的方法`Document`類別透過指定儲存選項將文件儲存為 PDF 格式。

#### Q：標準影像壓縮和 PDF/A-2u 影像壓縮有什麼區別？
答：標準影像壓縮可減少 PDF 文件中影像的大小，同時保留表單欄位。這會減少 PDF 檔案的整體大小，而不會影響表單欄位的功能。

PDF/A-2u 影像壓縮是一個附加選項，可讓您在套用影像壓縮時產生符合 PDF/A-2u 標準的 PDF 檔案。 PDF/A-2u 是存檔 PDF 文件的 ISO 標準，可確保文件的長期保存。
