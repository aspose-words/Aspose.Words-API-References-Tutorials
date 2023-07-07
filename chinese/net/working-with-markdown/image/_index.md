---
title: 图像
linktitle: 图像
second_title: Aspose.Words for .NET API 参考
description: 了解如何使用 Aspose.Words for .NET 分步指南插入和自定义图像。
type: docs
weight: 10
url: /zh/net/working-with-markdown/image/
---

在此示例中，我们将解释如何通过 Aspose.Words for .NET 使用图像功能。图片允许您将插图和图形插入文档中。

## 第 1 步：使用文档生成器

首先，我们将使用文档生成器将内容添加到文档中。

```csharp
DocumentBuilder builder = new DocumentBuilder();
```

## 第 2 步：插入图像

我们可以使用插入图像`Shape`类并指定图像的类型，在这里`ShapeType.Image`。我们还将图像的环绕类型设置为`WrapType.Inline`.

```csharp
Shape shape = new Shape(builder.Document, ShapeType.Image);
shape. WrapType = WrapType. Inline;
```

## 第3步：图像定制

我们通过指定其完整路径来自定义图像，例如`"/attachment/1456/pic001.png"`，并为图像添加标题。

```csharp
shape.ImageData.SourceFullName = "/attachment/1456/pic001.png";
shape.ImageData.Title = "Title";
```

### 使用 Aspose.Words for .NET 的图像示例源代码

```csharp
//使用文档生成器将内容添加到文档中。
DocumentBuilder builder = new DocumentBuilder();

//插入图像。
Shape shape = new Shape(builder.Document, ShapeType.Image);
shape.WrapType = WrapType.Inline;
shape.ImageData.SourceFullName = "/attachment/1456/pic001.png";
shape.ImageData.Title = "title";
builder.InsertNode(shape);
```

恭喜！您现在已经了解了如何使用 Aspose.Words for .NET 的图像功能。


### 常见问题解答

#### 问：如何将本地文件中的图像插入到 Aspose.Words 中？

答：要将本地文件中的图像插入到 Aspose.Words 中，您可以使用`Shape`类和`InsertImage`方法。

#### 问：我可以在 Aspose.Words 中插入来自 URL 的图像吗？

答：是的，您可以在 Aspose.Words 中插入来自 URL 的图像。您可以使用相同的`InsertImage`方法并指定图像 URL 而不是本地文件路径。

#### 问：如何在 Aspose.Words 中调整图像大小？

答：要在 Aspose.Words 中调整图像大小，您可以使用`Width`和`Height`的属性`Shape`目的。

#### 问：我可以在 Aspose.Words 中对图像应用滤镜吗？

答：是的，您可以在 Aspose.Words 中对图像应用滤镜。例如，您可以使用以下命令将模糊滤镜应用于图像`ApplyGaussianBlur`的方法`Shape`目的。

#### 问：如何在 Aspose.Words 中将一张图像替换为另一张图像？

答：要在 Aspose.Words 中将一张图像替换为另一张图像，您可以使用`Replace`的方法`Shape`班级。该方法将`Shape`要替换的图像的对象和`Shape`新图像的对象。