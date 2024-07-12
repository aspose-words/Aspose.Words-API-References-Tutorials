---
title: 使用目标机器的字体
linktitle: 使用目标机器的字体
second_title: Aspose.Words 文档处理 API
description: 了解如何使用 Aspose.Words for .NET 将 Word 文档转换为使用目标机器字体的固定 HTML。
type: docs
weight: 10
url: /zh/net/programming-with-htmlfixedsaveoptions/use-font-from-target-machine/
---

在 C# 应用程序中将 Word 文档转换为固定 HTML 时，您可能希望使用目标机器的字体来确保呈现的 HTML 保留文档的原始外观和样式。使用 .NET 的 Aspose.Words 库，您可以使用 HtmlFixedSaveOptions 保存选项轻松指定此功能。在本分步指南中，我们将引导您了解如何使用 .NET 的 Aspose.Words 的 C# 源代码，使用 HtmlFixedSaveOptions 将 Word 文档转换为使用目标机器字体的固定 HTML。

## 了解 Aspose.Words 库

在深入研究代码之前，了解 .NET 的 Aspose.Words 库非常重要。Aspose.Words 是一个功能强大的库，可用于在包括 .NET 在内的不同平台中创建、编辑、转换和保护 Word 文档。它提供了许多用于操作文档的功能，例如插入文本、更改格式、添加部分等等。

## 加载 Word 文档

第一步是加载要转换为固定 HTML 的 Word 文档。使用 Document 类从源文件加载文档。以下是示例：

```csharp
Document doc = new Document(dataDir + "Bullet points with alternative font.docx");
```

在这个例子中，我们加载位于文档目录中的文档“Bullet points with alternative font.docx”。

## 配置备份选项

下一步是配置转换为固定 HTML 的保存选项。使用 HtmlFixedSaveOptions 类并将 UseTargetMachineFonts 属性设置为 true，以告诉 Aspose.Words 使用目标机器的字体。操作方法如下：

```csharp
HtmlFixedSaveOptions saveOptions = new HtmlFixedSaveOptions { UseTargetMachineFonts = true };
```

我们创建一个新的 HtmlFixedSaveOptions 对象并将 UseTargetMachineFonts 属性设置为 true，以便在转换时使用目标机器的字体。

## 修复 HTML 文档转换

现在我们已经配置了保存选项，我们可以继续将文档转换为固定 HTML。使用 Document 类的 Save 方法通过指定保存选项将转换后的文档保存为固定 HTML 格式。以下是示例：

```csharp
doc.Save(dataDir + "WorkingWithHtmlFixedSaveOptions.UseFontFromTargetMachine.html", saveOptions);
```

在此示例中，我们使用指定的保存选项将转换后的文档保存为“WorkingWithHtmlFixedSaveOptions.UseFontFromTargetMachine.html”。

### 使用 Aspose.Words for .NET 的具有“使用目标机器的字体”功能的 HtmlFixedSaveOptions 示例源代码

```csharp
//文档目录的路径
string dataDir = "YOUR DOCUMENTS DIRECTORY";

//加载 Word 文档
Document doc = new Document(dataDir + "Bullet points with alternative font.docx");

//使用“使用目标机器的字体”功能配置备份选项
HtmlFixedSaveOptions saveOptions = new HtmlFixedSaveOptions { UseTargetMachineFonts = true };

//将文档转换为固定 HTML
doc.Save(dataDir + "WorkingWithHtmlFixedSaveOptions.UseFontFromTargetMachine.html", saveOptions);
```

## 结论

在本指南中，我们解释了如何使用目标机器的字体和适用于 .NET 的 Aspose.Words 库将 Word 文档转换为固定 HTML。通过遵循提供的步骤并使用提供的 C# 源代码，您可以轻松地在 C# 应用程序中应用此功能。使用目标机器的字体转换为固定 HTML 可确保以 HTML 格式忠实一致地呈现文档。
