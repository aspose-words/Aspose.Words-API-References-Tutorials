---
title: 清晰的內容控制
linktitle: 清晰的內容控制
second_title: Aspose.Words 文件處理 API
description: 了解如何使用 Aspose.Words for .NET 清除 Word 文件中控制項的內容。
type: docs
weight: 10
url: /zh-hant/net/programming-with-sdt/clear-contents-control/
---

本教學課程示範如何使用 Aspose.Words for .NET 清除 Word 文件中 SDT 的內容。清除 SDT 的內容會刪除內容控制項內的所有文字或子節點。

## 先決條件
要學習本教程，您需要具備以下條件：

- 已安裝 Aspose.Words for .NET 程式庫。
- C# 和 Word 文件文字處理的基礎知識。

## 第 1 步：設定文檔目錄
首先設定文檔目錄的路徑。代替`"YOUR DOCUMENT DIRECTORY"`與文件所在目錄的實際路徑。

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## 第 2 步：載入文件並取得 StructuredDocumentTag
使用以下命令載入 Word 文檔`Document`建構函數，將文檔的路徑作為參數傳遞。然後，檢索所需的`StructuredDocumentTag`從文檔中。在此範例中，我們假設 SDT 是文件中的第一個子節點。

```csharp
Document doc = new Document(dataDir + "Structured document tags.docx");
StructuredDocumentTag sdt = (StructuredDocumentTag)doc.GetChild(NodeType.StructuredDocumentTag, 0, true);
```

## 步驟 3：清除 StructuredDocumentTag 的內容
使用以下命令清除 SDT 的內容`Clear`方法。這將刪除內容控制項內的所有文字或子節點。

```csharp
sdt.Clear();
```

## 步驟 4：儲存文檔
使用以下命令儲存修改後的文檔`Save`方法。提供所需的檔案名稱和適當的檔案副檔名。在此範例中，我們將文件另存為「WorkingWithSdt.ClearContentsControl.doc」。

```csharp
doc.Save(dataDir + "WorkingWithSdt.ClearContentsControl.doc");
```

### 使用 Aspose.Words for .NET 的清除內容控制範例原始程式碼 

```csharp
	//文檔目錄的路徑
	string dataDir = "YOUR DOCUMENT DIRECTORY";

	Document doc = new Document(dataDir + "Structured document tags.docx");
	StructuredDocumentTag sdt = (StructuredDocumentTag) doc.GetChild(NodeType.StructuredDocumentTag, 0, true);
	sdt.Clear();
	doc.Save(dataDir + "WorkingWithSdt.ClearContentsControl.doc");
```

就是這樣！您已使用 Aspose.Words for .NET 成功清除了 Word 文件中 StructuredDocumentTag 的內容。