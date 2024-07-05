---
title: 將圖元檔轉換為 Svg
linktitle: 將圖元檔轉換為 Svg
second_title: Aspose.Words 文件處理 API
description: 使用 Aspose.Words for .NET 將文件轉換為 HTML 時將圖元檔案轉換為 SVG 格式的逐步指南。
type: docs
weight: 10
url: /zh-hant/net/programming-with-htmlsaveoptions/convert-metafiles-to-svg/
---

在本教學中，我們將引導您完成 C# 原始程式碼，以使用 Aspose.Words for .NET 將圖元檔案轉換為 SVG 格式。此功能可讓您在將文件轉換為 HTML 時將圖元檔案轉換為 SVG 格式。

## 第 1 步：項目設置

首先，在您最喜歡的 IDE 中建立一個新的 C# 專案。請確定您的專案中引用了 Aspose.Words for .NET 程式庫。

## 步驟 2：將 SVG 影像插入文件中

在此步驟中，我們將在要轉換的文檔中插入 SVG 映像。使用以下程式碼透過 HTML 標籤插入 SVG 圖像：

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

builder.Write("Here is an SVG image: ");
builder.InsertHtml(
	@"<svg height='210' width='500'>
	<polygon points='100,10 40,198 190,78 10,78 160,198' 
		style='fill:lime;stroke:purple;stroke-width:5;fill-rule:evenodd;' />
</svg> ");
```

這段程式碼創建了一個實例`Document`和`DocumentBuilder`建置文檔。它插入一個`<svg>`標籤包含一個`<polygon>`具有定義 SVG 圖像的形狀和样式的屬性的元素。

## 第 3 步：設定 HTML 儲存選項

現在我們將設定 HTML 儲存選項，指定圖元檔案應轉換為 SVG 格式。使用以下程式碼：

```csharp
HtmlSaveOptions saveOptions = new HtmlSaveOptions { MetafileFormat = HtmlMetafileFormat.Svg };
```

這段程式碼創建了一個實例`HtmlSaveOptions`和集`MetafileFormat`到`HtmlMetafileFormat.Svg`指定圖元檔案在轉換為 HTML 時應轉換為 SVG 格式。

## 步驟 4：將文件轉換並儲存為 HTML

最後，我們將使用先前定義的 HTML 儲存選項將文件轉換為 HTML。使用以下程式碼：

```csharp
doc.Save(dataDir + "WorkingWithHtmlSaveOptions.ConvertMetafilesToSvg.html", saveOptions);
```

此程式碼將文件轉換為 HTML，並將其保存到一個文件中，其中圖元文件已轉換為 SVG。

### 使用 Aspose.Words for .NET 將圖元檔案轉換為 Svg 的範例原始程式碼

```csharp

	//文檔目錄的路徑。
	string dataDir = "YOUR DOCUMENT DIRECTORY";
	Document doc = new Document();
	DocumentBuilder builder = new DocumentBuilder(doc);
	
	builder.Write("Here is an SVG image: ");
	builder.InsertHtml(
		@"<svg height='210' width='500'>
		<polygon points='100,10 40,198 190,78 10,78 160,198' 
			style='fill:lime;stroke:purple;stroke-width:5;fill-rule:evenodd;' />
	</svg> ");

	HtmlSaveOptions saveOptions = new HtmlSaveOptions { MetafileFormat = HtmlMetafileFormat.Svg };

	doc.Save(dataDir + "WorkingWithHtmlSaveOptions.ConvertMetafilesToSvg.html", saveOptions);
	
```
