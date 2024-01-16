---
title: 更新上次儲存時間屬性
linktitle: 更新上次儲存時間屬性
second_title: Aspose.Words 文件處理 API
description: 了解如何在使用 Aspose.Words for .NET 儲存文件時自動更新「上次儲存時間」屬性。
type: docs
weight: 10
url: /zh-hant/net/programming-with-ooxmlsaveoptions/update-last-saved-time-property/
---
在本教程中，我們將探索提供的 C# 原始程式碼，以在使用 Aspose.Words for .NET 儲存文件時更新上次儲存時間屬性。此功能可讓您自動更新產生文件的上次儲存時間屬性。

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
OoxmlSaveOptions saveOptions = new OoxmlSaveOptions { UpdateLastSavedTimeProperty = true };
```

在此步驟中，我們使用下列命令來設定 OOXML 儲存選項`OoxmlSaveOptions`班級。我們透過設定啟用上次儲存時間屬性的自動更新`UpdateLastSavedTimeProperty`到`true`.

## 步驟 4：儲存具有更新屬性的文檔

```csharp
doc.Save(dataDir + "WorkingWithOoxmlSaveOptions.UpdateLastSavedTimeProperty.docx", saveOptions);
```

在最後一步中，我們使用以下命令儲存文檔`Save`方法並將路徑傳遞給輸出文件`.docx`擴展名以及指定的儲存選項。

現在，您可以運行原始程式碼以在儲存文件時自動更新上次儲存時間屬性。產生的檔案將保存在指定目錄中，名稱為「WorkingWithOoxmlSaveOptions.UpdateLastSavedTimeProperty.docx」。

### 使用 Aspose.Words for .NET 更新上次儲存時間屬性的範例原始碼 

```csharp

//文檔目錄的路徑
string dataDir = "YOUR DOCUMENT DIRECTORY"; 

Document doc = new Document(dataDir + "Document.docx");

OoxmlSaveOptions saveOptions = new OoxmlSaveOptions { UpdateLastSavedTimeProperty = true };

doc.Save(dataDir + "WorkingWithOoxmlSaveOptions.UpdateLastSavedTimeProperty.docx", saveOptions);
            
        
```

## 結論

在本教學中，我們探索了使用 Aspose.Words for .NET 儲存文件時自動更新上次儲存時間屬性的功能。透過使用 OOXML 儲存選項啟用此功能，您可以確保上次儲存時間屬性在產生的文件中自動更新。

更新上次儲存時間屬性對於追蹤文件的變更和版本非常有用。它還會追蹤文件上次保存的時間，這在各種情況下都很有用。

Aspose.Words for .NET 透過提供靈活且強大的備份選項，可以輕鬆自動更新上次備份時間屬性。您可以將此功能整合到您的專案中，以確保產生的文件具有準確的備份資訊。