---
title: 在 Word 文件中顯示隱藏書籤內容
linktitle: 在 Word 文件中顯示隱藏書籤內容
second_title: Aspose.Words 文件處理 API
description: 透過這份全面的逐步指南，了解如何使用 Aspose.Words for .NET 動態顯示或隱藏 Word 文件中的書籤內容。
type: docs
weight: 10
url: /zh-hant/net/programming-with-bookmarks/show-hide-bookmarked-content/
---

## 介紹

嘿！您是否曾經想根據特定條件控制Word文件中特定內容的可見性？使用 Aspose.Words for .NET，您只需幾行程式碼即可動態顯示或隱藏書籤內容。在本教程中，我將逐步引導您完成該過程，確保您理解程式碼的每個部分。到最後，您將成為在 Word 文件中操作書籤的專家。讓我們開始吧！

## 先決條件

在我們深入學習本教程之前，讓我們確保您擁有所需的一切：

1. C# 基礎知識：您應該熟悉 C# 文法和概念。
2.  Aspose.Words for .NET：下載[這裡](https://releases.aspose.com/words/net/) 。如果您還沒有準備好購買，您可以從[免費試用](https://releases.aspose.com/).
3. Visual Studio：任何最新版本都可以使用，但建議使用最新版本。
4. .NET Framework：確保您的電腦上已安裝它。

準備好開始了嗎？偉大的！讓我們先導入必要的命名空間。

## 導入命名空間

要使用 Aspose.Words for .NET，我們需要匯入所需的命名空間。此步驟確保我們能夠存取我們將使用的所有類別和方法。

```csharp
using System;
using Aspose.Words;
using Aspose.Words.Fields;
```

這些命名空間對於處理 Word 文件和操作其內容至關重要。

## 第 1 步：設定文檔

首先，讓我們建立一個新的 Word 文件和文件產生器。文件產生器可幫助我們輕鬆新增和操作文件中的內容。

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
```

在此步驟中，我們初始化一個新文件和一個文檔產生器。這為我們進一步的操作奠定了環境。

## 第 2 步：新增書籤內容

接下來，我們將向文件添加一些內容並圍繞其建立書籤。這份書籤將幫助我們識別和操作內容。

```csharp
builder.Write("This is some text before the bookmark.");
builder.StartBookmark("MyBookmark");
builder.Write("This is the bookmarked content.");
builder.EndBookmark("MyBookmark");
builder.Write("This is some text after the bookmark.");
```

在這裡，我們在書籤內容之前和之後添加一些文字。這`StartBookmark`和`EndBookmark`方法定義書籤的邊界。

## 步驟 3：插入條件字段

為了控制添加書籤的內容的可見性，我們將使用條件欄位。此欄位將檢查條件並相應地顯示或隱藏內容。

```csharp
builder.MoveToDocumentEnd();
Field field = builder.InsertField("IF \"", null);
builder.MoveTo(field.Start.NextSibling);
builder.InsertField("MERGEFIELD MyBookmark", null);
builder.Write("\" = \"true\" \"Visible\" \"Hidden\"");
```

在此步驟中，我們插入一個 IF 欄位來檢查書籤的值。如果值為“true”，則顯示“Visible”；否則會顯示“隱藏”。

## 步驟 4：重新排列節點

接下來，我們需要重新排列節點，以確保條件邏輯正確應用於新增書籤的內容。

```csharp
Bookmark bm = doc.Range.Bookmarks["MyBookmark"];
Node currentNode = field.Start;
bool flag = true;

while (currentNode != null && flag)
{
    if (currentNode.NodeType == NodeType.Run && currentNode.ToString(SaveFormat.Text).Trim() == "\"")
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
```

在這裡，我們移動節點以確保條件正確包含書籤內容。

## 第 5 步：執行郵件合併

最後，我們將執行郵件合併來設定書籤的值並確定是否應顯示或隱藏內容。

```csharp
doc.MailMerge.Execute(new[] { "MyBookmark" }, new object[] { "true" });
```

此步驟將書籤值設為“true”，這將使內容根據我們的條件可見。

## 第 6 步：儲存文檔

完成所有操作後，最後一步是儲存修改後的文件。

```csharp
doc.Save("ShowHideBookmarkedContent.docx");
```

在這裡，我們使用描述性檔案名稱儲存文件以指示變更。

## 結論

就是這樣！您已成功學習如何使用 Aspose.Words for .NET 在 Word 文件中顯示或隱藏新增書籤的內容。本教學介紹了建立文件、新增書籤、插入條件欄位、重新排列節點以及執行郵件合併。 Aspose.Words 提供了大量的功能，因此請毫不猶豫地探索[API文件](https://reference.aspose.com/words/net/)以獲得更高級的功能。

## 常見問題解答

### 1. 什麼是 Aspose.Words for .NET？

Aspose.Words for .NET 是一個功能強大的程式庫，可讓開發人員以程式設計方式建立、修改和轉換 Word 文件。它廣泛用於文件自動化任務。

### 2. 我可以免費使用Aspose.Words for .NET嗎？

您可以嘗試使用 Aspose.Words for .NET[免費試用](https://releases.aspose.com/)。如需長期使用，您需要購買授權。

### 3. 如何修改書籤的其他屬性？

 Aspose.Words 可讓您操作書籤的各種屬性，例如其文字和位置。請參閱[API文件](https://reference.aspose.com/words/net/)取得詳細說明。

### 4. 如何獲得 Aspose.Words for .NET 支援？

您可以透過訪問獲得支持[Aspose 支援論壇](https://forum.aspose.com/c/words/8).

### 5. 我可以使用 Aspose.Words for .NET 操作其他類型的內容嗎？

是的，Aspose.Words for .NET 支援各種類型的內容操作，包括文字、圖像、表格等。