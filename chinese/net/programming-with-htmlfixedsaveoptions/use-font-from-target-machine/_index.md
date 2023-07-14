---
title: 使用目标机中的字体
linktitle: 使用目标机中的字体
second_title: Aspose.Words 文档处理 API
description: 了解如何通过 Aspose.Words for .NET 使用目标计算机的字体将 Word 文档转换为固定 HTML。
type: docs
weight: 10
url: /zh/net/programming-with-htmlfixedsaveoptions/use-font-from-target-machine/
---

在 C# 应用程序中将 Word 文档转换为固定 HTML 时，您可能需要使用目标计算机的字体来确保呈现的 HTML 保留文档的原始外观和样式。借助适用于 .NET 的 Aspose.Words 库，您可以使用 HtmlFixedSaveOptions 保存选项轻松指定此功能。在本分步指南中，我们将引导您了解如何使用 Aspose.Words for .NET 的 C# 源代码，通过 HtmlFixedSaveOptions 将 Word 文档转换为使用目标计算机字体的固定 HTML。

## 了解 Aspose.Words 库

在深入研究代码之前，了解 .NET 的 Aspose.Words 库非常重要。 Aspose.Words 是一个功能强大的库，可在包括.NET 在内的不同平台上创建、编辑、转换和保护 Word 文档。它提供了许多用于操作文档的功能，例如插入文本、更改格式、添加部分等等。

## 加载Word文档

第一步是加载要转换为固定 HTML 的 Word 文档。使用 Document 类从源文件加载文档。这是一个例子：

```csharp
Document doc = new Document(dataDir + "Bullet points with alternative font.docx");
```

在此示例中，我们加载位于文档目录中的文档“Bulletpoints with Alternative font.docx”。

## 配置备份选项

下一步是配置保存选项以转换为固定 HTML。使用 HtmlFixedSaveOptions 类并将 UseTargetMachineFonts 属性设置为 true 以告诉 Aspose.Words 使用目标计算机中的字体。操作方法如下：

```csharp
HtmlFixedSaveOptions saveOptions = new HtmlFixedSaveOptions { UseTargetMachineFonts = true };
```

我们创建一个新的 HtmlFixedSaveOptions 对象并将 UseTargetMachineFonts 属性设置为 true，以便在转换时使用目标计算机的字体。

## 修复 HTML 文档转换

现在我们已经配置了保存选项，我们可以继续将文档转换为固定 HTML。使用 Document 类的 Save 方法通过指定保存选项以固定 HTML 格式保存转换后的文档。这是一个例子：

```csharp
doc.Save(dataDir + "WorkingWithHtmlFixedSaveOptions.UseFontFromTargetMachine.html", saveOptions);
```

在此示例中，我们使用指定的保存选项将转换后的文档另存为“WorkingWithHtmlFixedSaveOptions.UseFontFromTargetMachine.html”。

### 使用 Aspose.Words for .NET 的 HtmlFixedSaveOptions 示例源代码，具有“使用目标计算机中的字体”功能

```csharp
//文档目录的路径
string dataDir = "YOUR DOCUMENTS DIRECTORY";

//加载Word文档
Document doc = new Document(dataDir + "Bullet points with alternative font.docx");

//使用“使用目标计算机中的字体”功能配置备份选项
HtmlFixedSaveOptions saveOptions = new HtmlFixedSaveOptions { UseTargetMachineFonts = true };

//将文档转换为固定 HTML
doc.Save(dataDir + "WorkingWithHtmlFixedSaveOptions.UseFontFromTargetMachine.html", saveOptions);
```

## 结论

在本指南中，我们解释了如何使用目标计算机的字体以及适用于 .NET 的 Aspose.Words 库将 Word 文档转换为固定 HTML。通过遵循提供的步骤并使用提供的 C# 源代码，您可以轻松地在 C# 应用程序中应用此功能。使用目标计算机的字体转换为固定 HTML 可以确保以 HTML 格式忠实且一致地呈现文档。
