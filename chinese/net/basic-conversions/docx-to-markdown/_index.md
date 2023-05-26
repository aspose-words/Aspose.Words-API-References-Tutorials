---
title: Docx 转 Markdown
linktitle: Docx 转 Markdown
second_title: Aspose.Words for .NET API 参考
description: 了解如何使用 Aspose.Words for .NET 将 Word 文档从 Docx 格式转换为 Markdown 格式。带示例源代码的分步教程。
type: docs
weight: 10
url: /zh/net/basic-conversions/docx-to-markdown/
---

在这个循序渐进的教程中，我们将指导您如何使用 Aspose.Words for .NET 将 Docx 格式的 Word 文档转换为 Markdown。我们将解释提供的 C# 源代码，并向您展示如何在您自己的项目中实现它。

要开始，请确保您已在开发环境中安装和设置 Aspose.Words for .NET。如果您还没有这样做，请从官方网站下载并安装该库。

## 步骤 1：初始化 Document 和 DocumentBuilder 对象

首先，初始化`Document`对象和`DocumentBuilder`目的：

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
```

## 第 2 步：向文档添加内容

接下来，使用`DocumentBuilder`向文档添加内容的对象。在此示例中，我们将使用`Writeln`方法：

```csharp
builder.Writeln("Some text!");
```

您可以根据需要随意添加更复杂的内容，例如标题、表格、列表或格式。

## 第三步：将文档保存为 Markdown 格式

要以 Markdown 格式保存文档，请使用`Save`上的方法`Document`对象并提供输出文档的路径和文件名。在这个例子中，我们将它保存为`"BaseConversions.DocxToMarkdown.md"`:

```csharp
doc.Save(dataDir + "BaseConversions.DocxToMarkdown.md");
```

就是这样！您已经使用 Aspose.Words for .NET 成功地将 Docx 格式的 Word 文档转换为 Markdown。

### 使用 Aspose.Words for .NET 的 Docx To Markdown 示例源代码

```csharp

	//文档目录的路径。
	string dataDir = "YOUR DOCUMENT DIRECTORY";
	Document doc = new Document();
	DocumentBuilder builder = new DocumentBuilder(doc);

	builder.Writeln("Some text!");

	doc.Save(dataDir + "BaseConversions.DocxToMarkdown.md");

```

随意在您自己的项目中使用此代码，并根据您的特定要求对其进行修改。