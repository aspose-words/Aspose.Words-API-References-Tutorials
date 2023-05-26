---
title: 插入 HTML
linktitle: 插入 HTML
second_title: Aspose.Words for .NET API 参考
description: 了解如何使用 Aspose.Words for .NET 将 HTML 内容插入到 Word 文档中。分步指南。
type: docs
weight: 10
url: /zh/net/add-content-using-documentbuilder/insert-html/
---

在这个综合教程中，您将学习如何使用 Aspose.Words for .NET 将 HTML 内容插入到 Word 文档中。我们将指导您完成整个过程，并为您提供必要的 C# 代码片段。在本指南结束时，您将能够向 Word 文档添加 HTML 元素、格式和样式。

## 先决条件
在我们开始之前，请确保您具备以下先决条件：
- Aspose.Words for .NET 库安装在您的系统上。

## 第 1 步：创建新文档和 DocumentBuilder
首先，使用 Document 类创建一个新文档并初始化一个 DocumentBuilder 对象：

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
```

## 第 2 步：插入 HTML 内容
接下来，使用 DocumentBuilder 类的 InsertHtml 方法将 HTML 内容插入到文档中。您可以在 HTML 字符串中包含 HTML 标记、属性和样式：

```csharp
builder.InsertHtml(
	"<P align='right'>Paragraph right</P>" +
	"<b>Implicit paragraph left</b>" +
	"<div align='center'>Div center</div>" +
	"<h1 align='left'>Heading 1 left.</h1>");
```

## 第 3 步：保存文档
插入 HTML 内容后，使用 Document 类的 Save 方法将文档保存到文件：

```csharp
doc.Save(ArtifactsDir + "AddContentUsingDocumentBuilder.InsertHtml.docx");
```

## 使用 Aspose.Words for .NET 插入 HTML 的示例源代码
以下是使用 Aspose.Words for .NET 将 HTML 内容插入 Word 文档的完整源代码：
当您有现有的 HTML 内容并希望将其包含在 Word 文档中同时保留原始格式和布局时，此功能特别有用。

```csharp

	Document doc = new Document();
	DocumentBuilder builder = new DocumentBuilder(doc);
	
	builder.InsertHtml(
		"<P align='right'>Paragraph right</P>" +
		"<b>Implicit paragraph left</b>" +
		"<div align='center'>Div center</div>" +
		"<h1 align='left'>Heading 1 left.</h1>");

	doc.Save(ArtifactsDir + "AddContentUsingDocumentBuilder.InsertHtml.docx");
	
```

请记住根据您的特定 HTML 内容和要求调整代码。确保您的 HTML 格式正确并且与 Aspose.Words for .NET 兼容。

## 结论
恭喜！您已经成功学习了如何使用 Aspose.Words for .NET 将 HTML 内容插入到 Word 文档中。按照分步指南并利用提供的源代码，您现在可以将 HTML 元素、格式和样式合并到您的 Word 文档中。


