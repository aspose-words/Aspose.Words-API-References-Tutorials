---
title: 在 Word 文件中顯示隱藏書籤
linktitle: 在 Word 文件中顯示隱藏書籤
second_title: Aspose.Words 文件處理 API
description: 了解如何使用 Aspose.Words for .NET 在 Word 文件中顯示或隱藏特定書籤。
type: docs
weight: 10
url: /zh-hant/net/programming-with-bookmarks/show-hide-bookmarks/
---

在本文中，我們將探索上面的 C# 原始程式碼，以了解如何使用 Aspose.Words for .NET 程式庫中的顯示隱藏書籤功能。此功能可讓您顯示或隱藏 Word 文件中的特定書籤。

## 先決條件

- C# 語言的基礎知識。
- 安裝了 Aspose.Words 函式庫的 .NET 開發環境。

## 第 1 步：載入文檔

我們使用`Document`類別從文件載入現有文件：

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document doc = new Document(dataDir + "Bookmarks.docx");
```

## 步驟 2：顯示或隱藏特定書籤

我們使用`ShowHideBookmarkedContent`函數顯示或隱藏文件中的特定書籤。此函數將文件、書籤名稱和一個布林值作為參數來指示是否顯示或隱藏書籤：

```csharp
ShowHideBookmarkedContent(doc, "MyBookmark1", false);
```

## 第三步：儲存修改後的文檔

我們使用`Save`將修改後的文件儲存到文件的方法：

```csharp
doc.Save(dataDir + "WorkingWithBookmarks.ShowHideBookmarks.docx");
```

### 使用 Aspose.Words for .NET 顯示隱藏書籤的範例原始碼

以下是完整的範例原始程式碼，示範使用 Aspose.Words for .NET 顯示或隱藏特定書籤：

```csharp

	//文檔目錄的路徑。
	string dataDir = "YOUR DOCUMENT DIRECTORY";
	Document doc = new Document(dataDir + "Bookmarks.docx");

	ShowHideBookmarkedContent(doc, "MyBookmark1", false);
	
	doc.Save(dataDir + "WorkingWithBookmarks.ShowHideBookmarks.docx");

```

#### 顯示隱藏書籤內容原始碼

```csharp

public void ShowHideBookmarkedContent(Document doc, string bookmarkName, bool showHide)
        {
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
        }
		
```
## 結論

在本文中，我們探索了 C# 原始程式碼，以了解如何使用 Aspose.Words for .NET 的顯示隱藏書籤功能。我們按照逐步指南來顯示或隱藏文件中的特定書籤。

### 在 Word 文件中顯示隱藏書籤的常見問題解答

#### Q：我可以在同一文件中顯示或隱藏多個書籤嗎？

答：是的，您可以透過對要處理的每個書籤重複步驟 2 和 3，在同一文件中顯示或隱藏多個書籤。

#### Q：提供的程式碼是否適用於其他 Word 文件格式，例如 .doc 或 .docm？

答：是的，所提供的程式碼適用於 Aspose.Words 支援的各種 Word 文件格式，例如 .doc 和 .docm。載入和儲存文件時請確保使用正確的文件名稱和路徑。

#### Q：如何再次顯示隱藏的書籤？

 A：要再次顯示隱藏的書籤，您需要使用相同的`ShowHideBookmarkedContent`函數傳遞值`true`布林參數，指示是否顯示或隱藏書籤。

#### Q：我可以使用條件根據文件中的合併欄位值顯示或隱藏書籤嗎？

答：是的，您可以使用條件和合併欄位值來確定是否應顯示或隱藏書籤。您可以自訂以下程式碼`ShowHideBookmarkedContent`函數考慮適當的條件和值。

#### Q：如何使用 Aspose.Words for .NET 刪除 Word 文件中的書籤？

答：要使用 Aspose.Words for .NET 刪除 Word 文件中的書籤，您可以使用`RemoveBookmarks`的方法`Document`班級。這是範例程式碼：

```csharp
doc.RemoveBookmarks("BookmarkName");
```