---
title: 錨評論
linktitle: 錨評論
second_title: Aspose.Words 文件處理 API
description: 了解如何使用 Aspose.Words for .NET 將評論回應錨定到 Word 文件中的特定文字。
type: docs
weight: 10
url: /zh-hant/net/working-with-comments/anchor-comment/
---

在這個綜合教學中，您將學習如何使用 Aspose.Words for .NET 將評論回應錨定到 Word 文件中的特定文字。我們將引導您完成整個過程，並為您提供必要的 C# 程式碼片段。在本指南結束時，您將能夠將註釋與文件中的特定文字相關聯。

## 先決條件
在我們開始之前，請確保您符合以下先決條件：
- Aspose.Words for .NET 程式庫安裝在您的系統上。

## 第 1 步：建立新文件並新增文本
首先，使用 Document 類別建立新文件並新增所需的文字：

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document doc = new Document();

Paragraph para1 = new Paragraph(doc);
Run run1 = new Run(doc, "Some ");
Run run2 = new Run(doc, "text ");
para1.AppendChild(run1);
para1.AppendChild(run2);
doc.FirstSection.Body.AppendChild(para1);

Paragraph para2 = new Paragraph(doc);
Run run3 = new Run(doc, "is ");
Run run4 = new Run(doc, "added ");
para2.AppendChild(run3);
para2.AppendChild(run4);
doc.FirstSection.Body.AppendChild(para2);
```

## 第 2 步：建立評論並新增評論範圍
接下來，建立註解並使用 CommentRangeStart 和 CommentRangeEnd 物件將其與特定文字關聯：

```csharp
Comment comment = new Comment(doc, "Awais Hafeez", "AH", DateTime.Today);
comment.Paragraphs.Add(new Paragraph(doc));
comment.FirstParagraph.Runs.Add(new Run(doc, "Comment text."));

CommentRangeStart commentRangeStart = new CommentRangeStart(doc, comment.Id);
CommentRangeEnd commentRangeEnd = new CommentRangeEnd(doc, comment.Id);

run1.ParentNode.InsertAfter(commentRangeStart, run1);
run3.ParentNode.InsertAfter(commentRangeEnd, run3);
commentRangeEnd.ParentNode.InsertAfter(comment, commentRangeEnd);
```

## 第 3 步：儲存文檔
將註解錨定到特定文字後，使用 Document 類別的 Save 方法將文件儲存到文件中：

```csharp
doc.Save(dataDir + "WorkingWithComments.AnchorComment.doc");
```

### 使用 Aspose.Words for .NET 進行錨評論回應的範例原始程式碼
以下是使用 Aspose.Words for .NET 錨定評論回應的完整原始碼：

```csharp
//建立文檔的實例。
string dataDir = "YOUR DOCUMENT DIRECTORY";        
Document doc = new Document();

//建立三個 Run 物件。
//前兩個運行一些文本，而第三個運行註釋

Paragraph para1 = new Paragraph(doc);
Run run1 = new Run(doc, "Some ");
Run run2 = new Run(doc, "text ");
para1.AppendChild(run1);
para1.AppendChild(run2);
doc.FirstSection.Body.AppendChild(para1);

Paragraph para2 = new Paragraph(doc);
Run run3 = new Run(doc, "is ");
Run run4 = new Run(doc, "added ");
para2.AppendChild(run3);
para2.AppendChild(run4);
doc.FirstSection.Body.AppendChild(para2);

Comment comment = new Comment(doc, "Awais Hafeez", "AH", DateTime.Today);
comment.Paragraphs.Add(new Paragraph(doc));
comment.FirstParagraph.Runs.Add(new Run(doc, "Comment text."));

//每個 Run 物件都有一個關聯的 CommentRangeStart 和 CommentRangeEnd 物件。

CommentRangeStart commentRangeStart = new CommentRangeStart(doc, comment.Id);
CommentRangeEnd commentRangeEnd = new CommentRangeEnd(doc, comment.Id);

run1.ParentNode.InsertAfter(commentRangeStart, run1);
run3.ParentNode.InsertAfter(commentRangeEnd, run3);
commentRangeEnd.ParentNode.InsertAfter(comment, commentRangeEnd);

doc.Save(dataDir + "WorkingWithComments.AnchorComment.doc");	
```

### 常見問題解答

#### Q：Aspose.Words for .NET 中的註解錨點是什麼？

答：在 Aspose.Words for .NET 中，註解錨是將註解連接到文件中特定位置的標記。

#### Q：如何在 Aspose.Words for .NET 文件中新增註解錨點？

答：要在 Aspose.Words for .NET 文件中新增註解錨點，請依照教學中提到的步驟操作。

#### Q：如何存取 Aspose.Words for .NET 中現有的評論錨點？

答：您可以使用 Aspose.Words for .NET 存取現有註解錨點`Comment.Anchor`財產。

#### Q：我可以在 Aspose.Words for .NET 中支援評論錨點嗎？

答：是的，您可以使用以下指令刪除 Aspose.Words for .NET 中的註解錨點：`Comment.Remove`方法。

#### Q：如何在 Aspose.Words for .NET 中編輯連結到評論錨點的評論文字？

答：要修改 Aspose.Words for .NET 中綁定到註解錨點的註解文本，您可以存取`Comment.Text`對應的屬性`Comment`反對並根據需要修改文本。

