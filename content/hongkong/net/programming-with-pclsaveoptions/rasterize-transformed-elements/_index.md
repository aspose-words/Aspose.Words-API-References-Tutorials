---
title: 柵格化變換的元素
linktitle: 柵格化變換的元素
second_title: Aspose.Words 文件處理 API
description: 了解在使用 Aspose.Words for .NET 轉換為 PCL 格式時如何停用轉換元素的光柵化。
type: docs
weight: 10
url: /zh-hant/net/programming-with-pclsaveoptions/rasterize-transformed-elements/
---

Aspose.Words for .NET 是一個功能強大的程式庫，用於在 C# 應用程式中建立、操作和轉換 Word 文件。 Aspose.Words 提供的功能之一是能夠在將文件轉換為不同格式時對轉換後的元素進行光柵化。在本指南中，我們將向您展示如何使用 Aspose.Words for .NET 的 C# 原始程式碼在將文件轉換為 PCL 格式時停用轉換元素的光柵化。

## 了解 Aspose.Words 函式庫

在深入研究程式碼之前，了解 .NET 的 Aspose.Words 函式庫非常重要。 Aspose.Words 是一個受歡迎的函式庫，它讓 Word 文件的文字處理變得簡單有效率。它提供了用於建立、編輯和轉換 Word 文件的廣泛功能，包括支援在轉換過程中對轉換後的元素進行光柵化。

## 載入Word文檔

第一步是載入要轉換為 PCL 格式的 Word 文件。使用 Document 類別從來源檔案載入文件。這是一個例子：

```csharp
Document doc = new Document(dataDir + "Rendering.docx");
```

在此範例中，我們載入位於文件目錄中的「Rendering.docx」文件。

## 配置備份選項

下一步是配置轉換為 PCL 格式的儲存選項。使用 PclSaveOptions 類別並將 RasterizeTransformedElements 屬性設為 false。操作方法如下：

```csharp
PclSaveOptions saveOptions = new PclSaveOptions
{
     SaveFormat = SaveFormat.Pcl,
     RasterizeTransformedElements = false
};
```

我們建立一個新的 PclSaveOptions 物件並將 SaveFormat 屬性設為 SaveFormat.Pcl 以指定我們要以 PCL 格式儲存文件。接下來，我們將 RasterizeTransformedElements 屬性設為 false 以停用轉換元素的光柵化。

## 將文件轉換為 PCL 格式

現在我們已經配置了儲存選項，我們可以繼續將文件轉換為 PCL 格式。使用 Document 類別的 Save 方法透過指定儲存選項以 PCL 格式儲存轉換後的文件。這是一個例子：

```csharp
doc.Save(dataDir + "WorkingWithPclSaveOptions.RasterizeTransformedElements.pcl", saveOptions);
```

在此範例中，我們使用指定的儲存選項將轉換後的文件儲存為「WorkingWithPclSaveOptions.RasterizeTransformedElements.pcl」。

### 使用 Aspose.Words for .NET 進行「光柵化轉換元素」功能的範例原始碼

```csharp
//文檔目錄的路徑
string dataDir = "YOUR DOCUMENTS DIRECTORY";

//載入Word文檔


Document doc = new Document(dataDir + "Rendering.docx");

//配置備份選項以轉換為 PCL 格式
PclSaveOptions saveOptions = new PclSaveOptions
{
     SaveFormat = SaveFormat.Pcl,
     RasterizeTransformedElements = false
};

//將文件轉換為 PCL 格式
doc.Save(dataDir + "WorkingWithPclSaveOptions.RasterizeTransformedElements.pcl", saveOptions);
```

## 結論

在本指南中，我們介紹了在使用提供的 C# 原始程式碼將文件轉換為 PCL 格式時如何使用 Aspose.Words for .NET 停用轉換元素的光柵化。透過按照提供的步驟操作，您可以在將 Word 文件轉換為不同格式時輕鬆控制轉換元素的光柵化行為。 Aspose.Words 提供了巨大的靈活性和強大的功能來處理轉換後的元素，使您能夠精確地根據您的特定需求建立轉換後的文件。