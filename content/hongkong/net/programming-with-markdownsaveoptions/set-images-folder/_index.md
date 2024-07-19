---
title: 設定圖像資料夾
linktitle: 設定圖像資料夾
second_title: Aspose.Words 文件處理 API
description: 了解使用 Aspose.Words for .NET 匯出到 Markdown 時如何設定圖片資料夾。自訂影像的位置以更好地組織和整合。
type: docs
weight: 10
url: /zh-hant/net/programming-with-markdownsaveoptions/set-images-folder/
---

以下是逐步指南，解釋以下 C# 原始程式碼，有助於使用 .NET 的 Aspose.Words 函式庫為 Markdown 匯出選項設定映像資料夾。在使用此程式碼之前，請確保您已在專案中包含 Aspose.Words 程式庫。

## 步驟1：設定文檔目錄路徑

```csharp
//文檔目錄的路徑。
string dataDir = "YOUR_DIRECTORY_OF_DOCUMENTS";
```

請務必指定包含影像的文件所在文件目錄的正確路徑。

## 步驟 2：載入包含圖像的文檔

```csharp
Document doc = new Document(dataDir + "Image bullet points.docx");
```

我們載入包含要使用 Markdown 選項匯出的映像的指定文件。

## 步驟 3：為 Markdown 匯出選項設定圖片資料夾

```csharp
MarkdownSaveOptions saveOptions = new MarkdownSaveOptions { ImagesFolder = dataDir + "Images" };
```

我們建立一個實例`MarkdownSaveOptions`並使用以下命令設定圖像資料夾的路徑`ImagesFolder`財產。確保指定要儲存匯出影像的資料夾的正確路徑。

## 步驟 4：使用 Markdown 匯出選項儲存文檔

```csharp
using (MemoryStream stream = new MemoryStream())
     doc. Save(stream, saveOptions);
```

我們使用指定的 Markdown 匯出選項將文件儲存到記憶體流。然後，您可以使用該流程執行其他操作，例如將 Markdown 內容儲存到文件中。

### 使用 Aspose.Words for .NET 為 MarkdownSaveOptions 設定圖片資料夾的範例原始碼

```csharp
//文檔目錄的路徑。
string dataDir = "YOUR_DIRECTORY_OF_DOCUMENTS";

Document doc = new Document(dataDir + "Image bullet points.docx");

MarkdownSaveOptions saveOptions = new MarkdownSaveOptions { ImagesFolder = dataDir + "Images" };

using (MemoryStream stream = new MemoryStream())
     doc. Save(stream, saveOptions);
```

此原始程式碼示範如何載入包含映像的文檔，然後為 Markdown 匯出選項設定映像資料夾。然後使用指定的選項將文件儲存到記憶體流中。這允許您在匯出 Markdown 內容時自訂映像資料夾的位置。