---
title: 栅格化变换后的元素
linktitle: 栅格化变换后的元素
second_title: Aspose.Words for .NET API 参考
description: 了解如何在使用 Aspose.Words for .NET 转换为 PCL 格式时禁用已转换元素的光栅化。
type: docs
weight: 10
url: /zh/net/programming-with-pclsaveoptions/rasterize-transformed-elements/
---

Aspose.Words for .NET 是一个强大的库，用于在 C# 应用程序中创建、操作和转换 Word 文档。 Aspose.Words 提供的功能之一是能够在将文档转换为不同格式时对转换后的元素进行栅格化。在本指南中，我们将向您展示如何使用 Aspose.Words for .NET 的 C# 源代码在将文档转换为 PCL 格式时禁用已转换元素的光栅化。

## 理解 Aspose.Words 库

在深入研究代码之前，了解 .NET 的 Aspose.Words 库很重要。 Aspose.Words 是一个流行的库，它使处理 Word 文档变得简单而高效。它提供了用于创建、编辑和转换 Word 文档的广泛功能，包括支持在转换过程中栅格化转换后的元素。

## 载入Word文档

第一步是加载要转换为 PCL 格式的 Word 文档。使用 Document 类从源文件加载文档。这是一个例子：

```csharp
Document doc = new Document(dataDir + "Rendering.docx");
```

在此示例中，我们正在加载位于文档目录中的“Rendering.docx”文档。

## 配置备份选项

下一步是配置转换为 PCL 格式的保存选项。使用 PclSaveOptions 类并将 RasterizeTransformedElements 属性设置为 false。方法如下：

```csharp
PclSaveOptions saveOptions = new PclSaveOptions
{
     SaveFormat = SaveFormat.Pcl,
     RasterizeTransformedElements = false
};
```

我们创建一个新的 PclSaveOptions 对象并将 SaveFormat 属性设置为 SaveFormat.Pcl 以指定我们要以 PCL 格式保存文档。接下来，我们将 RasterizeTransformedElements 属性设置为 false 以禁用转换元素的光栅化。

## 将文档转换为 PCL 格式

现在我们已经配置了保存选项，我们可以继续将文档转换为 PCL 格式。使用 Document 类的 Save 方法通过指定保存选项以 PCL 格式保存转换后的文档。这是一个例子：

```csharp
doc.Save(dataDir + "WorkingWithPclSaveOptions.RasterizeTransformedElements.pcl", saveOptions);
```

在此示例中，我们使用指定的保存选项将转换后的文档保存为“WorkingWithPclSaveOptions.RasterizeTransformedElements.pcl”。

### Aspose.Words for .NET 的“栅格化转换元素”功能示例源代码

```csharp
//文档目录的路径
string dataDir = "YOUR DOCUMENTS DIRECTORY";

//载入Word文档


Document doc = new Document(dataDir + "Rendering.docx");

//配置转换为 PCL 格式的备份选项
PclSaveOptions saveOptions = new PclSaveOptions
{
     SaveFormat = SaveFormat.Pcl,
     RasterizeTransformedElements = false
};

//将文档转换为 PCL 格式
doc.Save(dataDir + "WorkingWithPclSaveOptions.RasterizeTransformedElements.pcl", saveOptions);
```

## 结论

在本指南中，我们介绍了如何使用 Aspose.Words for .NET 在使用提供的 C# 源代码将文档转换为 PCL 格式时禁用转换元素的光栅化。按照提供的步骤操作，您可以在将 Word 文档转换为不同格式时轻松控制转换元素的光栅化行为。 Aspose.Words 提供了巨大的灵活性和强大的功能来处理转换后的元素，允许您根据您的特定需求精确地创建转换后的文档。