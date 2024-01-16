---
title: 組合框內容控件
linktitle: 組合框內容控件
second_title: Aspose.Words 文件處理 API
description: 了解如何使用 Aspose.Words for .NET 在 Word 文件中建立組合框內容控制項。
type: docs
weight: 10
url: /zh-hant/net/programming-with-sdt/combo-box-content-control/
---

本教學課程說明如何使用 Aspose.Words for .NET 在 Word 文件中建立組合方塊內容控制項。組合框內容控制項可讓使用者從下拉清單中選擇項目。

## 先決條件
要學習本教程，您需要具備以下條件：

- 已安裝 Aspose.Words for .NET 程式庫。
- C# 和 Word 文件文字處理的基礎知識。

## 第 1 步：設定文檔目錄
首先設定文檔目錄的路徑。代替`"YOUR DOCUMENT DIRECTORY"`與要儲存文件的目錄的實際路徑。

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## 步驟 2：建立文件和 StructuredDocumentTag
建立一個新實例`Document`類別和一個`StructuredDocumentTag`代表組合框內容控制項。指定`SdtType.ComboBox`作為類型和`MarkupLevel.Block`作為標記層級來建立區塊級組合框。

```csharp
Document doc = new Document();
StructuredDocumentTag sdt = new StructuredDocumentTag(doc, SdtType.ComboBox, MarkupLevel.Block);
```

## 第 3 步：將項目新增至組合框
使用以下命令將項目新增至組合框`ListItems`的財產`StructuredDocumentTag`。每個項目都由一個表示`SdtListItem`對象，它接受顯示文字和值。在此範例中，我們將三個項目新增到組合框中。

```csharp
sdt.ListItems.Add(new SdtListItem("Choose an item", "-1"));
sdt.ListItems.Add(new SdtListItem("Item 1", "1"));
sdt.ListItems.Add(new SdtListItem("Item 2", "2"));
```

## 步驟 4：將 StructuredDocumentTag 附加到文檔
使用以下命令將組合框內容控制項附加到文件正文`AppendChild`文檔第一部分主體的方法。

```csharp
doc.FirstSection.Body.AppendChild(sdt);
```

## 第 5 步：儲存文檔
使用以下命令將文件儲存到指定目錄`Save`方法。提供所需的檔案名稱和適當的檔案副檔名。在此範例中，我們將文件另存為「WorkingWithSdt.ComboBoxContentControl.docx」。

```csharp
doc.Save(dataDir + "WorkingWithSdt.ComboBoxContentControl.docx");
```

### 使用 Aspose.Words for .NET 的組合框內容控制項的範例原始程式碼 

```csharp
	//文檔目錄的路徑
	string dataDir = "YOUR DOCUMENT DIRECTORY";

	Document doc = new Document();
	StructuredDocumentTag sdt = new StructuredDocumentTag(doc, SdtType.ComboBox, MarkupLevel.Block);
	sdt.ListItems.Add(new SdtListItem("Choose an item", "-1"));
	sdt.ListItems.Add(new SdtListItem("Item 1", "1"));
	sdt.ListItems.Add(new SdtListItem("Item 2", "2"));
	doc.FirstSection.Body.AppendChild(sdt);
	doc.Save(dataDir + "WorkingWithSdt.ComboBoxContentControl.docx");
```

就是這樣！您已使用 Aspose.Words for .NET 在 Word 文件中成功建立了組合框內容控制項。