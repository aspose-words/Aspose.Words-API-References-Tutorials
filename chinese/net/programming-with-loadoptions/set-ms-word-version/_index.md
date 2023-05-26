---
title: 设置 Ms Word 版本
linktitle: 设置 Ms Word 版本
second_title: Aspose.Words for .NET API 参考
description: 了解如何使用 Aspose.Words for .NET 使用指定版本的 MS Word 加载文档。
type: docs
weight: 10
url: /zh/net/programming-with-loadoptions/set-ms-word-version/
---

在 C# 应用程序中处理 Word 文档时，可能需要指定加载文档时要使用的 Microsoft Word 版本。借助 .NET 的 Aspose.Words 库，您可以使用 LoadOptions 轻松设置要使用的 MS Word 版本。在这个循序渐进的指南中，我们将带您了解如何使用 Aspose.Words for .NET C# 源代码使用 LoadOptions 加载选项加载包含指定版本 MS Word 的文档。

## 理解 Aspose.Words 库

在深入研究代码之前，了解 .NET 的 Aspose.Words 库很重要。 Aspose.Words 是一个强大的库，可以在包括.NET 在内的不同平台上创建、编辑、转换和保护 Word 文档。它提供了许多用于操作文档的功能，例如插入文本、更改格式、添加部分等等。

## 配置加载选项

第一步是为我们的文档配置加载选项。使用 LoadOptions 类指定加载参数。在我们的例子中，我们需要将 MswVersion 属性设置为所需的 MS Word 版本。例如，我们使用的是 Microsoft Word 2010 版本。这是如何做到的：

```csharp
LoadOptions loadOptions = new LoadOptions { MswVersion = MsWordVersion.Word2010 };
```

我们创建一个新的 LoadOptions 对象并将 MswVersion 属性设置为 MsWordVersion.Word2010 以指定 MS Word 2010 的版本。

## 使用指定版本的 MS Word 加载文档

现在我们已经配置了加载选项，我们可以使用 Document 类加载文档并指定加载选项。这是一个例子：

```csharp
Document doc = new Document(dataDir + "Document.docx", loadOptions);
```

在此示例中，我们使用指定的加载选项加载位于文档目录中的文档“Document.docx”。

### 使用 Aspose.Words for .NET 的具有“设置 MS Word 版本”功能的 LoadOptions 示例源代码

```csharp
//文档目录的路径
string dataDir = "YOUR DOCUMENTS DIRECTORY";

//使用“设置 MS Word 版本”功能配置加载选项
LoadOptions loadOptions = new LoadOptions { MswVersion = MsWordVersion.Word2010 };

//使用指定版本的 MS Word 加载文档
Document doc = new Document(dataDir + "Document.docx", loadOptions);

//保存文件
doc.Save(dataDir + "WorkingWithLoadOptions.SetMsWordVersion.docx");
```

## 结论

在本指南中，我们解释了如何使用 .NET 的 Aspose.Words 库上传指定特定版本 MS Word 的文档。按照提供的步骤并使用提供的代码 C# 源代码，您可以轻松地将此功能应用到您的 C# 应用程序中。使用指定版本的 MS Word 加载文档可以确保在应用程序中正确兼容和处理文档。
