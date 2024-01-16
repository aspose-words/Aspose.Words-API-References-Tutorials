---
title: 設定Ms Word版本
linktitle: 設定Ms Word版本
second_title: Aspose.Words 文件處理 API
description: 了解如何使用 Aspose.Words for .NET 使用指定版本的 MS Word 載入文件。
type: docs
weight: 10
url: /zh-hant/net/programming-with-loadoptions/set-ms-word-version/
---
在 C# 應用程式中對 Word 文件進行文字處理時，可能需要指定載入文件時要使用的 Microsoft Word 版本。使用適用於 .NET 的 Aspose.Words 程式庫，您可以使用 LoadOptions 輕鬆設定要使用的 MS Word 版本。在本逐步指南中，我們將引導您了解如何使用 Aspose.Words for .NET C# 原始程式碼使用 LoadOptions 載入選項載入具有指定版本的 MS Word 的文件。

## 了解 Aspose.Words 函式庫

在深入研究程式碼之前，了解 .NET 的 Aspose.Words 函式庫非常重要。 Aspose.Words 是一個功能強大的程式庫，可在包括.NET 在內的不同平台上建立、編輯、轉換和保護 Word 文件。它提供了許多用於操作文件的功能，例如插入文字、更改格式、添加部分等等。

## 配置載入選項

第一步是配置文檔的載入選項。使用 LoadOptions 類別指定載入參數。在我們的範例中，我們需要將 MswVersion 屬性設定為所需的 MS Word 版本。例如，我們使用的是Microsoft Word 2010版本。操作方法如下：

```csharp
LoadOptions loadOptions = new LoadOptions { MswVersion = MsWordVersion.Word2010 };
```

我們建立一個新的 LoadOptions 物件並將 MswVersion 屬性設定為 MsWordVersion.Word2010 以指定 MS Word 2010 的版本。

## 使用指定版本的 MS Word 載入文檔

現在我們已經配置了載入選項，我們可以使用 Document 類別載入文件並指定載入選項。這是一個例子：

```csharp
Document doc = new Document(dataDir + "Document.docx", loadOptions);
```

在此範例中，我們使用指定的載入選項載入位於文件目錄中的文件「Document.docx」。

### 使用 Aspose.Words for .NET 的具有「設定 MS Word 版本」功能的 LoadOptions 範例原始碼

```csharp
//文檔目錄的路徑
string dataDir = "YOUR DOCUMENTS DIRECTORY";

//使用「設定 MS Word 版本」功能配置載入選項
LoadOptions loadOptions = new LoadOptions { MswVersion = MsWordVersion.Word2010 };

//使用指定版本的 MS Word 載入文檔
Document doc = new Document(dataDir + "Document.docx", loadOptions);

//儲存文件
doc.Save(dataDir + "WorkingWithLoadOptions.SetMsWordVersion.docx");
```

## 結論

在本指南中，我們說明如何使用 .NET 的 Aspose.Words 程式庫上傳指定 MS Word 特定版本的文件。透過遵循提供的步驟並使用提供的程式碼 C# 原始程式碼，您可以輕鬆地在 C# 應用程式中應用此功能。使用指定版本的 MS Word 載入文件可以確保應用程式中文件的正確相容性和處理。


### 常見問題解答

#### Q：為什麼在 C# 應用程式中載入文件時需要指定 MS Word 的版本？

指定 MS Word 的版本可確保正確載入和處理文檔，尤其是在處理不同版本之間可能有所不同的特定格式或功能時。

#### Q：Aspose.Words 支援哪些版本的 MS Word？

答：Aspose.Words for .NET 支援各種版本的 MS Word，包括 Word 97、Word 2003、Word 2007、Word 2010、Word 2013、Word 2016、Word 2019 等。

#### Q：我可以使用與我的系統上安裝的版本不同的 MS Word 版本來載入文件嗎？

答：是的，Aspose.Words 允許您在載入文件時指定不同的 MS Word 版本，即使目標系統具有不同的 MS Word 版本，也能確保相容性。

#### Q：設定 MS Word 版本對我的 C# 應用程式有何好處？

答：設定 MS Word 版本可確保根據特定版本的預期格式和功能處理文檔，從而提供一致的輸出。

#### Q：Aspose.Words 是否僅限於處理 DOCX 文件？

答：不需要，Aspose.Words 支援多種文件格式，包括 DOC、RTF、HTML、PDF 等，使其成為處理不同類型文件的多功能工具。