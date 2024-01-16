---
title: 保留舊控製字符
linktitle: 保留舊控製字符
second_title: Aspose.Words 文件處理 API
description: 了解如何在使用 Aspose.Words for .NET 儲存文件時保留舊控製字元。
type: docs
weight: 10
url: /zh-hant/net/programming-with-ooxmlsaveoptions/keep-legacy-control-chars/
---

在本教程中，我們將探索提供的 C# 原始程式碼，以在使用 Aspose.Words for .NET 儲存文件時保留舊控製字元。此功能可讓您在轉換或儲存文件時保留特殊控製字元。

## 第一步：建構環境

在開始之前，請確保您已使用 Aspose.Words for .NET 設定開發環境。確保您已新增必要的引用並匯入適當的命名空間。

## 第 2 步：載入文檔

```csharp
//文檔目錄的路徑
string dataDir = "YOUR DOCUMENTS DIRECTORY";

Document doc = new Document(dataDir + "Legacy control character.doc");
```

在此步驟中，我們使用以下命令載入文檔`Document`方法並將路徑傳遞給包含繼承的控製字元的檔案。

## 步驟 3：設定 OOXML 備份選項

```csharp
OoxmlSaveOptions saveOptions = new OoxmlSaveOptions(SaveFormat.FlatOpc) { KeepLegacyControlChars = true };
```

在此步驟中，我們透過建立新的 OOXML 儲存選項來配置`OoxmlSaveOptions`目的。我們指定所需的保存格式（此處，`FlatOpc` ）並啟用`KeepLegacyControlChars`保留傳統控製字元的選項。

## 步驟 4：使用舊控製字元儲存文檔

```csharp
doc.Save(dataDir + "WorkingWithOoxmlSaveOptions.KeepLegacyControlChars.docx", saveOptions);
```

在最後一步中，我們使用以下命令儲存文檔`Save`方法並將路徑傳遞給輸出文件`.docx`擴展名以及指定的儲存選項。

現在，您可以運行原始程式碼以在儲存文件時保留舊控製字元。產生的檔案將保存在指定目錄中，名稱為「WorkingWithOoxmlSaveOptions.KeepLegacyControlChars.docx」。

### 使用 Aspose.Words for .NET 保留舊版控製字元的範例原始程式碼 
```csharp

//文檔目錄的路徑
string dataDir = "YOUR DOCUMENT DIRECTORY"; 

Document doc = new Document(dataDir + "Legacy control character.doc");

OoxmlSaveOptions saveOptions = new OoxmlSaveOptions(SaveFormat.FlatOpc) { KeepLegacyControlChars = true };

doc.Save(dataDir + "WorkingWithOoxmlSaveOptions.KeepLegacyControlChars.docx", saveOptions);
            
        
```

## 結論

在本教學中，我們探討了使用 Aspose.Words for .NET 儲存文件時保留舊控製字元的功能。我們已經了解如何保留那些對於正確的文件格式或顯示可能很重要的特殊字元。

當對使用較舊或特定功能（例如特殊控製字元）的文件進行文字處理時，保留舊控製字元特別有用。透過啟用`KeepLegacyControlChars`儲存文件時選擇選項，確保保留這些字元。

Aspose.Words for .NET 提供了一系列靈活且強大的備份選項來滿足您的文件作業需求。透過使用適當的選項，您可以自訂備份過程以保留文件的特定特徵。

請隨意將此功能合併到您的 Aspose.Words for .NET 專案中，以確保文件中舊控製字元的完整性和保留。