---
title: 富文本框內容控件
linktitle: 富文本框內容控件
second_title: Aspose.Words 文件處理 API
description: 了解如何使用 Aspose.Words for .NET 在 Word 文件中建立富文本框內容控制項，從而實現文字格式設定和樣式設定。
type: docs
weight: 10
url: /zh-hant/net/programming-with-sdt/rich-text-box-content-control/
---

本教學課程示範如何使用 Aspose.Words for .NET 在 Word 文件中建立富文本框內容控制項。富文本框內容控制項可讓使用者使用各種樣式和格式選項輸入文字並設定文字格式。

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
建立一個新實例`Document`類別和一個`StructuredDocumentTag`代表富文本方塊內容控制項。指定`SdtType.RichText`作為類型和`MarkupLevel.Block`作為標記層級來建立區塊級富文本框。

```csharp
Document doc = new Document();
StructuredDocumentTag sdtRichText = new StructuredDocumentTag(doc, SdtType.RichText, MarkupLevel.Block);
```

## 第 3 步：建立富文本內容並設定其格式
建立一個段落並運行以表示富文本內容。設定文字和格式選項，例如顏色、字體等。

```csharp
Paragraph para = new Paragraph(doc);
Run run = new Run(doc);
run.Text = "Hello World";
run.Font.Color = Color.Green;
para.Runs.Add(run);
```

## 步驟 4：將富文本內容新增至內容控件
將包含富文本內容的段落加入到`ChildNodes`富文本方塊內容控制項的集合。

```csharp
sdtRichText.ChildNodes.Add(para);
```

## 步驟 5：將內容控制項附加到文檔
使用以下命令將富文本框內容控制項附加到文件正文`AppendChild`文檔第一部分主體的方法。

```csharp
doc.FirstSection.Body.AppendChild(sdtRichText);
```

## 第 6 步：儲存文檔
使用以下命令將文件儲存到指定目錄`Save`方法。提供所需的檔案名稱和適當的檔案副檔名。在此範例中，我們將文件另存為「WorkingWithSdt.RichTextBoxContentControl.docx」。

```csharp
doc.Save(dataDir + "WorkingWithSdt.RichTextBoxContentControl.docx");
```

### 使用 Aspose.Words for .NET 的富文本框內容控制項的範例原始碼 

```csharp
	//文檔目錄的路徑
	string dataDir = "YOUR DOCUMENT DIRECTORY";

	Document doc = new Document();
	StructuredDocumentTag sdtRichText = new StructuredDocumentTag(doc, SdtType.RichText, MarkupLevel.Block);
	Paragraph para = new Paragraph(doc);
	Run run = new Run(doc);
	run.Text = "Hello World";
	run.Font.Color = Color.Green;
	para.Runs.Add(run);
	sdtRichText.ChildNodes.Add(para);
	doc.FirstSection.Body.AppendChild(sdtRichText);
	doc.Save(dataDir + "WorkingWithSdt.RichTextBoxContentControl.docx");
```

就是這樣！您已使用 Aspose.Words for .NET 在 Word 文件中成功建立了富文本框內容控制項。