---
title: 解開Word文檔中的行書籤
linktitle: 解開Word文檔中的行書籤
second_title: Aspose.Words 文件處理 API
description: 了解如何解開 Word 文件中的巢狀行書籤以刪除特定行而不影響其他書籤。
type: docs
weight: 10
url: /zh-hant/net/programming-with-bookmarks/untangle-row-bookmarks/
---

在本文中，我們將探索上面的 C# 原始程式碼，以了解如何使用 Aspose.Words for .NET 程式庫中的 Untangle Row Bookmarks 功能。此功能可以將行書籤的末尾與書籤的開頭放在同一行中。

## 先決條件

- C# 語言的基礎知識。
- 安裝了 Aspose.Words 函式庫的 .NET 開發環境。

## 第 1 步：載入文檔

我們使用`Document`類別從文件載入現有文件：

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document doc = new Document(dataDir + "Table column bookmarks.docx");
```

## 第 2 步：解開線書籤

我們使用`Untangle`函數從行中解開書籤。此函數執行將書籤行尾與書籤開頭放在同一行的自訂任務：

```csharp
Untangle(doc);
```

## 步驟 3：按書籤刪除行

我們使用`DeleteRowByBookmark`透過書籤刪除特定行的函數：

```csharp
DeleteRowByBookmark(doc, "ROW2");
```

## 步驟 4：檢查其他書籤的完整性

我們透過檢查書籤末尾是否仍然存在來驗證其他書籤沒有損壞：

```csharp
if (doc.Range.Bookmarks["ROW1"].BookmarkEnd == null)
throw new Exception("Wrong, the end of the bookmark was deleted.");

doc.Save(dataDir + "WorkingWithBookmarks.UntangleRowBookmarks.docx");
```

### 使用 Aspose.Words for .NET 解開行書籤的範例原始程式碼

以下是使用 Aspose.Words for .NET 從行中解開書籤的完整範例原始程式碼：


```csharp

	//文檔目錄的路徑。
	string dataDir = "YOUR DOCUMENT DIRECTORY";
	Document doc = new Document(dataDir + "Table column bookmarks.docx");

	//這將執行將行書籤結尾放入與書籤開頭相同的行中的自訂任務。
	Untangle(doc);

	//現在我們可以輕鬆地刪除書籤所在的行，而不會損壞任何其他行的書籤。
	DeleteRowByBookmark(doc, "ROW2");

	//這只是為了檢查另一個書籤是否有損壞。
	if (doc.Range.Bookmarks["ROW1"].BookmarkEnd == null)
		throw new Exception("Wrong, the end of the bookmark was deleted.");

	doc.Save(dataDir + "WorkingWithBookmarks.UntangleRowBookmarks.docx");

```

#### 解開原始碼
```csharp

private void Untangle(Document doc)
        {
            foreach (Bookmark bookmark in doc.Range.Bookmarks)
            {
                //取得書籤和書籤結束節點的父行。
                Row row1 = (Row) bookmark.BookmarkStart.GetAncestor(typeof(Row));
                Row row2 = (Row) bookmark.BookmarkEnd.GetAncestor(typeof(Row));

                //如果發現兩行都正常，且書籤開頭和結尾包含在相鄰行中，
                //將書籤結束節點移到頂行最後一個儲存格中最後一段的結尾。
                if (row1 != null && row2 != null && row1.NextSibling == row2)
                    row1.LastCell.LastParagraph.AppendChild(bookmark.BookmarkEnd);
            }
        }

```

#### 透過書籤刪除行原始碼
```csharp

 private void DeleteRowByBookmark(Document doc, string bookmarkName)
        {
            Bookmark bookmark = doc.Range.Bookmarks[bookmarkName];

            Row row = (Row) bookmark?.BookmarkStart.GetAncestor(typeof(Row));
            row?.Remove();
        }

```
## 結論

在本文中，我們探索了 C# 原始程式碼，以了解如何使用 Aspose.Words for .NET 的 Untangle Row Bookmarks 功能。我們按照逐步指南來解開行書籤並刪除特定行而不損壞其他書籤。

### 解開 Word 文件中的行書籤的常見問題解答

#### Q：Unscramble Row Bookmarks 是否僅適用於表中的行書籤？

答：是的，解開行書籤功能專門用於解開表中的行書籤。此函數可用於處理陣列中的行書籤，並確保書籤結尾與書籤開頭位於同一行。

#### Q：解讀行書籤功能是否會修改原始文件的內容？

答：是的，解讀行書籤功能透過移動行書籤的末尾以將它們放置在與書籤開頭相同的行中來修改原始文件。在套用此功能之前，請確保已儲存文件的備份副本。

#### Q：如何識別 Word 文件中的行書籤？

答：行書籤通常在表格中用於標記特定部分。您可以透過瀏覽文件中的書籤並檢查書籤是否位於表格行中來識別行書籤。

#### Q：是否可以解開非相鄰表中的行書籤？

答：本文介紹的解開行書籤功能旨在解開相鄰表中的行書籤。要解開不相鄰表格中的行書籤，可能需要根據文件的結構對程式碼進行額外的調整。

#### Q：解開行書籤後，我還可以對其執行哪些其他操作？

答：線書籤解開後，您可以根據需要執行不同的操作。這可能包括編輯、刪除內容或將內容新增至已新增書籤的行。請務必小心處理行書籤，以避免對文件的其餘部分產生任何不必要的影響。