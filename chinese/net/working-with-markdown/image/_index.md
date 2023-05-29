---
title: 图像
linktitle: 图像
second_title: Aspose.Words for .NET API 参考
description: 了解如何使用 Aspose.Words for .NET 分步指南插入和自定义图像。
type: docs
weight: 10
url: /zh/net/working-with-markdown/image/
---

在这个例子中，我们将解释如何使用 Aspose.Words for .NET 的图像功能。图片允许您将插图和图形插入到文档中。

## 第 1 步：使用文档生成器

首先，我们将使用文档生成器将内容添加到我们的文档中。

```csharp
DocumentBuilder builder = new DocumentBuilder();
```

## 第 2 步：插入图像

我们可以使用插入图像`Shape`类并指定图像的类型，在这里`ShapeType.Image`.我们还将图像的环绕类型设置为`WrapType.Inline`.

```csharp
Shape shape = new Shape(builder.Document, ShapeType.Image);
shape. WrapType = WrapType. Inline;
```

## 第 3 步：图像定制

我们通过指定其完整路径来自定义图像，例如`"/attachment/1456/pic001.png"`并为图像添加标题。

```csharp
shape.ImageData.SourceFullName = "/attachment/1456/pic001.png";
shape.ImageData.Title = "Title";
```

### 使用 Aspose.Words for .NET 的图像示例源代码

```csharp
//使用文档生成器向文档添加内容。
DocumentBuilder builder = new DocumentBuilder();

//插入图像。
Shape shape = new Shape(builder.Document, ShapeType.Image);
shape.WrapType = WrapType.Inline;
shape.ImageData.SourceFullName = "/attachment/1456/pic001.png";
shape.ImageData.Title = "title";
builder.InsertNode(shape);
```

恭喜！您现在已经了解了如何使用 Aspose.Words for .NET 的图像功能。

