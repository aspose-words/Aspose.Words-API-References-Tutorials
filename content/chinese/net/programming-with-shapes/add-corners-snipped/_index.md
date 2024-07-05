---
title: 添加角剪断
linktitle: 添加角剪断
second_title: Aspose.Words 文档处理 API
description: 了解如何使用 Aspose.Words for .NET 将带有角剪切的形状添加到 Word 文档。
type: docs
weight: 10
url: /zh/net/programming-with-shapes/add-corners-snipped/
---

本教程介绍如何使用 Aspose.Words for .NET 将带角剪裁的形状添加到 Word 文档。可以使用`InsertShape`方法。

## 先决条件
要遵循本教程，您需要满足以下条件：

- 已安装 Aspose.Words for .NET 库。
- 具备 C# 和 Word 文档文字处理的基本知识。

## 步骤 1：设置文档目录
首先设置文档目录的路径。替换`"YOUR DOCUMENT DIRECTORY"`替换为您想要保存文档的目录的实际路径。

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## 步骤 2：创建新文档和 DocumentBuilder
创建一个新的实例`Document`类和一个`DocumentBuilder`对象来处理该文档。

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
```

## 步骤 3：插入角剪断形状
使用`InsertShape`方法`DocumentBuilder`对象以插入带有角剪断的形状。指定形状类型（在本例中为`ShapeType.TopCornersSnipped`并提供形状所需的尺寸。

```csharp
builder.InsertShape(ShapeType.TopCornersSnipped, 50, 50);
```

## 步骤 4：保存文档
使用将文档保存到指定目录`Save`方法。提供所需的文件名和适当的文件扩展名。在此示例中，我们将文档保存为“WorkingWithShapes.AddCornersSnipped.docx”。

```csharp
OoxmlSaveOptions saveOptions = new OoxmlSaveOptions(SaveFormat.Docx)
{
    Compliance = OoxmlCompliance.Iso29500_2008_Transitional
};
doc.Save(dataDir + "WorkingWithShapes.AddCornersSnipped.docx", saveOptions);
```

### 使用 Aspose.Words for .NET 添加 Corners Snipped 的示例源代码 

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

就是这样！您已成功使用 Aspose.Words for .NET 将角落剪切形状添加到 Word 文档中。