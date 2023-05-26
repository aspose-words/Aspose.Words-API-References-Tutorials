---
title: 访问修订版
linktitle: 访问修订版
second_title: Aspose.Words for .NET API 参考
description: 使用 Aspose.Words for .NET 访问 Word 文档的修订版本。
type: docs
weight: 10
url: /zh/net/working-with-revisions/access-revised-version/
---

在本分步指南中，我们将向您展示如何使用 Aspose.Words for .NET 访问修订版的 Word 文档。我们将为您提供完整的源代码，并向您展示如何格式化降价输出。

## 第 1 步：装入文档

第一步是上传包含修订的文档。

```csharp
Document doc = new Document(MyDir + "Revisions.docx");
doc.UpdateListLabels();
```

## 第 2 步：访问修改后的版本

我们现在将继续讨论文档的修订版本。

```csharp
doc.RevisionsView = RevisionsView.Final;
```

## 第 3 步：浏览修订

接下来，我们将遍历文档中存在的修订并显示作为列表项的段落的特定信息。

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

以下是使用 Aspose.Words for .NET 访问文档修订版的完整源代码：

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


