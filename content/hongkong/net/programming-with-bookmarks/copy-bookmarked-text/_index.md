---
title: 在 Word 文件中複製添加書籤的文本
linktitle: 在 Word 文件中複製添加書籤的文本
second_title: Aspose.Words 文件處理 API
description: 了解如何使用 Aspose.Words for .NET 將 Word 文件中的書籤文字複製到另一個文件。
type: docs
weight: 10
url: /zh-hant/net/programming-with-bookmarks/copy-bookmarked-text/
---

在本文中，我們將探索上面的 C# 原始程式碼，以了解如何使用 Aspose.Words for .NET 程式庫中的複製書籤文字功能。此功能可讓您將特定書籤的內容從來源文件複製到另一個文件。

## 先決條件

- C# 語言的基礎知識。
- 安裝了 Aspose.Words 函式庫的 .NET 開發環境。

## 步驟1：載入來源文檔

在複製書籤文字之前，我們需要將來源文檔載入到`Document`使用檔案路徑的物件：

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document srcDoc = new Document(dataDir + "Bookmarks.docx");
```

## 第二步：取得來源書籤

我們使用`Bookmarks`來源文檔範圍的屬性來取得我們要複製的特定書籤：

```csharp
Bookmark srcBookmark = srcDoc.Range.Bookmarks["MyBookmark1"];
```

## 步驟 3：建立目標文檔

我們建立一個新文件作為複製書籤內容的目標文件：

```csharp
Document dstDoc = new Document();
```

## 步驟 4：指定複製位置

我們指定要新增複製文字的位置。在我們的範例中，我們將文字新增到目標文件最後一部分的正文末尾：

```csharp
CompositeNode dstNode = dstDoc.LastSection.Body;
```

## 第 5 步：匯入並複製書籤文本

我們使用一個`NodeImporter`物件將書籤文字從來源文件匯入並複製到目標文件：

```csharp
NodeImporter importer = new NodeImporter(srcDoc, dstDoc, ImportFormatMode.KeepSourceFormatting);

AppendBookmarkedText(import, srcBookmark, dstNode);

dstDoc.Save(dataDir + "WorkingWithBookmarks.CopyBookmarkedText.docx");
```

### 使用 Aspose.Words for .NET 複製書籤文字的範例原始碼

以下是示範使用 Aspose.Words for .NET 從書籤複製文字的完整範例原始碼：

```csharp

	//文檔目錄的路徑。
	string dataDir = "YOUR DOCUMENT DIRECTORY";
	Document srcDoc = new Document(dataDir + "Bookmarks.docx");

	//這是我們要複製其內容的書籤。
	Bookmark srcBookmark = srcDoc.Range.Bookmarks["MyBookmark1"];

	//我們將新增到此文件中。
	Document dstDoc = new Document();

	//假設我們將附加到最後一節正文的結尾。
	CompositeNode dstNode = dstDoc.LastSection.Body;

	//如果在沒有單一上下文的情況下多次匯入，將導致建立許多樣式。
	NodeImporter importer = new NodeImporter(srcDoc, dstDoc, ImportFormatMode.KeepSourceFormatting);

	AppendBookmarkedText(importer, srcBookmark, dstNode);
	
	dstDoc.Save(dataDir + "WorkingWithBookmarks.CopyBookmarkedText.docx");

```

#### AppendBookmarkedText 原始碼

```csharp

private void AppendBookmarkedText(NodeImporter importer, Bookmark srcBookmark, CompositeNode dstNode)
        {
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
        }

```
## 結論

在本文中，我們探索了 C# 原始程式碼，以了解如何使用從 Aspose.Words for .NET 複製書籤文字的功能。我們按照逐步指南將書籤的內容從來源文件複製到另一個文件。

### 在 Word 文件中複製書籤文字的常見問題解答

#### Q：使用 Aspose.Words for .NET 中的「複製帶有書籤的文字」功能有什麼要求？

答：要使用 Aspose.Words for .NET 中的「複製帶有書籤的文字」功能，您需要具備 C# 語言的基礎知識。您還需要一個安裝了 Aspose.Words 函式庫的 .NET 開發環境。

#### Q：如何將來源文件載入到 Aspose.Words for .NET 中？

答：要在 Aspose.Words for .NET 中載入來源文檔，您可以使用`Document`透過指定文件的文件路徑來定義類別。這是範例程式碼：

```csharp
Document srcDoc = new Document("path/to/your/document.docx");
```

#### Q：如何使用 Aspose.Words for .NET 取得來源文件中特定書籤的內容？

答：要使用 Aspose.Words for .NET 取得來源文件中特定書籤的內容，您可以存取`Bookmarks`來源文檔範圍的屬性並使用書籤名稱來檢索特定的書籤。這是範例程式碼：

```csharp
Bookmark srcBookmark = srcDoc.Range.Bookmarks["BookmarkName"];
```

#### Q：如何使用 Aspose.Words for .NET 指定目標文件中書籤文字副本的位置？

答：若要使用 Aspose.Words for .NET 指定在目標文件中新增複製的書籤文字的位置，您可以導覽至目標文件最後一部分的正文。您可以使用`LastSection`屬性來存取最後一部分和`Body`屬性來存取該部分的主體。這是範例程式碼：

```csharp
CompositeNode dstNode = dstDoc.LastSection.Body;
```

#### Q：如何使用 Aspose.Words for .NET 將書籤文字從來源文件匯入並複製到目標文件？

答：要使用 Aspose.Words for .NET 將書籤文字從來源文檔匯入並複製到目標文檔，您可以使用`NodeImporter`指定來源文件、目標文件和要保留的格式模式的類別。然後您可以使用`AppendBookmarkedText`方法在目標文件中加入書籤文字。這是範例程式碼：

```csharp
NodeImporter importer = new NodeImporter(srcDoc, dstDoc, ImportFormatMode.KeepSourceFormatting);
AppendBookmarkedText(import, srcBookmark, dstNode);
```

#### Q：使用 Aspose.Words for .NET 複製書籤文字後如何儲存目標文件？

答：要使用 Aspose.Words for .NET 從書籤複製文字後儲存目標文檔，您可以使用`Save`的方法`Document`指定目標檔案路徑的物件。這是範例程式碼：

```csharp
dstDoc.Save("path/to/your/destination-document.docx");
```