---
title: 图像
linktitle: 图像
second_title: Aspose.Words 文档处理 API
description: 了解如何使用 Aspose.Words for .NET 分步指南插入和自定义图像。
type: docs
weight: 10
url: /zh/net/working-with-markdown/image/
---

在此示例中，我们将解释如何使用 Aspose.Words for .NET 的图像功能。图片允许您将插图和图形插入文档。

## 步骤 1：使用文档生成器

首先，我们将使用文档生成器向文档添加内容。

```csharp
DocumentBuilder builder = new DocumentBuilder();
```

## 第 2 步：插入图片

我们可以使用`Shape`类并指定图像的类型，这里`ShapeType.Image`。我们还将图像的环绕类型设置为`WrapType.Inline`.

```csharp
Shape shape = new Shape(builder.Document, ShapeType.Image);
shape. WrapType = WrapType. Inline;
```

## 步骤 3：图像自定义

我们通过指定其完整路径来定制图像，例如`"/attachment/1456/pic001.png"`，并为图像添加标题。

```csharp
shape.ImageData.SourceFullName = "/attachment/1456/pic001.png";
shape.ImageData.Title = "Title";
```

### 使用 Aspose.Words for .NET 的图像示例源代码

```csharp
//使用文档生成器向文档添加内容。
DocumentBuilder builder = new DocumentBuilder();

//插入图片。
Shape shape = new Shape(builder.Document, ShapeType.Image);
shape.WrapType = WrapType.Inline;
shape.ImageData.SourceFullName = "/attachment/1456/pic001.png";
shape.ImageData.Title = "title";
builder.InsertNode(shape);
```

恭喜！现在您已经了解了如何使用 Aspose.Words for .NET 的图像功能。


### 常见问题解答

#### 问：如何将本地文件中的图像插入 Aspose.Words？

答：要将本地文件中的图像插入 Aspose.Words，您可以使用`Shape`类和`InsertImage`方法。

#### 问：我可以从 Aspose.Words 中的 URL 插入图像吗？

答：是的，您可以在 Aspose.Words 中从 URL 插入图像。您可以使用相同的`InsertImage`方法并指定图像URL而不是本地文件路径。

#### 问：如何在 Aspose.Words 中调整图像大小？

答：要在 Aspose.Words 中调整图像大小，您可以使用`Width`和`Height`的属性`Shape`目的。

#### 问：我可以在 Aspose.Words 中对图像应用过滤器吗？

答：是的，您可以在 Aspose.Words 中将滤镜应用于图像。例如，您可以使用`ApplyGaussianBlur`方法`Shape`目的。

#### 问：如何在 Aspose.Words 中用另一幅图像替换一幅图像？

答：要在 Aspose.Words 中将一个图像替换为另一个图像，您可以使用`Replace`方法`Shape`类。此方法将作为参数`Shape`要替换的图像的对象和`Shape`新图像的对象。