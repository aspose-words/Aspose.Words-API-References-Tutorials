---
title: 获取实际形状边界点
linktitle: 获取实际形状边界点
second_title: Aspose.Words 文档处理 API
description: 了解如何使用 Aspose.Words for .NET 检索 Word 文档中形状的实际边界（以点为单位，测量单位）。
type: docs
weight: 10
url: /zh/net/programming-with-shapes/get-actual-shape-bounds-points/
---

本教程介绍如何使用 Aspose.Words for .NET 检索 Word 文档中形状的实际边界（以点为单位）（测量单位）。边界表示文档中形状的大小和位置。

## 先决条件
要遵循本教程，您需要满足以下条件：

- 已安装 Aspose.Words for .NET 库。
- 具备 C# 和 Word 文档文字处理的基本知识。

## 步骤 1：创建新文档和 DocumentBuilder
创建一个新的实例`Document`类和一个`DocumentBuilder`对象来处理该文档。

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
```

## 步骤 2：插入图像形状
使用`InsertImage`方法`DocumentBuilder`对象将图像形状插入文档。提供图像文件的路径作为参数。

```csharp
Shape shape = builder.InsertImage(ImagesDir + "Transparent background logo.png");
shape.AspectRatioLocked = false;
```

## 步骤 3：检索实际形状边界点
访问形状的`ShapeRenderer`使用`GetShapeRenderer`方法。然后，使用`BoundsInPoints`财产。

```csharp
Console.Write("\nGets the actual bounds of the shape in points: ");
Console.WriteLine(shape.GetShapeRenderer().BoundsInPoints);
```


### 使用 Aspose.Words for .NET 获取实际形状边界点的示例源代码 

```csharp
	Document doc = new Document();
	DocumentBuilder builder = new DocumentBuilder(doc);
	Shape shape = builder.InsertImage(ImagesDir + "Transparent background logo.png");
	shape.AspectRatioLocked = false;
	Console.Write("\nGets the actual bounds of the shape in points: ");
	Console.WriteLine(shape.GetShapeRenderer().BoundsInPoints);
```

就是这样！您已成功使用 Aspose.Words for .NET 检索了 Word 文档中形状的实际边界（以点为单位）。