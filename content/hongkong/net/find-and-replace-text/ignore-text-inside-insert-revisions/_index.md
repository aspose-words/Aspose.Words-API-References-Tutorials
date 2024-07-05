---
title: 忽略插入修訂內的文本
linktitle: 忽略插入修訂內的文本
second_title: Aspose.Words 文件處理 API
description: 了解如何使用 Aspose.Words for .NET 的「忽略插入修訂內的文字」功能來操作 Word 文件中的插入修訂。
type: docs
weight: 10
url: /zh-hant/net/find-and-replace-text/ignore-text-inside-insert-revisions/
---

在本文中，我們將探索上面的 C# 原始程式碼，以了解如何使用 Aspose.Words for .NET 程式庫中的 Ignore Text Inside Insert Revisions 功能。當我們在操作文件時想要忽略插入修訂中的文字時，此功能非常有用。

## 先決條件

- C# 語言的基礎知識。
- 安裝了 Aspose.Words 函式庫的 .NET 開發環境。

## 第 1 步：建立新文檔

在我們開始操作插入修訂中的文字之前，我們需要使用 Aspose.Words for .NET 建立一個新文件。這可以透過實例化一個來完成`Document`目的：

```csharp
Document doc = new Document();
```

## 第 2 步：插入帶有修訂追蹤的文本

一旦我們有了文檔，我們就可以使用`DocumentBuilder`目的。例如，要插入帶有修訂追蹤的「已插入」文本，我們可以使用`StartTrackRevisions`, `Writeln`和`StopTrackRevisions`方法：

```csharp
DocumentBuilder builder = new DocumentBuilder(doc);
doc.StartTrackRevisions("author", DateTime.Now);
builder.Writeln("Inserted");
doc.StopTrackRevisions();
```

## 步驟 3：插入未經審閱的文本

除了帶有修訂追蹤的文字之外，我們還可以使用`DocumentBuilder`目的。例如，要插入文字“Text”而不進行修改，我們可以使用`Write`方法：

```csharp
builder.Write("Text");
```

## 步驟 4：使用「忽略插入修訂內的文字」功能

要在後續操作中忽略插入修訂內的文本，我們可以使用`FindReplaceOptions`對象並設定`IgnoreInserted`財產給`true`：

```csharp
FindReplaceOptions options = new FindReplaceOptions { IgnoreInserted = true };
```

## 步驟 5：使用正規表示式進行搜尋和替換

為了對文件文字執行搜尋操作和替換，我們將使用正規表示式。在我們的範例中，我們將搜尋所有出現的字母“e”並將其替換為星號“*「。我們將使用 .NET`Regex`為此類：

```csharp
Regex regex = new Regex("e");
doc.Range.Replace(regex, "*", options);
```

## 步驟6：查看修改後的文檔輸出

套用搜尋和取代後，我們可以使用以下命令顯示文件的變更內容`GetText`方法：

```csharp
Console.WriteLine(doc.GetText());
```

## 步驟 7：更改選項以包含插入修訂

如果我們想在輸出結果中包含插入修訂內的文本，我們可以更改選項以不忽略插入修訂。為此我們將設置`IgnoreInserted`財產給`false`：

```csharp
options.IgnoreInserted = false;
```

## 步驟 8：查看帶有插入修訂的修改文檔

更改選項後，我們可以再次執行搜尋並替換以獲得包含插入修訂內文本的結果：

```csharp
doc.Range.Replace(regex, "*", options);
Console.WriteLine(doc.GetText());
```


### 使用 Aspose.Words for .NET 忽略插入修訂內的文字的範例原始程式碼

以下是完整的範例原始程式碼，示範如何使用 Aspose.Words for .NET 忽略插入修訂內的文字功能：


```csharp
       
	Document doc = new Document();
	DocumentBuilder builder = new DocumentBuilder(doc);

	//插入帶有追蹤修訂的文字。
	doc.StartTrackRevisions("author", DateTime.Now);
	builder.Writeln("Inserted");
	doc.StopTrackRevisions();

	//插入未修改的文字。
	builder.Write("Text");

	FindReplaceOptions options = new FindReplaceOptions { IgnoreInserted = true };

	Regex regex = new Regex("e");
	doc.Range.Replace(regex, "*", options);
	
	Console.WriteLine(doc.GetText());

	options.IgnoreInserted = false;
	doc.Range.Replace(regex, "*", options);
	
	Console.WriteLine(doc.GetText());
   
```

## 結論

在本文中，我們探索了 C# 原始程式碼，以了解如何在 Aspose.Words for .NET 中使用 Ignore Text Inside Insert Revisions 功能。我們按照逐步指南建立文檔，插入帶有追蹤修訂和未修訂文字的文本，使用「忽略插入修訂內的文字」功能，使用正規表示式執行搜尋和取代操作，並顯示修改後的文檔。

### 常見問題解答

#### Q：Aspose.Words for .NET 中的「忽略插入修訂中的文字」功能是什麼？

答：Aspose.Words for .NET 中的「忽略插入修訂內的文字」功能可讓您指定在某些操作（例如尋找和取代文字）期間是否應忽略插入修訂內的文字。啟用此功能後，操作期間不會考慮插入修訂內的文字。

#### Q：如何使用 Aspose.Words for .NET 建立新文件？

答：要使用 Aspose.Words for .NET 建立新文檔，您可以實例化一個`Document`目的。以下是建立新文件的 C# 程式碼範例：

```csharp
Document doc = new Document();
```

#### Q：如何在 Aspose.Words for .NET 中插入帶有修訂追蹤的文字？

答：一旦您有了文檔，您就可以使用`DocumentBuilder`目的。例如，要插入具有修訂追蹤的「已插入」文本，您可以使用`StartTrackRevisions`, `Writeln`， 和`StopTrackRevisions`方法：

```csharp
DocumentBuilder builder = new DocumentBuilder(doc);
doc.StartTrackRevisions("author", DateTime.Now);
builder.Writeln("Inserted");
doc.StopTrackRevisions();
```

#### Q：如何在 Aspose.Words for .NET 中插入未修改的文字？

答：除了帶有修訂追蹤的文字之外，您還可以使用`DocumentBuilder`目的。例如，要插入文字“Text”而不進行修改，您可以使用`Write`方法：

```csharp
builder.Write("Text");
```

#### Q：如何忽略 Aspose.Words for .NET 中插入修訂中的文字？

答：要在後續操作中忽略插入修訂內的文本，您可以使用`FindReplaceOptions`對象並設定`IgnoreInserted`財產給`true`：

```csharp
FindReplaceOptions options = new FindReplaceOptions { IgnoreInserted = true };
```

#### Q：如何在 Aspose.Words for .NET 中使用正規表示式執行搜尋和取代？

答：要使用正規表示式對文件文字執行搜尋和取代操作，可以使用.NET`Regex`班級。例如，要搜尋所有出現的字母“e”並將其替換為星號“* “，您可以創建一個`Regex`對象並將其與`Replace`方法：

```csharp
Regex regex = new Regex("e");
doc.Range.Replace(regex, "*", options);
```

#### Q：如何在 Aspose.Words for .NET 中檢視文件的修改輸出？

 A：套用搜尋和取代操作後，您可以使用以下命令查看文件的變更內容：`GetText`方法：

```csharp
Console.WriteLine(doc.GetText());
```

#### Q：如何在 Aspose.Words for .NET 的輸出結果中包含插入修訂？

答：要在輸出結果中包含插入修訂內的文本，您可以變更選項以不忽略插入修訂。為此，您可以設定`IgnoreInserted`的財產`FindReplaceOptions`反對`false`：

```csharp
options.IgnoreInserted = false;
```

#### Q：如何在 Aspose.Words for .NET 中顯示帶有插入修訂的修改文件？

答：更改選項以包含插入修訂後，您可以再次執行搜尋並替換以獲得包含插入修訂內文字的結果：

```csharp
doc.Range.Replace(regex, "*", options);
Console.WriteLine(doc.GetText());
```