---
title: 將所有 CSS 規則寫入單一文件
linktitle: 將所有 CSS 規則寫入單一文件
second_title: Aspose.Words 文件處理 API
description: 了解如何使用 Aspose.Words for .NET 將所有 CSS 規則寫入單一檔案中，從而將 Word 文件轉換為固定 HTML。
type: docs
weight: 10
url: /zh-hant/net/programming-with-htmlfixedsaveoptions/write-all-css-rules-in-single-file/
---

在 C# 應用程式中將 Word 文件轉換為固定 HTML 時，您可能希望將所有 CSS 規則合併到單一文件中，以實現更好的組織和可移植性。使用適用於 .NET 的 Aspose.Words 程式庫，您可以使用 HtmlFixedSaveOptions 儲存選項輕鬆指定此功能。在本逐步指南中，我們將引導您了解如何使用 Aspose.Words for .NET C# 原始程式碼，透過使用儲存選項 HtmlFixedSaveOptions 將所有 CSS 規則寫入單一檔案中，將 Word 文件轉換為固定 HTML。

## 了解 Aspose.Words 函式庫

在深入研究程式碼之前，了解 .NET 的 Aspose.Words 函式庫非常重要。 Aspose.Words 是一個功能強大的程式庫，可在包括.NET 在內的不同平台上建立、編輯、轉換和保護 Word 文件。它提供了許多用於操作文件的功能，例如插入文字、更改格式、添加部分等等。

## 載入Word文檔

第一步是載入要轉換為固定 HTML 的 Word 文件。使用 Document 類別從來源檔案載入文件。這是一個例子：

```csharp
Document doc = new Document(dataDir + "Document.docx");
```

在此範例中，我們載入位於文件目錄中的文件「Document.docx」。

## 配置備份選項

下一步是配置儲存選項以轉換為固定 HTML。使用 HtmlFixedSaveOptions 類別並將 SaveFontFaceCssSeparately 屬性設為 false 以將所有 CSS 規則寫入單一檔案中。操作方法如下：

```csharp
HtmlFixedSaveOptions saveOptions = new HtmlFixedSaveOptions { SaveFontFaceCssSeparately = false };
```

我們建立一個新的 HtmlFixedSaveOptions 物件並將 SaveFontFaceCssSeparately 屬性設為 false 以將所有 CSS 規則寫入單一檔案中。

## 修復 HTML 文件轉換

現在我們已經配置了儲存選項，我們可以繼續將文件轉換為固定 HTML。使用 Document 類別的 Save 方法透過指定儲存選項以固定 HTML 格式儲存轉換後的文件。這是一個例子：

```csharp
doc.Save(dataDir + "WorkingWithHtmlFixedSaveOptions.WriteAllCssRulesInSingleFile.html", saveOptions);
```

在此範例中，我們使用指定的儲存選項將轉換後的文件儲存為「WorkingWithHtmlFixedSaveOptions.WriteAllCssRulesInSingleFile.html」。

### 使用 Aspose.Words for .NET 的 HtmlFixedSaveOptions 範例原始程式碼，具有「將所有 CSS 規則寫入一個檔案」功能

```csharp
//文檔目錄的存取路徑
string dataDir = "YOUR DOCUMENTS DIRECTORY";

//載入Word文檔
Document doc = new Document(dataDir + "Document.docx");

//使用「將所有 CSS 規則寫入一個檔案」功能配置備份選項
HtmlFixedSaveOptions saveOptions = new HtmlFixedSaveOptions { SaveFontFaceCssSeparately = false };

//將文檔轉換為固定 HTML
doc.Save(dataDir + "WorkingWithHtmlFixedSaveOptions.WriteAllCssRulesInSingleFile.html", saveOptions);
```

## 結論

在本指南中，我們介紹如何使用 HtmlFixedSaveOptions 和適用於 .NET 的 Aspose.Words 庫將所有 CSS 規則寫入單個文件，從而將 Word 文件轉換為固定 HTML。透過遵循提供的步驟並使用提供的 C# 原始程式碼，您可以輕鬆地在 C# 應用程式中應用此功能。將所有 CSS 規則寫入單一文件中可以更輕鬆地組織和管理文件轉換期間產生的 HTML 程式碼。