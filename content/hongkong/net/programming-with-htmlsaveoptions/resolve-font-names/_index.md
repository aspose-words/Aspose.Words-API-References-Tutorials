---
title: 解析字體名稱
linktitle: 解析字體名稱
second_title: Aspose.Words 文件處理 API
description: 使用 Aspose.Words for .NET 轉換為 HTML 時解決缺少字體名稱的逐步指南。
type: docs
weight: 10
url: /zh-hant/net/programming-with-htmlsaveoptions/resolve-font-names/
---

在本教程中，我們將引導您完成 C# 原始程式碼，以使用 Aspose.Words for .NET 解決缺少的字體名稱問題。此功能可讓您在將文件轉換為 HTML 時自動解決遺失的字型名稱問題。

## 第 1 步：項目設置

首先，在您最喜歡的 IDE 中建立一個新的 C# 專案。請確定您的專案中引用了 Aspose.Words for .NET 程式庫。

## 第 2 步：載入文檔

在此步驟中，我們將載入要處理的文件。使用以下程式碼從指定目錄載入文件：

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document doc = new Document(dataDir + "Missing font.docx");
```

這段程式碼創建了一個實例`Document`透過從指定目錄載入文件。

## 步驟 3：設定 HTML 備份選項

現在我們將配置 HTML 儲存選項以解決轉換期間遺失的字體名稱問題。使用以下程式碼：

```csharp
HtmlSaveOptions saveOptions = new HtmlSaveOptions(SaveFormat.Html)
{
PrettyFormat = true,
ResolveFontNames=true
};
```

這段程式碼創建了一個實例`HtmlSaveOptions`並設定`ResolveFontNames`選項`true`解決轉換為 HTML 時缺少字體名稱的問題。另外，`PrettyFormat`選項設定為`true`獲得格式良好的 HTML 程式碼。

## 步驟 4：將文件轉換並儲存為 HTML

最後，我們將使用先前配置的 HTML 儲存選項將文件轉換為 HTML。使用以下程式碼：

```csharp
doc.Save(dataDir + "WorkingWithHtmlSaveOptions.ResolveFontNames.html", saveOptions);
```

此程式碼透過自動解析缺少的字型名稱將文件轉換為 HTML，並將轉換後的 HTML 檔案儲存到指定目錄。

### 使用 Aspose.Words for .NET 解析字體名稱的範例原始程式碼

```csharp

	//文檔目錄的路徑。
	string dataDir = "YOUR DOCUMENT DIRECTORY";
	Document doc = new Document(dataDir + "Missing font.docx");

	HtmlSaveOptions saveOptions = new HtmlSaveOptions(SaveFormat.Html)
	{
		PrettyFormat = true, ResolveFontNames = true
	};

	doc.Save(dataDir + "WorkingWithHtmlSaveOptions.ResolveFontNames.html", saveOptions);

```

請務必在檔案目錄中指定正確的路徑`dataDir`多變的。