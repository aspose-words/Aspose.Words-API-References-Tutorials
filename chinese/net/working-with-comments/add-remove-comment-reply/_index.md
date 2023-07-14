---
title: 添加 删除评论 回复
linktitle: 添加 删除评论 回复
second_title: Aspose.Words 文档处理 API
description: 了解如何使用 Aspose.Words for .NET 在 Word 文档中添加和删除评论回复。
type: docs
weight: 10
url: /zh/net/working-with-comments/add-remove-comment-reply/
---

在这个综合教程中，您将学习如何使用 Aspose.Words for .NET 在 Word 文档中添加和删除评论回复。我们将指导您完成整个过程，并为您提供必要的 C# 代码片段。在本指南结束时，您将能够管理评论回复并根据您的要求对其进行自定义。

## 先决条件
在我们开始之前，请确保您满足以下先决条件：
- Aspose.Words for .NET 库安装在您的系统上。

## 第 1 步：加载文档
首先，使用 Document 类加载包含注释的文档：

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document doc = new Document(dataDir + "Comments.docx");
```

## 第 2 步：访问评论并管理回复
接下来，使用带有 NodeType.Comment 参数的 GetChild 方法访问文档中的注释：

```csharp
Comment comment = (Comment)doc.GetChild(NodeType.Comment, 0, true);
```

要从评论中删除回复，请使用RemoveReply方法并提供所需的回复索引：

```csharp
comment.RemoveReply(comment.Replies[0]);
```

要向评论添加新回复，请使用 AddReply 方法并提供作者姓名、作者姓名缩写、日期和时间以及回复文本：

```csharp
comment.AddReply("John Doe", "JD", new DateTime(2017, 9, 25, 12, 15, 0), "New reply");
```

## 第 3 步：保存文档
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
恭喜！您已成功学习如何使用 Aspose.Words for .NET 在 Word 文档中添加和删除评论回复。通过遵循分步指南并利用提供的源代码，您现在可以管理评论回复并根据您的要求对其进行自定义。

评论回复允许在文档中进行协作讨论和反馈。尝试使用不同的回复作者、姓名缩写、日期和文本，以增强文档中的协作和沟通。

### 常见问题解答

#### 问：如何在 Aspose.Words for .NET 中添加注释？

答：要在 Aspose.Words for .NET 中添加注释，您可以使用`Comment.AddComment`方法指定注释文本以及要将其添加到文档中的位置。

#### 问：如何删除 Aspose.Words for .NET 中的注释？

答：要删除 Aspose.Words for .NET 中的注释，您可以使用`Comment.Remove`方法指定`Comment`您要删除的对象。

#### 问：我可以在 Aspose.Words for .NET 中回复评论吗？

答：是的，您可以使用 Aspose.Words for .NET 回复评论`Comment.AddReply`方法指定回复文本以及要将其添加到文档中的位置。

#### 问：如何访问 Aspose.Words for .NET 中的现有注释？

答：您可以使用 Aspose.Words for .NET 访问现有注释`CommentCollection`的财产`Document`目的。这将允许您浏览文档中存在的所有注释。

#### 问：我可以在 Aspose.Words for .NET 中编辑评论文本吗？

答：是的，您可以通过访问 Aspose.Words for .NET 来编辑注释文本`Comment.Text`对应的属性`Comment`对象并根据需要修改文本。