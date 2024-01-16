---
title: 格式 1Bpp 索引
linktitle: 格式 1Bpp 索引
second_title: Aspose.Words 文件處理 API
description: 了解如何格式化使用 Aspose.Words for .NET 索引的 1 bpp 映像。低色彩深度影像的完整教學。
type: docs
weight: 10
url: /zh-hant/net/programming-with-imagesaveoptions/format-1bpp-indexed/
---
在本教學中，我們將探索為 Aspose.Words for .NET 的「Format 1Bpp Indexed」功能提供的 C# 原始碼。此功能可讓您將文件中的影像格式化為 PNG 格式，色彩深度為每像素 1 位元 (1 bpp)，並採用索引色彩模式。

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
ImageSaveOptions saveOptions = new ImageSaveOptions(SaveFormat.Png)
{
     PageSet = new PageSet(1),
     ImageColorMode = ImageColorMode.BlackAndWhite,
     PixelFormat = ImagePixelFormat.Format1bppIndexed
};
```

在此步驟中，我們配置映像的備份選項。我們創建一個新的`ImageSaveOptions`物件指定所需的儲存格式，此處「Png」表示 PNG 格式。我們也定義了要包含在影像中的頁面、黑白色彩模式和索引 1 bpp 像素格式。

## 第 4 步：備份映像

```csharp
doc.Save(dataDir + "WorkingWithImageSaveOptions.Format1BppIndexed.Png", saveOptions);
```

在最後一步中，我們使用以下命令將文件圖像儲存為 PNG 格式`Save`方法並將路徑傳遞到輸出檔案以及指定的儲存選項。

現在，您可以執行原始程式碼以將文件影像格式化為 PNG 格式，索引色彩深度為 1 bpp。產生的檔案將保存在指定目錄中，名稱為「WorkingWithImageSaveOptions.Format1BppIndexed.Png」。

### 使用 Aspose.Words for .NET 進行索引的格式 1Bpp 的範例原始碼

```csharp 
 
			 //文檔目錄的路徑
			 string dataDir = "YOUR DOCUMENT DIRECTORY"; 
            
            Document doc = new Document(dataDir + "Rendering.docx");

            ImageSaveOptions saveOptions = new ImageSaveOptions(SaveFormat.Png)
            {
                PageSet = new PageSet(1),
                ImageColorMode = ImageColorMode.BlackAndWhite,
                PixelFormat = ImagePixelFormat.Format1bppIndexed
            };

            doc.Save(dataDir + "WorkingWithImageSaveOptions.Format1BppIndexed.Png", saveOptions);
            
        
```

### 結論

在本教學中，我們探索了 Aspose.Words for .NET 的 1Bpp 索引格式功能。我們學習如何以每像素 1 位元 (1 bpp) 的色彩深度和索引色彩模式對 PNG 格式的文件中的影像進行格式化。

當您想要取得低色彩深度和小檔案大小的影像時，此功能非常有用。 1Bpp 索引格式允許使用索引調色板來表示圖像，這對於某些特定應用程式可能是有益的。

Aspose.Words for .NET 為文件操作和產生提供了廣泛的進階功能。 1Bpp 索引格式是您可以使用的眾多強大工具之一。