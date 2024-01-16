---
title: 在 Word 文件中顯示隱藏書籤內容
linktitle: 在 Word 文件中顯示隱藏書籤內容
second_title: Aspose.Words 文件處理 API
description: 了解如何使用 Aspose.Words for .NET 在 Word 文件中顯示或隱藏書籤內容。
type: docs
weight: 10
url: /zh-hant/net/programming-with-bookmarks/show-hide-bookmarked-content/
---

在本文中，我們將探索上述 C# 原始程式碼，以了解如何在 Aspose.Words for .NET 程式庫中使用「顯示隱藏書籤內容」功能。此功能可讓您在合併資料時根據特定條件顯示或隱藏 Word 文件中書籤的內容。

## 先決條件

- C# 語言的基礎知識。
- 安裝了 Aspose.Words 函式庫的 .NET 開發環境。

## 第一步：取得書籤

我們使用`Bookmarks`文件範圍的屬性來取得我們要顯示或隱藏內容的特定書籤：

```csharp
Bookmark bm = doc.Range.Bookmarks[bookmarkName];
```

## 步驟 2：插入合併字段

我們使用文件產生器`DocumentBuilder`插入必要的合併欄位。這些合併欄位將設定一個條件來顯示或隱藏書籤內容，具體取決於`showHide`多變的：

```csharp
DocumentBuilder builder = new DocumentBuilder(doc);
builder. MoveToDocumentEnd();

Field field = builder. InsertField("IF \"", null);
builder. MoveTo(field. Start. NextSibling);
builder. InsertField("MERGEFIELD " + bookmarkName + "", null);
builder. Write("\" = \"true\" ");
builder. Write("\"");
builder. Write("\"");
builder. Write(" \"\"");
```

## 步驟 3：行動書籤內容

我們循環瀏覽書籤的內容並移動它以使其出現

isse 在書籤之前。這將根據指定條件控制顯示或隱藏內容：

```csharp
Node currentNode = field. Start;
bool flag = true;
while (currentNode != null && flag)
{
     if (currentNode.NodeType == NodeType.Run)
         if (currentNode.ToString(SaveFormat.Text).Trim() == "\"")
             flag = false;

     Node nextNode = currentNode.NextSibling;

     bm.BookmarkStart.ParentNode.InsertBefore(currentNode, bm.BookmarkStart);
     currentNode = nextNode;
}
```

## 步驟 4：行動書籤的其餘內容

我們將書籤的其餘內容移到書籤之後，使用書籤的結束節點作為插入點：

```csharp
Node endNode = bm.BookmarkEnd;
flag = true;
while (currentNode != null && flag)
{
     if (currentNode.NodeType == NodeType.FieldEnd)
         flag = false;

     Node nextNode = currentNode.NextSibling;

     bm.BookmarkEnd.ParentNode.InsertAfter(currentNode, endNode);
     endNode = currentNode;
     currentNode = nextNode;
}
```

## 第 5 步：執行合併

我們使用`Execute`文檔方法`s `郵件合併` object to execute the merge using the bookmark name and the value of the `顯示隱藏`變數：

```csharp
doc. MailMerge. Execute(new[] { bookmarkName }, new object[] { showHide });
```

### 使用 Aspose.Words for .NET 顯示隱藏書籤內容的範例原始碼

以下是原始程式碼的完整範例，示範使用 Aspose.Words for .NET 顯示或隱藏書籤內容：

```csharp

	Bookmark bm = doc.Range.Bookmarks[bookmarkName];

	DocumentBuilder builder = new DocumentBuilder(doc);
	builder.MoveToDocumentEnd();

	// {IF "{MERGEFIELD 書籤}" = "true" "" ""}
	Field field = builder.InsertField("IF \"", null);
	builder.MoveTo(field.Start.NextSibling);
	builder.InsertField("MERGEFIELD " + bookmarkName + "", null);
	builder.Write("\" = \"true\" ");
	builder.Write("\"");
	builder.Write("\"");
	builder.Write(" \"\"");

	Node currentNode = field.Start;
	bool flag = true;
	while (currentNode != null && flag)
	{
		if (currentNode.NodeType == NodeType.Run)
			if (currentNode.ToString(SaveFormat.Text).Trim() == "\"")
				flag = false;

		Node nextNode = currentNode.NextSibling;

		bm.BookmarkStart.ParentNode.InsertBefore(currentNode, bm.BookmarkStart);
		currentNode = nextNode;
	}

	Node endNode = bm.BookmarkEnd;
	flag = true;
	while (currentNode != null && flag)
	{
		if (currentNode.NodeType == NodeType.FieldEnd)
			flag = false;

		Node nextNode = currentNode.NextSibling;

		bm.BookmarkEnd.ParentNode.InsertAfter(currentNode, endNode);
		endNode = currentNode;
		currentNode = nextNode;
	}

	doc.MailMerge.Execute(new[] { bookmarkName }, new object[] { showHide });

```

## 結論

在本文中，我們探索了 C# 原始程式碼，以了解如何使用 Aspose.Words for .NET 的顯示隱藏書籤內容功能。我們按照逐步指南在合併資料時根據特定條件顯示或隱藏書籤的內容。

### 有關在 Word 文件中顯示隱藏書籤內容的常見問題解答

#### Q：我可以對同一文件中的多個書籤使用相同的條件嗎？

答：是的，您可以對同一文件中的多個書籤使用相同的條件。只需對每個書籤重複步驟 2-5，調整書籤名以及可選的值`showhide`根據需要可變。

#### Q：如何新增更多條件來顯示或隱藏書籤內容？

 A：若要新增更多條件，您可以使用邏輯運算符，例如`AND`和`OR`在步驟 2 插入合併欄位的程式碼中。編輯以下程式碼中的條件以新增其他條件：

```csharp
builder. Write("\" = \"true\" ");
```

#### Q：如何使用 Aspose.Words for .NET 刪除 Word 文件中的書籤？

答：要使用 Aspose.Words for .NET 刪除 Word 文件中的書籤，您可以使用`Remove`方法從`Bookmarks`文檔範圍的集合。以下是刪除特定書籤的範例程式碼：

```csharp
doc.Range.Bookmarks.Remove(bookmarkName);
```

#### Q：Aspose.Words 庫是免費的嗎？

答：Aspose.Words 庫是一個商業庫，需要有效的許可證才能在您的專案中使用。你可以檢查[Aspose.Words for .NET API 參考](https://reference.aspose.com/words/net/)了解有關許可選項和定價的更多資訊。

#### Q：是否還有其他函式庫可用於在 .NET 中對 Word 文件進行文字處理？

答：是的，還有其他函式庫可用於在 .NET 中對 Word 文件進行文字處理，例如 Open XML SDK 和 GemBox.Document。您可以根據您的特定需求和偏好來探索這些程式庫作為 Aspose.Words 的替代品。