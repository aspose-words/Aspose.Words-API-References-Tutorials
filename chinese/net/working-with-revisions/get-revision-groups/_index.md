---
title: 获取修订组
linktitle: 获取修订组
second_title: Aspose.Words for .NET API 参考
description: 使用 Aspose.Words for .NET 获取 Word 文档中的修订组。
type: docs
weight: 10
url: /zh/net/working-with-revisions/get-revision-groups/
---

在本分步指南中，我们将告诉您如何使用 Aspose.Words for .NET 获取 Word 文档中的修订组。我们将为您提供完整的源代码，并向您展示如何格式化 Markdown 输出。

## 第 1 步：加载文档

第一步是上传包含修订的文档。

```csharp
Document doc = new Document(MyDir + "Revisions.docx");
```

## 第 2 步：浏览修订组

接下来，我们将循环浏览文档中存在的修订组并显示其详细信息，例如作者、修订类型和修订文本。

```csharp
foreach(RevisionGroup group in doc.Revisions.Groups)
{
     Console.WriteLine("{0}, {1}:", group.Author, group.RevisionType);
     Console.WriteLine(group.Text);
}
```


### 使用 Aspose.Words for .NET 获取修订组的示例源代码

以下是使用 Aspose.Words for .NET 获取文档中的修订组的完整源代码：

```csharp
Document doc = new Document(MyDir + "Revisions.docx");

foreach(RevisionGroup group in doc.Revisions.Groups)
{
	 Console.WriteLine("{0}, {1}:", group.Author, group.RevisionType);
	 Console.WriteLine(group.Text);
}
```

## 结论

在本教程中，我们学习了如何使用 Aspose.Words for .NET 获取 Word 文档中的修订组。我们按照以下步骤加载文档并浏览审阅组，显示作者和审阅类型等详细信息。您现在可以应用这些知识，使用 Aspose.Words for .NET 来分析您自己的 Word 文档的修订。

### 常见问题解答

#### 问：如何在 Aspose.Words for .NET 中上传文档？

答：使用`Document`用于从文件加载文档的 Aspose.Words for .NET 类。您可以指定完整的文档路径。

```csharp
Document doc = new Document("path/to/the/document.docx");
```

#### 问：如何在 Aspose.Words for .NET 中浏览文档中的修订组？

答：使用`Groups`文档的属性`Revisions`对象获取修订组的集合。然后，您可以使用循环来遍历每个审阅组。

```csharp
foreach(RevisionGroup group in doc.Revisions.Groups)
{
     //在此处理每个审核组
}
```

#### 问：如何在 Aspose.Words for .NET 中获取审阅组的作者？

答：使用`Author`的财产`RevisionGroup`对象获取修订组的作者。

```csharp
string author = group.Author;
```

#### 问：如何在 Aspose.Words for .NET 中获取修订组的修订类型？

答：使用`RevisionType`的财产`RevisionGroup`对象来获取组的修订类型。

```csharp
string revisionType = group.RevisionType;
```