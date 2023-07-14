---
title: 公开 Tiff 二值化的阈值控制
linktitle: 公开 Tiff 二值化的阈值控制
second_title: Aspose.Words 文档处理 API
description: 了解如何使用 Aspose.Words for .NET 控制 TIFF 二值化阈值。获得更高质量图像的完整教程。
type: docs
weight: 10
url: /zh/net/programming-with-imagesaveoptions/expose-threshold-control-for-tiff-binarization/
---
在本教程中，我们将探索使用 Aspose.Words for .NET 为“TIFF 二值化阈值控制曝光”功能提供的 C# 源代码。此功能允许您在将文档转换为 TIFF 格式时控制二值化阈值。

## 第一步：搭建环境

在开始之前，请确保您已使用 Aspose.Words for .NET 设置开发环境。确保您已添加必要的引用并导入适当的命名空间。

## 第 2 步：加载文档

```csharp
//文档目录的路径
string dataDir = "YOUR DOCUMENTS DIRECTORY";

Document doc = new Document(dataDir + "Rendering.docx");
```

在此步骤中，我们使用以下命令加载文档`Document`方法并传递要加载的 DOCX 文件的路径。

## 步骤 3：配置映像备份选项

```csharp
ImageSaveOptions saveOptions = new ImageSaveOptions(SaveFormat.Tiff)
{
TiffCompression = TiffCompression.Ccitt3,
ImageColorMode = ImageColorMode.Grayscale,
TiffBinarizationMethod = ImageBinarizationMethod.FloydSteinbergDithering,
ThresholdForFloydSteinbergDithering = 254
};
```

在此步骤中，我们配置图像的备份选项。我们创建一个新的`ImageSaveOptions`指定所需保存格式的对象，此处“Tiff”表示 TIFF 格式。我们还设置压缩选项、图像颜色模式和具有指定二值化阈值的 TIFF 二值化方法。

## 第 4 步：备份图像

```csharp
doc.Save(dataDir + "WorkingWithImageSaveOptions.ExposeThresholdControlForTiffBinarization.tiff", saveOptions);
```

在最后一步中，我们使用以下命令将文档图像保存为 TIFF 格式：`Save`方法并将路径传递到输出文件以及指定的保存选项。

现在，您可以运行源代码将文档转换为 TIFF 格式，同时使用指定选项控制二值化阈值。生成的文件将保存在指定目录中，名称为“WorkingWithImageSaveOptions.ExposeThresholdControlForTiffBinarization.tiff”。

### 示例源代码公开 Tiff 二值化的阈值控制

```csharp 

//文档目录的路径
 string dataDir = "YOUR DOCUMENT DIRECTORY"; 

Document doc = new Document(dataDir + "Rendering.docx");

ImageSaveOptions saveOptions = new ImageSaveOptions(SaveFormat.Tiff)
{
	TiffCompression = TiffCompression.Ccitt3,
	ImageColorMode = ImageColorMode.Grayscale,
	TiffBinarizationMethod = ImageBinarizationMethod.FloydSteinbergDithering,
	ThresholdForFloydSteinbergDithering = 254
};

doc.Save(dataDir + "WorkingWithImageSaveOptions.ExposeThresholdControlForTiffBinarization.tiff", saveOptions);
            
        
```

### 结论

在本教程中，我们使用 Aspose.Words for .NET 探索了 TIFF 二值化阈值控制的曝光功能。我们学习了如何在将文档转换为 TIFF 格式时控制二值化阈值。

当您想要调整二值化阈值以获得具有更好质量和清晰度的 TIFF 图像时，此功能非常有用。通过使用保存选项指定二值化阈值，您可以获得根据您的需求定制的自定义结果。

Aspose.Words for .NET 提供了多种用于文档操作和生成的高级功能。公开 TIFF 二值化阈值控制是它为您提供的众多强大工具之一。

请随意将此功能合并到您的 Aspose.Words for .NET 项目中，以通过精确的二值化阈值控制获得高质量的 TIFF 图像。