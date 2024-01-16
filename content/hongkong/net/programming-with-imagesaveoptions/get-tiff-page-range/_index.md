---
title: 取得 Tiff 頁面範圍
linktitle: 取得 Tiff 頁面範圍
second_title: Aspose.Words 文件處理 API
description: 了解如何使用 Aspose.Words for .NET 擷取一系列 TIFF 頁面。自訂 TIFF 檔案的完整教學。
type: docs
weight: 10
url: /zh-hant/net/programming-with-imagesaveoptions/get-tiff-page-range/
---

在本教程中，我們將探索提供的 C# 原始程式碼，以使用 Aspose.Words for .NET 取得一系列 TIFF 頁面。此功能可讓您從文件中提取特定範圍的頁面並將其儲存為 TIFF 檔案。

## 第一步：建構環境

在開始之前，請確保您已使用 Aspose.Words for .NET 設定開發環境。確保您已新增必要的引用並匯入適當的命名空間。

## 第 2 步：載入文檔

```csharp
//文檔目錄的路徑
string dataDir = "YOUR DOCUMENTS DIRECTORY";

Document doc = new Document(dataDir + "Rendering.docx");
```

在此步驟中，我們使用以下命令載入文檔`Document`方法並傳遞要載入的 DOCX 檔案的路徑。

## 步驟 3：將完整文件儲存為 TIFF 格式

```csharp
doc.Save(dataDir + "WorkingWithImageSaveOptions.MultipageTiff.tiff");
```

在此步驟中，我們使用以下命令將完整文件儲存為 TIFF 格式：`Save`方法並指定帶有擴展名的輸出檔案的路徑`.tiff`.

## 步驟 4：設定頁面範圍的備份選項

```csharp
ImageSaveOptions saveOptions = new ImageSaveOptions(SaveFormat.Tiff)
{
PageSet = new PageSet(new PageRange(0, 1)),
TiffCompression = TiffCompression.Ccitt4,
Resolution = 160
};
```

在此步驟中，我們為特定頁面範圍配置備份選項。我們創建一個新的`ImageSaveOptions`指定所需儲存格式的對象，此處「Tiff」表示 TIFF 格式。我們用`PageSet`指定我們要擷取的頁面範圍，這裡是從第 0 頁到第 1 頁（含）。我們也將 TIFF 壓縮設定為`Ccitt4`解析度為 160 dpi。

## 步驟 5：將頁面範圍儲存為 TIFF

```csharp
doc.Save(dataDir + "WorkingWithImageSaveOptions.GetTiffPageRange.tiff", saveOptions);
```

在最後一步中，我們使用以下命令將指定的頁面範圍儲存為 TIFF 格式：`Save`方法並將路徑傳遞給輸出文件`.tiff`擴展名以及指定的儲存選項。

現在，您可以運行原始程式碼以從文件中取得特定範圍的頁面並將它們儲存為 TIFF 檔案。產生的文件將保存在指定目錄中，完整文件的名稱為“WorkingWithImageSaveOptions.MultipageTiff.tiff”，指定頁面範圍的名稱為“WorkingWithImageSaveOptions.GetTiffPageRange.tiff”。

### 使用 Aspose.Words for .NET 取得 Tiff 頁面範圍的範例原始碼

```csharp 

//文檔目錄的路徑
string dataDir = "YOUR DOCUMENT DIRECTORY"; 

Document doc = new Document(dataDir + "Rendering.docx");

doc.Save(dataDir + "WorkingWithImageSaveOptions.MultipageTiff.tiff");



ImageSaveOptions saveOptions = new ImageSaveOptions(SaveFormat.Tiff)
{
	PageSet = new PageSet(new PageRange(0, 1)), TiffCompression = TiffCompression.Ccitt4, Resolution = 160
};

doc.Save(dataDir + "WorkingWithImageSaveOptions.GetTiffPageRange.tiff", saveOptions);
            
            
        
```

## 結論

在本教學中，我們探索了使用 Aspose.Words for .NET 取得一系列 TIFF 頁面的功能。我們學習如何從文件中提取特定範圍的頁面並將其儲存為 TIFF 檔案。

當您只想從文件中提取某些頁面並將其儲存為標準影像格式（例如 TIFF）時，此功能非常有用。您還可以自訂壓縮和解析度選項以獲得最佳品質的 TIFF 檔案。

Aspose.Words for .NET 提供了廣泛的文件操作和產生進階功能。取得 TIFF 頁面範圍是它為您提供的眾多強大工具之一。

請隨意將此功能整合到您的 Aspose.Words for .NET 專案中，以從文件中提取特定範圍的頁面並以 TIFF 格式儲存。