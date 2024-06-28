---
title: 忽略刪除修訂內的文本
linktitle: 忽略刪除修訂內的文本
second_title: Aspose.Words 文件處理 API
description: 了解如何使用 Aspose.Words for .NET 的「忽略刪除修訂內的文字」功能。
type: docs
weight: 10
url: /zh-hant/net/find-and-replace-text/ignore-text-inside-delete-revisions/
---

在本文中，我們將探索上面的 C# 原始程式碼，以了解如何使用 Aspose.Words for .NET 程式庫中的「忽略刪除修訂內的文字」功能。當我們在對文件進行文字處理時想要忽略刪除修訂內的文字時，此功能非常有用。

## Aspose.Words for .NET 函式庫概述

在深入了解程式碼細節之前，讓我先簡單介紹一下 Aspose.Words for .NET 函式庫。它是一個功能強大的程式庫，允許在 .NET 應用程式中建立、修改和轉換 Word 文件。它為文件的文字處理提供了許多高級功能，包括修訂管理。

## 了解「忽略刪除修訂內的文字」功能

Aspose.Words for .NET 中的「忽略刪除修訂內的文字」功能可讓您指定在某些操作（例如尋找和取代文字）期間是否應忽略刪除修訂內的文字。啟用此功能後，操作期間不會考慮修訂版內已刪除的文字。

## 步驟 1：使用 Aspose.Words for .NET 建立新文檔

在開始操作文件中的文字之前，我們需要使用 Aspose.Words for .NET 建立一個新文件。可以透過實例化一個來完成`Document`目的：

```csharp
Document doc = new Document();
```

## 步驟 2：將未修改的文字插入文件中

一旦我們有了文檔，我們就可以使用插入未審閱的文本`DocumentBuilder`目的。例如，要插入文字“Deleted Text”，我們可以使用`Writeln`和`Write`方法：

```csharp
DocumentBuilder builder = new DocumentBuilder(doc);
builder. Writen("Deleted");
builder. Write("Text");
```

## 步驟 3：刪除有追蹤修訂的段落

為了說明「忽略刪除修訂內的文字」功能的用法，我們將使用修訂追蹤從文件中刪除一個段落。這將使我們能夠看到該功能如何影響後續操作。

```csharp
doc.StartTrackRevisions("author", DateTime.Now);
doc.FirstSection.Body.FirstParagraph.Remove();
doc.StopTrackRevisions();
```

## 步驟 4：套用「忽略刪除修訂內的文字」功能

現在我們已經透過刪除段落準備了文檔，我們可以使用以下命令啟用「忽略刪除修訂內的文字」功能`FindReplaceOptions`目的。我們將設定`IgnoreDeleted`財產給`true`:

```csharp
FindReplaceOptions options = new FindReplaceOptions { IgnoreDeleted = true };
```

## 步驟 5：使用正規表示式進行尋找和替換

為了對文件文字執行搜尋和取代操作，我們將使用正規表示式。在我們的範例中，我們將搜尋所有出現的字母“e”並將其替換為星號“* 「。 。網`Regex`類別用於此目的：

```csharp
Regex regex = new Regex("e");
doc.Range.Replace(regex, "*", options);
```

## 步驟 6：顯示修改後的文件輸出

套用搜尋和取代後，我們可以使用以下命令顯示文件的變更內容`GetText`方法：

```csharp
Console.WriteLine(doc.GetText());
```

## 步驟 7：修改選項以包含已刪除的文本

如果我們想在輸出結果中包含已刪除的文本，我們可以更改選項以不忽略已刪除的文本。為此我們將設置`IgnoreDeleted`財產給`false`:

```csharp
options. IgnoreDeleted = false;
```

## 步驟8：輸出刪除文字的修改後的文檔

更改選項後，我們可以再次執行搜尋並替換以獲得包含刪除文字的結果：

```csharp
doc.Range.Replace(regex, "*", options);
Console.WriteLine(doc.GetText());
```

### 使用 Aspose.Words for .NET 忽略刪除修訂內的文字的範例原始程式碼

以下是完整的範例原始程式碼，示範如何使用 Aspose.Words for .NET 的「忽略刪除修訂內的文字」功能：

```csharp
        
	Document doc = new Document();
	DocumentBuilder builder = new DocumentBuilder(doc);

	//插入未修改的文字。
	builder.Writeln("Deleted");
	builder.Write("Text");

	//刪除帶有追蹤修訂的第一段。
	doc.StartTrackRevisions("author", DateTime.Now);
	doc.FirstSection.Body.FirstParagraph.Remove();
	doc.StopTrackRevisions();

	FindReplaceOptions options = new FindReplaceOptions { IgnoreDeleted = true };

	Regex regex = new Regex("e");
	doc.Range.Replace(regex, "*", options);

	Console.WriteLine(doc.GetText());

	options.IgnoreDeleted = false;
	doc.Range.Replace(regex, "*", options);

	Console.WriteLine(doc.GetText());
    
```

## 結論

在本文中，我們探索了 C# 原始程式碼，以了解如何使用 Aspose.Words for .NET 中的「忽略刪除修訂內的文字」功能。此功能對於在操作文件時忽略刪除修訂內的文字非常有用。我們依照逐步指南建立文件、插入文字、刪除有修訂追蹤的段落、套用「忽略刪除修訂內的文字」功能，以及執行尋找和取代操作。

### 常見問題解答

#### Q：Aspose.Words for .NET 中的「忽略刪除修訂內的文字」功能是什麼？

答：Aspose.Words for .NET 中的「忽略刪除修訂內的文字」功能可讓您指定在某些操作（例如尋找和取代文字）期間是否應忽略刪除修訂內的文字。啟用此功能後，操作期間不會考慮修訂版內已刪除的文字。

#### Q：什麼是 Aspose.Words for .NET？

答：Aspose.Words for .NET 是一個功能強大的程式庫，用於建立、編輯 Word 文件並將其轉換為 .NET 應用程式。它為文件的文字處理提供了許多高級功能，包括修訂管理。

#### Q：如何在 Aspose.Words for .NET 中建立新文件？

答：在開始操作文件中的文字之前，您需要使用 Aspose.Words for .NET 建立一個新文件。這可以透過實例化一個來完成`Document`目的。以下是建立新文件的範例程式碼：

```csharp
Document doc = new Document();
```

#### Q：如何使用 Aspose.Words for .NET 將未編輯的文字插入文件中？

答：一旦有了文檔，您可以使用`DocumentBuilder`目的。例如，要插入文字“已刪除文字”，您可以使用`Writeln`和`Write`方法：

```csharp
DocumentBuilder builder = new DocumentBuilder(doc);
builder.Writen("Deleted");
builder.Write("Text");
```

#### Q：如何在 Aspose.Words for .NET 中刪除帶有修訂追蹤的段落？

答：為了說明「忽略刪除修訂內的文字」功能的使用，我們將使用修訂追蹤從文件中刪除一個段落。這將使我們能夠看到該函數如何影響後續操作。

```csharp
doc.StartTrackRevisions("author", DateTime.Now);
doc.FirstSection.Body.FirstParagraph.Remove();
doc.StopTrackRevisions();
```

#### Q：如何在 Aspose.Words for .NET 中啟用「忽略刪除修訂內的文字」功能？

答：現在我們已經透過刪除段落準備好了文檔，我們可以使用以下命令啟用「忽略刪除修訂內的文字」功能：`FindReplaceOptions`目的。我們將設定`IgnoreDeleted`財產給`true`:

```csharp
FindReplaceOptions options = new FindReplaceOptions { IgnoreDeleted = true };
```

#### Q：如何在 Aspose.Words for .NET 中使用正規表示式進行搜尋和取代？

答：為了對文檔文字執行搜尋和取代操作，我們將使用正規表示式。在我們的範例中，我們將搜尋所有出現的字母“e”並將其替換為星號“* 」。我們將使用.NET`Regex`為此類：

```csharp
Regex regex = new Regex("e");
doc.Range.Replace(regex, "*", options);
```

#### Q：如何在 Aspose.Words for .NET 中查看更改的文件內容？

A：套用搜尋和取代後，我們可以使用以下命令顯示文件的變更內容`GetText`方法：

```csharp
Console.WriteLine(doc.GetText());
```

#### Q：如何在 Aspose.Words for .NET 的輸出結果中包含刪除的文字？

答：如果我們想在輸出結果中包含已刪除的文本，我們可以更改選項以不忽略已刪除的文本。為此，我們將設置`IgnoreDeleted`財產給`false`:

```csharp
options. IgnoreDeleted = false;
```

#### Q：如何在 Aspose.Words for .NET 中顯示已編輯且已刪除文字的文件？

A：更改選項後，我們可以進行新的搜尋和替換，得到包含刪除文字的結果：

```csharp
doc.Range.Replace(regex, "*", options);
Console.WriteLine(doc.GetText());
```
