---
title: 不要壓縮小圖元文件
linktitle: 不要壓縮小圖元文件
second_title: Aspose.Words 文件處理 API
description: 了解如何使用 Aspose.Words for .NET 在儲存文件時啟用「不壓縮小圖元檔案」功能。
type: docs
weight: 10
url: /zh-hant/net/programming-with-docsaveoptions/do-not-compress-small-metafiles/
---

在 C# 應用程式中對檔案進行文字處理時，壓縮文件中的元資料是一個常見功能。但是，可能有必要不壓縮小檔案的元資料以保持其品質。在本逐步指南中，我們將向您展示如何使用 Aspose.Words for .NET 的 C# 原始程式碼在文件儲存選項中啟用「不壓縮小圖元檔案」功能。

## 了解 Aspose.Words 函式庫

在深入研究程式碼之前，了解 .NET 的 Aspose.Words 函式庫非常重要。 Aspose.Words 是一個功能強大的程式庫，可在包括.NET 在內的不同平台上建立、編輯、轉換和保護 Word 文件。它提供了許多用於操作文件的功能，例如插入文字、更改格式、添加部分等等。

## 步驟1：設定文檔目錄

第一步是定義要儲存文件的目錄。您必須指定完整的目錄路徑。例如 ：

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
```

請務必將「您的文件目錄」替換為文件目錄的實際路徑。

## 第 2 步：插入部分和文字

然後您可以將部分和文字插入文件中。使用 Aspose.Words 提供的 DocumentBuilder 類別來建立文件的內容。這是一個簡單的例子：

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
builder.Writeln("Text added to a document.");
```

在此範例中，我們建立一個新的空白文檔，然後使用 DocumentBuilder 新增一行文字。

## 第 3 步：設定選項

'登記

現在讓我們來配置文檔的儲存選項。使用 DocSaveOptions 類別指定儲存設定。例如 ：

```csharp
DocSaveOptions saveOptions = new DocSaveOptions();
```

在此範例中，我們將建立一個新的 DocSaveOptions 物件來設定儲存選項。

## 步驟 4：啟用「不壓縮小圖元檔案」功能

若要啟用「不壓縮小圖元檔案」功能，您必須設定`Compliance`DocSaveOptions 物件的屬性值`PdfCompliance.PdfA1a`。就是這樣：

```csharp
saveOptions.Compliance = PdfCompliance.PdfA1a;
```

此配置可確保儲存文件時不會壓縮小文件元資料。

## 第 5 步：儲存文檔

最後，您可以使用以下命令儲存文檔`Save`Document 類別的方法。指定檔案的完整路徑和所需的檔案名稱。例如 ：

```csharp
doc.Save(dataDir + "DocumentWithDoNotCompressMetafiles.pdf", saveOptions);
```

請務必將“dataDir”替換為文件目錄的路徑。

### 使用 Aspose.Words for .NET 具有不壓縮小圖元檔案功能的 DocSaveOptions 範例原始碼

```csharp
//文檔目錄的路徑
string dataDir = "YOUR DOCUMENTS DIRECTORY";

//插入帶有一些文字的兩個部分。
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
builder.Writeln("Text added to a document.");

//使用「不壓縮小圖元檔案」功能配置儲存選項
DocSaveOptions saveOptions = new DocSaveOptions();
saveOptions.Compliance = PdfCompliance.PdfA1a;

//使用指定選項儲存文檔
doc.Save(dataDir + "DocumentWithDoNotCompressMetafiles.pdf", saveOptions);
```

## 結論

在本指南中，我們說明如何使用 Aspose.Words for .NET 程式庫在儲存文件時啟用「不壓縮小圖元檔案」功能。透過遵循提供的步驟並使用提供的 C# 原始程式碼，您可以輕鬆地在 C# 應用程式中應用此功能。保留未壓縮的小文件元資料對於維護文件品質和完整性非常重要。