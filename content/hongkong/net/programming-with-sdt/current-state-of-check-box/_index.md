---
title: 複選框的目前狀態
linktitle: 複選框的目前狀態
second_title: Aspose.Words 文件處理 API
description: 了解如何使用 Aspose.Words for .NET 擷取並設定 Word 文件中複選框內容控制項的目前狀態。
type: docs
weight: 10
url: /zh-hant/net/programming-with-sdt/current-state-of-check-box/
---

本教學課程說明如何使用 Aspose.Words for .NET 擷取並設定 Word 文件中複選框內容控制項的目前狀態。您可以根據複選框的目前狀態選取或取消選取該複選框。

## 先決條件
要學習本教程，您需要具備以下條件：

- 已安裝 Aspose.Words for .NET 程式庫。
- C# 和 Word 文件文字處理的基礎知識。

## 第 1 步：設定文檔目錄
首先設定文檔目錄的路徑。代替`"YOUR DOCUMENT DIRECTORY"`與文件所在目錄的實際路徑。

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## 步驟 2：載入文件並檢索複選框內容控件
使用以下命令載入 Word 文檔`Document`建構函數，將文檔的路徑作為參數傳遞。然後，從文件中檢索所需的複選框內容控制項。在此範例中，我們假設複選框是文件中的第一個結構化文件標籤。

```csharp
Document doc = new Document(dataDir + "Structured document tags.docx");
StructuredDocumentTag sdtCheckBox =
	(StructuredDocumentTag)doc.GetChild(NodeType.StructuredDocumentTag, 0, true);
```

## 步驟 3：根據目前狀態選取或取消選取複選框
檢查檢索到的結構化文件標籤是否為類型`SdtType.Checkbox`。如果是，則設定`Checked`內容控制項的屬性`true`選中該框。否則，您可以不選中它。

```csharp
if (sdtCheckBox.SdtType == SdtType.Checkbox)
	sdtCheckBox.Checked = true;
```

## 步驟 4：儲存文檔
使用指令將修改後的文件儲存到指定目錄`Save`方法。提供所需的檔案名稱和適當的檔案副檔名。在此範例中，我們將文件另存為「WorkingWithSdt.CurrentStateOfCheckBox.docx」。

```csharp
doc.Save(dataDir + "WorkingWithSdt.CurrentStateOfCheckBox.docx");
```

### 使用 Aspose.Words for .NET 的複選框目前狀態的範例原始程式碼 

```csharp
	//文檔目錄的路徑
	string dataDir = "YOUR DOCUMENT DIRECTORY";

	Document doc = new Document(dataDir + "Structured document tags.docx");
	//從文件中取得第一個內容控制項。
	StructuredDocumentTag sdtCheckBox =
		(StructuredDocumentTag) doc.GetChild(NodeType.StructuredDocumentTag, 0, true);
	if (sdtCheckBox.SdtType == SdtType.Checkbox)
		sdtCheckBox.Checked = true;
	doc.Save(dataDir + "WorkingWithSdt.CurrentStateOfCheckBox.docx");
```

就是這樣！您已使用 Aspose.Words for .NET 成功檢索並設定了 Word 文件中複選框內容控制項的目前狀態。