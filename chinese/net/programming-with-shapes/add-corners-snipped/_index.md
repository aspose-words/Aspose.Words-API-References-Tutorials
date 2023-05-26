---
title: 添加剪角
linktitle: 添加剪角
second_title: Aspose.Words for .NET API 参考
description: 了解如何使用 Aspose.Words for .NET 将带角的形状添加到 Word 文档。
type: docs
weight: 10
url: /zh/net/programming-with-shapes/add-corners-snipped/
---

本教程解释了如何使用 Aspose.Words for .NET 将带角的形状添加到 Word 文档中。角剪断的形状可以使用自定义和插入`InsertShape`方法。

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

## 第 3 步：插入角剪断形状
使用`InsertShape`的方法`DocumentBuilder`对象以插入带有被剪断角的形状。指定形状类型（在本例中，`ShapeType.TopCornersSnipped`) 并为形状提供所需的大小。

```csharp
builder.InsertShape(ShapeType.TopCornersSnipped, 50, 50);
```

## 第 4 步：保存文档
使用 将文档保存到指定目录`Save`方法。提供具有适当文件扩展名的所需文件名。在本例中，我们将文档保存为“WorkingWithShapes.AddCornersSnipped.docx”。

```csharp
OoxmlSaveOptions saveOptions = new OoxmlSaveOptions(SaveFormat.Docx)
{
    Compliance = OoxmlCompliance.Iso29500_2008_Transitional
};
doc.Save(dataDir + "WorkingWithShapes.AddCornersSnipped.docx", saveOptions);
```

### 使用 Aspose.Words for .NET 的 Add Corners Snipped 示例源代码 

```csharp
	//文档目录的路径
	string dataDir = "YOUR DOCUMENT DIRECTORY";

	Document doc = new Document();
	DocumentBuilder builder = new DocumentBuilder(doc);
	builder.InsertShape(ShapeType.TopCornersSnipped, 50, 50);
	OoxmlSaveOptions saveOptions = new OoxmlSaveOptions(SaveFormat.Docx)
	{
		Compliance = OoxmlCompliance.Iso29500_2008_Transitional
	};
	doc.Save(dataDir + "WorkingWithShapes.AddCornersSnipped.docx", saveOptions);

```

就是这样！您已经使用 Aspose.Words for .NET 成功地向您的 Word 文档添加了一个角剪断形状。