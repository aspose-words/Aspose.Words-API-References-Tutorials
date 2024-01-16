---
title: Word 文件中的多層清單格式
linktitle: Word 文件中的多層清單格式
second_title: Aspose.Words 文件處理 API
description: 了解如何使用 Aspose.Words for .NET 建立多層清單並在 Word 文件中套用自訂格式。
type: docs
weight: 10
url: /zh-hant/net/document-formatting/multilevel-list-formatting/
---
在本教學中，我們將向您展示如何透過 Aspose.Words for .NET 使用 Word 文件功能中的多層清單格式。請按照以下步驟了解原始程式碼並套用變更。

## 第 1 步：建立並設定文檔

首先，建立一個新文件和關聯的 DocumentBuilder 物件。就是這樣：

```csharp
//文檔目錄的路徑。
string dataDir = "YOUR DOCUMENTS DIRECTORY";
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
```

## 步驟 2：格式化多層列表

現在，我們將使用 DocumentBuilder 物件中可用的方法來套用多層清單格式。就是這樣：

```csharp
builder.ListFormat.ApplyNumberDefault();
builder. Writen("Element 1");
builder. Writen("Element 2");

builder.ListFormat.ListIndent();
builder.Writeln("Element 2.1");
builder.Writeln("Element 2.2");

builder.ListFormat.ListIndent();
builder.Writeln("Element 2.2.1");
builder.Writeln("Element 2.2.2");

builder.ListFormat.ListOutdent();
builder.Writeln("Element 2.3");

builder.ListFormat.ListOutdent();
builder.Writeln("Element 3");

builder.ListFormat.RemoveNumbers();
```

## 步驟 3：儲存文檔

插入文字輸入表單欄位後，使用以下命令將文件儲存到所需位置`Save`方法。確保提供適當的文件路徑：

```csharp
doc.Save(dataDir + "DocumentFormatting.MultilevelListFormatting.docx");
```

### 使用 Aspose.Words for .NET 進行多層清單格式化的範例原始碼

以下是 Aspose.Words for .NET 的多層清單格式化功能的完整原始碼：


```csharp

//文檔目錄的路徑。
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

builder.ListFormat.ApplyNumberDefault();
builder.Writeln("Item 1");
builder.Writeln("Item 2");

builder.ListFormat.ListIndent();
builder.Writeln("Item 2.1");
builder.Writeln("Item 2.2");

builder.ListFormat.ListIndent();
builder.Writeln("Item 2.2.1");
builder.Writeln("Item 2.2.2");

builder.ListFormat.ListOutdent();
builder.Writeln("Item 2.3");

builder.ListFormat.ListOutdent();
builder.Writeln("Item 3");

builder.ListFormat.RemoveNumbers();

doc.Save(dataDir + "DocumentFormatting.MultilevelListFormatting.docx");

```

透過此程式碼，您將能夠建立多層列表，並使用 Aspose.Words for .NET 對每個層級套用正確的格式。


## 結論

在本教學中，我們探索了透過 Aspose.Words for .NET 在 Word 文件中利用多層清單格式化功能的過程。透過遵循概述的步驟，您可以建立組織良好的多個層級的列表，從而增強文件的結構和可讀性。

### 常見問題解答

#### Q：什麼是Word文檔中的多層列表？

答：Word 文件中的多層列表是一個分層列表，可讓您將項目組織為不同層級的子項目。它有助於以結構化的方式呈現訊息，使讀者更容易理解內容。

#### Q：我可以自訂多層清單的外觀嗎？

答：是的，您可以自訂 Word 文件中多層清單的外觀。透過套用不同的樣式（例如項目符號、數字或字母）以及調整縮排和間距，您可以建立一個具有視覺吸引力且組織有序的清單。

#### Q：Aspose.Words for .NET 支援其他清單格式選項嗎？

答：是的，Aspose.Words for .NET 提供了一套全面的清單格式化功能。它支援各種清單類型，包括項目符號清單、編號清單和多層清單。您可以操縱清單的格式、新增或刪除項目以及自訂其外觀。

#### Q：我可以使用 Aspose.Words for .NET 處理其他文件元素嗎？

答：是的，Aspose.Words for .NET 提供了處理各種文件元素（例如段落、表格、圖像等）的廣泛功能。它使您能夠以程式設計方式建立、修改和轉換 Word 文檔，從而簡化文檔處理任務。