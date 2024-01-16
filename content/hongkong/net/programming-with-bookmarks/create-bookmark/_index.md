---
title: 在Word文檔中建立書籤
linktitle: 在Word文檔中建立書籤
second_title: Aspose.Words 文件處理 API
description: 了解如何使用 Aspose.Words for .NET 在 Word 文件中建立書籤並在 PDF 中指定書籤預覽等級。
type: docs
weight: 10
url: /zh-hant/net/programming-with-bookmarks/create-bookmark/
---

在本文中，我們將探索上面的 C# 原始程式碼，以了解如何使用 Aspose.Words for .NET 程式庫中的建立書籤功能。此功能可讓您在文件中建立書籤並在輸出 PDF 檔案中指定書籤預覽等級。

## 先決條件

- C# 語言的基礎知識。
- 安裝了 Aspose.Words 函式庫的 .NET 開發環境。

## 第 1 步：建立文件和產生器

在建立書籤之前，我們需要使用以下命令建立一個文件和一個文件產生器`Document`和`DocumentBuilder`對象：

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
```

## 第 2 步：建立主書籤

我們使用`StartBookmark`啟動主書籤的方法和`EndBookmark`方法來結束它。在兩者之間，我們可以添加文字和其他書籤：

```csharp
builder. StartBookmark("My Bookmark");
builder.Writeln("Text inside a bookmark.");

//在此處添加更多書籤或文字。

builder. EndBookmark("My Bookmark");
```

## 第 3 步：建立巢狀書籤

我們也可以在主書籤內建立嵌套書籤。我們用同樣的`StartBookmark`和`EndBookmark`建立和結束巢狀書籤的方法：

```csharp
builder.StartBookmark("Embedded bookmark");
builder.Writeln("Text inside nested bookmark.");
builder.EndBookmark("Embedded bookmark");
```

## 步驟 4：在輸出 PDF 檔案中指定書籤預覽級別

我們使用`PdfSaveOptions`物件來指定輸出 PDF 檔案中的書籤預覽等級。我們使用`BookmarksOutlineLevels`財產

  新增主書籤和巢狀書籤及其各自的等級：

```csharp
PdfSaveOptions options = new PdfSaveOptions();
options.OutlineOptions.BookmarksOutlineLevels.Add("My Bookmark", 1);
options.OutlineOptions.BookmarksOutlineLevels.Add("Embedded bookmark", 2);
doc.Save(dataDir + "WorkingWithBookmarks.CreateBookmark.pdf", options);
```

### 使用 Aspose.Words for .NET 建立書籤的範例原始碼

以下是示範使用 Aspose.Words for .NET 建立書籤的完整範例原始碼：

```csharp

	//文檔目錄的路徑。
	string dataDir = "YOUR DOCUMENT DIRECTORY";
	Document doc = new Document();
	DocumentBuilder builder = new DocumentBuilder(doc);

	builder.StartBookmark("My Bookmark");
	builder.Writeln("Text inside a bookmark.");

	builder.StartBookmark("Nested Bookmark");
	builder.Writeln("Text inside a NestedBookmark.");
	builder.EndBookmark("Nested Bookmark");

	builder.Writeln("Text after Nested Bookmark.");
	builder.EndBookmark("My Bookmark");

	PdfSaveOptions options = new PdfSaveOptions();
	options.OutlineOptions.BookmarksOutlineLevels.Add("My Bookmark", 1);
	options.OutlineOptions.BookmarksOutlineLevels.Add("Nested Bookmark", 2);

	doc.Save(dataDir + "WorkingWithBookmarks.CreateBookmark.pdf", options);
  
```

## 結論

在本文中，我們探索了 C# 原始程式碼，以了解如何使用 Aspose.Words for .NET 的建立書籤功能。我們按照逐步指南在文件中建立書籤並在輸出 PDF 文件中指定書籤預覽等級。

### 常見問題解答

#### Q：使用 Aspose.Words for .NET 中的「建立書籤」功能有哪些先決條件？

答：要使用Aspose.Words for .NET中的「建立書籤」功能，您必須具備C#語言的基礎。您還需要一個安裝了 Aspose.Words 函式庫的 .NET 開發環境。

#### Q：如何在 Aspose.Words for .NET 中建立文件？

答：要在 Aspose.Words for .NET 中建立文檔，您可以使用`Document`班級。這是範例程式碼：

```csharp
Document doc = new Document();
```

#### Q：如何使用 Aspose.Words for .NET 在文件中建立主書籤？

答：要使用 Aspose.Words for .NET 在文件中建立主書籤，您可以使用`StartBookmark`方法啟動書籤，在裡面添加文字或其他書籤，然後使用` EndBookmark`結束它。這是範例程式碼：

```csharp
builder.StartBookmark("My Bookmark");
builder.Writeln("Text inside bookmark.");
builder.EndBookmark("My Bookmark");
```

#### Q：如何使用 Aspose.Words for .NET 在主書籤內建立巢狀書籤？

答：要使用 Aspose.Words for .NET 在主書籤內建立巢狀書籤，您可以使用相同的`StartBookmark`和`EndBookmark`開始和結束嵌套書籤的方法。這是範例程式碼：

```csharp
builder.StartBookmark("Embedded bookmark");
builder.Writeln("Text inside nested bookmark.");
builder.EndBookmark("Embedded bookmark");
```

#### Q：如何使用 Aspose.Words for .NET 在輸出 PDF 中指定書籤預覽等級？

答：要使用 Aspose.Words for .NET 在輸出 PDF 中指定書籤預覽級別，您可以使用`PdfSaveOptions`類和`BookmarksOutlineLevels`財產。您可以添加主書籤和嵌套書籤及其各自的層級。這是範例程式碼：

```csharp
PdfSaveOptions options = new PdfSaveOptions();
options.OutlineOptions.BookmarksOutlineLevels.Add("My Bookmark", 1);
options.OutlineOptions.BookmarksOutlineLevels.Add("Embedded bookmark", 2);
```

#### Q：使用 Aspose.Words for .NET 建立書籤後如何儲存文件？

答：要在使用 Aspose.Words for .NET 建立書籤後儲存文檔，您可以使用`Save`的方法`Document`指定目標檔案路徑的物件。這是範例程式碼：

```csharp
doc.Save("path/to/your/output-document.docx");
```

#### Q：如何使用 Aspose.Words for .NET 在輸出 PDF 中指定書籤預覽等級？

答：要使用 Aspose.Words for .NET 在輸出 PDF 中指定書籤預覽級別，您可以使用`PdfSaveOptions`類和`BookmarksOutlineLevels`財產。您可以添加主書籤和嵌套書籤及其各自的層級。這是範例程式碼：

```csharp
PdfSaveOptions options = new PdfSaveOptions();
options.OutlineOptions.BookmarksOutlineLevels.Add("My Bookmark", 1);
options.OutlineOptions.BookmarksOutlineLevels.Add("Embedded bookmark", 2);
doc.Save("path/to/your/output-pdf-file.pdf", options);
```

#### Q：如何使用 Aspose.Words for .NET 在主書籤內建立巢狀書籤？

答：要使用 Aspose.Words for .NET 在主書籤內建立巢狀書籤，您可以使用相同的`StartBookmark`和`EndBookmark`開始和結束嵌套書籤的方法。呼叫時請務必指定父書籤作為參數`StartBookmark`方法。這是範例程式碼：

```csharp
builder.StartBookmark("Main bookmark");
builder.Writeln("Text inside main bookmark.");

builder.StartBookmark("Nested bookmark 1");
builder.Writeln("Text inside first nested bookmark.");
builder.EndBookmark("Nested bookmark 1");

builder.StartBookmark("Nested bookmark 2");
builder.Writeln("Text inside second nested bookmark.");
builder.EndBookmark("Nested bookmark 2");

builder.EndBookmark("Main bookmark");
```

#### Q：如何使用 Aspose.Words for .NET 在書籤內新增文字？

答：要使用 Aspose.Words for .NET 在書籤內新增文本，您可以使用`Write`的方法`DocumentBuilder`指定要新增的文字的物件。這是範例程式碼：

```csharp
builder.StartBookmark("My Bookmark");
builder.Write("Text inside bookmark.");
builder.EndBookmark("My Bookmark");
```

#### Q：如何使用 Aspose.Words for .NET 在文件中建立主書籤？

答：要使用 Aspose.Words for .NET 在文件中建立主書籤，您可以使用`StartBookmark`啟動書籤的方法和`EndBookmark`方法來結束它。這是範例程式碼：

```csharp
builder.StartBookmark("My Bookmark");
builder.Writeln("Text inside bookmark.");
builder.EndBookmark("My Bookmark");
```