---
title: 按部分 Html
linktitle: 按部分 Html
second_title: Aspose.Words for .NET API 参考
description: 通过完整的代码示例，了解如何使用 Aspose.Words for .NET 将 Word 文档拆分为 Html 部分。
type: docs
weight: 10
url: /zh/net/split-document/by-sections-html/
---

在本例中，我们将向您展示如何使用 Aspose.Words for .NET 的按 HTML 部分功能将 Word 文档拆分为 HTML 格式的单独部分。按照以下步骤了解源代码并为每个部分生成单独的 HTML 文档。

## 第 1 步：装入文档

首先，指定文档的目录并将文档加载到 Document 对象中。就是这样：

```csharp
//文档目录的路径。
string dataDir = "YOUR DOCUMENTS DIRECTORY";
Document doc = new Document(MyDir + "Rendering.docx");
```

## 第 2 步：将文档分成 HTML 格式的部分

现在我们将设置保存选项以将文档分成 HTML 格式的部分。方法如下：

```csharp
HtmlSaveOptions options = new HtmlSaveOptions { DocumentSplitCriteria = DocumentSplitCriteria.SectionBreak };

doc.Save(dataDir + "SplitDocument.ParSectionsHtml.html", options);
```

### 使用 Aspose.Words for .NET 的 By Sections HTML 示例源代码

以下是 Aspose.Words for .NET 的 By HTML Sections 功能的完整源代码：

```csharp

	//文档目录的路径。
	string dataDir = "YOUR DOCUMENT DIRECTORY";
	Document doc = new Document(MyDir + "Rendering.docx");

	
	HtmlSaveOptions options = new HtmlSaveOptions { DocumentSplitCriteria = DocumentSplitCriteria.SectionBreak };
	
	
	doc.Save(dataDir + "SplitDocument.BySectionsHtml.html", options);

```

使用此代码，您将能够使用 Aspose.Words for .NET 将 Word 文档拆分为 HTML 格式的单独部分。

现在您可以为初始文档的每个部分生成单独的 HTML 文档。



