---
title: 接受評論
linktitle: 接受評論
second_title: Aspose.Words 文件處理 API
description: 了解如何使用 Aspose.Words for .NET 接受 Word 文件的修訂
type: docs
weight: 10
url: /zh-hant/net/working-with-revisions/accept-revisions/
---

在本教學中，我們將引導您使用 Aspose.Words for .NET 的接受修訂功能接受 Word 文件的修訂。請按照以下步驟了解原始程式碼並接受對文件的變更。

## 步驟1：新增和編輯文檔內容

在此範例中，我們將建立一個文件並新增內容。我們用幾個段落來說明變化和修訂。就是這樣：

```csharp
//文檔目錄的路徑。
string dataDir = "YOUR DOCUMENTS DIRECTORY";
Document doc = new Document();
Body body = doc.FirstSection.Body;
Paragraph para = body.FirstParagraph;

//將文字新增到第一個段落，然後再新增兩個段落。
para.AppendChild(new Run(doc, "Paragraph 1. "));
body.AppendParagraph("Paragraph 2.");
body.AppendParagraph("Paragraph 3.");
```

## 第 2 步：追蹤評論並新增評論

我們啟用修訂追蹤並新增修訂文件。就是這樣：

```csharp
doc.StartTrackRevisions("John Doe", DateTime.Now);

//該段落是修訂版，並且將設定相應的“IsInsertRevision”標誌。
para = body.AppendParagraph("Paragraph 4.");
Assert.True(para.IsInsertRevision);
```

## 第 3 步：刪除段落並管理修訂

我們刪除一個段落並檢查已儲存的修訂。就是這樣：

```csharp
ParagraphCollection paragraphs = body.Paragraphs;
Assert.AreEqual(4, paragraphs.Count);
para = paragraphs[2];
para.Remove();

//由於我們正在追蹤修訂，該段落仍然存在於文件中，將設定「IsDeleteRevision」標誌
//並將在 Microsoft Word 中顯示為評論，直到我們接受或拒絕所有評論。
Assert.AreEqual(4, paragraphs.Count);
Assert.True(para.IsDeleteRevision);
```

## 第 4 步：接受更改

我們接受對文檔的所有更改。就是這樣：

```csharp
doc.AcceptAllRevisions();
Assert.AreEqual(3, paragraphs.Count);
Assert.That(para, Is.Empty);
```

## 第 5 步：停止追蹤評論

我們將停止追蹤修訂，以便對文件的變更不再顯示為修訂。就是這樣：

```csharp
doc.StopTrackRevisions();
```
## 第 6 步：儲存文檔

插入文字輸入表單欄位後，使用以下命令將文件儲存到所需位置`Save`方法。確保提供適當的文件路徑：

```csharp
doc.Save(dataDir + "WorkingWithRevisions.AcceptRevisions.docx");
```

### 使用 Aspose.Words for .NET 接受修訂的範例原始程式碼

以下是使用 Aspose.Words for .NET 接受文件變更的完整原始碼：


```csharp
//文檔目錄的路徑。
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document doc = new Document();
Body body = doc.FirstSection.Body;
Paragraph para = body.FirstParagraph;

//將文字新增到第一個段落，然後再新增兩個段落。
para.AppendChild(new Run(doc, "Paragraph 1. "));
body.AppendParagraph("Paragraph 2. ");
body.AppendParagraph("Paragraph 3. ");

//我們有三個段落，其中沒有一個被註冊為任何類型的修訂
//如果我們在追蹤修訂時新增/刪除文件中的任何內容，
//它們將在文件中顯示並可以接受/拒絕。
doc.StartTrackRevisions("John Doe", DateTime.Now);

//本段是修訂版，並將設定對應的「IsInsertRevision」標誌。
para = body.AppendParagraph("Paragraph 4. ");
Assert.True(para.IsInsertRevision);

//取得文件的段落集合並刪除段落。
ParagraphCollection paragraphs = body.Paragraphs;
Assert.AreEqual(4, paragraphs.Count);
para = paragraphs[2];
para.Remove();

//由於我們正在追蹤修訂，該段落仍然存在於文件中，將設定“IsDeleteRevision”
//並將在 Microsoft Word 中顯示為修訂版本，直到我們接受或拒絕所有修訂版本。
Assert.AreEqual(4, paragraphs.Count);
Assert.True(para.IsDeleteRevision);

//一旦我們接受更改，已刪除的修訂段落就會被刪除。
doc.AcceptAllRevisions();
Assert.AreEqual(3, paragraphs.Count);
Assert.That(para, Is.Empty);

//停止追蹤修訂會使該文字顯示為普通文字。
//文件變更時不計算修訂版本。
doc.StopTrackRevisions();

//儲存文檔。
doc.Save(dataDir + "WorkingWithRevisions.AcceptRevisions.docx");
```
## 結論

在本教學中，我們學習如何使用 Aspose.Words for .NET 的接受修訂功能接受 Word 文件中的修訂。我們已按照以下步驟新增和編輯文件內容、追蹤修訂、刪除修訂的段落、接受所有變更以及停止追蹤修訂。現在，您可以使用 Aspose.Words for .NET 應用這些知識來有效管理您自己的 Word 文件中的修訂。

### 常見問題解答

#### Q：如何在 Aspose.Words for .NET 中啟用修訂追蹤？

#### 解決方案一：

答：要在 Aspose.Words for .NET 中啟用修訂跟踪，請使用`StartTrackRevisions`的方法`Document`對象並指定作者姓名和修訂追蹤的開始日期。

```csharp
doc.StartTrackRevisions("John Doe", DateTime.Now);
```

#### 解決方案2：

答：您還可以使用以下命令啟用修訂跟踪`Document`接受的構造函數`trackRevisions`和`author`參數。

```csharp
Document doc = new Document("document.docx", new LoadOptions { TrackRevisions = true, Author = "John Doe" });
```

#### Q：如何使用 Aspose.Words for .NET 接受文件中的所有變更？

答：使用`AcceptAllRevisions`的方法`Document`反對接受對文件所做的所有更改。

```csharp
doc.AcceptAllRevisions();
```

#### Q：如何儲存已接受修訂的修改文件？

使用`Save`的方法`Document`物件保存已接受修訂的修改後的文件。請務必提供正確的檔案路徑。

```csharp
doc.Save("path/to/the/document.docx");
```

#### Q：如何停止追蹤 Aspose.Words for .NET 中的修訂？

答：使用`StopTrackRevisions`的方法`Document`反對停止追蹤修訂。

```csharp
doc.StopTrackRevisions();
```

#### Q：如何使用 Aspose.Words for .NET 刪除文件中修改的段落？

答：要刪除文件中修改的段落，您可以使用`Remove`段落收集方法。

```csharp
ParagraphCollection paragraphs = body.Paragraphs;
Paragraph para = paragraphs[2];
para.Remove();
```