---
title: 宽高比锁定
linktitle: 宽高比锁定
second_title: Aspose.Words 文档处理 API
description: 了解如何使用 Aspose.Words for .NET 锁定或解锁 Word 文档中形状的长宽比。
type: docs
weight: 10
url: /zh/net/programming-with-shapes/aspect-ratio-locked/
---

本教程介绍如何使用 Aspose.Words for .NET 锁定或解锁 Word 文档中形状的长宽比。通过锁定纵横比，您可以在调整形状大小时保持形状的原始比例。

## 先决条件
要学习本教程，您需要具备以下条件：

- 已安装 Aspose.Words for .NET 库。
- C# 和 Word 文档文字处理的基础知识。

## 第 1 步：设置文档目录
首先设置文档目录的路径。代替`"YOUR DOCUMENT DIRECTORY"`与要保存文档的目录的实际路径。

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## 第 2 步：创建新文档和 DocumentBuilder
创建一个新实例`Document`类和一个`DocumentBuilder`对象使用该文档。

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
```

## 第 3 步：插入图像形状
使用`InsertImage`的方法`DocumentBuilder`对象将图像形状插入到文档中。提供图像文件的路径作为参数。

```csharp
Shape shape = builder.InsertImage(ImagesDir + "Transparent background logo.png");
```

## 步骤 4：锁定或解锁宽高比
设置`AspectRatioLocked`形状的属性为`true`或者`false`分别锁定或解锁宽高比。

```csharp
shape.AspectRatioLocked = false; //解锁宽高比
```

## 第 5 步：保存文档
使用以下命令将文档保存到指定目录`Save`方法。提供所需的文件名和适当的文件扩展名。在此示例中，我们将文档另存为“WorkingWithShapes.AspectRatioLocked.docx”。

```csharp
doc.Save(dataDir + "WorkingWithShapes.AspectRatioLocked.docx");
```

### 使用 Aspose.Words for .NET 锁定宽高比的示例源代码 

```csharp
	//文档目录的路径
	string dataDir = "YOUR DOCUMENT DIRECTORY";

	Document doc = new Document();
	DocumentBuilder builder = new DocumentBuilder(doc);
	Shape shape = builder.InsertImage(ImagesDir + "Transparent background logo.png");
	shape.AspectRatioLocked = false;
	doc.Save(dataDir + "WorkingWithShapes.AspectRatioLocked.docx");
```

就是这样！您已使用 Aspose.Words for .NET 成功锁定或解锁 Word 文档中形状的长宽比。