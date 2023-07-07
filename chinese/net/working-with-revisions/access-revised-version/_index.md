---
title: 访问修订版本
linktitle: 访问修订版本
second_title: Aspose.Words for .NET API 参考
description: 使用 Aspose.Words for .NET 访问 Word 文档的修订版本。
type: docs
weight: 10
url: /zh/net/working-with-revisions/access-revised-version/
---

在本分步指南中，我们将向您展示如何使用 Aspose.Words for .NET 访问 Word 文档的修订版本。我们将为您提供完整的源代码，并向您展示如何格式化 Markdown 输出。

## 第 1 步：加载文档

第一步是上传包含修订的文档。

```csharp
Document doc = new Document(MyDir + "Revisions.docx");
doc.UpdateListLabels();
```

## 第2步：访问修改后的版本

我们现在将讨论该文件的修订版本。

```csharp
doc.RevisionsView = RevisionsView.Final;
```

## 第 3 步：浏览修订版本

接下来，我们将循环浏览文档中存在的修订并显示列表项段落的特定信息。

```csharp
foreach (Revision revision in doc.Revisions)
{
     if (revision.ParentNode.NodeType == NodeType.Paragraph)
     {
         Paragraph paragraph = (Paragraph)revision.ParentNode;
         if (paragraph.IsListItem)
         {
             Console.WriteLine(paragraph.ListLabel.LabelString);
             Console.WriteLine(paragraph.ListFormat.ListLevel);
         }
     }
}
```

### 使用 Aspose.Words for .NET 访问修订版本的示例源代码

以下是使用 Aspose.Words for .NET 访问文档修订版本的完整源代码：

```csharp
Document doc = new Document(MyDir + "Revisions.docx");
doc.UpdateListLabels();

//切换到文档的修订版本。
doc.RevisionsView = RevisionsView.Final;

foreach (Revision revision in doc.Revisions)
{
	 if (revision.ParentNode.NodeType == NodeType.Paragraph)
	 {
		 Paragraph paragraph = (Paragraph)revision.ParentNode;
		 if (paragraph.IsListItem)
		 {
			 Console.WriteLine(paragraph.ListLabel.LabelString);
			 Console.WriteLine(paragraph.ListFormat.ListLevel);
		 }
	 }
}
```

## 结论

在本教程中，我们学习了如何使用 Aspose.Words for .NET 访问 Word 文档的修订版本。通过加载文档、导航到修订版本并浏览修订版本，我们能够获取列表项段落的特定信息。 Aspose.Words for .NET 提供了用于操作 Word 文档的强大功能，包括访问评论。您现在可以利用这些知识，使用 Aspose.Words for .NET 访问您自己的 Word 文档的修订版本。

### 常见问题解答

#### 问：如何将经过修订的文档加载到 Aspose.Words for .NET 中？

答：使用`Document`Aspose.Words for .NET 类从包含修订的文件加载文档。您可以指定完整的文档路径。

```csharp
Document doc = new Document("path/to/the/document.docx");
```

#### 问：如何在 Aspose.Words for .NET 中访问文档的修订版本？

答：使用`RevisionsView`的财产`Document`对象访问文档的修订版本。您可以设置的值`RevisionsView`财产给`RevisionsView.Final`显示没有修改的最终版本。

```csharp
doc.RevisionsView = RevisionsView.Final;
```

#### 问：如何在 Aspose.Words for .NET 中浏览文档修订版本？

答：使用一个`foreach`循环以迭代文档中存在的修订。您可以使用`Revisions`的财产`Document`对象获取文档所有修订的集合。

```csharp
foreach (Revision revision in doc.Revisions)
{
     //在这里处理每个修订
}
```

#### 问：如何检查一个段落是否是 Aspose.Words for .NET 中的列表项？

答：使用`IsListItem`的财产`Paragraph`对象检查段落是否是列表项。这`IsListItem`财产回报`true`如果该段落是列表项，否则返回`false`.

```csharp
if (paragraph.IsListItem)
{
     //该段落是一个列表项
}
else
{
     //该段落不是列表项
}
```