---
title: 在单个文件中写入所有 CSS 规则
linktitle: 在单个文件中写入所有 CSS 规则
second_title: Aspose.Words 文档处理 API
description: 了解如何通过使用 Aspose.Words for .NET 在单个文件中编写所有 CSS 规则将 Word 文档转换为固定 HTML。
type: docs
weight: 10
url: /zh/net/programming-with-htmlfixedsaveoptions/write-all-css-rules-in-single-file/
---

在 C# 应用程序中将 Word 文档转换为固定 HTML 时，您可能希望将所有 CSS 规则合并到单个文件中，以便更好地组织和移植。使用 .NET 的 Aspose.Words 库，您可以使用 HtmlFixedSaveOptions 保存选项轻松指定此功能。在本分步指南中，我们将引导您了解如何使用 Aspose.Words for .NET C# 源代码将 Word 文档转换为固定 HTML，方法是使用保存选项 HtmlFixedSaveOptions 在单个文件中编写所有 CSS 规则。

## 了解 Aspose.Words 库

在深入研究代码之前，了解 .NET 的 Aspose.Words 库非常重要。Aspose.Words 是一个功能强大的库，可用于在包括 .NET 在内的不同平台中创建、编辑、转换和保护 Word 文档。它提供了许多用于操作文档的功能，例如插入文本、更改格式、添加部分等等。

## 加载 Word 文档

第一步是加载要转换为固定 HTML 的 Word 文档。使用 Document 类从源文件加载文档。以下是示例：

```csharp
Document doc = new Document(dataDir + "Document.docx");
```

在此示例中，我们加载位于文档目录中的文档“Document.docx”。

## 配置备份选项

下一步是配置转换为固定 HTML 的保存选项。使用 HtmlFixedSaveOptions 类并将 SaveFontFaceCssSeparately 属性设置为 false，以将所有 CSS 规则写入单个文件中。操作方法如下：

```csharp
HtmlFixedSaveOptions saveOptions = new HtmlFixedSaveOptions { SaveFontFaceCssSeparately = false };
```

我们创建一个新的 HtmlFixedSaveOptions 对象并将 SaveFontFaceCssSeparately 属性设置为 false，以将所有 CSS 规则写入单个文件中。

## 修复 HTML 文档转换

现在我们已经配置了保存选项，我们可以继续将文档转换为固定 HTML。使用 Document 类的 Save 方法通过指定保存选项将转换后的文档保存为固定 HTML 格式。以下是示例：

```csharp
doc.Save(dataDir + "WorkingWithHtmlFixedSaveOptions.WriteAllCssRulesInSingleFile.html", saveOptions);
```

在此示例中，我们使用指定的保存选项将转换后的文档保存为“WorkingWithHtmlFixedSaveOptions.WriteAllCssRulesInSingleFile.html”。

### 使用 Aspose.Words for .NET 实现“在一个文件中写入所有 CSS 规则”功能的 HtmlFixedSaveOptions 示例源代码

```csharp
//访问文档目录的路径
string dataDir = "YOUR DOCUMENTS DIRECTORY";

//加载 Word 文档
Document doc = new Document(dataDir + "Document.docx");

//使用“将所有 CSS 规则写入一个文件中”功能配置备份选项
HtmlFixedSaveOptions saveOptions = new HtmlFixedSaveOptions { SaveFontFaceCssSeparately = false };

//将文档转换为固定 HTML
doc.Save(dataDir + "WorkingWithHtmlFixedSaveOptions.WriteAllCssRulesInSingleFile.html", saveOptions);
```

## 结论

在本指南中，我们介绍了如何使用 HtmlFixedSaveOptions 和 Aspose.Words 库在单个文件中编写所有 CSS 规则，将 Word 文档转换为固定 HTML。通过遵循提供的步骤并使用提供的 C# 源代码，您可以轻松地在 C# 应用程序中应用此功能。将所有 CSS 规则编写在单个文件中可以更轻松地组织和管理文档转换期间生成的 HTML 代码。