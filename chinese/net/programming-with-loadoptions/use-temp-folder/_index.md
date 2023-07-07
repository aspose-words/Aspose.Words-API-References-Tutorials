---
title: 使用临时文件夹
linktitle: 使用临时文件夹
second_title: Aspose.Words for .NET API 参考
description: 了解使用 Aspose.Words for .NET 上传文档时如何使用临时文件夹。
type: docs
weight: 10
url: /zh/net/programming-with-loadoptions/use-temp-folder/
---

在 C# 应用程序中处理 Word 文档时，可能需要使用临时文件夹来存储文档处理过程中生成的临时文件。借助适用于 .NET 的 Aspose.Words 库，您可以使用 LoadOptions 加载选项轻松指定临时文件夹。在本分步指南中，我们将向您展示如何使用 Aspose.Words for .NET C# 源代码通过 LoadOptions 加载选项指定的临时文件夹来加载文档。

## 了解 Aspose.Words 库

在深入研究代码之前，了解 .NET 的 Aspose.Words 库非常重要。 Aspose.Words 是一个功能强大的库，可在包括.NET 在内的不同平台上创建、编辑、转换和保护 Word 文档。它提供了许多用于操作文档的功能，例如插入文本、更改格式、添加部分等等。

## 配置加载选项

第一步是配置文档的加载选项。使用 LoadOptions 类指定加载参数。在我们的例子中，我们需要将 TempFolder 属性设置为所需临时文件夹的路径。操作方法如下：

```csharp
LoadOptions loadOptions = new LoadOptions { TempFolder = ArtifactsDir };
```

我们创建一个新的 LoadOptions 对象并将 TempFolder 属性设置为所需临时文件夹的路径。

## 使用指定的临时文件夹上传文档

现在我们已经配置了加载选项，我们可以使用 Document 类加载文档并指定加载选项。这是一个例子：

```csharp
Document doc = new Document(dataDir + "Document.docx", loadOptions);
```

在此示例中，我们使用指定的加载选项加载位于文档目录中的文档“Document.docx”。

### 使用 Aspose.Words for .NET 的具有“使用临时文件夹”功能的 LoadOptions 示例源代码

```csharp
//文档目录的路径
string dataDir = "YOUR DOCUMENTS DIRECTORY";

//使用“使用临时文件夹”功能配置加载选项
LoadOptions loadOptions = new LoadOptions { TempFolder = ArtifactsDir };

//使用指定的临时文件夹加载文档
Document doc = new Document(dataDir + "Document.docx", loadOptions);
```

## 结论

在本指南中，我们解释了如何使用 .NET 的 Aspose.Words 库使用指定的临时文件夹上传文档。通过遵循提供的步骤并使用提供的 C# 源代码，您可以轻松地在 C# 应用程序中应用此功能。使用临时文件夹可以以有组织且高效的方式存储文档处理过程中生成的临时文件。
