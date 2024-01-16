---
title: 使用密碼加密文檔
linktitle: 使用密碼加密文檔
second_title: Aspose.Words 文件處理 API
description: 了解如何使用 Aspose.Words for .NET 使用密碼加密文件。
type: docs
weight: 10
url: /zh-hant/net/programming-with-docsaveoptions/encrypt-document-with-password/
---
在 C# 應用程式中對文件進行文字處理時，文件安全性至關重要。使用適用於 .NET 的 Aspose.Words 程式庫，您可以透過使用密碼加密來輕鬆保護您的文件。在本逐步指南中，我們將引導您了解如何使用 Aspose.Words for .NET C# 原始程式碼並使用 DocSaveOptions 儲存選項來加密文件。

## 了解 Aspose.Words 函式庫

在深入研究程式碼之前，了解 .NET 的 Aspose.Words 函式庫非常重要。 Aspose.Words 是一個功能強大的程式庫，可在包括.NET 在內的不同平台上建立、編輯、轉換和保護 Word 文件。它提供了許多用於操作文件的功能，例如插入文字、更改格式、添加部分等等。

## 步驟一：定義文檔目錄

第一步是設定要儲存加密文件的目錄。您必須指定完整的目錄路徑。例如 ：

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
```

請務必將「您的文件目錄」替換為文件目錄的實際路徑。

## 第 2 步：建立和編輯文檔

然後您可以建立一個文件並向其中添加內容。使用 Aspose.Words 提供的 DocumentBuilder 類別來建立文件的內容。例如 ：

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
            
builder.Write("Hello world!");
```

在此範例中，我們建立一個新的空白文檔，然後使用 DocumentBuilder 寫入文字「Hello World!」。

## 步驟 3：配置錄製選項

現在讓我們來配置文檔的儲存選項。使用 DocSaveOptions 類別指定儲存設定。例如 ：

```csharp
DocSaveOptions saveOptions = new DocSaveOptions { Password = "password" };
```

在此範例中，我們建立一個新的 DocSaveOptions 物件並將 Password 屬性設為「password」以使用此密碼加密文件。

## 步驟4：啟用「使用密碼加密文件」功能

我們已經配置了以下選項

使用指定密碼註冊，會自動啟動「使用密碼加密文件」功能。這可確保文件使用儲存時指定的密碼進行加密。

## 第 5 步：儲存文檔

最後，您可以使用 Document 類別的 Save 方法來儲存文件。指定檔案的完整路徑和所需的檔案名稱。例如 ：

```csharp
doc.Save(dataDir + "WorkingWithDocSaveOptions.EncryptDocumentWithPassword.docx", saveOptions);
```

請務必將“dataDir”替換為文件的目錄路徑。

### 使用 Aspose.Words for .NET 的 DocSaveOptions 儲存選項以及「使用密碼加密文件」功能的範例原始碼

```csharp
//文檔目錄的路徑
string dataDir = "YOUR DOCUMENTS DIRECTORY";

//建立和編輯文檔
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
            
builder.Write("Hello world!");

//使用「使用密碼加密文件」功能設定儲存選項
DocSaveOptions saveOptions = new DocSaveOptions { Password = "password" };

//使用指定選項儲存文檔
doc.Save(dataDir + "WorkingWithDocSaveOptions.EncryptDocumentWithPassword.docx", saveOptions);
```

## 結論

在本指南中，我們解釋瞭如何使用 .NET 的 Aspose.Words 函式庫透過 DocSaveOptions 儲存選項使用密碼加密文件。透過遵循提供的步驟並使用提供的 C# 原始程式碼，您可以輕鬆地在 C# 應用程式中應用此功能。使用密碼對文件進行加密可以保證處理文件時的機密性和安全性。