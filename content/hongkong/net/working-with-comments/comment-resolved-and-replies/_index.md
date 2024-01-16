---
title: 評論已解決並回复
linktitle: 評論已解決並回复
second_title: Aspose.Words 文件處理 API
description: 了解如何使用 Aspose.Words for .NET 解析 Word 文件中的註解及其回應。
type: docs
weight: 10
url: /zh-hant/net/working-with-comments/comment-resolved-and-replies/
---

在這個綜合教學中，您將學習如何使用 Aspose.Words for .NET 解析 Word 文件中的註解及其回應。我們將引導您完成整個過程，並為您提供必要的 C# 程式碼片段。在本指南結束時，您將能夠管理評論解決方案並更新評論及其回應的狀態。

## 先決條件
在我們開始之前，請確保您符合以下先決條件：
- Aspose.Words for .NET 程式庫安裝在您的系統上。

## 第 1 步：載入文件並造訪評論
首先，使用 Document 類別載入包含註解的文件並存取註解集合：

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document doc = new Document(dataDir + "Comments.docx");

NodeCollection comments = doc.GetChildNodes(NodeType.Comment, true);
```

## 第 2 步：解決評論及其回复
接下來，迭代評論及其回復以將其標記為已解決：

```csharp
Comment parentComment = (Comment)comments[0];

foreach (Comment childComment in parentComment.Replies)
{
    Console.WriteLine(childComment.Ancestor.Id);
    Console.WriteLine(childComment.Done);

    childComment.Done = true;
}
```

在上面的程式碼中，我們訪問父評論並迭代其回應。我們可以檢索父親評論 ID 及其解決狀態。然後，我們更新每個評論回應的「完成」標記以指示解決方案。

## 第 3 步：儲存文檔
解決註解並更新其狀態後，使用 Document 類別的 Save 方法將修改後的文件儲存到文件中：

```csharp
doc.Save(dataDir + "WorkingWithComments.CommentResolvedAndReplies.docx");
```

### 使用 Aspose.Words for .NET 解析評論及其回應的範例原始程式碼
以下是使用 Aspose.Words for .NET 解析評論及其回應的完整原始碼：

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document doc = new Document(dataDir + "Comments.docx");

NodeCollection comments = doc.GetChildNodes(NodeType.Comment, true);

Comment parentComment = (Comment)comments[0];

foreach (Comment childComment in parentComment.Replies)
{
    Console.WriteLine(childComment.Ancestor.Id);
    Console.WriteLine(childComment.Done);

    childComment.Done = true;
}

doc.Save(dataDir + "WorkingWithComments.CommentResolvedAndReplies.docx");
```
請記住根據您的特定要求調整程式碼，包括文件文件路徑和其他自訂

## 結論
恭喜！您已成功學習如何使用 Aspose.Words for .NET 解析 Word 文件中的註解及其回應。透過遵循逐步指南並利用提供的原始程式碼，您現在可以管理評論解決方案並根據您的要求更新評論及其回應的狀態。

評論解析有助於追蹤和管理文件中的回饋。嘗試不同的評論狀態並對其進行自訂，以改善文件中的協作和審閱流程。

### 常見問題解答

#### Q：如何解決 Aspose.Words for .NET 中的註解？

答：要解析 Aspose.Words for .NET 中的註釋，您可以使用`Comment.Resolve`方法指定`Comment`您要解決的對象。這會將評論標記為已解決並將其隱藏在最終文件中。

#### Q：如何在 Aspose.Words for .NET 中新增已解決評論的回應？

答：雖然已解決的評論預設隱藏在最終文件中，但您仍然可以使用`Comment.AddReply`方法指定回覆文字以及要新增它的位置。

#### Q：如何在 Aspose.Words for .NET 中查看已解決的註解？

答：預設情況下，已解決的註解隱藏在最終文件中。但是，您可以使用`CommentOptions.ShowResolvedComments`的財產`Document`對象並將其設定為`true`.

#### Q：如何在 Aspose.Words for .NET 中隱藏所有評論，包括回應？

答：要在 Aspose.Words for .NET 中隱藏所有評論（包括回應），您可以使用`CommentOptions.CommentDisplayMode`的財產`Document`對象並將其設定為`CommentDisplayMode.None`.

#### Q：我可以在 Aspose.Words for .NET 中編輯已解決評論的文字嗎？

答：是的，您可以透過造訪 Aspose.Words for .NET 來編輯已解決評論的文本`Comment.Text`對應的屬性`Comment`物件並根據需要修改文字。