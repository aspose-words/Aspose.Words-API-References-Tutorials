---
title: 获取 Jpeg 页面范围
linktitle: 获取 Jpeg 页面范围
second_title: Aspose.Words 文档处理 API
description: 了解如何使用 Aspose.Words for .NET 获取一系列 JPEG 页面。提取自定义图像的完整教程。
type: docs
weight: 10
url: /zh/net/programming-with-imagesaveoptions/get-jpeg-page-range/
---

在本教程中，我们将探索 Aspose.Words for .NET 提供的“获取 JPEG 页面范围”功能的 C# 源代码。此功能允许您将文档的特定范围的页面转换为 JPEG 格式的图像。

## 步骤 1：设置环境

开始之前，请确保您已使用 Aspose.Words for .NET 设置开发环境。请确保您已添加必要的引用并导入适当的命名空间。

## 步骤 2：加载文档

```csharp
//文档目录的路径
string dataDir = "YOUR DOCUMENTS DIRECTORY";

Document doc = new Document(dataDir + "Rendering.docx");
```

在此步骤中，我们使用`Document`方法并传递要加载的 DOCX 文件的路径。

## 步骤 3：配置映像备份选项

```csharp
ImageSaveOptions options = new ImageSaveOptions(SaveFormat.Jpeg);
options. PageSet = new PageSet(0);
options. ImageBrightness = 0.3f;
options. ImageContrast = 0.7f;
options. HorizontalResolution = 72f;
```

在此步骤中，我们配置图像的备份选项。我们创建一个新的`ImageSaveOptions`对象指定所需的保存格式，这里“Jpeg”表示 JPEG 格式。我们还使用`PageSet`对象。最后，我们使用`ImageBrightness`和`ImageContrast`属性。我们还使用`HorizontalResolution`财产。

## 步骤 4：备份图像

```csharp
doc.Save(dataDir + "WorkingWithImageSaveOptions.GetJpegPageRange.jpeg", options);
```

在最后一步中，我们使用`Save`方法并传递输出文件的路径以及指定的保存选项。

现在您可以运行源代码，将文档中特定范围的页面转换为 JPEG 图像。生成的文件将保存在指定的目录中，名称为“WorkingWithImageSaveOptions.GetJpegPageRange.jpeg”。

### 使用 Aspose.Words For .NET 获取 Jpeg 页面范围的示例源代码

```csharp 
 //文档目录的路径
 string dataDir = "YOUR DOCUMENT DIRECTORY"; 

Document doc = new Document(dataDir + "Rendering.docx");

ImageSaveOptions options = new ImageSaveOptions(SaveFormat.Jpeg);

//将“PageSet”设置为“0”以仅转换文档的第一页。
options.PageSet = new PageSet(0);

//改变图像的亮度和对比度。
//两者的比例均为 0-1，默认为 0.5。
options.ImageBrightness = 0.3f;
options.ImageContrast = 0.7f;

//更改水平分辨率。
//这些属性的默认值为 96.0，分辨率为 96dpi。
options.HorizontalResolution = 72f;

doc.Save(dataDir + "WorkingWithImageSaveOptions.GetJpegPageRange.jpeg", options);
            
        
```

## 结论

在本教程中，我们探索了使用 Aspose.Words for .NET 获取 JPEG 页面范围的功能。我们学习了如何将文档的特定页面范围转换为 JPEG 格式的图像，同时自定义保存选项。

当您想从文档中提取特定页面并将其保存为 JPEG 图像时，此功能非常有用。您还可以调整图像的亮度、对比度和水平分辨率以获得个性化效果。

Aspose.Words for .NET 提供了大量用于文档操作和生成的高级功能。获取 JPEG 页面范围是它为您提供的众多强大工具之一。

请随意将此功能集成到您的 Aspose.Words for .NET 项目中，以从您的文档中获取高质量的 JPEG 图像。