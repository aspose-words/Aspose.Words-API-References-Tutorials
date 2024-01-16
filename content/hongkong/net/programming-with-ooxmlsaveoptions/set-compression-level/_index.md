---
title: 設定壓縮等級
linktitle: 設定壓縮等級
second_title: Aspose.Words 文件處理 API
description: 了解如何在使用 Aspose.Words for .NET 儲存文件時設定壓縮等級。
type: docs
weight: 10
url: /zh-hant/net/programming-with-ooxmlsaveoptions/set-compression-level/
---
在本教程中，我們將探索提供的 C# 原始程式碼，以在使用 Aspose.Words for .NET 儲存文件時設定壓縮等級。此功能可讓您控制產生文件的壓縮等級。

## 第一步：建構環境

在開始之前，請確保您已使用 Aspose.Words for .NET 設定開發環境。確保您已新增必要的引用並匯入適當的命名空間。

## 第 2 步：載入文檔

```csharp
//文檔目錄的路徑
string dataDir = "YOUR DOCUMENTS DIRECTORY";

Document doc = new Document(dataDir + "Document.docx");
```

在此步驟中，我們使用以下命令載入文檔`Document`方法並傳遞要載入的 DOCX 檔案的路徑。

## 步驟 3：設定 OOXML 備份選項

```csharp
OoxmlSaveOptions saveOptions = new OoxmlSaveOptions { CompressionLevel = CompressionLevel.SuperFast };
```

在此步驟中，我們使用下列命令來設定 OOXML 儲存選項`OoxmlSaveOptions`班級。我們將壓縮等級設定為`SuperFast`以獲得更快的壓縮。

## 步驟 4：使用指定的壓縮等級儲存文檔

```csharp
doc.Save(dataDir + "WorkingWithOoxmlSaveOptions.SetCompressionLevel.docx", saveOptions);
```

在最後一步中，我們使用以下命令儲存文檔`Save`方法並將路徑傳遞給輸出文件`.docx`擴展名以及指定的儲存選項。

現在您可以運行原始程式碼來設定儲存文件時的壓縮等級。產生的檔案將保存在指定目錄中，名稱為「WorkingWithOoxmlSaveOptions.SetCompressionLevel.docx」。

### 使用 Aspose.Words for .NET 設定壓縮等級的範例原始碼 

```csharp

//文檔目錄的路徑
string dataDir = "YOUR DOCUMENT DIRECTORY"; 
 
Document doc = new Document(dataDir + "Document.docx");

OoxmlSaveOptions saveOptions = new OoxmlSaveOptions { CompressionLevel = CompressionLevel.SuperFast };

doc.Save(dataDir + "WorkingWithOoxmlSaveOptions.SetCompressionLevel.docx", saveOptions);
            
        
```

## 結論

在本教學中，我們探討了使用 Aspose.Words for .NET 儲存文件時設定壓縮等級的功能。透過指定適當的壓縮級別，您可以優化文件大小和產生速度。

這`OoxmlSaveOptions`類別提供了透過設定來靈活地控制壓縮級別`CompressionLevel`屬性到適當的值，例如`SuperFast`。這使您可以根據您的特定需求在檔案大小和備份速度之間取得適當的平衡。

當您需要減小生成的文件的大小時，尤其是對於大型文檔，使用壓縮會很有用。這可以使儲存、共用和傳輸文件變得更加容易。

Aspose.Words for .NET 提供了一系列強大的文件操作選項和功能。透過使用適當的備份選項，您可以自訂文件生成流程並優化應用程式的效能。

請隨意探索 Aspose.Words for .NET 的更多功能，以增強您的文件產生工作流程。
