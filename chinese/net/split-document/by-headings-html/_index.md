---
title: 按标题 Html
linktitle: 按标题 Html
second_title: Aspose.Words for .NET API 参考
description: 分步指南解释 Aspose.Words for .NET 的按标题 HTML 功能的 C# 源代码
type: docs
weight: 10
url: /zh/net/split-document/by-headings-html/
---
在本教程中，我们将向您介绍如何使用 Aspose.Words for .NET 的按 HTML 标题功能将 Word 文档拆分成更小的部分。按照以下步骤了解源码，根据Heading生成单独的HTML文档。

## 第 1 步：装入文档

首先，指定文档的目录并将文档加载到 Document 对象中。就是这样：

```csharp
//文档目录的路径。
string dataDir = "YOUR DOCUMENTS DIRECTORY";
Document doc = new Document(MyDir + "Rendering.docx");
```

## 步骤 2：将文档按 HTML 格式的标题划分

现在我们将设置保存选项，根据 HTML 格式的标题将文档拆分成更小的部分。就是这样：

```csharp
HtmlSaveOptions options = new HtmlSaveOptions
{
//将文档拆分成更小的部分，在本例中按标题分隔。
DocumentSplitCriteria = DocumentSplitCriteria.HeadingParagraph
};

doc.Save(dataDir + "SplitDocument.ParTitresHtml.html", options);
```

### 使用 Aspose.Words for .NET 的 By Headings HTML 示例源代码

以下是 Aspose.Words for .NET 的 By HTML Heading 功能的完整源代码：

```csharp
//文档目录的路径。
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document doc = new Document(MyDir + "Rendering.docx");

HtmlSaveOptions options = new HtmlSaveOptions
{
	//将文档拆分为更小的部分，在本例中按标题拆分。
	DocumentSplitCriteria = DocumentSplitCriteria.HeadingParagraph
};


doc.Save(dataDir + "SplitDocument.ByHeadingsHtml.html", options);
```

使用此代码，您将能够根据标题使用 Aspose.Words for .NET 将 Word 文档拆分为更小的部分。然后，您可以为每个部分生成单独的 HTML 文档。

