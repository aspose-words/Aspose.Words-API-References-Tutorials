---
title: 评论解决和回复
linktitle: 评论解决和回复
second_title: Aspose.Words for .NET API 参考
description: 了解如何使用 Aspose.Words for .NET 解决 Word 文档中的评论和回复。
type: docs
weight: 10
url: /zh/net/working-with-comments/comment-resolved-and-replies/
---

在这个综合教程中，您将学习如何使用 Aspose.Words for .NET 解决 Word 文档中的评论和回复。我们将指导您完成整个过程，并为您提供必要的 C# 代码片段。到本指南结束时，您将能够管理评论解决方案并更新评论及其回复的状态。

## 先决条件
在我们开始之前，请确保您具备以下先决条件：
- Aspose.Words for .NET 库安装在您的系统上。

## 第 1 步：加载文档并访问评论
首先，使用 Document 类加载包含评论的文档并访问评论集合：

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document doc = new Document(dataDir + "Comments.docx");

NodeCollection comments = doc.GetChildNodes(NodeType.Comment, true);
```

## 第 2 步：解决评论及其回复
接下来，遍历评论和他们的回复以将它们标记为已解决：

```csharp
Comment parentComment = (Comment)comments[0];

foreach (Comment childComment in parentComment.Replies)
{
    Console.WriteLine(childComment.Ancestor.Id);
    Console.WriteLine(childComment.Done);

    childComment.Done = true;
}
```

在上面的代码中，我们访问父评论并遍历其回复。我们可以检索父评论 ID 及其解决状态。然后，我们更新每个评论回复的“完成”标记以指示解决方案。

## 第 3 步：保存文档
解决评论并更新其状态后，使用 Document 类的 Save 方法将修改后的文档保存到文件中：

```csharp
doc.Save(dataDir + "WorkingWithComments.CommentResolvedAndReplies.docx");
```

### 使用 Aspose.Words for .NET 解析评论及其回复的示例源代码
下面是使用 Aspose.Words for .NET 解析评论和回复的完整源代码：

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
恭喜！您已经成功学习了如何使用 Aspose.Words for .NET 解决 Word 文档中的评论和回复。按照分步指南并利用提供的源代码，您现在可以管理评论解决方案并根据您的要求更新评论及其回复的状态。

评论解决有助于跟踪和管理文档中的反馈。尝试不同的评论状态并自定义它们以改进文档中的协作和审阅流程。
