---
title: 忽略字段內的文本
linktitle: 忽略字段內的文本
second_title: Aspose.Words 文件處理 API
description: 了解如何使用 Aspose.Words for .NET 的「忽略欄位內的文字」功能。
type: docs
weight: 10
url: /zh-hant/net/find-and-replace-text/ignore-text-inside-fields/
---
在本文中，我們將探索上面的 C# 原始程式碼，以了解如何使用 Aspose.Words for .NET 程式庫中的 Ignore Text Inside Fields 功能。當我們在操作文件時想要忽略欄位內的文字時，此功能非常有用。

## 先決條件

- C# 語言的基礎知識。
- 安裝了 Aspose.Words 函式庫的 .NET 開發環境。

## 第 1 步：建立新文檔

在開始操作欄位內的文字之前，我們需要使用 Aspose.Words for .NET 建立一個新文件。這可以透過實例化一個來完成`Document`目的：

```csharp
Document doc = new Document();
```

## 第 2 步：插入一個包含文字的字段

一旦我們有了一個文檔，我們就可以使用 a 在其中插入一個包含文字的字段`DocumentBuilder`目的。例如，要插入帶有文字“字段中的文字”的“INCLUDETEXT”字段，我們可以使用`InsertField`方法：

```csharp
DocumentBuilder builder = new DocumentBuilder(doc);
builder.InsertField("INCLUDETEXT", "Text in field");
```

## 步驟 3：使用「忽略欄位內的文字」功能

要在後續操作中忽略字段內的文本，我們可以使用`FindReplaceOptions`對象並設定`IgnoreFields`財產給`true`：

```csharp
FindReplaceOptions options = new FindReplaceOptions { IgnoreFields = true };
```

## 步驟 4：使用正規表示式進行搜尋和替換

為了對文件文字執行搜尋和取代操作，我們將使用正規表示式。在我們的範例中，我們將搜尋所有出現的字母“e”並將其替換為星號“*「。我們將使用 .NET`Regex`為此類：

```csharp
Regex regex = new Regex("e");
doc.Range.Replace(regex, "*", options);
```

## 步驟5：查看修改後的文檔輸出

套用搜尋和取代後，我們可以使用以下命令顯示文件的變更內容`GetText`方法：

```csharp
Console.WriteLine(doc.GetText());
```

## 第 6 步：更改選項以包含字段

我們在輸出結果中包含欄位內的文本，我們可以更改選項以不忽略欄位。為此我們將設置`IgnoreFields`財產給`false`：

```csharp
options.IgnoreFields = false;
```

## 步驟 7：顯示修改後的文件及其字段

更改選項後，我們可以再次執行搜尋並替換以獲得包含欄位中文字的結果：

```csharp
doc.Range.Replace(regex, "*", options);
Console.WriteLine(doc.GetText());
```

### 使用 Aspose.Words for .NET 忽略欄位內文字的範例原始碼

以下是完整的範例原始程式碼，示範如何使用 Aspose.Words for .NET 忽略欄位內的文字功能：

```csharp
    
	Document doc = new Document();
	DocumentBuilder builder = new DocumentBuilder(doc);

	//插入帶有文字的欄位。
	builder.InsertField("INCLUDETEXT", "Text in field");
	
	FindReplaceOptions options = new FindReplaceOptions { IgnoreFields = true };
	
	Regex regex = new Regex("e");
	doc.Range.Replace(regex, "*", options);
	
	Console.WriteLine(doc.GetText());

	options.IgnoreFields = false;
	doc.Range.Replace(regex, "*", options);
	
	Console.WriteLine(doc.GetText());
  
```

## 結論

在本文中，我們探索了 C# 原始程式碼，以了解如何在 Aspose.Words for .NET 中使用「忽略欄位內的文字」功能。我們按照逐步指南建立一個文檔，插入一個內部有文字的字段，使用「忽略字段內的文字」功能，使用正規表示式執行搜尋和取代操作，並顯示修改後的文檔。

### 常見問題解答

#### Q：Aspose.Words for .NET 中的「忽略欄位內的文字」功能是什麼？

答：Aspose.Words for .NET 中的「忽略欄位內的文字」功能可讓您指定在某些操作（例如尋找和取代文字）期間是否應忽略欄位內的文字。啟用此功能後，操作期間不會考慮欄位內的文字。

#### Q：如何使用 Aspose.Words for .NET 建立新文件？

答：要使用 Aspose.Words for .NET 建立新文檔，您可以實例化一個`Document`目的。以下是建立新文件的 C# 程式碼範例：

```csharp
Document doc = new Document();
```

#### Q：如何使用 Aspose.Words for .NET 在文件中插入帶有文字的欄位？

答：一旦有了文檔，您就可以使用`DocumentBuilder`目的。例如，要插入包含文字“字段中的文字”的“INCLUDETEXT”字段，您可以使用`InsertField`方法：

```csharp
DocumentBuilder builder = new DocumentBuilder(doc);
builder.InsertField("INCLUDETEXT", "Text in field");
```

#### Q：如何忽略 Aspose.Words for .NET 中欄位內的文字？

答：要在後續操作中忽略欄位內的文本，您可以使用`FindReplaceOptions`對象並設定`IgnoreFields`財產給`true`：

```csharp
FindReplaceOptions options = new FindReplaceOptions { IgnoreFields = true };
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

#### Q：如何在 Aspose.Words for .NET 的輸出結果中包含欄位？

答：要在輸出結果中包含欄位內的文本，您可以變更選項以不忽略欄位。為此，您可以設定`IgnoreFields`的財產`FindReplaceOptions`反對`false`：

```csharp
options.IgnoreFields = false;
```

#### Q：如何在 Aspose.Words for .NET 中顯示修改後的文件及其欄位？

答：將選項變更為包含欄位後，您可以再次執行搜尋並替換以獲得包含欄位內文字的結果：

```csharp
doc.Range.Replace(regex, "*", options);
Console.WriteLine(doc.GetText());
```