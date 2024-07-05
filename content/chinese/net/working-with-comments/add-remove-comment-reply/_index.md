---
title: 添加删除评论回复
linktitle: 添加删除评论回复
second_title: Aspose.Words 文档处理 API
description: 了解如何使用 Aspose.Words for .NET 在 Word 文档中添加和删除评论回复。
type: docs
weight: 10
url: /zh/net/working-with-comments/add-remove-comment-reply/
---

在本综合教程中，您将学习如何使用 Aspose.Words for .NET 在 Word 文档中添加和删除评论回复。我们将指导您完成整个过程并为您提供必要的 C# 代码片段。在本指南结束时，您将能够管理评论回复并根据您的要求对其进行自定义。

## 先决条件
在开始之前，请确保您满足以下先决条件：
- 您的系统上安装了 Aspose.Words for .NET 库。

## 步骤 1：加载文档
首先，使用 Document 类加载包含评论的文档：

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document doc = new Document(dataDir + "Comments.docx");
```

## 第 2 步：访问评论并管理回复
接下来，使用带有 NodeType.Comment 参数的 GetChild 方法从文档中访问注释：

```csharp
Comment comment = (Comment)doc.GetChild(NodeType.Comment, 0, true);
```

要从评论中删除回复，请使用 RemoveReply 方法并提供所需的回复索引：

```csharp
comment.RemoveReply(comment.Replies[0]);
```

要向评论添加新的回复，请使用 AddReply 方法并提供作者姓名、作者姓名首字母、日期和时间以及回复文本：

```csharp
comment.AddReply("John Doe", "JD", new DateTime(2017, 9, 25, 12, 15, 0), "New reply");
```

## 步骤 3：保存文档
添加或删除评论回复后，使用 Document 类的 Save 方法将文档保存到文件中：

```csharp
doc.Save(dataDir + "WorkingWithComments.AddRemoveCommentReply.docx");
```

### 使用 Aspose.Words for .NET 添加和删除评论回复的示例源代码
以下是使用 Aspose.Words for .NET 添加和删除评论回复的完整源代码：

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document doc = new Document(dataDir + "Comments.docx");

Comment comment = (Comment)doc.GetChild(NodeType.Comment, 0, true);

comment.RemoveReply(comment.Replies[0]);

comment.AddReply("John Doe", "JD", new DateTime(2017, 9, 25, 12, 15, 0), "New reply");

doc.Save(dataDir + "WorkingWithComments.AddRemoveCommentReply.docx");
```

## 结论
恭喜！您已成功学习了如何使用 Aspose.Words for .NET 在 Word 文档中添加和删除评论回复。通过遵循分步指南并利用提供的源代码，您现在可以管理评论回复并根据您的要求对其进行自定义。

评论回复允许在文档内进行协作讨论和反馈。尝试使用不同的回复作者、姓名首字母、日期和文本来增强文档内的协作和沟通。

### 常见问题解答

#### 问：如何在 Aspose.Words for .NET 中添加注释？

答：要在 Aspose.Words for .NET 中添加注释，您可以使用`Comment.AddComment`方法指定注释的文本以及您想要在文档中添加它的位置。

#### 问：如何在 Aspose.Words for .NET 中删除注释？

答：要删除 Aspose.Words for .NET 中的注释，您可以使用`Comment.Remove`方法指定`Comment`想要移除的对象。

#### 问：我可以回复 Aspose.Words for .NET 中的评论吗？

答：是的，您可以使用 Aspose.Words for .NET 回复评论`Comment.AddReply`方法指定回复文本以及您想要在文档中添加它的位置。

#### 问：如何访问 Aspose.Words for .NET 中的现有评论？

答：您可以使用 Aspose.Words for .NET 访问现有注释`CommentCollection`的财产`Document`对象。这将允许您浏览文档中存在的所有评论。

#### 问：我可以在 Aspose.Words for .NET 中编辑评论文本吗？

答：是的，您可以通过访问`Comment.Text`相应财产`Comment`对象并根据需要修改文本。