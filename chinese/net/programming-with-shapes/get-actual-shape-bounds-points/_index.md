---
title: 获取实际形状边界点
linktitle: 获取实际形状边界点
second_title: Aspose.Words for .NET API 参考
description: 了解如何使用 Aspose.Words for .NET 在 Word 文档中以点（测量单位）检索形状的实际边界。
type: docs
weight: 10
url: /zh/net/programming-with-shapes/get-actual-shape-bounds-points/
---

本教程解释了如何使用 Aspose.Words for .NET 在 Word 文档中以点（测量单位）检索形状的实际边界。边界表示文档中形状的大小和位置。

## 先决条件
要学习本教程，您需要具备以下条件：

- 安装了 Aspose.Words for .NET 库。
- C# 的基本知识和使用 Word 文档。

## 第 1 步：创建新文档和 DocumentBuilder
创建一个新的实例`Document`类和一个`DocumentBuilder`对象来处理文档。

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
```

## 第 2 步：插入图像形状
使用`InsertImage`的方法`DocumentBuilder`对象将图像形状插入到文档中。提供图像文件的路径作为参数。

```csharp
Shape shape = builder.InsertImage(ImagesDir + "Transparent background logo.png");
shape.AspectRatioLocked = false;
```

## 第 3 步：检索实际形状边界点
访问形状的`ShapeRenderer`使用`GetShapeRenderer`方法。然后，使用点检索形状的实际边界`BoundsInPoints`财产。

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

就是这样！您已经使用 Aspose.Words for .NET 成功地检索了 Word 文档中形状的实际边界（以点为单位）。