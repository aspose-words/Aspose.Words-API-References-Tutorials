---
title: 按标题 Html
linktitle: 按标题 Html
second_title: Aspose.Words for .NET API 参考
description: 分步指南解释 Aspose.Words for .NET 的按标题 HTML 功能的 C# 源代码
type: docs
weight: 10
url: /zh/net/split-document/by-headings-html/
---
在本教程中，我们将引导您了解如何使用 Aspose.Words for .NET 的“按 HTML 标题”功能将 Word 文档拆分为更小的部分。按照以下步骤了解源代码并根据 Heading 生成单独的 HTML 文档。

## 第 1 步：加载文档

首先，指定文档的目录并将文档加载到 Document 对象中。就是这样：

```csharp
//文档目录的路径。
string dataDir = "YOUR DOCUMENTS DIRECTORY";
Document doc = new Document(MyDir + "Rendering.docx");
```

## 步骤 2：按 HTML 格式的标题划分文档

现在我们将设置保存选项，根据 HTML 格式的标题将文档分割成更小的部分。就是这样：

```csharp
HtmlSaveOptions options = new HtmlSaveOptions
{
//将文档拆分为更小的部分，在本例中按标题分隔。
DocumentSplitCriteria = DocumentSplitCriteria.HeadingParagraph
};

doc.Save(dataDir + "SplitDocument.ParTitresHtml.html", options);
```

### 使用 Aspose.Words for .NET 的按标题 HTML 的示例源代码

以下是 Aspose.Words for .NET 的“按 HTML 标题”功能的完整源代码：

```csharp
//文档目录的路径。
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document doc = new Document(MyDir + "Rendering.docx");

HtmlSaveOptions options = new HtmlSaveOptions
{
	//将文档拆分为较小的部分，在本例中按标题拆分。
	DocumentSplitCriteria = DocumentSplitCriteria.HeadingParagraph
};


doc.Save(dataDir + "SplitDocument.ByHeadingsHtml.html", options);
```

通过此代码，您将能够使用 Aspose.Words for .NET 根据标题将 Word 文档拆分为更小的部分。然后您可以为每个部分生成单独的 HTML 文档。

