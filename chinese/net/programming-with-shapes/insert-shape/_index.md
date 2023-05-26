---
title: 插入形状
linktitle: 插入形状
second_title: Aspose.Words for .NET API 参考
description: 了解如何使用 Aspose.Words for .NET 将形状插入 Word 文档。
type: docs
weight: 10
url: /zh/net/programming-with-shapes/insert-shape/
---

本教程解释了如何使用 Aspose.Words for .NET 将形状插入到 Word 文档中。形状可用于增强文档的视觉外观和布局。

## 先决条件
要学习本教程，您需要具备以下条件：

- 安装了 Aspose.Words for .NET 库。
- C# 的基本知识和使用 Word 文档。

## 第 1 步：设置文档目录
首先设置文档目录的路径。代替`"YOUR DOCUMENT DIRECTORY"`使用要保存文档的目录的实际路径。

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## 第 2 步：创建新文档和 DocumentBuilder
创建一个新的实例`Document`类和一个`DocumentBuilder`对象来处理文档。

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
```

## 第 3 步：插入形状
使用`InsertShape`的方法`DocumentBuilder`对象将形状插入到文档中。指定形状类型、相对水平和垂直位置、页面尺寸、大小和环绕类型。如果需要，您还可以设置形状的旋转角度。

```csharp
Shape shape = builder.InsertShape(ShapeType.TextBox, RelativeHorizontalPosition.Page, 100,
	RelativeVerticalPosition.Page, 100, 50, 50, WrapType.None);
shape.Rotation = 30.0;
builder.Writeln();
shape = builder.InsertShape(ShapeType.TextBox, 50, 50);
shape.Rotation = 30.0;
```

## 第 4 步：保存文档
使用 将文档保存到指定目录`Save`方法。提供具有适当文件扩展名的所需文件名。在本例中，我们将文档保存为“WorkingWithShapes.InsertShape.docx”。

```csharp
OoxmlSaveOptions saveOptions = new OoxmlSaveOptions(SaveFormat.Docx)
{
	Compliance = OoxmlCompliance.Iso29500_2008_Transitional
};
doc.Save(dataDir + "WorkingWithShapes.InsertShape.docx", saveOptions);
```

### 使用 Aspose.Words for .NET 插入形状的示例源代码 

```csharp
	//文档目录的路径
	string dataDir = "YOUR DOCUMENT DIRECTORY";

	Document doc = new Document();
	DocumentBuilder builder = new DocumentBuilder(doc);
	Shape shape = builder.InsertShape(ShapeType.TextBox, RelativeHorizontalPosition.Page, 100,
		RelativeVerticalPosition.Page, 100, 50, 50, WrapType.None);
	shape.Rotation = 30.0;
	builder.Writeln();
	shape = builder.InsertShape(ShapeType.TextBox, 50, 50);
	shape.Rotation = 30.0;
	OoxmlSaveOptions saveOptions = new OoxmlSaveOptions(SaveFormat.Docx)
	{
		Compliance = OoxmlCompliance.Iso29500_2008_Transitional
	};
	doc.Save(dataDir + "WorkingWithShapes.InsertShape.docx", saveOptions);
```

就是这样！您已经使用 Aspose.Words for .NET 成功地将形状插入到您的 Word 文档中。