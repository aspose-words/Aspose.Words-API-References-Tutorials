---
title: 頁面儲存回調
linktitle: 頁面儲存回調
second_title: Aspose.Words 文件處理 API
description: 了解如何使用 Aspose.Words for .NET 自訂將文件頁面儲存為圖片。
type: docs
weight: 10
url: /zh-hant/net/programming-with-imagesaveoptions/page-saving-callback/
---

在本教程中，我們將探索提供的 C# 原始程式碼，用於將頁面保存回呼與 .NET 的 Aspose.Words 圖像保存選項結合使用。此功能可讓您在將文件的每一頁儲存為映像時執行自訂操作。

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
ImageSaveOptions imageSaveOptions = new ImageSaveOptions(SaveFormat.Png)
{
     PageSet = new PageSet(new PageRange(0, doc.PageCount - 1)),
     PageSavingCallback = new HandlePageSavingCallback()
};
```

在此步驟中，我們透過建立新的圖像來配置圖像保存選項`ImageSaveOptions`目的。我們指定所需的備份格式，此處「Png」為PNG 格式。我們用`PageSet`指定要儲存的頁面範圍，這裡是從文件的第一頁到最後一頁（`doc.PageCount - 1`）。我們還設定了`PageSavingCallback`到一個實例`HandlePageSavingCallback`，這是一個處理頁面保存回調的自訂類別。

## 第四步：實現保存頁面回調

```csharp
public class HandlePageSavingCallback : IPageSavingCallback
{
     public void PageSaving(PageSavingArgs args)
     {
         //在此實施您的自訂操作
         //您可以透過「args.PageIndex」屬性存取頁面訊息
         //您也可以單獨更改每個頁面的儲存選項
     }
}
```

在這一步中，我們實現`HandlePageSavingCallback`實現的類別`IPageSavingCallback`介面.您可以透過在中新增您的特定操作來自訂此類`PageSaving`方法。您可以透過以下方式存取頁面信息`args.PageIndex`的財產`PageSavingArgs`作為參數傳遞的物件。

## 步驟 5：將頁面另存為圖像

```csharp
doc.Save(dataDir + "WorkingWithImageSaveOptions.PageSavingCallback.png", imageSaveOptions);
```

在最後一步中，我們使用以下命令將文件的每一頁儲存為映像：`Save`方法並將路徑傳遞給輸出文件`.png`擴展名以及指定的儲存選項。

現在，您可以運行原始程式碼以在將文件的每一頁儲存為映像時執行自訂操作。產生的檔案將保存在指定目錄中，名稱為「WorkingWithImageSaveOptions.PageSavingCallback.png」。

### 使用 Aspose.Words for .NET 進行頁面儲存回呼的範例原始碼


```csharp 
//文檔目錄的路徑
string dataDir = "YOUR DOCUMENT DIRECTORY"; 


Document doc = new Document(dataDir + "Rendering.docx");

ImageSaveOptions imageSaveOptions = new ImageSaveOptions(SaveFormat.Png)
{
	PageSet = new PageSet(new PageRange(0, doc.PageCount - 1)),
	PageSavingCallback = new HandlePageSavingCallback()
};

doc.Save(dataDir + "WorkingWithImageSaveOptions.PageSavingCallback.png", imageSaveOptions);
        
```

## 結論

在本教程中，我們探索了 .NET 的 Aspose.Words 圖像保存選項的頁面保存回呼功能。我們學習瞭如何在將文件的每一頁儲存為影像時執行自訂操作。

當您想要在轉換為圖像時對每個頁面執行特定操作時，此功能非常有用。您可以存取頁面資訊並使用它來自訂備份選項或執行其他特定於頁面的處理。

Aspose.Words for .NET 提供了廣泛的文件操作和產生進階功能。儲存頁面提醒是眾多功能強大的工具之一，它使您可以自訂將頁面儲存到圖像的過程。