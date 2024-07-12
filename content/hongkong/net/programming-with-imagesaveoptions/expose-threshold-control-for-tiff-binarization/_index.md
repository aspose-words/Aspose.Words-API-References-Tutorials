---
title: 公開 Tiff 二值化的閾值控制
linktitle: 公開 Tiff 二值化的閾值控制
second_title: Aspose.Words 文件處理 API
description: 了解如何使用 Aspose.Words for .NET 控制 TIFF 二值化閾值。獲得更高品質圖像的完整教程。
type: docs
weight: 10
url: /zh-hant/net/programming-with-imagesaveoptions/expose-threshold-control-for-tiff-binarization/
---
在本教程中，我們將探索使用 Aspose.Words for .NET 為「TIFF 二值化閾值控制曝光」功能提供的 C# 原始程式碼。此功能可讓您在將文件轉換為 TIFF 格式時控制二值化閾值。

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
ImageSaveOptions saveOptions = new ImageSaveOptions(SaveFormat.Tiff)
{
TiffCompression = TiffCompression.Ccitt3,
ImageColorMode = ImageColorMode.Grayscale,
TiffBinarizationMethod = ImageBinarizationMethod.FloydSteinbergDithering,
ThresholdForFloydSteinbergDithering = 254
};
```

在此步驟中，我們配置映像的備份選項。我們創建一個新的`ImageSaveOptions`指定所需儲存格式的對象，此處「Tiff」表示 TIFF 格式。我們還設定壓縮選項、影像色彩模式和具有指定二值化閾值的 TIFF 二值化方法。

## 第 4 步：備份映像

```csharp
doc.Save(dataDir + "WorkingWithImageSaveOptions.ExposeThresholdControlForTiffBinarization.tiff", saveOptions);
```

在最後一步中，我們使用以下命令將文件影像儲存為 TIFF 格式：`Save`方法並將路徑傳遞到輸出檔案以及指定的儲存選項。

現在，您可以執行原始程式碼將文件轉換為 TIFF 格式，同時使用指定選項控制二值化閾值。產生的檔案將保存在指定目錄中，名稱為「WorkingWithImageSaveOptions.ExposeThresholdControlForTiffBinarization.tiff」。

### 範例原始碼公開 Tiff 二值化的閾值控制

```csharp 

//文檔目錄的路徑
 string dataDir = "YOUR DOCUMENT DIRECTORY"; 

Document doc = new Document(dataDir + "Rendering.docx");

ImageSaveOptions saveOptions = new ImageSaveOptions(SaveFormat.Tiff)
{
	TiffCompression = TiffCompression.Ccitt3,
	ImageColorMode = ImageColorMode.Grayscale,
	TiffBinarizationMethod = ImageBinarizationMethod.FloydSteinbergDithering,
	ThresholdForFloydSteinbergDithering = 254
};

doc.Save(dataDir + "WorkingWithImageSaveOptions.ExposeThresholdControlForTiffBinarization.tiff", saveOptions);
            
        
```

### 結論

在本教程中，我們使用 Aspose.Words for .NET 探索了 TIFF 二值化閾值控制的曝光功能。我們學習如何在將文件轉換為 TIFF 格式時控制二值化閾值。

當您想要調整二值化閾值以獲得具有更好品質和清晰度的 TIFF 影像時，此功能非常有用。透過使用儲存選項指定二值化閾值，您可以獲得根據您的需求自訂的自訂結果。

Aspose.Words for .NET 提供了多種文件操作和產生的進階功能。公開 TIFF 二值化閾值控制是它為您提供的眾多強大工具之一。

請隨意將此功能合併到您的 Aspose.Words for .NET 專案中，以透過精確的二值化閾值控制獲得高品質的 TIFF 影像。