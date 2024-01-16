---
title: 在 Word 文件中附加添加書籤的文本
linktitle: 在 Word 文件中附加添加書籤的文本
second_title: Aspose.Words 文件處理 API
description: 了解如何使用 Aspose.Words for .NET 從 Word 文件中的書籤新增文字。
type: docs
weight: 10
url: /zh-hant/net/programming-with-bookmarks/append-bookmarked-text/
---

在本文中，我們將探索上述 C# 原始程式碼，以了解如何在 Aspose.Words for .NET 程式庫中使用追加書籤文字功能。此功能可讓您將 Word 文件的特定書籤中包含的文字新增至另一個文件。

## 先決條件

- C# 語言的基礎知識。
- 安裝了 Aspose.Words 函式庫的 .NET 開發環境。

## 步驟1：從書籤中獲取段落

在開始加入書籤文字之前，我們需要取得包含書籤開頭和結尾的段落。這可以透過訪問來完成`BookmarkStart`和`BookmarkEnd`書籤的屬性：

```csharp
Paragraph startPara = (Paragraph) srcBookmark.BookmarkStart.ParentNode;
Paragraph endPara = (Paragraph) srcBookmark.BookmarkEnd.ParentNode;
```

## 第 2 步：檢查父段落

我們檢查開頭和結尾段落是否有有效的父段落，即它們是否確實屬於一個段落。如果沒有，我們會產生一個異常：

```csharp
if (startPara == null || endPara == null)
throw new InvalidOperationException(
"The parent of the beginning or the end of the bookmark is not a paragrap

hey, this situation can't be handled yet.");
```

## 第 3 步：檢查段落的父級

我們檢查開始和結束段落是否具有相同的父級。如果不是，則表示這些段落不包含在同一部分或文件中，並且我們將引發異常：

```csharp
if (startPara.ParentNode != endPara.ParentNode)
throw new InvalidOperationException(
"Beginning and ending paragraphs have different parents, this situation cannot be handled yet.");
```

## 第四步：複製段落

我們迭代從開始段落到結束段落的節點（段落）。對於每個節點，我們建立一個副本並將其匯入到目標文件的上下文中：

```csharp
Node endNode = endPara.NextSibling;

for (Node curNode = startPara; curNode != endNode; curNode = curNode.NextSibling)
{
Node newNode = importer.ImportNode(curNode, true);

dstNode.AppendChild(newNode);
}
```

### 使用 Aspose.Words for .NET 附加書籤文字的範例原始碼

以下是示範使用 Aspose.Words for .NET 從書籤新增文字的完整範例原始碼：

```csharp

	//這是包含書籤開頭的段落。
	Paragraph startPara = (Paragraph) srcBookmark.BookmarkStart.ParentNode;

	//這是包含書籤結尾的段落。
	Paragraph endPara = (Paragraph) srcBookmark.BookmarkEnd.ParentNode;

	if (startPara == null || endPara == null)
		throw new InvalidOperationException(
			"Parent of the bookmark start or end is not a paragraph, cannot handle this scenario yet.");

	//將我們限制在一個相當簡單的場景。
	if (startPara.ParentNode != endPara.ParentNode)
		throw new InvalidOperationException(
			"Start and end paragraphs have different parents, cannot handle this scenario yet.");

	//我們想要複製從開始段落到（並包括）結束段落的所有段落，
	//因此，我們停止的節點是結束段落之後的節點。
	Node endNode = endPara.NextSibling;

	for (Node curNode = startPara; curNode != endNode; curNode = curNode.NextSibling)
	{
		//這將創建當前節點的副本並將其導入到上下文中（使其有效）
		//目標文檔的。導入意味著調整樣式並正確列出標識符。
		Node newNode = importer.ImportNode(curNode, true);

		dstNode.AppendChild(newNode);
	}

```

## 結論

在本文中，我們探索了 C# 原始程式碼，以了解如何使用 Aspose.Words for .NET 的追加書籤文字功能。我們按照逐步指南從書籤中獲取段落、驗證父項以及將段落複製到另一個文件。

### 在 Word 文件中附加書籤文字的常見問題解答

#### Q1：使用 Aspose.Words for .NET 中的「新增帶有書籤的文字」功能有哪些先決條件？

答：要使用Aspose.Words for .NET中的「新增附有書籤的文字」功能，您需要具備C#語言的基礎知識。您還需要一個安裝了 Aspose.Words 函式庫的 .NET 開發環境。

#### Q2：如何取得Word文件中包含書籤開頭和結尾的段落？

答：要取得Word文件中包含書籤開頭和結尾的段落，您可以訪問`BookmarkStart`和`BookmarkEnd`書籤的屬性。這是範例程式碼：

```csharp
Paragraph startPara = (Paragraph) srcBookmark.BookmarkStart.ParentNode;
Paragraph endPara = (Paragraph) srcBookmark.BookmarkEnd.ParentNode;
```

#### Q3：如果開始段落和結束段落沒有有效的父親段落會怎樣？

答：如果開始和結束段落沒有有效的父段落，即它們不是真正的段落，則會拋出異常。這種情況目前無法處理。
