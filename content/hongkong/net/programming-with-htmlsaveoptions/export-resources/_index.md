---
title: 出口資源
linktitle: 出口資源
second_title: Aspose.Words 文件處理 API
description: 使用 Aspose.Words for .NET 將文件資源儲存為 HTML 時匯出文件資源的逐步指南。
type: docs
weight: 10
url: /zh-hant/net/programming-with-htmlsaveoptions/export-resources/
---

在本教學中，我們將引導您完成 C# 原始程式碼，以使用 Aspose.Words for .NET 匯出文件資源。此功能可讓您在以 HTML 格式儲存文件時將資源（例如字體）匯出為外部文件。

## 第 1 步：項目設置

首先，在您最喜歡的 IDE 中建立一個新的 C# 專案。請確定您的專案中引用了 Aspose.Words for .NET 程式庫。

## 第 2 步：載入文檔

在此步驟中，我們將載入要匯出的文件。使用以下程式碼從指定目錄載入文件：

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document doc = new Document(dataDir + "Rendering.docx");
```

這段程式碼創建了一個實例`Document`透過從指定目錄載入文件。

## 步驟 3：設定 HTML 備份選項

現在我們將配置 HTML 儲存選項來匯出文件資源。使用以下程式碼：

```csharp
HtmlSaveOptions saveOptions = new HtmlSaveOptions
{
CssStyleSheetType = CssStyleSheetType.External,
ExportFontResources=true,
ResourceFolder = ArtifactsDir + "Resources",
ResourceFolderAlias = "http://example.com/resources”
};
```

這段程式碼創建了一個實例`HtmlSaveOptions`並設定以下選項：

- `CssStyleSheetType`被設定為`CssStyleSheetType.External`將 CSS 樣式表匯出到外部文件。
- `ExportFontResources`被設定為`true`導出字體資源。
- `ResourceFolder`指定保存資源的目標目錄。
- `ResourceFolderAlias`指定將用於存取資源的 URL 別名。

## 步驟 4：將文件轉換並儲存為 HTML

最後，我們將使用先前配置的 HTML 儲存選項將文件轉換為 HTML。使用以下程式碼：

```csharp
doc.Save(dataDir + "WorkingWithHtmlSaveOptions.ExportResources.html", saveOptions);
```

此程式碼將文件轉換為 HTML 並使用指定的 URL 別名將資源儲存到指定目錄。

### 使用 Aspose.Words for .NET 匯出資源的範例原始程式碼

```csharp

	//文檔目錄的路徑。
	string dataDir = "YOUR DOCUMENT DIRECTORY";
	Document doc = new Document(dataDir + "Rendering.docx");

	HtmlSaveOptions saveOptions = new HtmlSaveOptions
	{
		CssStyleSheetType = CssStyleSheetType.External,
		ExportFontResources = true,
		ResourceFolder = ArtifactsDir + "Resources",
		ResourceFolderAlias = "http://example.com/resources”
	};

	doc.Save(dataDir + "WorkingWithHtmlSaveOptions.ExportResources.html", saveOptions);
  
```

請務必在檔案目錄中指定正確的路徑`dataDir`多變的。