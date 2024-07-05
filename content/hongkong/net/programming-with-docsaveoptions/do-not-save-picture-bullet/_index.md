---
title: 不保存圖片項目符號
linktitle: 不保存圖片項目符號
second_title: Aspose.Words 文件處理 API
description: 了解如何使用 Aspose.Words for .NET 在 Word 文件中停用儲存圖片項目符號。
type: docs
weight: 10
url: /zh-hant/net/programming-with-docsaveoptions/do-not-save-picture-bullet/
---

圖片項目符號是Word文件中常用的功能，用於新增自訂項目符號。但是，在某些情況下，使用 Aspose.Words Library for .NET 操作文件時可能需要停用影像項目符號註冊。在本逐步指南中，我們將解釋如何使用 Aspose.Words C# .NET 原始程式碼透過 DocSaveOptions 儲存選項來停用圖像項目符號儲存。

## 了解 Aspose.Words 函式庫

在深入研究程式碼之前，了解 .NET 的 Aspose.Words 函式庫非常重要。 Aspose.Words 是一個功能強大的程式庫，可在包括.NET 在內的不同平台上建立、編輯、轉換和保護 Word 文件。它提供了許多用於操作文件的功能，例如插入文字、更改格式、添加部分等等。

## 步驟1：設定文檔目錄

第一步是定義文檔所在的目錄。您必須指定完整的目錄路徑。例如 ：

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
```

請務必將「您的文件目錄」替換為文件目錄的實際路徑。

## 步驟 2：載入帶有圖像項目符號的文檔

接下來，您需要載入帶有圖像項目符號的文件。使用 Document 類別從文件載入文件。例如 ：

```csharp
Document doc = new Document(dataDir + "Image bullet points.docx");
```

在此範例中，我們從文件「ImageBulletpoints.docx」載入文檔

  位於文檔目錄中。

## 步驟 3：配置錄製選項

現在讓我們來配置文檔的儲存選項。使用 DocSaveOptions 類別指定儲存設定。例如 ：

```csharp
DocSaveOptions saveOptions = new DocSaveOptions { SavePictureBullet = false };
```

在此範例中，我們建立一個新的 DocSaveOptions 物件並將 SavePictureBullet 屬性設為 false 以停用儲存圖片項目符號。

## 步驟4：啟用「不儲存圖片項目符號」功能

為了啟用「不儲存圖片項目符號」功能，我們已經配置了儲存選項，並將 SavePictureBullet 設為 false。這可確保圖像項目符號不會儲存在最終文件中。

## 第 5 步：儲存文檔

最後，您可以使用 Document 類別的 Save 方法來儲存文件。指定檔案的完整路徑和所需的檔案名稱。例如 ：

```csharp
doc.Save(dataDir + "WorkingWithDocSaveOptions.DoNotSavePictureBullet.docx", saveOptions);
```

請務必將“dataDir”替換為文件的目錄路徑。

## 使用 Aspose.Words for .NET 的 DocSaveOptions 儲存選項以及「不儲存圖片項目符號」功能的範例原始碼

```csharp
//文檔目錄的路徑
string dataDir = "YOUR DOCUMENTS DIRECTORY";

//載入帶有圖像項目符號的文檔
Document doc = new Document(dataDir + "Image bullet points.docx");

//使用「不儲存圖片項目符號」功能配置儲存選項
DocSaveOptions saveOptions = new DocSaveOptions { SavePictureBullet = false };

//使用指定選項儲存文檔
doc.Save(dataDir + "WorkingWithDocSaveOptions.DoNotSavePictureBullet.docx", saveOptions);
```

## 結論

在本指南中，我們介紹如何使用 .NET 的 Aspose.Words 函式庫停用在文件中儲存影像項目符號。透過遵循提供的步驟並使用提供的 C# 原始程式碼，您可以輕鬆地在 C# 應用程式中應用此功能。在某些情況下，停用圖片項目符號儲存可能很有用，可以保留文件結構和格式而不儲存圖片項目符號。