---
title: 將文字輸入表單欄位匯出為文字
linktitle: 將文字輸入表單欄位匯出為文字
second_title: Aspose.Words 文件處理 API
description: 使用 Aspose.Words for .NET 將文字輸入表單欄位匯出為純文字的逐步指南。
type: docs
weight: 10
url: /zh-hant/net/programming-with-htmlsaveoptions/export-text-input-form-field-as-text/
---

在本教程中，我們將引導您完成 C# 原始程式碼，以使用 Aspose.Words for .NET 將文字輸入表單欄位匯出為純文字。此功能可讓您將文本輸入表單欄位匯出為可讀文本，而不是將其匯出為 HTML 輸入元素。

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

現在我們將配置 HTML 儲存選項以將文字輸入表單欄位匯出為純文字。使用以下程式碼：

```csharp
string imagesDir = Path. Combine(ArtifactsDir, "Images");

//指定的資料夾必須存在且為空。
if (Directory.Exists(imagesDir))
Directory. Delete(imagesDir, true);

Directory.CreateDirectory(imagesDir);

HtmlSaveOptions saveOptions = new HtmlSaveOptions(SaveFormat.Html)
{
ExportTextInputFormFieldAsText = true,
ImagesFolder = imagesDir
};
```

這段程式碼創建了一個實例`HtmlSaveOptions`並設定`ExportTextInputFormFieldAsText`選項`true`將文字輸入表單欄位匯出為純文字。此外，它還指定保存提取的圖像的資料夾。

## 步驟 4：將文件轉換並儲存為 HTML

最後，我們將使用先前配置的 HTML 儲存選項將文件轉換為 HTML。使用以下程式碼：

```csharp
doc.Save(dataDir + "WorkingWithHtmlSaveOptions.ExportTextInputFormFieldAsText.html", saveOptions);
```

此程式碼透過將文字輸入表單欄位匯出為純文字來將文件轉換為 HTML，並將匯出的 HTML 檔案儲存到指定目錄。

### 使用 Aspose.Words for .NET 將文字輸入表單欄位匯出為文字的範例原始程式碼


```csharp

	//文檔目錄的路徑。
	string dataDir = "YOUR DOCUMENT DIRECTORY";
	Document doc = new Document(dataDir + "Rendering.docx");

	string imagesDir = Path.Combine(ArtifactsDir, "Images");

	//指定的資料夾需要存在並且應該為空。
	if (Directory.Exists(imagesDir))
		Directory.Delete(imagesDir, true);

	Directory.CreateDirectory(imagesDir);

	//設定選項以將表單欄位匯出為純文本，而不是 HTML 輸入元素。
	HtmlSaveOptions saveOptions = new HtmlSaveOptions(SaveFormat.Html)
	{
		ExportTextInputFormFieldAsText = true, ImagesFolder = imagesDir
	};

	doc.Save(dataDir + "WorkingWithHtmlSaveOptions.ExportTextInputFormFieldAsText.html", saveOptions);

```

請務必在檔案目錄中指定正確的路徑`dataDir`多變的。