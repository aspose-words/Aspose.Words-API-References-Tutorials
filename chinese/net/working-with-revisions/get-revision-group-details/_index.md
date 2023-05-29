---
title: 获取修订组详细信息
linktitle: 获取修订组详细信息
second_title: Aspose.Words for .NET API 参考
description: 使用 Aspose.Words for .NET 在 Word 文档中获取修订组详细信息。
type: docs
weight: 10
url: /zh/net/working-with-revisions/get-revision-group-details/
---

在本分步指南中，我们将向您展示如何使用 Aspose.Words for .NET 获取 Word 文档中一组修订的详细信息。我们将为您提供完整的源代码，并向您展示如何格式化降价输出。

## 第 1 步：装入文档

第一步是上传包含修订的文档。

```csharp
Document doc = new Document(MyDir + "Revisions.docx");
```

## 第 2 步：浏览修订

接下来，我们将遍历文档中的修订并显示它们的详细信息，例如类型、作者、日期和修订文本。

```csharp
foreach (Revision revision in doc.Revisions)
{
     string groupText = revision.Group != null
         ? "Revision group text: " + revision.Group.Text
         : "The revision does not belong to any group";

     Console.WriteLine("Type: " + revision.RevisionType);
     Console.WriteLine("Author: " + revision.Author);
     Console.WriteLine("Date: " + revision.DateTime);
     Console.WriteLine("Revision text: " + revision.ParentNode.ToString(SaveFormat.Text));
     Console.WriteLine(groupText);
}
```


### 使用 Aspose.Words for .NET 获取修订组详细信息的示例源代码

以下是使用 Aspose.Words for .NET 获取文档中一组修订的详细信息的完整源代码：

```csharp
Document doc = new Document(MyDir + "Revisions.docx");

foreach (Revision revision in doc.Revisions)
{
	 string groupText = revision.Group != null
		 ? "Revision group text: " + revision.Group.Text
		 : "The revision does not belong to any group";

	 Console.WriteLine("Type: " + revision.RevisionType);
	 Console.WriteLine("Author: " + revision.Author);
	 Console.WriteLine("Date: " + revision.DateTime);
	 Console.WriteLine("Revision text: " + revision.ParentNode.ToString(SaveFormat.Text));
	 Console.WriteLine(groupText);
}
```

