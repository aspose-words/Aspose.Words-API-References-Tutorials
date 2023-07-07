---
title: 将形状转换为 Office 数学
linktitle: 将形状转换为 Office 数学
second_title: Aspose.Words for .NET API 参考
description: 了解使用 Aspose.Words for .NET 上传文档时如何将形状转换为 Office 数学公式。
type: docs
weight: 10
url: /zh/net/programming-with-loadoptions/convert-shape-to-office-math/
---

在 C# 应用程序中处理包含数学形状的文档时，您可能需要将它们转换为 Office 数学公式，以获得更好的兼容性和演示效果。借助适用于 .NET 的 Aspose.Words 库，您可以在加载文档时轻松将形状转换为 Office 数学公式。在本分步指南中，我们将引导您了解如何使用 Aspose.Words for .NET C# 源代码加载文档，并使用 LoadOptions 将形状转换为 Office 数学公式。

## 了解 Aspose.Words 库

在深入研究代码之前，了解 .NET 的 Aspose.Words 库非常重要。 Aspose.Words 是一个功能强大的库，可在包括.NET 在内的不同平台上创建、编辑、转换和保护 Word 文档。它提供了许多用于操作文档的功能，例如插入文本、更改格式、添加部分等等。

## 配置加载选项

第一步是配置文档的加载选项。使用 LoadOptions 类指定加载参数。在我们的例子中，我们想要将形状转换为 Office 数学公式，因此我们需要将 ConvertShapeToOfficeMath 属性设置为 true。操作方法如下：

```csharp
LoadOptions loadOptions = new LoadOptions { ConvertShapeToOfficeMath = true };
```

我们创建一个新的 LoadOptions 对象并将 ConvertShapeToOfficeMath 属性设置为 true，以便在加载文档时将形状转换为 Office 数学公式。

## 通过将形状转换为 Office 数学公式来加载文档

现在我们已经配置了加载选项，我们可以使用 Document 类加载文档并指定加载选项。这是一个例子：

```csharp
Document doc = new Document(dataDir + "Office math.docx", loadOptions);
```

在此示例中，我们使用指定的加载选项加载位于文档目录中的文档“Office math.docx”。

## 文件登记

加载文档并将形状转换为 Office 数学公式后，您可以使用 Document 类的 Save 方法将其保存为所需的格式。例如，要将文档保存为 .docx 格式：

```csharp
doc.Save(dataDir + "WorkingWithLoadOptions.ConvertShapeToOfficeMath.docx", SaveFormat.Docx);
```

请务必将“dataDir”替换为文档的目录路径。

### 使用 Aspose.Words for .NET 具有“将形状转换为 Office 数学”功能的 LoadOptions 示例源代码

```csharp
//文档目录的路径
string dataDir = "YOUR DOCUMENTS DIRECTORY";

//使用“转换形状”功能配置加载选项

  To Office Math"
LoadOptions loadOptions = new LoadOptions { ConvertShapeToOfficeMath = true };

//使用指定选项加载文档
Document doc = new Document(dataDir + "Office math.docx", loadOptions);

//以所需格式保存文档
doc.Save(dataDir + "WorkingWithLoadOptions.ConvertShapeToOfficeMath.docx", SaveFormat.Docx);
```

## 结论

在本指南中，我们解释了如何使用 .NET 的 Aspose.Words 库加载文档并将形状转换为 Office 数学公式。通过遵循提供的步骤并使用提供的 C# 源代码，您可以轻松地在 C# 应用程序中应用此功能。将形状转换为 Office 数学公式可为包含数学元素的文档提供更好的兼容性和演示。
