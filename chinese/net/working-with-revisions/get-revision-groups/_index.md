---
title: 获取修订组
linktitle: 获取修订组
second_title: Aspose.Words for .NET API 参考
description: 使用 Aspose.Words for .NET 在 Word 文档中获取修订组。
type: docs
weight: 10
url: /zh/net/working-with-revisions/get-revision-groups/
---

在这个循序渐进的指南中，我们将告诉您如何使用 Aspose.Words for .NET 在 Word 文档中获取修订组。我们将为您提供完整的源代码，并向您展示如何格式化降价输出。

## 第 1 步：装入文档

第一步是上传包含修订的文档。

```csharp
Document doc = new Document(MyDir + "Revisions.docx");
```

## 第 2 步：浏览修订组

接下来，我们将遍历文档中的修订组并显示其详细信息，例如作者、修订类型和修订文本。

```csharp
foreach(RevisionGroup group in doc.Revisions.Groups)
{
     Console.WriteLine("{0}, {1}:", group.Author, group.RevisionType);
     Console.WriteLine(group.Text);
}
```


### 使用 Aspose.Words for .NET 获取修订组的示例源代码

以下是使用 Aspose.Words for .NET 获取文档中修订组的完整源代码：

```csharp
Document doc = new Document(MyDir + "Revisions.docx");

foreach(RevisionGroup group in doc.Revisions.Groups)
{
	 Console.WriteLine("{0}, {1}:", group.Author, group.RevisionType);
	 Console.WriteLine(group.Text);
}
```


