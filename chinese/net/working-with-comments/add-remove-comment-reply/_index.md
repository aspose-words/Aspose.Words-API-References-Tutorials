---
title: 添加删除评论回复
linktitle: 添加删除评论回复
second_title: Aspose.Words for .NET API 参考
description: 了解如何使用 Aspose.Words for .NET 在 Word 文档中添加和删除评论回复。
type: docs
weight: 10
url: /zh/net/working-with-comments/add-remove-comment-reply/
---

在这个综合教程中，您将学习如何使用 Aspose.Words for .NET 在 Word 文档中添加和删除评论回复。我们将指导您完成整个过程，并为您提供必要的 C# 代码片段。到本指南结束时，您将能够管理评论回复并根据您的要求对其进行自定义。

## 先决条件
在我们开始之前，请确保您具备以下先决条件：
- Aspose.Words for .NET 库安装在您的系统上。

## 第 1 步：装入文档
首先，使用 Document 类加载包含评论的文档：

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document doc = new Document(dataDir + "Comments.docx");
```

## 第 2 步：访问评论和管理回复
接下来，使用带有 NodeType.Comment 参数的 GetChild 方法访问文档中的评论：

```csharp
Comment comment = (Comment)doc.GetChild(NodeType.Comment, 0, true);
```

要从评论中删除回复，请使用 RemoveReply 方法并提供所需的回复索引：

```csharp
comment.RemoveReply(comment.Replies[0]);
```

要向评论添加新回复，请使用 AddReply 方法并提供作者姓名、作者姓名首字母、日期和时间以及回复文本：

```csharp
comment.AddReply("John Doe", "JD", new DateTime(2017, 9, 25, 12, 15, 0), "New reply");
```

## 第 3 步：保存文档
添加或删除评论回复后，使用 Document 类的 Save 方法将文档保存到文件：

```csharp
doc.Save(dataDir + "WorkingWithComments.AddRemoveCommentReply.docx");
```

### 使用 Aspose.Words for .NET 添加和删除评论回复的示例源代码
下面是使用 Aspose.Words for .NET 添加和删除评论回复的完整源代码：

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document doc = new Document(dataDir + "Comments.docx");

Comment comment = (Comment)doc.GetChild(NodeType.Comment, 0, true);

comment.RemoveReply(comment.Replies[0]);

comment.AddReply("John Doe", "JD", new DateTime(2017, 9, 25, 12, 15, 0), "New reply");

doc.Save(dataDir + "WorkingWithComments.AddRemoveCommentReply.docx");
```

## 结论
恭喜！您已经成功学习了如何使用 Aspose.Words for .NET 在 Word 文档中添加和删除评论回复。按照分步指南并利用提供的源代码，您现在可以管理评论回复并根据您的要求对其进行自定义。

评论回复允许在文档中进行协作讨论和反馈。尝试使用不同的回复作者、首字母、日期和文本来增强文档中的协作和交流。