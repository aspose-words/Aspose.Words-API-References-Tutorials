---
title: 页面保存回调
linktitle: 页面保存回调
second_title: Aspose.Words 文档处理 API
description: 了解如何使用 Aspose.Words for .NET 自定义将文档页面保存为图像。
type: docs
weight: 10
url: /zh/net/programming-with-imagesaveoptions/page-saving-callback/
---

在本教程中，我们将探索提供的 C# 源代码，以便将页面保存回调与适用于 .NET 的 Aspose.Words 图像保存选项结合使用。此功能允许您在将文档的每一页保存为图像时执行自定义操作。

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
ImageSaveOptions imageSaveOptions = new ImageSaveOptions(SaveFormat.Png)
{
     PageSet = new PageSet(new PageRange(0, doc.PageCount - 1)),
     PageSavingCallback = new HandlePageSavingCallback()
};
```

在此步骤中，我们通过创建新的图像来配置图像保存选项`ImageSaveOptions`目的。我们指定所需的备份格式，此处“Png”为PNG 格式。我们用`PageSet`指定要保存的页面范围，这里是从文档的第一页到最后一页（`doc.PageCount - 1`）。我们还设置了`PageSavingCallback`到一个实例`HandlePageSavingCallback`，这是一个处理页面保存回调的自定义类。

## 第四步：实现保存页面回调

```csharp
public class HandlePageSavingCallback : IPageSavingCallback
{
     public void PageSaving(PageSavingArgs args)
     {
         //在此实施您的自定义操作
         //您可以通过“args.PageIndex”属性访问页面信息
         //您还可以单独更改每个页面的保存选项。
     }
}
```

在这一步中，我们实现`HandlePageSavingCallback`实现的类`IPageSavingCallback`界面。您可以通过在中添加您的特定操作来自定义此类`PageSaving`方法。您可以通过以下方式访问页面信息`args.PageIndex`的财产`PageSavingArgs`作为参数传递的对象。

## 步骤 5：将页面另存为图像

```csharp
doc.Save(dataDir + "WorkingWithImageSaveOptions.PageSavingCallback.png", imageSaveOptions);
```

在最后一步中，我们使用以下命令将文档的每一页保存为图像：`Save`方法并将路径传递给输出文件`.png`扩展名以及指定的保存选项。

现在，您可以运行源代码以在将文档的每一页保存为图像时执行自定义操作。生成的文件将保存在指定目录中，名称为“WorkingWithImageSaveOptions.PageSavingCallback.png”。

### 使用 Aspose.Words for .NET 进行页面保存回调的示例源代码


```csharp 
//文档目录的路径
string dataDir = "YOUR DOCUMENT DIRECTORY"; 


Document doc = new Document(dataDir + "Rendering.docx");

ImageSaveOptions imageSaveOptions = new ImageSaveOptions(SaveFormat.Png)
{
	PageSet = new PageSet(new PageRange(0, doc.PageCount - 1)),
	PageSavingCallback = new HandlePageSavingCallback()
};

doc.Save(dataDir + "WorkingWithImageSaveOptions.PageSavingCallback.png", imageSaveOptions);
        
```

## 结论

在本教程中，我们探索了 .NET 的 Aspose.Words 图像保存选项的页面保存回调功能。我们学习了如何在将文档的每一页保存为图像时执行自定义操作。

当您想要在转换为图像时对每个页面执行特定操作时，此功能非常有用。您可以访问页面信息并使用它来自定义备份选项或执行其他特定于页面的处理。

Aspose.Words for .NET 提供了广泛的文档操作和生成高级功能。保存页面提醒是众多功能强大的工具之一，它使您可以自定义将页面保存到图像的过程。