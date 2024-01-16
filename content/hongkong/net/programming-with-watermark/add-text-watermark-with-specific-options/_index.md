---
title: 新增具有特定選項的文字浮水印
linktitle: 新增具有特定選項的文字浮水印
second_title: Aspose.Words 文件處理 API
description: 了解如何使用 Aspose.Words for .NET 新增具有特定選項的文字浮水印。逐步指南。
type: docs
weight: 10
url: /zh-hant/net/programming-with-watermark/add-text-watermark-with-specific-options/
---

在本教學中，我們將引導您了解如何使用 Aspose.Words for .NET 新增具有特定選項的文字浮水印。文字浮水印是疊加在文件上的文本，用於表示該文件是草稿、機密等。

## 第 1 步：使用文件產生器

首先，我們將使用文件產生器將內容新增至文件。

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## 第 2 步：載入文檔

我們將使用文檔路徑載入現有文檔。

```csharp
Document doc = new Document(MyDir + "Document.docx");
```

## 步驟 3：新增具有特定選項的文字浮水印

我們將建立一個實例`TextWatermarkOptions`類別並設定文字浮水印所需的選項。

```csharp
TextWatermarkOptions options = new TextWatermarkOptions()
{
FontFamily = "Arial",
FontSize = 36,
Color = Color.Black,
Layout = WatermarkLayout.Horizontal,
IsSemitrasparent = false
};

doc.Watermark.SetText("Test", options);
```

## 步驟 4：儲存文檔

最後，我們可以儲存新增了文字浮水印的文件。

```csharp
	doc.Save(dataDir + "WorkWithWatermark.AddTextWatermarkWithSpecificOptions.docx");
```

### 使用 Aspose.Words for .NET 新增具有特定選項的文字浮水印的範例原始程式碼

```csharp

	//文檔目錄的路徑。
	string dataDir = "YOUR DOCUMENT DIRECTORY";
	Document doc = new Document(MyDir + "Document.docx");

	TextWatermarkOptions options = new TextWatermarkOptions()
	{
		FontFamily = "Arial",
		FontSize = 36,
		Color = Color.Black,
		Layout = WatermarkLayout.Horizontal,
		IsSemitrasparent = false
	};

	doc.Watermark.SetText("Test", options);

	doc.Save(dataDir + "WorkWithWatermark.AddTextWatermarkWithSpecificOptions.docx");
	
```

恭喜！現在您已經了解如何使用 Aspose.Words for .NET 新增具有特定選項的文字浮水印。

