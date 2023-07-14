---
title: 格式 1Bpp 索引
linktitle: 格式 1Bpp 索引
second_title: Aspose.Words 文档处理 API
description: 了解如何格式化使用 Aspose.Words for .NET 索引的 1 bpp 图像。低颜色深度图像的完整教程。
type: docs
weight: 10
url: /zh/net/programming-with-imagesaveoptions/format-1bpp-indexed/
---
在本教程中，我们将探索为 Aspose.Words for .NET 的“Format 1Bpp Indexed”功能提供的 C# 源代码。此功能允许您将文档中的图像格式化为 PNG 格式，颜色深度为每像素 1 位 (1 bpp)，并采用索引颜色模式。

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
ImageSaveOptions saveOptions = new ImageSaveOptions(SaveFormat.Png)
{
     PageSet = new PageSet(1),
     ImageColorMode = ImageColorMode.BlackAndWhite,
     PixelFormat = ImagePixelFormat.Format1bppIndexed
};
```

在此步骤中，我们配置图像的备份选项。我们创建一个新的`ImageSaveOptions`对象指定所需的保存格式，此处“Png”表示 PNG 格式。我们还定义了要包含在图像中的页面、黑白颜色模式和索引 1 bpp 像素格式。

## 第 4 步：备份图像

```csharp
doc.Save(dataDir + "WorkingWithImageSaveOptions.Format1BppIndexed.Png", saveOptions);
```

在最后一步中，我们使用以下命令将文档图像保存为 PNG 格式`Save`方法并将路径传递到输出文件以及指定的保存选项。

现在，您可以运行源代码以将文档图像格式化为 PNG 格式，索引颜色深度为 1 bpp。生成的文件将保存在指定目录中，名称为“WorkingWithImageSaveOptions.Format1BppIndexed.Png”。

### 使用 Aspose.Words for .NET 进行索引的格式 1Bpp 的示例源代码

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

在本教程中，我们探索了 Aspose.Words for .NET 的 1Bpp 索引格式功能。我们学习了如何以每像素 1 位 (1 bpp) 的颜色深度和索引颜色模式对 PNG 格式的文档中的图像进行格式化。

当您想要获取低颜色深度和小文件大小的图像时，此功能非常有用。 1Bpp 索引格式允许使用索引调色板来表示图像，这对于某些特定应用程序可能是有益的。

Aspose.Words for .NET 为文档操作和生成提供了广泛的高级功能。 1Bpp 索引格式是您可以使用的众多强大工具之一。