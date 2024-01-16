---
title: 將圖元檔轉換為 Emf 或 Wmf
linktitle: 將圖元檔轉換為 Emf 或 Wmf
second_title: Aspose.Words 文件處理 API
description: 使用 Aspose.Words for .NET 將文件轉換為 HTML 時將圖元檔案轉換為 EMF 或 WMF 格式的逐步指南。
type: docs
weight: 10
url: /zh-hant/net/programming-with-htmlsaveoptions/convert-metafiles-to-emf-or-wmf/
---

在本教程中，我們將引導您完成 C# 原始程式碼，以使用 Aspose.Words for .NET 將圖元檔案轉換為 EMF 或 WMF 格式。此功能可讓您在將文件轉換為 HTML 時將圖元檔案格式的圖片轉換為更相容的格式，例如 EMF 或 WMF。

## 第 1 步：項目設置

首先，在您最喜歡的 IDE 中建立一個新的 C# 專案。請確定您的專案中引用了 Aspose.Words for .NET 程式庫。

## 步驟 2：將影像插入文檔

在此步驟中，我們將在要轉換的文件中插入影像。使用以下程式碼透過 HTML 標記插入來自資料來源的圖像：

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

builder.Write("Here is an image as is: ");
builder.InsertHtml(
	@"<img src=""data:image/png;base64,
		iVBORw0KGgoAAAANSUhEUgAAAAoAAAAKCAYAAACNMs+9AAAABGdBTUEAALGP
		C/xhBQAAAAlwSFlzAAALEwAACxMBAJqcGAAAAAd0SU1FB9YGARc5KB0XV+IA
		AAAddEVYdENvbW1lbnQAQ3JlYXRlZCB3aXRoIFRoZSBHSU1Q72QlbgAAAF1J
		REFUGNO9zL0NglAAxPEfdLTs4BZM4DIO4C7OwQg2JoQ9LE1exdlYvBBeZ7jq
		ch9//q1uH4TLzw4d6+ErXMMcXuHWxId3KOETnnXXV6MJpcq2MLaI97CER3N0
		vr4MkhoXe0rZigAAAABJRU5ErkJggg=="" alt=""Red dot"" />");
```

這段程式碼創建了一個實例`Document`和`DocumentBuilder`建置文檔。它插入一個`<img>`使用 base64 編碼影像標記到文件中。

## 第 3 步：設定 HTML 儲存選項

現在我們將設定 HTML 儲存選項，包括用於圖像的圖元檔案格式。使用以下程式碼：

```csharp
HtmlSaveOptions saveOptions = new HtmlSaveOptions { MetafileFormat = HtmlMetafileFormat.EmfOrWmf };
```

這段程式碼創建了一個實例`HtmlSaveOptions`和集`MetafileFormat`到`HtmlMetafileFormat.EmfOrWmf`指定圖元檔案在轉換為 HTML 時應轉換為 EMF 或 WMF 格式。

## 步驟 4：將文件轉換並儲存為 HTML

最後，我們將使用先前定義的儲存 HTML 選項將文件轉換為 HTML。使用以下程式碼：

```csharp
doc.Save(dataDir + "WorkingWithHtmlSaveOptions.ConvertMetafilesToEmfOrWmf.html", saveOptions);
```

此程式碼將文件轉換為 HTML，並將其儲存到具有 EMF 或 WMF 格式的轉換圖元檔案的檔案中，具體取決於儲存選項集。

### 使用 Aspose.Words for .NET 將圖元檔轉換為 Emf 或 Wmf 的範例原始碼

```csharp

	//文檔目錄的路徑。
	string dataDir = "YOUR DOCUMENT DIRECTORY";
	Document doc = new Document();
	DocumentBuilder builder = new DocumentBuilder(doc);

	builder.Write("Here is an image as is: ");
	builder.InsertHtml(
		@"<img src=""data:image/png;base64,
			iVBORw0KGgoAAAANSUhEUgAAAAoAAAAKCAYAAACNMs+9AAAABGdBTUEAALGP
			C/xhBQAAAAlwSFlzAAALEwAACxMBAJqcGAAAAAd0SU1FB9YGARc5KB0XV+IA
			AAAddEVYdENvbW1lbnQAQ3JlYXRlZCB3aXRoIFRoZSBHSU1Q72QlbgAAAF1J
			REFUGNO9zL0NglAAxPEfdLTs4BZM4DIO4C7OwQg2JoQ9LE1exdlYvBBeZ7jq
			ch9//q1uH4TLzw4d6+ErXMMcXuHWxId3KOETnnXXV6MJpcq2MLaI97CER3N0
			vr4MkhoXe0rZigAAAABJRU5ErkJggg=="" alt=""Red dot"" />");

	HtmlSaveOptions saveOptions = new HtmlSaveOptions { MetafileFormat = HtmlMetafileFormat.EmfOrWmf };

	doc.Save(dataDir + "WorkingWithHtmlSaveOptions.ConvertMetafilesToEmfOrWmf.html", saveOptions);

```

請務必在檔案目錄中指定正確的路徑`dataDir`多變的。

現在您已經了解了在使用 Aspose.Words for .NET 將文件轉換為 HTML 時如何將圖元檔轉換為 EMF 或 WMF 格式。透過遵循本教學中提供的逐步指南，您可以輕鬆管理轉換後的 HTML 文件中的圖元檔案。