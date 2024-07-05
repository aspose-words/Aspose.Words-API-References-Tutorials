---
title: 评论已解决并回复
linktitle: 评论已解决并回复
second_title: Aspose.Words 文档处理 API
description: 了解如何使用 Aspose.Words for .NET 解决 Word 文档中的评论及其回复。
type: docs
weight: 10
url: /zh/net/working-with-comments/comment-resolved-and-replies/
---

在本综合教程中，您将学习如何使用 Aspose.Words for .NET 解决 Word 文档中的评论及其回复。我们将指导您完成整个过程并为您提供必要的 C# 代码片段。在本指南结束时，您将能够管理评论解析并更新评论及其回复的状态。

## 先决条件
在开始之前，请确保您满足以下先决条件：
- 您的系统上安装了 Aspose.Words for .NET 库。

## 步骤 1：加载文档并访问注释
首先，使用 Document 类加载包含评论的文档并访问评论集合：

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document doc = new Document(dataDir + "Comments.docx");

NodeCollection comments = doc.GetChildNodes(NodeType.Comment, true);
```

## 第 2 步：解决评论及其回复
接下来，遍历评论及其回复以将其标记为已解决：

```csharp
Comment parentComment = (Comment)comments[0];

foreach (Comment childComment in parentComment.Replies)
{
    Console.WriteLine(childComment.Ancestor.Id);
    Console.WriteLine(childComment.Done);

    childComment.Done = true;
}
```

在上面的代码中，我们访问父评论并遍历其回复。我们可以检索父评论 ID 及其解决状态。然后，我们更新每个评论回复的“完成”标记以指示已解决。

## 步骤 3：保存文档
解析注释并更新其状态后，使用 Document 类的 Save 方法将修改后的文档保存到文件中：

```csharp
doc.Save(dataDir + "WorkingWithComments.CommentResolvedAndReplies.docx");
```

### 使用 Aspose.Words for .NET 解析评论及其回复的示例源代码
以下是使用 Aspose.Words for .NET 解析评论及其回复的完整源代码：

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
请记住根据您的具体要求调整代码，包括文档文件路径和其他自定义

## 结论
恭喜！您已成功了解如何使用 Aspose.Words for .NET 解决 Word 文档中的评论及其回复。通过遵循分步指南并利用提供的源代码，您现在可以管理评论解析并根据您的要求更新评论及其回复的状态。

评论解析有助于跟踪和管理文档中的反馈。尝试不同的评论状态并对其进行自定义，以改进文档中的协作和审阅流程。

### 常见问题解答

#### 问：如何解决 Aspose.Words for .NET 中的评论？

答：要解决 Aspose.Words for .NET 中的注释，您可以使用`Comment.Resolve`方法指定`Comment`您要解决的对象。这会将评论标记为已解决，并将其隐藏在最终文档中。

#### 问：如何在 Aspose.Words for .NET 中对已解决的评论添加回复？

答：虽然已解决的评论默认隐藏在最终文档中，但您仍然可以使用`Comment.AddReply`方法指定回复文本以及要添加它的位置。

#### 问：如何在 Aspose.Words for .NET 中查看已解决的评论？

答：默认情况下，已解决的评论会隐藏在最终文档中。但是，您可以使用`CommentOptions.ShowResolvedComments`的财产`Document`对象并将其设置为`true`.

#### 问：如何在 Aspose.Words for .NET 中隐藏所有评论（包括回复）？

答：要在 Aspose.Words for .NET 中隐藏所有评论（包括回复），您可以使用`CommentOptions.CommentDisplayMode`的财产`Document`对象并将其设置为`CommentDisplayMode.None`.

#### 问：我可以在 Aspose.Words for .NET 中编辑已解决的评论的文本吗？

答：是的，您可以通过访问 Aspose.Words for .NET 中的`Comment.Text`相应财产`Comment`对象并根据需要修改文本。