---
title: 添加组形状
linktitle: 添加组形状
second_title: Aspose.Words for .NET API 参考
description: 了解如何使用 Aspose.Words for .NET 将具有多个形状的组形状添加到 Word 文档。
type: docs
weight: 10
url: /zh/net/programming-with-shapes/add-group-shape/
---

本教程介绍如何使用 Aspose.Words for .NET 将包含多个形状的组形状添加到 Word 文档。组形状允许您将多个形状组合和操作为一个实体。

## 先决条件
要学习本教程，您需要具备以下条件：

- 安装了 Aspose.Words for .NET 库。
- C# 的基本知识和使用 Word 文档。

## 第 1 步：设置文档目录
首先设置文档目录的路径。代替`"YOUR DOCUMENT DIRECTORY"`使用要保存文档的目录的实际路径。

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## 第 2 步：创建新文档和 GroupShape
创建一个新的实例`Document`类和`GroupShape`对象来处理文档。

```csharp
Document doc = new Document();
doc.EnsureMinimum();
GroupShape groupShape = new GroupShape(doc);
```

## 第 3 步：创建形状并将其添加到 GroupShape
创建单独的形状，例如`accentBorderShape`和`actionButtonShape`使用`Shape`班级。根据需要自定义它们的属性。将这些形状附加到`groupShape`目的。

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

## 第 4 步：设置 GroupShape 的维度
设置宽度、高度和坐标大小`groupShape`.

```csharp
groupShape.Width = 200;
groupShape.Height = 200;
groupShape.CoordSize = new Size(200, 200);
```

## 第 5 步：将 GroupShape 插入到文档中
创建一个`DocumentBuilder`对象并插入`groupShape`使用`InsertNode`方法。

```csharp
DocumentBuilder builder = new DocumentBuilder(doc);
builder.InsertNode(groupShape);
```

## 第 6 步：保存文档
使用 将文档保存到指定目录`Save`方法。提供具有适当文件扩展名的所需文件名。在本例中，我们将文档保存为“WorkingWithShapes.AddGroupShape.docx”。

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

就是这样！您已使用 Aspose.W 成功地将包含多个形状的组形状添加到您的 Word 文档中