---
title: 移動到 Word 文件中的合併字段
linktitle: 移動到 Word 文件中的合併字段
second_title: Aspose.Words 文件處理 API
description: 了解如何使用逐步指南實作 Aspose.Words for .NET 的「移動到 Word 文件中的合併欄位」功能。
type: docs
weight: 10
url: /zh-hant/net/add-content-using-documentbuilder/move-to-merge-field/
---
在此範例中，我們將探索 Aspose.Words for .NET 的「移動到 Word 文件中的合併欄位」功能。 Aspose.Words 是一個功能強大的文件操作庫，使開發人員能夠以程式設計方式建立、修改和轉換 Word 文件。移動到合併欄位功能允許我們導航到文件中的合併欄位並對它們執行各種操作。


## 一步步解釋原始碼

讓我們逐步瀏覽原始程式碼，了解如何使用 Aspose.Words for .NET 使用「移動到合併欄位」功能。

## 步驟 1：初始化文檔和文檔產生器

首先，初始化 Document 和 DocumentBuilder 物件：

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
```

## 步驟 2 插入合併欄位並在其後添加文本

使用 DocumentBuilder 類別的 InsertField 方法插入合併字段，然後在其後面添加文字：

```csharp
Field field = builder.InsertField("MERGEFIELD field");
builder.Write(" Text after the field.");
```

## 步驟 3：建構器的遊標目前位於文件末端。

```csharp
Assert.Null(builder.CurrentNode);
```
## 步驟 4：將文件產生器遊標移至合併字段

若要將文件產生器遊標移至合併字段，請使用 DocumentBuilder 類別的 MoveToField 方法：

```csharp
builder.MoveToField(field, true);
```

## 立即在合併欄位後新增文本

一旦文件產生器遊標位於合併欄位內，您可以使用 Write 方法立即在其後面新增文字：

```csharp
Assert.AreEqual(field.End, builder.CurrentNode.PreviousSibling);
builder.Write(" Text immediately after the field.");
```

### 使用 Aspose.Words for .NET 移至合併欄位的範例原始碼

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

//使用 DocumentBuilder 插入一個欄位並在其後添加一串文字。
Field field = builder.InsertField("MERGEFIELD field");
builder.Write(" Text after the field.");

//建構器的遊標目前位於文件末尾。
Assert.Null(builder.CurrentNode);
//我們可以將建構器移動到這樣的字段，將遊標放在緊鄰該字段之後。
builder.MoveToField(field, true);

//請注意，遊標位於欄位的 FieldEnd 節點之後的位置，這意味著我們實際上並不在欄位內部。
//如果我們希望將 DocumentBuilder 移動到欄位內，
//我們需要使用 DocumentBuilder.MoveTo() 方法將其移至欄位的 FieldStart 或 FieldSeparator 節點。
Assert.AreEqual(field.End, builder.CurrentNode.PreviousSibling);
builder.Write(" Text immediately after the field.");
```

## 結論

我們已經探索了 Aspose.Words for .NET 的「移動到合併欄位」功能。我們學習如何使用 DocumentBuilder 類別導覽到合併文件中的欄位並對它們執行操作。當以程式設計方式進行合併的文字處理時，此功能非常有用

### Word 文件中移動合併欄位的常見問題解答

#### Q：Aspose.Words for .NET 中的「移動到合併欄位」功能的用途是什麼？

答：Aspose.Words for .NET 中的「移動到合併字段」功能允許開發人員導航到 Word 文件中的合併字段，並以程式設計方式對其執行各種操作。合併欄位是 Word 文件中用於郵件合併操作的特殊佔位符。

#### Q：如何使用 Aspose.Words for .NET 在 Word 文件中插入合併欄位？

答：您可以使用 DocumentBuilder 類別的 InsertField 方法將合併欄位插入文件中。插入合併欄位後，您可以使用 Write 方法在欄位之前或之後新增內容，例如文字。

#### Q：如何將文件產生器遊標移至特定合併欄位？

答：要將文件產生器遊標移至特定合併字段，請使用 DocumentBuilder 類別的 MoveToField 方法並將該欄位作為參數傳遞。這會將遊標放置在合併欄位之後。

#### Q：我可以使用「移至合併欄位」功能在合併欄位內新增文字嗎？

答：不，「移動到合併欄位」功能會將文件建構器遊標置於合併欄位之後。若要在合併欄位內新增文本，可以使用 DocumentBuilder.MoveTo 方法將遊標移至合併欄位的 FieldStart 或 FieldSeparator 節點。

#### Q：如何使用 Aspose.Words for .NET 執行郵件合併作業？

答：Aspose.Words for .NET 為郵件合併作業提供廣泛的支援。您可以使用 MailMerge 類別使用來自各種來源（例如陣列、資料集或自訂資料來源）的資料來執行郵件合併。