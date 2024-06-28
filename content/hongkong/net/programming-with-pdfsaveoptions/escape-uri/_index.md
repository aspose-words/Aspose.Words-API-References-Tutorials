---
title: PDF 文件中的轉義 URI
linktitle: PDF 文件中的轉義 URI
second_title: Aspose.Words 文件處理 API
description: 逐步指南如何使用 Aspose.Words for .NET 在 PDF 文件中轉義 URI。
type: docs
weight: 10
url: /zh-hant/net/programming-with-pdfsaveoptions/escape-uri/
---

本文提供了有關如何使用 Aspose.Words for .NET 轉義 PDF 文件中的 URI 的逐步指南。我們將詳細解釋程式碼的每一部分。在本教程結束時，您將能夠了解如何在文件中插入帶有轉義 Uri 的超連結。

在開始之前，請確保您已在專案中安裝並設定了 Aspose.Words for .NET 程式庫。您可以在 Aspose 網站上找到庫和安裝說明。

## 步驟1：定義文檔目錄

首先，您需要定義文件所在目錄的路徑。代替`"YOUR DOCUMENT DIRECTORY"`與文檔目錄的實際路徑。

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## 第 2 步：建立文件和 DocumentBuilder

接下來，我們需要建立一個新的`Document`物件和一個`DocumentBuilder`對象來建構文檔。

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
```

## 步驟 3：插入帶有轉義 Uri 的超鏈接

使用`InsertHyperlink`的方法`DocumentBuilder`物件將超連結插入文件中。 Uri 必須使用轉義`Uri.EscapeUriString`函數以避免格式錯誤。

```csharp
builder.InsertHyperlink("Testlink",
     Uri.EscapeUriString("https://www.google.com/search?q=%2Fthe%20test"), false);
builder. Writen();
builder.InsertHyperlink(Uri.EscapeUriString("https://www.google.com/search?q=%2Fthe%20test"),
     Uri.EscapeUriString("https://www.google.com/search?q=%2Fthe%20test"), false);
```

## 步驟 4：將文件另存為 PDF

最後，我們可以使用以下命令將文件另存為 PDF：`Save`的方法`Document`目的。指定輸出檔名。

```csharp
doc.Save(dataDir + "WorkingWithPdfSaveOptions.EscapeUri.pdf");
```

就這樣 ！您已使用 Aspose.Words for .NET 在文件中成功插入帶有轉義 Uri 的超連結。

### 使用 Aspose.Words for .NET 進行 Uri 轉義的範例原始碼


```csharp

	//文檔目錄的路徑。
	string dataDir = "YOUR DOCUMENT DIRECTORY";
	Document doc = new Document();
	DocumentBuilder builder = new DocumentBuilder(doc);
	
	builder.InsertHyperlink("Testlink", 
		"https://www.google.com/search?q=%2Fthe%20test", false);
	builder.Writeln();
	builder.InsertHyperlink("https:// www.google.com/search?q=%2Fthe%20test",
		"https://www.google.com/search?q=%2Fthe%20test", false);

	doc.Save(dataDir + "WorkingWithPdfSaveOptions.EscapeUri.pdf");    
  
```

## 結論

在本教學中，我們介紹如何使用 Aspose.Words for .NET 在 PDF 文件中轉義 URI。透過轉義 URI，您可以避免格式錯誤並確保超連結在 PDF 文件中正確解釋和顯示。請依照概述的步驟將帶有轉義 URI 的超連結插入到 PDF 文件中。一定要逃走。

### 經常問的問題

#### Q：PDF 文件中的轉義 URI 是什麼？
答：PDF文件中的轉義URI是指將URL中的特殊字元轉換為轉義序列以避免格式錯誤的方法。這很重要，因為 URL 中的特殊字元可能會破壞 URL 的結構並導致誤解或不正確的呈現。透過轉義特殊字符，我們保證 URL 被正確解釋並顯示在 PDF 文件中。

#### Q：如何使用 Aspose.Words for .NET 轉義 PDF 文件中的 URI？
答：若要使用 Aspose.Words for .NET 轉義 PDF 文件中的 URI，請依照下列步驟操作：

透過替換設定文件所在的目錄路徑`"YOUR DOCUMENT DIRECTORY"`與文檔目錄的實際路徑。

建立一個新實例`Document`類別和一個`DocumentBuilder`對象來建構文檔。

使用`InsertHyperlink`的方法`DocumentBuilder`物件將超連結插入文件中。確保使用轉義 URI`Uri.EscapeUriString`函數以避免格式錯誤。

使用`Save`的方法`Document`物件透過指定輸出檔案的名稱將文件儲存為 PDF 格式。

#### Q：在 PDF 文件中轉義 URI 有什麼好處？
答：在 PDF 文件中轉義 URI 的好處是：

防止格式錯誤：URI 轉義有助於防止 URL 中的特殊字元引起的格式錯誤，確保 URL 被正確解釋並顯示在 PDF 文件中。

與 PDF 閱讀器的兼容性：轉義 URI 通常受到 PDF 閱讀器的良好支持，確保更好的兼容性和一致的用戶體驗。

#### Q：URI 中哪些特殊字元應該轉義？
答：URI 中必須轉義的特殊字元有：空格、<、>、"、#、%、{、}、|, \, ^, ~, [, ], `, ;, /, ?, :, @, =, &, $, +, ,, [, ], and !.