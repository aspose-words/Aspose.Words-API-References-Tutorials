---
title: 页面保存回调
linktitle: 页面保存回调
second_title: Aspose.Words for .NET API 参考
description: 了解如何使用 Aspose.Words for .NET 自定义将文档页面保存为图像。
type: docs
weight: 10
url: /zh/net/programming-with-imagesaveoptions/page-saving-callback/
---

在本教程中，我们将探索为将页面保存回调与 .NET 的 Aspose.Words 图像保存选项一起使用而提供的 C# 源代码。此功能允许您在将文档的每一页另存为图像时执行自定义操作。

## 第 1 步：设置环境

在您开始之前，请确保您已经使用 Aspose.Words for .NET 设置了您的开发环境。确保您已经添加了必要的引用并导入了适当的命名空间。

## 第 2 步：装入文档

```csharp
//文档目录的路径
string dataDir = "YOUR DOCUMENTS DIRECTORY";

Document doc = new Document(dataDir + "Rendering.docx");
```

在此步骤中，我们使用`Document`方法并将路径传递给要加载的 DOCX 文件。

## 第 3 步：配置映像备份选项

```csharp
ImageSaveOptions imageSaveOptions = new ImageSaveOptions(SaveFormat.Png)
{
     PageSet = new PageSet(new PageRange(0, doc.PageCount - 1)),
     PageSavingCallback = new HandlePageSavingCallback()
};
```

在此步骤中，我们通过创建一个新的`ImageSaveOptions`目的。我们指定所需的备份格式，此处为 PNG 格式的“Png”。我们用`PageSet`指定要保存的页面范围，这里是从文档的第一页到最后一页 (`doc.PageCount - 1`).我们还设置`PageSavingCallback`到一个实例`HandlePageSavingCallback`，这是一个自定义类来处理页面保存回调。

## 第 4 步：实现保存页面回调

```csharp
public class HandlePageSavingCallback : IPageSavingCallback
{
     public void PageSaving(PageSavingArgs args)
     {
         //在这里实施您的自定义操作
         //您可以通过“args.PageIndex”属性访问页面信息
         //您还可以单独更改每个页面的保存选项
     }
}
```

在这一步中，我们实现`HandlePageSavingCallback`实现的类`IPageSavingCallback`界面。您可以通过在`PageSaving`方法。您可以通过`args.PageIndex`的财产`PageSavingArgs`作为参数传递的对象。

## 第 5 步：将页面另存为图像

```csharp
doc.Save(dataDir + "WorkingWithImageSaveOptions.PageSavingCallback.png", imageSaveOptions);
```

在这最后一步中，我们使用`Save`方法并将路径传递给输出文件`.png`扩展名，以及指定的保存选项。

现在您可以运行源代码以在将文档的每一页另存为图像时执行自定义操作。生成的文件将保存在指定目录中，名称为“WorkingWithImageSaveOptions.PageSavingCallback.png”。

### 使用 Aspose.Words for .NET 的页面保存回调示例源代码


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

在本教程中，我们使用 .NET 的 Aspose.Words 图像保存选项探索了页面保存回调功能。我们学习了如何在将文档的每一页保存为图像时执行自定义操作。

当您希望在转换为图像时对每个页面执行特定操作时，此功能很有用。您可以访问页面信息并使用它来自定义备份选项或执行其他特定于页面的处理。

Aspose.Words for .NET 为文档操作和生成提供了广泛的高级功能。保存页面提醒是众多强大的工具之一，它使您可以自定义将页面保存为图像的过程。