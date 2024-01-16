---
title: 複選框類型內容控件
linktitle: 複選框類型內容控件
second_title: Aspose.Words 文件處理 API
description: 了解如何使用 Aspose.Words for .NET 在 Word 文件中建立複選框類型內容控制項。
type: docs
weight: 10
url: /zh-hant/net/programming-with-sdt/check-box-type-content-control/
---

本教學課程介紹如何使用 Aspose.Words for .NET 在 Word 文件中建立複選框類型內容控制項。複選框內容控制項可讓使用者選擇或清除文件中的複選框。

## 先決條件
要學習本教程，您需要具備以下條件：

- 已安裝 Aspose.Words for .NET 程式庫。
- C# 和 Word 文件文字處理的基礎知識。

## 第 1 步：設定文檔目錄
首先設定文檔目錄的路徑。代替`"YOUR DOCUMENT DIRECTORY"`與要儲存文件的目錄的實際路徑。

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## 第 2 步：建立文件和 DocumentBuilder
建立一個新實例`Document`類別和一個`DocumentBuilder`建構文檔的內容。

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
```

## 步驟 3：新增複選框類型內容控件
創建一個`StructuredDocumentTag`和`SdtType.Checkbox`代表複選框內容控制項。指定`MarkupLevel.Inline`將其放置在文字中。

```csharp
StructuredDocumentTag sdtCheckBox = new StructuredDocumentTag(doc, SdtType.Checkbox, MarkupLevel.Inline);
builder.InsertNode(sdtCheckBox);
```

## 步驟 4：儲存文檔
使用以下命令將文件儲存到指定目錄`Save`方法。提供所需的檔案名稱和適當的檔案副檔名。在此範例中，我們將文件另存為「WorkingWithSdt.CheckBoxTypeContentControl.docx」。

```csharp
doc.Save(dataDir + "WorkingWithSdt.CheckBoxTypeContentControl.docx", SaveFormat.Docx);
```

### 使用 Aspose.Words for .NET 的複選框類型內容控制項的範例原始程式碼 

```csharp
	//文檔目錄的路徑
	string dataDir = "YOUR DOCUMENT DIRECTORY";

	Document doc = new Document();
	DocumentBuilder builder = new DocumentBuilder(doc);
	StructuredDocumentTag sdtCheckBox = new StructuredDocumentTag(doc, SdtType.Checkbox, MarkupLevel.Inline);
	builder.InsertNode(sdtCheckBox);
	doc.Save(dataDir + "WorkingWithSdt.CheckBoxTypeContentControl.docx", SaveFormat.Docx);
```

就是這樣！您已使用 Aspose.Words for .NET 在 Word 文件中成功建立了複選框類型內容控制項。