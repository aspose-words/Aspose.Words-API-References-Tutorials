---
title: 在Word文檔中新增雙向標記
linktitle: 在Word文檔中新增雙向標記
second_title: Aspose.Words 文件處理 API
description: 學習使用 Aspose.Words for .NET 將 Bidi 標籤新增至 Word 文件並建立專業的多語言文件。
type: docs
weight: 10
url: /zh-hant/net/programming-with-txtsaveoptions/add-bidi-marks/
---

Aspose.Words for .NET 是一個功能強大的程式庫，用於在 C# 應用程式中建立、編輯和操作 Word 文件。 Aspose.Words 提供的功能之一是能夠為文件添加 Bidi（雙向）標記。在本指南中，我們將引導您了解如何使用 Aspose.Words for .NET 的 C# 原始程式碼為文件新增 Bidi 標記。

## 了解 Aspose.Words 函式庫

在深入研究程式碼之前，了解 .NET 的 Aspose.Words 函式庫非常重要。 Aspose.Words 是一個受歡迎的函式庫，它讓 Word 文件的文字處理變得簡單有效率。它提供了用於建立、編輯和操作 Word 文件的廣泛功能，包括添加 Bidi 標記。

## 建立文件並添加內容

第一步是建立一個新文件並在其中添加內容。使用 Document 類別建立一個新的文檔實例。然後使用 DocumentBuilder 類別將文字新增到文件中。這是一個例子：

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

builder. Writen("Hello world!");
builder.ParagraphFormat.Bidi = true;
builder. Writen("שלום עולם!");
builder. Writen("مرحبا بالعالم!");
```

在此範例中，我們建立一個新文件並使用 DocumentBuilder 新增文字。我們添加了三行文本：一行是英語，一行是希伯來語，一行是阿拉伯語，以演示如何添加不同語言的內容。

## 新增了 Bidi 標記

新增內容後，我們現在可以將 Bidi 標記新增到文件中。為此，我們使用 TxtSaveOptions 類別並將 AddBidiMarks 屬性設為 true。就是這樣：

```csharp
TxtSaveOptions saveOptions = new TxtSaveOptions { AddBidiMarks = true };
doc.Save(dataDir + "WorkingWithTxtSaveOptions.AddBidiMarks.txt", saveOptions);
```

在此範例中，我們建立 TxtSaveOptions 的實例並將 AddBidiMarks 屬性設為 true。接下來，我們使用 Document 類別的 Save 方法來保存帶有 Bidi 標記的文件。

### 使用 Aspose.Words for .NET 的「新增 Bidi 標記」功能的範例原始碼

```csharp
//文檔目錄的路徑
string dataDir = "YOUR DOCUMENTS DIRECTORY";

//建立文件並添加內容
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

builder. Writen("Hello world!");
builder.ParagraphFormat.Bidi = true;
builder. Writen("שלום עולם!");
builder. Writen("مرحبا بالعالم!");

//新增 Bidi 標記
TxtSaveOptions saveOptions = new TxtSaveOptions { AddBidiMarks = true

  };
doc.Save(dataDir + "WorkingWithTxtSaveOptions.AddBidiMarks.txt", saveOptions);
```

## 結論

在本指南中，我們解釋如何使用 Aspose.Words for .NET 使用提供的 C# 原始程式碼將 Bidi 標籤新增至 Word 文件。透過按照提供的步驟操作，您可以輕鬆地將 Bidi 標記新增至 C# 應用程式中的 Word 文件。 Aspose.Words 透過文字格式設定和語言管理為文字處理提供了巨大的靈活性和強大功能，使您能夠專業地建立多語言文件。

### 經常問的問題

#### Q：什麼是 Aspose.Words for .NET？
Aspose.Words for .NET 是一個功能強大的程式庫，用於在 C# 應用程式中建立、編輯和操作 Word 文件。它為 Word 文件的文字處理提供了許多功能，包括添加 Bidi（雙向）標記。

#### Q：Aspose.Words for .NET 提供哪些功能？
Aspose.Words for .NET 提供了廣泛的用於建立、編輯和操作 Word 文件的功能。其中一些功能包括建立文件、新增內容、格式化文字、管理表格、合併和分割文件、轉換文件等。

#### Q：如何使用 Aspose.Words for .NET 將 Bidi 標籤新增至 Word 文件？
您可以按照以下步驟將 Bidi 標記新增至 Word 文件：

使用建立一個新文檔`Document`班級。

使用`DocumentBuilder`類別會向文件添加內容。

新增內容後，使用`TxtSaveOptions`類別並設定`AddBidiMarks`財產給`true`.

使用以下命令儲存帶有 Bidi 標記的文檔`Save`的方法`Document`班級。

#### Q：Aspose.Words 是否支援多種語言添加 Bidi 標記？
是的，Aspose.Words 支援多種語言添加 Bidi 標記。您可以使用 Aspose.Words for .NET 將 Bidi 標籤新增至不同語言的文字中，例如英語、希伯來語和阿拉伯語。

#### Q：是否有其他選項可以保存帶有 Bidi 標記的文件？
是的，您可以在使用 Bidi 標記儲存文件時指定其他選項`TxtSaveOptions`班級。例如，您可以設定文件儲存格式、編碼選項等。