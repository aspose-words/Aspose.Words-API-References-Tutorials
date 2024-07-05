---
title: 添加组形状
linktitle: 添加组形状
second_title: Aspose.Words 文档处理 API
description: 了解如何使用 Aspose.Words for .NET 将具有多个形状的组形状添加到 Word 文档。
type: docs
weight: 10
url: /zh/net/programming-with-shapes/add-group-shape/
---

本教程介绍如何使用 Aspose.Words for .NET 将包含多个形状的组形状添加到 Word 文档。组形状允许您将多个形状组合并作为单个实体进行操作。

## 先决条件
要遵循本教程，您需要满足以下条件：

- 已安装 Aspose.Words for .NET 库。
- 具备 C# 和 Word 文档文字处理的基本知识。

## 步骤 1：设置文档目录
首先设置文档目录的路径。替换`"YOUR DOCUMENT DIRECTORY"`替换为您想要保存文档的目录的实际路径。

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## 步骤 2：创建新文档和 GroupShape
创建一个新的实例`Document`类和`GroupShape`对象来处理该文档。

```csharp
Document doc = new Document();
doc.EnsureMinimum();
GroupShape groupShape = new GroupShape(doc);
```

## 步骤 3：创建形状并将其添加到 GroupShape
创建单独的形状，例如`accentBorderShape`和`actionButtonShape`使用`Shape`类。根据需要自定义其属性。将这些形状附加到`groupShape`目的。

```csharp
Shape accentBorderShape = new Shape(doc, ShapeType.AccentBorderCallout1) { Width = 100, Height = 100 };
groupShape.AppendChild(accentBorderShape);

Shape actionButtonShape = new Shape(doc, ShapeType.ActionButtonBeginning)
{
    Left = 100,
    Width = 100,
    Height = 200
};
groupShape.AppendChild(actionButtonShape);
```

## 步骤 4：设置 GroupShape 的尺寸
设置宽度、高度和坐标大小`groupShape`.

```csharp
groupShape.Width = 200;
groupShape.Height = 200;
groupShape.CoordSize = new Size(200, 200);
```

## 步骤 5：将 GroupShape 插入文档
创建一个`DocumentBuilder`对象并插入`groupShape`使用`InsertNode`方法。

```csharp
DocumentBuilder builder = new DocumentBuilder(doc);
builder.InsertNode(groupShape);
```

## 步骤 6：保存文档
使用将文档保存到指定目录`Save`方法。提供所需的文件名和适当的文件扩展名。在此示例中，我们将文档保存为“WorkingWithShapes.AddGroupShape.docx”。

```csharp
doc.Save(dataDir + "WorkingWithShapes.AddGroupShape.docx");
```

### 使用 Aspose.Words for .NET 添加组形状的示例源代码 

```csharp
	//文档目录的路径
	string dataDir = "YOUR DOCUMENT DIRECTORY";

	Document doc = new Document();
	doc.EnsureMinimum();
	GroupShape groupShape = new GroupShape(doc);
	Shape accentBorderShape = new Shape(doc, ShapeType.AccentBorderCallout1) { Width = 100, Height = 100 };
	groupShape.AppendChild(accentBorderShape);
	Shape actionButtonShape = new Shape(doc, ShapeType.ActionButtonBeginning)
	{
		Left = 100, Width = 100, Height = 200
	};
	groupShape.AppendChild(actionButtonShape);
	groupShape.Width = 200;
	groupShape.Height = 200;
	groupShape.CoordSize = new Size(200, 200);
	DocumentBuilder builder = new DocumentBuilder(doc);
	builder.InsertNode(groupShape);
	doc.Save(dataDir + "WorkingWithShapes.AddGroupShape.docx");
```

就这样！您已成功使用 Aspose.W 将包含多个形状的组形状添加到 Word 文档中