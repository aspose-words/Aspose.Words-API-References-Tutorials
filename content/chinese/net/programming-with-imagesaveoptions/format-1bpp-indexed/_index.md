---
title: 格式 1Bpp 索引
linktitle: 格式 1Bpp 索引
second_title: Aspose.Words 文档处理 API
description: 了解如何使用 Aspose.Words for .NET 以 1 bpp 格式索引图像。低色深图像的完整教程。
type: docs
weight: 10
url: /zh/net/programming-with-imagesaveoptions/format-1bpp-indexed/
---
在本教程中，我们将探索 Aspose.Words for .NET 提供的“Format 1Bpp Indexed”功能的 C# 源代码。此功能允许您以 PNG 格式格式化文档中的图像，颜色深度为每像素 1 位 (1 bpp) 和索引颜色模式。

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
ImageSaveOptions saveOptions = new ImageSaveOptions(SaveFormat.Png)
{
     PageSet = new PageSet(1),
     ImageColorMode = ImageColorMode.BlackAndWhite,
     PixelFormat = ImagePixelFormat.Format1bppIndexed
};
```

在此步骤中，我们配置图像的备份选项。我们创建一个新的`ImageSaveOptions`对象指定所需的保存格式，此处的“Png”表示 PNG 格式。我们还定义了要包含在图像中的页面、黑白颜色模式和索引的 1 bpp 像素格式。

## 步骤 4：备份图像

```csharp
doc.Save(dataDir + "WorkingWithImageSaveOptions.Format1BppIndexed.Png", saveOptions);
```

在最后一步中，我们使用`Save`方法并传递输出文件的路径以及指定的保存选项。

现在您可以运行源代码，将文档图像格式化为 PNG 格式，颜色深度为 1 bpp 索引。生成的文件将保存在指定的目录中，名称为“WorkingWithImageSaveOptions.Format1BppIndexed.Png”。

### 使用 Aspose.Words for .NET 索引的 1Bpp 格式示例源代码

```csharp 
 
			 //文档目录的路径
			 string dataDir = "YOUR DOCUMENT DIRECTORY"; 
            
            Document doc = new Document(dataDir + "Rendering.docx");

            ImageSaveOptions saveOptions = new ImageSaveOptions(SaveFormat.Png)
            {
                PageSet = new PageSet(1),
                ImageColorMode = ImageColorMode.BlackAndWhite,
                PixelFormat = ImagePixelFormat.Format1bppIndexed
            };

            doc.Save(dataDir + "WorkingWithImageSaveOptions.Format1BppIndexed.Png", saveOptions);
            
        
```

### 结论

在本教程中，我们探索了 Aspose.Words for .NET 的 1Bpp 索引格式功能。我们学习了如何将文档中的图像格式化为 PNG 格式，颜色深度为每像素 1 位 (1 bpp) 和索引颜色模式。

当您想要获取颜色深度较低且文件大小较小的图像时，此功能非常有用。1Bpp 索引格式允许使用索引调色板来表示图像，这对于某些特定应用程序非常有用。

Aspose.Words for .NET 提供多种用于文档操作和生成的高级功能。1Bpp 索引格式是它为您提供的众多强大工具之一。