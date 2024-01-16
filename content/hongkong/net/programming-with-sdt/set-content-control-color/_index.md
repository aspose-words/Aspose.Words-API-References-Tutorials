---
title: 設定內容控制顏色
linktitle: 設定內容控制顏色
second_title: Aspose.Words 文件處理 API
description: 了解如何使用 Aspose.Words for .NET 設定 Word 文件中內容控制項的顏色，並自訂其外觀。
type: docs
weight: 10
url: /zh-hant/net/programming-with-sdt/set-content-control-color/
---

本教學介紹如何使用 Aspose.Words for .NET 設定 Word 文件中內容控制項的顏色。您可以透過變更內容控制項的顏色來自訂內容控制項的外觀。

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

## 第三步：設定內容控制顏色
透過分配一個來設定內容控制項的顏色`Color`的價值`Color`結構化文檔標籤的屬性。在此範例中，我們將顏色設為紅色。

```csharp
sdt.Color = Color.Red;
```

## 步驟 4：儲存文檔
使用指令將修改後的文件儲存到指定目錄`Save`方法。提供所需的檔案名稱和適當的檔案副檔名。在此範例中，我們將文件另存為「WorkingWithSdt.SetContentControlColor.docx」。

```csharp
doc.Save(dataDir + "WorkingWithSdt.SetContentControlColor.docx");
```

### 使用 Aspose.Words for .NET 設定內容控制項顏色的範例原始程式碼 

```csharp
	//文檔目錄的路徑
	string dataDir = "YOUR DOCUMENT DIRECTORY";

	Document doc = new Document(dataDir + "Structured document tags.docx");
	StructuredDocumentTag sdt = (StructuredDocumentTag) doc.GetChild(NodeType.StructuredDocumentTag, 0, true);
	sdt.Color = Color.Red;
	doc.Save(dataDir + "WorkingWithSdt.SetContentControlColor.docx");
```

就是這樣！您已使用 Aspose.Words for .NET 成功設定了 Word 文件中內容控制項的顏色。