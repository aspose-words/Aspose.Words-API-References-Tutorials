---
title: 新增 刪除評論 回复
linktitle: 新增 刪除評論 回复
second_title: Aspose.Words 文件處理 API
description: 了解如何使用 Aspose.Words for .NET 在 Word 文件中新增和刪除評論回應。
type: docs
weight: 10
url: /zh-hant/net/working-with-comments/add-remove-comment-reply/
---

在這個綜合教學中，您將學習如何使用 Aspose.Words for .NET 在 Word 文件中新增和刪除評論回應。我們將引導您完成整個過程，並為您提供必要的 C# 程式碼片段。在本指南結束時，您將能夠管理評論回應並根據您的要求進行自訂。

## 先決條件
在我們開始之前，請確保您符合以下先決條件：
- Aspose.Words for .NET 程式庫安裝在您的系統上。

## 第 1 步：載入文檔
首先，使用 Document 類別載入包含註解的文件：

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document doc = new Document(dataDir + "Comments.docx");
```

## 第 2 步：造訪評論並管理回复
接下來，使用帶有 NodeType.Comment 參數的 GetChild 方法存取文件中的註解：

```csharp
Comment comment = (Comment)doc.GetChild(NodeType.Comment, 0, true);
```

要從評論中刪除回复，請使用RemoveReply方法並提供所需的回复索引：

```csharp
comment.RemoveReply(comment.Replies[0]);
```

若要為評論新增回复，請使用 AddReply 方法並提供作者姓名、作者姓名縮寫、日期和時間以及回覆文字：

```csharp
comment.AddReply("John Doe", "JD", new DateTime(2017, 9, 25, 12, 15, 0), "New reply");
```

## 第 3 步：儲存文檔
新增或刪除評論回覆後，使用 Document 類別的 Save 方法將文件儲存到文件中：

```csharp
doc.Save(dataDir + "WorkingWithComments.AddRemoveCommentReply.docx");
```

### 使用 Aspose.Words for .NET 新增和刪除評論回應的範例原始程式碼
以下是使用 Aspose.Words for .NET 新增和刪除評論回應的完整原始碼：

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document doc = new Document(dataDir + "Comments.docx");

Comment comment = (Comment)doc.GetChild(NodeType.Comment, 0, true);

comment.RemoveReply(comment.Replies[0]);

comment.AddReply("John Doe", "JD", new DateTime(2017, 9, 25, 12, 15, 0), "New reply");

doc.Save(dataDir + "WorkingWithComments.AddRemoveCommentReply.docx");
```

## 結論
恭喜！您已成功學習如何使用 Aspose.Words for .NET 在 Word 文件中新增和刪除評論回應。透過遵循逐步指南並利用提供的原始程式碼，您現在可以管理評論回應並根據您的要求進行自訂。

評論回應允許在文件中進行協作討論和回饋。嘗試使用不同的回覆作者、姓名縮寫、日期和文本，以增強文件中的協作和溝通。

### 常見問題解答

#### Q：如何在 Aspose.Words for .NET 中新增註解？

答：要在 Aspose.Words for .NET 中新增註釋，您可以使用`Comment.AddComment`方法指定註釋文字以及要將其新增至文件中的位置。

#### Q：如何刪除 Aspose.Words for .NET 中的註解？

答：要刪除 Aspose.Words for .NET 中的註釋，您可以使用`Comment.Remove`方法指定`Comment`您要刪除的物件。

#### Q：我可以在 Aspose.Words for .NET 中回覆評論嗎？

答：是的，您可以使用 Aspose.Words for .NET 回覆評論`Comment.AddReply`方法指定回覆文字以及要將其新增至文件中的位置。

#### Q：如何存取 Aspose.Words for .NET 中的現有註解？

答：您可以使用 Aspose.Words for .NET 存取現有註釋`CommentCollection`的財產`Document`目的。這將允許您瀏覽文件中存在的所有註釋。

#### Q：我可以在 Aspose.Words for .NET 中編輯評論文字嗎？

答：是的，您可以透過造訪 Aspose.Words for .NET 來編輯註解文本`Comment.Text`對應的屬性`Comment`物件並根據需要修改文字。