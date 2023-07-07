---
title: 获取单词的修订类型
linktitle: 获取单词的修订类型
second_title: Aspose.Words for .NET API 参考
description: 使用 Aspose.Words for .NET 获取 Word 文档中单词的修订类型。
type: docs
weight: 10
url: /zh/net/working-with-revisions/get-revision-types/
---

在本分步指南中，我们将告诉您如何使用 Aspose.Words for .NET 获取 Word 文档中的单词修订类型。我们将为您提供完整的源代码，并向您展示如何格式化 Markdown 输出。

## 第 1 步：加载文档

第一步是上传包含修订的文档。

```csharp
Document doc = new Document(MyDir + "Revisions.docx");
```

## 第 2 步：逐步浏览段落

接下来，我们将浏览文档的段落并检查与每个段落相关的单词修订类型。

```csharp
ParagraphCollection paragraphs = doc.FirstSection.Body.Paragraphs;
for (int i = 0; i < paragraphs.Count; i++)
{
     if (paragraphs[i].IsMoveFromRevision)
         Console.WriteLine("Paragraph {0} has been moved (deleted).", i);
     if (paragraphs[i].IsMoveToRevision)
         Console.WriteLine("Paragraph {0} has been moved (inserted).", i);
}
```

### 使用 Aspose.Words for .NET 获取修订类型的示例源代码

以下是使用 Aspose.Words for .NET 获取文档中的修订类型的完整源代码：

```csharp
Document doc = new Document(MyDir + "Revisions.docx");

ParagraphCollection paragraphs = doc.FirstSection.Body.Paragraphs;
for (int i = 0; i < paragraphs.Count; i++)
{
	 if (paragraphs[i].IsMoveFromRevision)
		 Console.WriteLine("Paragraph {0} has been moved (deleted).", i);
	 if (paragraphs[i].IsMoveToRevision)
		 Console.WriteLine("Paragraph {0} has been moved (inserted).", i);
}
```

## 结论

在本教程中，我们学习了如何使用 Aspose.Words for .NET 获取 Word 文档中单词修订的类型。我们按照以下步骤加载文档，浏览段落，并检查与每个段落相关的单词评论类型。现在，您可以使用 Aspose.Words for .NET 应用这些知识来分析您自己的 Word 文档中的文字评论。

### 获取单词修订类型的常见问题解答

#### 问：如何在 Aspose.Words for .NET 中上传文档？

答：使用`Document`用于从文件加载文档的 Aspose.Words for .NET 类。您可以指定完整的文档路径。

```csharp
Document doc = new Document("path/to/the/document.docx");
```

#### 问：如何在 Aspose.Words for .NET 中循环浏览文档中的段落？

答：使用`Paragraphs`文档部分的属性来获取段落的集合。然后，您可以使用循环来循环遍历每个段落。

```csharp
ParagraphCollection paragraphs = doc.FirstSection.Body.Paragraphs;
for (int i = 0; i < paragraphs.Count; i++)
{
     //在这里处理每个段落
}
```

#### 问：如何检查 Aspose.Words for .NET 中的段落是否已被移动（删除）？

 A：使用段落`IsMoveFromRevision`属性来检查它是否已被移动（删除）。

```csharp
if (paragraph. IsMove

FromRevision)
{
     //该段落已移动（删除）
}
```

#### 问：如何检查 Aspose.Words for .NET 中的段落是否已移动（插入）？

 A：使用段落`IsMoveToRevision`属性来检查它是否已被移动（插入）。

```csharp
if (paragraph.IsMoveToRevision)
{
     //该段落已被移动（插入）
}
```