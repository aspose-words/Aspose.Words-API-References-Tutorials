---
title: 将图元文件转换为 Png
linktitle: 将图元文件转换为 Png
second_title: Aspose.Words 文档处理 API
description: 了解使用 Aspose.Words for .NET 上传文档时如何将图元文件转换为 PNG 图像。
type: docs
weight: 10
url: /zh/net/programming-with-loadoptions/convert-metafiles-to-png/
---
在 C# 应用程序中对文档进行文字处理时，可能需要将图元文件转换为 PNG 图像，以获得更好的兼容性和准确的渲染。借助适用于 .NET 的 Aspose.Words 库，您可以在加载文档时轻松将图元文件转换为 PNG。在本分步指南中，我们将引导您了解如何使用 Aspose.Words for .NET C# 源代码来加载文档，并使用 LoadOptions 加载选项将图元文件转换为 PNG。

## 了解 Aspose.Words 库

在深入研究代码之前，了解 .NET 的 Aspose.Words 库非常重要。 Aspose.Words 是一个功能强大的库，可在包括.NET 在内的不同平台上创建、编辑、转换和保护 Word 文档。它提供了许多用于操作文档的功能，例如插入文本、更改格式、添加部分等等。

## 步骤一：定义文档目录

第一步是定义文档所在的目录。您必须指定完整的目录路径。例如 ：

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
```

请务必将“您的文档目录”替换为文档目录的实际路径。

## 第 2 步：配置加载选项

现在让我们配置文档的加载选项。使用 LoadOptions 类指定加载参数。例如 ：

```csharp
LoadOptions loadOptions = new LoadOptions { ConvertMetafilesToPng = true };
```

在此示例中，我们创建一个新的 LoadOptions 对象并将 ConvertMetafilesToPng 属性设置为 true，以便在加载文档时启用图元文件到 PNG 的转换。

## 步骤 3：加载文档并将图元文件转换为 PNG

现在我们已经配置了加载选项，我们可以使用 Document 类加载文档并指定加载选项。例如 ：

```csharp
Document doc = new Document(dataDir + "WMF with image.docx", loadOptions);
```

在此示例中，我们使用指定的加载选项加载位于文档目录中的文档“WMF with image.docx”。

## 使用 Aspose.Words for .NET 的 LoadOptions 和将图元文件转换为 Png 功能的示例源代码

```csharp
//文档目录的路径
string dataDir = "YOUR DOCUMENTS DIRECTORY";

//使用“将图元文件转换为 Png”功能配置加载选项
LoadOptions loadOptions = new LoadOptions { ConvertMetafilesToPng = true };

//使用指定选项加载文档
Document doc = new Document(dataDir + "WMF with image.docx", loadOptions);
```

## 结论

在本指南中，我们解释了如何使用 .NET 的 Aspose.Words 库将图元文件转换为 PNG 图像来加载文档。通过遵循提供的步骤并使用提供的 C# 源代码，您可以轻松地在 C# 应用程序中应用此功能。将图元文件转换为 PNG 可确保更好的兼容性和文档的准确渲染。
