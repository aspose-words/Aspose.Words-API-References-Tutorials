---
title: 添加评论
linktitle: 添加评论
second_title: Aspose.Words 文档处理 API
description: 了解如何使用 Aspose.Words for .NET 向 Word 文档添加注释。
type: docs
weight: 10
url: /zh/net/working-with-comments/add-comments/
---

在本综合教程中，您将学习如何使用 Aspose.Words for .NET 向 Word 文档添加注释。我们将指导您完成整个过程并为您提供必要的 C# 代码片段。在本指南结束时，您将能够在文档中插入注释并自定义其内容。

## 先决条件
在开始之前，请确保您满足以下先决条件：
- 您的系统上安装了 Aspose.Words for .NET 库。

## 步骤 1：创建新文档和 DocumentBuilder
首先，使用 Document 类创建一个新文档并初始化一个 DocumentBuilder 对象：

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
```

## 步骤 2：向文档添加内容
接下来，使用 DocumentBuilder 对象将所需内容添加到文档。在此示例中，我们添加一些文本：

```csharp
builder.Write("Some text is added.");
```

## 步骤 3：创建评论并添加内容
要添加评论，请创建 Comment 类的实例，并传递 Document 对象、作者姓名、作者姓名首字母和当前日期：

```csharp
Comment comment = new Comment(doc, "Awais Hafeez", "AH", DateTime.Today);
```

接下来，将评论附加到当前段落：

```csharp
builder.CurrentParagraph.AppendChild(comment);
```

向评论添加内容，例如段落和文本：

```csharp
comment.Paragraphs.Add(new Paragraph(doc));
comment.FirstParagraph.Runs.Add(new Run(doc, "Comment text."));
```

## 步骤 4：保存文档
添加注释及其内容后，使用 Document 类的 Save 方法将文档保存到文件中：

```csharp
doc.Save(dataDir + "WorkingWithComments.AddComments.docx");
```

## 使用 Aspose.Words for .NET 添加注释的示例源代码
以下是使用 Aspose.Words for .NET 添加注释的完整源代码：

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

builder.Write("Some text is added.");

Comment comment = new Comment(doc, "Awais Hafeez", "AH", DateTime.Today);
builder.CurrentParagraph.AppendChild(comment);

comment.Paragraphs.Add(new Paragraph(doc));
comment.FirstParagraph.Runs.Add(new Run(doc, "Comment text."));

doc.Save(dataDir + "WorkingWithComments.AddComments.docx");
```

## 结论
恭喜！您已成功了解如何使用 Aspose.Words for .NET 向 Word 文档添加注释。通过遵循分步指南并利用提供的源代码，您现在可以在文档中插入注释并自定义其内容。

评论对于协作、提供附加信息或在文档中做笔记非常有用。尝试使用不同的作者姓名、姓名首字母和评论内容来满足您的特定要求。

### 常见问题解答

#### 问：如何在 Aspose.Words for .NET 文档中添加注释？

答：要在 Aspose.Words for .NET 文档中添加注释，您需要按照教程中提到的步骤进行操作。

#### 问：我可以在 Aspose.Words for .NET 中格式化注释文本吗？

答：是的，您可以使用可用的格式化属性在 Aspose.Words for .NET 中格式化注释文本。

#### 问：如何检索文档中的所有评论？

答：您可以使用`Document.Comments`财产。

#### 问：我可以删除 Aspose.Words for .NET 中的特定评论吗？

答：是的，您可以使用 Aspose.Words for .NET 中的以下方法删除特定注释：`Comment.Remove`方法。

#### 问：如何修改 Aspose.Words for .NET 中现有注释的文本？

答：要修改 Aspose.Words for .NET 中现有注释的文本，您可以访问`Comment.Text`相应财产`Comment`对象并根据需要修改文本。