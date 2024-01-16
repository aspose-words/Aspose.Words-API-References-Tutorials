---
title: 加入 CSS 類別名稱前綴
linktitle: 加入 CSS 類別名稱前綴
second_title: Aspose.Words 文件處理 API
description: 使用 Aspose.Words for .NET 將文件轉換為 HTML 時新增 CSS 類別名稱前綴的逐步指南。
type: docs
weight: 10
url: /zh-hant/net/programming-with-htmlsaveoptions/add-css-class-name-prefix/
---

在本教學中，我們將引導您完成 C# 原始程式碼，以使用 Aspose.Words for .NET 新增 CSS 類別名稱前綴。此功能可讓您在將文件轉換為 HTML 時為產生的 CSS 類別名稱新增自訂前綴。

## 第 1 步：項目設置

首先，在您最喜歡的 IDE 中建立一個新的 C# 專案。請確定您的專案中引用了 Aspose.Words for .NET 程式庫。

## 第 2 步：載入文檔

在此步驟中，我們將載入要轉換為 HTML 的 Word 文件。使用以下程式碼載入文件：

```csharp
//文檔目錄的路徑。
string dataDir = "YOUR DOCUMENTS DIRECTORY";
Document doc = new Document(dataDir + "Rendering.docx");
```

代替`"YOUR DOCUMENTS DIRECTORY"`與文件所在目錄的實際路徑。

## 第 3 步：設定 HTML 儲存選項

現在讓我們設定 HTML 儲存選項，包括 CSS 樣式表類型和 CSS 類別名稱前綴。使用以下程式碼：

```csharp
HtmlSaveOptions saveOptions = new HtmlSaveOptions
{
     CssStyleSheetType = CssStyleSheetType.External,
     CssClassNamePrefix = "pfx_"
};
```

這段程式碼創建了一個實例`HtmlSaveOptions`和集`CssStyleSheetType`到`CssStyleSheetType.External`產生外部 CSS 樣式表，以及`CssClassNamePrefix`到`"pfx_"`前綴`"pfx_"`命名 CSS 類別。

## 步驟 4：將文件轉換並儲存為 HTML

最後，我們將使用先前定義的 HTML 儲存選項將文件轉換為 HTML。使用以下程式碼：

```csharp
doc.Save(dataDir + "WorkingWithHtmlSaveOptions.AddCssClassNamePrefix.html", saveOptions);
```

此程式碼將文件轉換為 HTML 並將其儲存到新增了 CSS 類別名稱前綴的檔案中。

### 使用 Aspose.Words for .NET 新增 Css 類別名稱前綴的範例原始程式碼

```csharp

	//文檔目錄的路徑。
	string dataDir = "YOUR DOCUMENT DIRECTORY";
	Document doc = new Document(dataDir + "Rendering.docx");

	HtmlSaveOptions saveOptions = new HtmlSaveOptions
	{
		CssStyleSheetType = CssStyleSheetType.External, CssClassNamePrefix = "pfx_"
	};
	
	doc.Save(dataDir + "WorkingWithHtmlSaveOptions.AddCssClassNamePrefix.html", saveOptions);

```

請務必在中指定正確的文件路徑`dataDir`多變的。

現在您已經了解如何使用 Aspose.Words for .NET 將文件轉換為 HTML 時新增 CSS 類別名稱前綴。按照本教學中提供的逐步指導步驟，您可以在轉換後的 HTML 文件中自訂 CSS 類別名稱。