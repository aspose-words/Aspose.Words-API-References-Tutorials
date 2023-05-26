---
title: 形状修正
linktitle: 形状修正
second_title: Aspose.Words for .NET API 参考
description: 使用 Aspose.Words for .NET 修改 Word 文档中的形状。
type: docs
weight: 10
url: /zh/net/working-with-revisions/shape-revision/
---

在本分步指南中，我们将向您介绍如何使用 Aspose.Words for .NET 修改 Word 文档中的形状。我们将为您提供完整的源代码，并向您展示如何格式化降价输出。

## 第 1 步：创建文档并添加形状

第一步是创建一个新文档并添加形状。

```csharp
Document doc = new Document();
Assert.False(doc.TrackRevisions);

Shape shape = new Shape(doc, ShapeType.Cube);
shape. WrapType = WrapType. Inline;
shape. Width = 100.0;
shape. Height = 100.0;
doc.FirstSection.Body.FirstParagraph.AppendChild(shape);
```

## 第 2 步：跟踪修改并添加另一个形状

我们将打开修订跟踪并添加另一个形状。

```csharp
doc.StartTrackRevisions("John Doe");

shape = new Shape(doc, ShapeType.Sun);
shape. WrapType = WrapType. Inline;
shape. Width = 100.0;
shape. Height = 100.0;
doc.FirstSection.Body.FirstParagraph.AppendChild(shape);
```

## 第 3 步：获取形状集合并检查修订

我们将从文档中获取形状集合并检查与每个形状关联的修订。

```csharp
List<Shape> shapes = doc.GetChildNodes(NodeType.Shape, true).Cast<Shape>().ToList();
Assert.AreEqual(2, shapes.Count);

Assert.AreEqual(ShapeType.Cube, shapes[0].ShapeType);
Assert.True(shapes[0].IsDeleteRevision);

Assert.AreEqual(ShapeType.Sun, shapes[1].ShapeType);
Assert.True(shapes[1].IsInsertRevision);
```

## 第 4 步：检查形状移动修订

我们将加载包含形状位移修订的现有文档并检查相关修订。

```csharp
doc = new Document(MyDir + "Revision shape.docx");

shapes = doc.GetChildNodes(NodeType.Shape, true).Cast<Shape>().ToList();
Assert.AreEqual(2, shapes.Count);

Assert. False(shapes[0].IsMoveFromRevision);
Assert.True(shapes[0].IsMoveToRevision);

Assert.True(shapes[1].IsMoveFromRevision);
Assert. False(shapes[1].IsMoveToRevision);
```

### 使用 Aspose.Words for .NET 的 Shape Revision 示例源代码

以下是使用 Aspose.Words for .NET 对文档中的形状进行修改的完整源代码：

```csharp

	Document doc = new Document();

	//插入内联形状而不跟踪修订。
	Assert.False(doc.TrackRevisions);
	Shape shape = new Shape(doc, ShapeType.Cube);
	shape.WrapType = WrapType.Inline;
	shape.Width = 100.0;
	shape.Height = 100.0;
	doc.FirstSection.Body.FirstParagraph.AppendChild(shape);

	//开始跟踪修订，然后插入另一个形状。
	doc.StartTrackRevisions("John Doe");
	shape = new Shape(doc, ShapeType.Sun);
	shape.WrapType = WrapType.Inline;
	shape.Width = 100.0;
	shape.Height = 100.0;
	doc.FirstSection.Body.FirstParagraph.AppendChild(shape);

	//获取文档的形状集合，其中仅包含我们添加的两个形状。
	List<Shape> shapes = doc.GetChildNodes(NodeType.Shape, true).Cast<Shape>().ToList();
	Assert.AreEqual(2, shapes.Count);

	//删除第一个形状。
	shapes[0].Remove();

	//因为我们在跟踪更改时删除了该形状，所以该形状算作删除修订。
	Assert.AreEqual(ShapeType.Cube, shapes[0].ShapeType);
	Assert.True(shapes[0].IsDeleteRevision);

	//我们在跟踪更改时插入了另一个形状，因此该形状将算作插入修订。
	Assert.AreEqual(ShapeType.Sun, shapes[1].ShapeType);
	Assert.True(shapes[1].IsInsertRevision);

	//该文档有一个形状被移动，但形状移动修订将有该形状的两个实例。
	//一个将是其到达目的地的形状，另一个将是其原始位置的形状。
	doc = new Document(MyDir + "Revision shape.docx");
	
	shapes = doc.GetChildNodes(NodeType.Shape, true).Cast<Shape>().ToList();
	Assert.AreEqual(2, shapes.Count);

	//这是修改的动作，也是到达目的地的形状。
	Assert.False(shapes[0].IsMoveFromRevision);
	Assert.True(shapes[0].IsMoveToRevision);

	//这是修订版的移动，即原始位置的形状。
	Assert.True(shapes[1].IsMoveFromRevision);
	Assert.False(shapes[1].IsMoveToRevision);
            
```

