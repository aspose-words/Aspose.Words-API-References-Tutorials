---
title: 添加剪掉的角
linktitle: 添加剪掉的角
second_title: Aspose.Words 文档处理 API
description: 了解如何使用 Aspose.Words for .NET 将带剪角的形状添加到 Word 文档中。
type: docs
weight: 10
url: /zh/net/programming-with-shapes/add-corners-snipped/
---

本教程介绍如何使用 Aspose.Words for .NET 将带剪角的形状添加到 Word 文档中。可以使用以下命令自定义和插入角剪断形状`InsertShape`方法。

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

## 第三步：插入剪角形状
使用`InsertShape`的方法`DocumentBuilder`对象插入一个带有剪角的形状。指定形状类型（在本例中，`ShapeType.TopCornersSnipped`）并提供所需的形状尺寸。

```csharp
builder.InsertShape(ShapeType.TopCornersSnipped, 50, 50);
```

## 步骤 4：保存文档
使用以下命令将文档保存到指定目录`Save`方法。提供所需的文件名和适当的文件扩展名。在此示例中，我们将文档另存为“WorkingWithShapes.AddCornersSnipped.docx”。

```csharp
OoxmlSaveOptions saveOptions = new OoxmlSaveOptions(SaveFormat.Docx)
{
    Compliance = OoxmlCompliance.Iso29500_2008_Transitional
};
doc.Save(dataDir + "WorkingWithShapes.AddCornersSnipped.docx", saveOptions);
```

### 使用 Aspose.Words for .NET 添加角点片段的示例源代码 

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

就是这样！您已使用 Aspose.Words for .NET 成功将剪角形状添加到 Word 文档中。