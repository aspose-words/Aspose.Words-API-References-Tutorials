---
title: 使用密碼加密 Docx
linktitle: 使用密碼加密 Docx
second_title: Aspose.Words 文件處理 API
description: 了解如何使用 Aspose.Words for .NET 使用密碼加密 DOCX 檔案。文件安全完整教學。
type: docs
weight: 10
url: /zh-hant/net/programming-with-ooxmlsaveoptions/encrypt-docx-with-password/
---
在本教程中，我們將探索提供的 C# 原始程式碼，以使用 Aspose.Words for .NET 使用密碼加密 DOCX 檔案。此功能可讓您透過僅使用指定的密碼才能存取文件來保護文件。

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
OoxmlSaveOptions saveOptions = new OoxmlSaveOptions { Password = "password" };
```

在此步驟中，我們透過建立新的 OOXML 儲存選項來配置`OoxmlSaveOptions`目的。我們透過設定指定所需的密碼來加密文檔`Password`屬性到您的自訂密碼。

## 第四步：使用密碼加密文檔

```csharp
doc.Save(dataDir + "WorkingWithOoxmlSaveOptions.EncryptDocxWithPassword.docx", saveOptions);
```

在最後一步中，我們使用以下命令儲存文檔`Save`方法並將路徑傳遞給輸出文件`.docx`擴展名以及指定的儲存選項。

現在您可以執行原始程式碼來使用密碼加密您的 DOCX 文件。產生的檔案將保存在指定目錄中，名稱為「WorkingWithOoxmlSaveOptions.EncryptDocxWithPassword.docx」。請確保您的密碼安全，因為開啟加密文件需要使用該密碼。

### 使用 Aspose.Words for .NET 使用密碼加密 Docx 的範例原始碼 

```csharp

//文檔目錄的路徑
string dataDir = "YOUR DOCUMENT DIRECTORY";  

Document doc = new Document(dataDir + "Document.docx");

OoxmlSaveOptions saveOptions = new OoxmlSaveOptions { Password = "password" };

doc.Save(dataDir + "WorkingWithOoxmlSaveOptions.EncryptDocxWithPassword.docx", saveOptions);
            
        
```

## 結論

在本教學中，我們探索了使用 Aspose.Words for .NET 使用密碼加密 DOCX 檔案的功能。我們學習瞭如何透過僅使用指定的密碼才能存取我們的文件來保護它們。

文檔加密是保護敏感資訊的重要安全措施。感謝 Aspose.Words for .NET，我們可以輕鬆地將此功能添加到我們的應用程式中。

透過依照提供的步驟操作，您可以將密碼加密整合到 Aspose.Words for .NET 專案中，並確保文件的機密性。

請隨意嘗試 Aspose.Words for .NET 提供的其他功能，以透過進階文件操作功能來豐富您的應用程式。
