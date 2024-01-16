---
title: 取得 Jpeg 頁面範圍
linktitle: 取得 Jpeg 頁面範圍
second_title: Aspose.Words 文件處理 API
description: 了解如何使用 Aspose.Words for .NET 取得一系列 JPEG 頁面。提取自訂圖像的完整教程。
type: docs
weight: 10
url: /zh-hant/net/programming-with-imagesaveoptions/get-jpeg-page-range/
---

在本教學中，我們將探索為 Aspose.Words for .NET 的「取得 JPEG 頁面範圍」功能提供的 C# 原始碼。此功能可讓您將文件的特定範圍的頁面轉換為 JPEG 格式的影像。

## 第一步：建構環境

在開始之前，請確保您已使用 Aspose.Words for .NET 設定開發環境。確保您已新增必要的引用並匯入適當的命名空間。

## 第 2 步：載入文檔

```csharp
//文檔目錄的路徑
string dataDir = "YOUR DOCUMENTS DIRECTORY";

Document doc = new Document(dataDir + "Rendering.docx");
```

在此步驟中，我們使用以下命令載入文檔`Document`方法並傳遞要載入的 DOCX 檔案的路徑。

## 步驟 3：設定映像備份選項

```csharp
ImageSaveOptions options = new ImageSaveOptions(SaveFormat.Jpeg);
options. PageSet = new PageSet(0);
options. ImageBrightness = 0.3f;
options. ImageContrast = 0.7f;
options. HorizontalResolution = 72f;
```

在此步驟中，我們配置映像的備份選項。我們創建一個新的`ImageSaveOptions`物件指定所需的儲存格式，此處「Jpeg」表示 JPEG 格式。我們還使用以下命令設定要轉換的頁面範圍`PageSet`目的。最後，我們使用以下命令調整影像的亮度和對比度`ImageBrightness`和`ImageContrast`屬性，分別。我們還使用以下命令更改水平分辨率`HorizontalResolution`財產。

## 第 4 步：備份映像

```csharp
doc.Save(dataDir + "WorkingWithImageSaveOptions.GetJpegPageRange.jpeg", options);
```

在最後一步中，我們使用以下命令將指定頁面範圍的圖像儲存為 JPEG 格式：`Save`方法並將路徑傳遞到輸出檔案以及指定的儲存選項。

現在，您可以運行原始程式碼將文件中特定範圍的頁面轉換為 JPEG 影像。產生的檔案將會儲存在指定目錄中，名稱為「WorkingWithImageSaveOptions.GetJpegPageRange.jpeg」。

### 使用 Aspose.Words For .NET 取得 Jpeg 頁面範圍的範例原始程式碼

```csharp 
 //文檔目錄的路徑
 string dataDir = "YOUR DOCUMENT DIRECTORY"; 

Document doc = new Document(dataDir + "Rendering.docx");

ImageSaveOptions options = new ImageSaveOptions(SaveFormat.Jpeg);

//將“PageSet”設定為“0”以僅轉換文件的第一頁。
options.PageSet = new PageSet(0);

//更改影像的亮度和對比度。
//兩者的評分範圍均為 0-1，預設值為 0.5。
options.ImageBrightness = 0.3f;
options.ImageContrast = 0.7f;

//更改水平分辨率。
//對於 96dpi 的分辨率，這些屬性的預設值為 96.0。
options.HorizontalResolution = 72f;

doc.Save(dataDir + "WorkingWithImageSaveOptions.GetJpegPageRange.jpeg", options);
            
        
```

## 結論

在本教學中，我們探索了使用 Aspose.Words for .NET 取得 JPEG 頁面範圍的功能。我們學習如何將文件的特定範圍的頁面轉換為 JPEG 格式的影像，同時自訂儲存選項。

當您想要從文件中提取特定頁面並將其另存為 JPEG 影像時，此功能非常有用。您還可以調整影像的亮度、對比度和水平解析度以實現個人化的結果。

Aspose.Words for .NET 提供了廣泛的文件操作和產生進階功能。取得 JPEG 頁面範圍是它為您提供的眾多強大工具之一。

請隨意將此功能整合到您的 Aspose.Words for .NET 專案中，以便從文件中取得高品質的 JPEG 影像。