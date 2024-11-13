---
title: 頁面儲存回調
linktitle: 頁面儲存回調
second_title: Aspose.Words 文件處理 API
description: 透過我們詳細的逐步指南，學習使用 Aspose.Words for .NET 將 Word 文件的每一頁儲存為單獨的 PNG 圖像。
type: docs
weight: 10
url: /zh-hant/net/programming-with-imagesaveoptions/page-saving-callback/
---
## 介紹

嘿！您是否曾經想過需要將 Word 文件的每一頁儲存為單獨的圖片？也許您想將大型報告分解為易於理解的視覺效果，或者您可能需要建立縮圖以進行預覽。無論您的原因是什麼，使用 Aspose.Words for .NET 都可以讓這項任務變得輕而易舉。在本指南中，我們將引導您完成設定頁面儲存回調以將文件的每個頁面儲存為單獨的 PNG 映像的過程。讓我們開始吧！

## 先決條件

在我們開始之前，請確保您具備以下條件：

1.  Aspose.Words for .NET：如果您還沒有安裝它，請從[這裡](https://releases.aspose.com/words/net/).
2. Visual Studio：任何版本都應該可以，但我將在本指南中使用 Visual Studio 2019。
3. C# 的基本知識：您需要對 C# 有基本的了解才能繼續學習。

## 導入命名空間

首先，我們需要導入必要的名稱空間。這有助於我們存取所需的類別和方法，而無需每次都鍵入完整的名稱空間。

```csharp
using System;
using Aspose.Words;
using Aspose.Words.Saving;
```

## 第 1 步：設定您的文件目錄

好吧，讓我們先定義文檔目錄的路徑。這是輸入 Word 文件所在的位置以及儲存輸出影像的位置。

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## 第 2 步：載入您的文檔

接下來，我們將載入您要處理的文件。確保您的文件（“Rendering.docx”）位於指定目錄中。

```csharp
Document doc = new Document(dataDir + "Rendering.docx");
```

## 步驟 3：設定影像儲存選項

我們需要配置保存影像的選項。在本例中，我們將頁面儲存為 PNG 檔案。

```csharp
ImageSaveOptions imageSaveOptions = new ImageSaveOptions(SaveFormat.Png)
{
    PageSet = new PageSet(new PageRange(0, doc.PageCount - 1)),
    PageSavingCallback = new HandlePageSavingCallback()
};
```

這裡，`PageSet`指定要儲存的頁面範圍，以及`PageSavingCallback`指向我們自訂的回調類別。

## 第四步：實現頁面保存回調

現在，讓我們實作處理每個頁面如何保存的回呼類別。

```csharp
private class HandlePageSavingCallback : IPageSavingCallback
{
    public void PageSaving(PageSavingArgs args)
    {
        args.PageFileName = string.Format(dataDir + "Page_{0}.png", args.PageIndex);
    }
}
```

這個類別實作了`IPageSavingCallback`接口，並在`PageSaving`方法中，我們為每個已儲存的頁面定義命名模式。

## 步驟 5：將文件另存為影像

最後，我們使用配置的選項來儲存文件。

```csharp
doc.Save(dataDir + "WorkingWithImageSaveOptions.PageSavingCallback.png", imageSaveOptions);
```

## 結論

現在你就擁有了！您已成功設定頁面儲存回調，使用 Aspose.Words for .NET 將 Word 文件的每一頁儲存為單獨的 PNG 圖片。該技術對於各種應用程式非常有用，從創建頁面預覽到為報告生成單獨的頁面圖像。 

快樂編碼！

## 常見問題解答

### 我可以將頁面儲存為 PNG 以外的格式嗎？  
是的，您可以透過變更不同的格式來儲存頁面，例如 JPEG、BMP 和 TIFF`SaveFormat`在`ImageSaveOptions`.

### 如果我只想保存特定頁面怎麼辦？  
您可以透過調整來指定要儲存的頁面`PageSet`參數輸入`ImageSaveOptions`.

### 是否可以自訂影像品質？  
絕對地！您可以設定屬性，例如`ImageSaveOptions.JpegQuality`控制輸出影像的品質。

### 如何有效率地處理大文檔？  
對於大型文檔，請考慮批次處理頁面以有效管理記憶體使用情況。

### 在哪裡可以找到有關 Aspose.Words for .NET 的更多資訊？  
查看[文件](https://reference.aspose.com/words/net/)取得全面的指南和範例。