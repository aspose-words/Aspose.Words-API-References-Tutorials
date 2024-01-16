---
title: 測量單位
linktitle: 測量單位
second_title: Aspose.Words 文件處理 API
description: 了解如何在使用 Aspose.Words for .NET 將 Word 文件轉換為 ODT 時指定度量單位。
type: docs
weight: 10
url: /zh-hant/net/programming-with-odtsaveoptions/measure-unit/
---

在 C# 應用程式中將 Word 文件轉換為 OpenDocument Text (ODT) 格式時，您可能需要指定用於可測量格式和內容屬性的測量單位。使用適用於 .NET 的 Aspose.Words 程式庫，您可以使用 OdtSaveOptions 儲存選項輕鬆指定此功能。在本逐步指南中，我們將引導您了解如何使用 Aspose.Words for .NET C# 原始程式碼透過使用 OdtSaveOptions 指定度量單位將 Word 文件轉換為 ODT。

## 了解 Aspose.Words 函式庫

在深入研究程式碼之前，了解 .NET 的 Aspose.Words 函式庫非常重要。 Aspose.Words 是一個功能強大的程式庫，可在包括.NET 在內的不同平台上建立、編輯、轉換和保護 Word 文件。它提供了許多用於操作文件的功能，例如插入文字、更改格式、添加部分等等。

## 載入Word文檔

第一步是載入要轉換為 ODT 的 Word 文件。使用 Document 類別從來源檔案載入文件。這是一個例子：

```csharp
Document doc = new Document(dataDir + "Document.docx");
```

在此範例中，我們載入位於文件目錄中的文件「Document.docx」。

## 配置備份選項

下一步是配置轉換為 ODT 的備份選項。使用 OdtSaveOptions 類別並將 MeasureUnit 屬性設定為所需的值。例如，如果要使用英吋作為測量單位，請將 MeasureUnit 設定為 OdtSaveMeasureUnit.Inches。操作方法如下：

```csharp
OdtSaveOptions saveOptions = new OdtSaveOptions { MeasureUnit = OdtSaveMeasureUnit.Inches };
```

我們建立一個新的 OdtSaveOptions 物件並將 MeasureUnit 屬性設定為所需的值，在我們的範例中，OdtSaveMeasureUnit.Inches 使用英吋作為測量單位。

## 將文件轉換為 ODT

現在我們已經配置了儲存選項，我們可以繼續將文件轉換為 ODT。使用 Document 類別的 Save 方法透過指定儲存選項以 ODT 格式儲存轉換後的文件。這是一個例子：

```csharp
doc.Save(dataDir + "WorkingWithOdtSaveOptions.MeasureUnit.odt", saveOptions);
```

在此範例中，我們使用指定的儲存選項將轉換後的文件儲存為「WorkingWithOdtSaveOptions.MeasureUnit.odt」。

### 使用 Aspose.Words for .NET 的具有「測量單位」功能的 OdtSaveOptions 範例原始碼



```csharp
//文檔目錄的路徑
string dataDir = "YOUR DOCUMENTS DIRECTORY";

//載入Word文檔
Document doc = new Document(dataDir + "Document.docx");

//使用“測量單位”功能配置備份選項
OdtSaveOptions saveOptions = new OdtSaveOptions { MeasureUnit = OdtSaveMeasureUnit.Inches };

//將文件轉換為 ODT
doc.Save(dataDir + "WorkingWithOdtSaveOptions.MeasureUnit.odt", saveOptions);
```

## 結論

在本指南中，我們解釋瞭如何透過使用適用於 .NET 的 Aspose.Words 函式庫的 OdtSaveOptions 儲存選項指定測量單位，將 Word 文件轉換為 ODT。透過遵循提供的步驟並使用提供的 C# 原始程式碼，您可以輕鬆地在 C# 應用程式中應用此功能。轉換為 ODT 時指定測量單位可讓您根據具體需求控制結果文件的格式和尺寸。