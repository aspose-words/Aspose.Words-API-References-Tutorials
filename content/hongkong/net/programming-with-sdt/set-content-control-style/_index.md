---
title: 設定內容控制樣式
linktitle: 設定內容控制樣式
second_title: Aspose.Words 文件處理 API
description: 了解如何使用 Aspose.Words for .NET 設定 Word 文件中內容控制項的樣式，並套用一致的格式。
type: docs
weight: 10
url: /zh-hant/net/programming-with-sdt/set-content-control-style/
---

本教學介紹如何使用 Aspose.Words for .NET 在 Word 文件中設定內容控制項的樣式。您可以將預先定義或自訂樣式套用至內容控制項以保持格式一致。

## 先決條件
要學習本教程，您需要具備以下條件：

- 已安裝 Aspose.Words for .NET 程式庫。
- C# 和 Word 文件文字處理的基礎知識。

## 第 1 步：設定文檔目錄
首先設定文檔目錄的路徑。代替`"YOUR DOCUMENT DIRECTORY"`與文件所在目錄的實際路徑。

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## 第 2 步：載入文件並檢索內容控件
使用以下命令載入 Word 文檔`Document`建構函數，將文檔的路徑作為參數傳遞。從文件中檢索所需的內容控制項。在此範例中，我們假設內容控制項是文件中的第一個結構化文件標籤。

```csharp
Document doc = new Document(dataDir + "Structured document tags.docx");
StructuredDocumentTag sdt = (StructuredDocumentTag)doc.GetChild(NodeType.StructuredDocumentTag, 0, true);
```

## 第 3 步：檢索樣式並套用於內容控制
從文件的樣式集合中檢索所需的樣式。在此範例中，我們透過使用檢索“Quote”樣式`StyleIdentifier.Quote`。然後，將檢索到的樣式指派給`Style`結構化文檔標籤的屬性。

```csharp
Style style = doc.Styles[StyleIdentifier.Quote];
sdt.Style = style;
```

## 步驟 4：儲存文檔
使用指令將修改後的文件儲存到指定目錄`Save`方法。提供所需的檔案名稱和適當的檔案副檔名。在此範例中，我們將文件另存為「WorkingWithSdt.SetContentControlStyle.docx」。

```csharp
doc.Save(dataDir + "WorkingWithSdt.SetContentControlStyle.docx");
```

### 使用 Aspose.Words for .NET 設定內容控制樣式的範例原始程式碼 

```csharp
	//文檔目錄的路徑
	string dataDir = "YOUR DOCUMENT DIRECTORY";

	Document doc = new Document(dataDir + "Structured document tags.docx");
	StructuredDocumentTag sdt = (StructuredDocumentTag) doc.GetChild(NodeType.StructuredDocumentTag, 0, true);
	Style style = doc.Styles[StyleIdentifier.Quote];
	sdt.Style = style;
	doc.Save(dataDir + "WorkingWithSdt.SetContentControlStyle.docx");
```

就是這樣！您已使用 Aspose.Words for .NET 在 Word 文件中成功設定內容控制項的樣式。