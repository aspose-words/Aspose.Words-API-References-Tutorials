---
title: 按标题 Html 拆分 Word 文档
linktitle: 按标题 Html
second_title: Aspose.Words 文档处理 API
description: 逐步解释 Aspose.Words for .NET 的按标题 HTML 功能拆分单词文档的 C# 源代码
type: docs
weight: 10
url: /zh/net/split-document/by-headings-html/
---
在本教程中，我们将引导您了解如何使用 Aspose.Words for .NET 的按 HTML 标题功能将 Word 文档拆分为更小的部分。按照以下步骤了解源代码并根据标题生成单独的 HTML 文档。

## 步骤 1：加载文档

首先，指定文档的目录并将文档加载到 Document 对象中。操作方法如下：

```csharp
//文档目录的路径。
string dataDir = "YOUR DOCUMENTS DIRECTORY";
Document doc = new Document(MyDir + "Rendering.docx");
```

## 步骤 2：按 HTML 格式的标题划分文档

现在我们将设置保存选项，以根据 HTML 格式的标题将文档拆分为更小的部分。操作方法如下：

```csharp
HtmlSaveOptions options = new HtmlSaveOptions
{
//将文档分成更小的部分，在本例中按标题分隔。
DocumentSplitCriteria = DocumentSplitCriteria.HeadingParagraph
};

doc.Save(dataDir + "SplitDocument.ParTitresHtml.html", options);
```

### 使用 Aspose.Words for .NET 的 By Headings HTML 示例源代码

以下是 Aspose.Words for .NET 的按 HTML 标题功能的完整源代码：

```csharp
//文档目录的路径。
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document doc = new Document(MyDir + "Rendering.docx");

HtmlSaveOptions options = new HtmlSaveOptions
{
	//将文档分成更小的部分，在本例中按标题分割。
	DocumentSplitCriteria = DocumentSplitCriteria.HeadingParagraph
};


doc.Save(dataDir + "SplitDocument.ByHeadingsHtml.html", options);
```

使用此代码，您将能够使用 Aspose.Words for .NET 根据标题将 Word 文档拆分为较小的部分。然后，您可以为每个部分生成单独的 HTML 文档。

## 结论

在本教程中，我们学习了如何使用 Aspose.Words for .NET 的按 HTML 标题功能将 Word 文档拆分为较小的部分。通过指定`DocumentSplitCriteria`作为`HeadingParagraph`在里面`HtmlSaveOptions`，我们能够根据原始文档中的标题生成单独的 HTML 文档。

按标题拆分文档对于组织和管理内容非常有用，尤其是在包含多个部分的大型文档中。Aspose.Words for .NET 提供了一种可靠而有效的解决方案来处理文档拆分并生成各种格式的输出。

请随意探索 Aspose.Words for .NET 提供的其他功能和选项，以进一步增强您的文档处理能力并简化您的工作流程。

### 常见问题解答

#### 如何使用 Aspose.Words for .NET 根据标题将 Word 文档拆分为更小的部分？

要根据标题拆分 Word 文档，可以使用 Aspose.Words for .NET 的按 HTML 标题功能。按照提供的源代码并设置`DocumentSplitCriteria`到`HeadingParagraph`在里面`HtmlSaveOptions`对象。这将按每个标题将文档拆分为更小的部分。

#### 我可以将 Word 文档拆分成哪些格式？

提供的源代码演示了如何将 Word 文档拆分为 HTML 格式的较小部分。但是，Aspose.Words for .NET 支持各种输出格式，包括 DOCX、PDF、EPUB 等。您可以修改代码并在`HtmlSaveOptions`提出相应反对。

#### 我可以选择不同的标准来拆分文档吗？

是的，您可以根据需要选择不同的标准来拆分文档。Aspose.Words for .NET 提供了几个标准选项，例如`HeadingParagraph`, `Page`, `Section`等。修改`DocumentSplitCriteria`财产在`HtmlSaveOptions`对象来选择适当的拆分标准。

#### 我如何自定义分割部分的输出 HTML？

 Aspose.Words for .NET 允许您通过在`HtmlSaveOptions`对象。您可以控制 CSS 样式、图像、字体等各个方面。有关自定义 HTML 输出的更多详细信息，请参阅 Aspose.Words 文档。

#### 我可以根据多个标准拆分文档吗？

是的，您可以通过组合条件选项来根据多个条件拆分文档。例如，您可以通过设置`DocumentSplitCriteria`财产`HeadingParagraph | Page`。这将按每个标题和每页分割文档，并根据两个标准创建更小的部分。