---
title: 获取修订类型
linktitle: 获取修订类型
second_title: Aspose.Words for .NET API 参考
description: 使用 Aspose.Words for .NET 在 Word 文档中获取修订类型。
type: docs
weight: 10
url: /zh/net/working-with-revisions/get-revision-types/
---

在这个分步指南中，我们将告诉您如何使用 Aspose.Words for .NET 获取 Word 文档中的修订类型。我们将为您提供完整的源代码，并向您展示如何格式化降价输出。

## 第 1 步：装入文档

第一步是上传包含修订的文档。

```csharp
Document doc = new Document(MyDir + "Revisions.docx");
```

## 第 2 步：遍历段落

接下来，我们将浏览文档的段落并检查与每个段落相关的修订类型。

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

以下是使用 Aspose.Words for .NET 在文档中获取修订类型的完整源代码：

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
