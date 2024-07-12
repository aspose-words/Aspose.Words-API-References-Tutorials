---
title: 形状修改
linktitle: 形状修改
second_title: Aspose.Words 文档处理 API
description: 使用 Aspose.Words for .NET 修改 Word 文档中的形状。
type: docs
weight: 10
url: /zh/net/working-with-revisions/shape-revision/
---

在本分步指南中，我们将引导您了解如何使用 Aspose.Words for .NET 对 Word 文档中的形状进行修改。我们将为您提供完整的源代码并向您展示如何格式化 markdown 输出。

## 步骤 1：创建文档并添加形状

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

## 第 2 步：跟踪修订并添加另一个形状

我们将启用修订跟踪并添加另一个形状。

```csharp
doc.StartTrackRevisions("John Doe");

shape = new Shape(doc, ShapeType.Sun);
shape. WrapType = WrapType. Inline;
shape. Width = 100.0;
shape. Height = 100.0;
doc.FirstSection.Body.FirstParagraph.AppendChild(shape);
```

## 步骤 3：获取形状集合并检查修订

我们将从文档中获取形状集合并检查与每个形状相关的修订。

```csharp
List<Shape> shapes = doc.GetChildNodes(NodeType.Shape, true).Cast<Shape>().ToList();
Assert.AreEqual(2, shapes.Count);

Assert.AreEqual(ShapeType.Cube, shapes[0].ShapeType);
Assert.True(shapes[0].IsDeleteRevision);

Assert.AreEqual(ShapeType.Sun, shapes[1].ShapeType);
Assert.True(shapes[1].IsInsertRevision);
```

## 步骤 4：检查形状移动修订

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

### 使用 Aspose.Words for .NET 进行形状修订的示例源代码

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

//我们在跟踪变化时插入了另一个形状，因此该形状将算作插入修订。
Assert.AreEqual(ShapeType.Sun, shapes[1].ShapeType);
Assert.True(shapes[1].IsInsertRevision);

//文档中有一个被移动的形状，但形状移动修订将有该形状的两个实例。
//一个是其到达目的地时的形状，另一个是其原始位置时的形状。
doc = new Document(MyDir + "Revision shape.docx");

shapes = doc.GetChildNodes(NodeType.Shape, true).Cast<Shape>().ToList();
Assert.AreEqual(2, shapes.Count);

//这是修正的举动，也是其到达目的地时的形状。
Assert.False(shapes[0].IsMoveFromRevision);
Assert.True(shapes[0].IsMoveToRevision);

//这是从修订版开始的移动，即其原始位置的形状。
Assert.True(shapes[1].IsMoveFromRevision);
Assert.False(shapes[1].IsMoveToRevision);
```

## 结论

在本教程中，我们学习了如何使用 Aspose.Words for .NET 对 Word 文档中的形状进行修订。通过遵循创建文档、启用修订跟踪、检查与每个形状相关的修订以及检查移动形状的修订的步骤，我们能够成功管理修订。Aspose.Words for .NET 为 Word 文档中的评论和表单提供了强大的文字处理 API。

### 常见问题解答

#### 问：如何在 Aspose.Words for .NET 中创建新文档并添加形状？

答：要在 Aspose.Words for .NET 中创建新文档并添加形状，您可以使用以下代码。这里我们在文档的第一部分添加了两个形状，一个立方体和一个太阳：

```csharp
Document doc = new Document();
Assert.False(doc.TrackRevisions);

Shape shape = new Shape(doc, ShapeType.Cube);
shape. WrapType = WrapType. Inline;
shape. Width = 100.0;
shape. Height = 100.0;
doc.FirstSection.Body.FirstParagraph.AppendChild(shape);
```

#### 问：如何在 Aspose.Words for .NET 中启用修订跟踪？

答：要在 Aspose.Words for .NET 中启用修订跟踪，您可以使用`StartTrackRevisions`方法`Document`对象。此方法将修订作者的姓名作为参数：

```csharp
doc.StartTrackRevisions("John Doe");
```

#### 问：如何检查 Aspose.Words for .NET 文档中每个形状相关的修订？

答：要检查 Aspose.Words for .NET 文档中每个形状相关的修订，您可以使用以下方式获取文档的形状集合：`GetChildNodes`方法`NodeType.Shape`节点类型。然后你可以访问每个形状的`IsDeleteRevision`, `IsInsertRevision`, `IsMoveFromRevision`， 和`IsMoveToRevision`属性来确定与形状相关的修订类型：

```csharp
List<Shape> shapes = doc.GetChildNodes(NodeType.Shape, true).Cast<Shape>().ToList();
Assert.AreEqual(2, shapes.Count);

Assert.AreEqual(ShapeType.Cube, shapes[0].ShapeType);
Assert.True(shapes[0].IsDeleteRevision);

Assert.AreEqual(ShapeType.Sun, shapes[1].ShapeType);
Assert.True(shapes[1].IsInsertRevision);
```

#### 问：如何检查 Aspose.Words for .NET 文档中形状的位移修订？

答：要检查 Aspose.Words for .NET 文档中的形状位移修订，您可以加载包含形状位移修订的现有文档。然后，您可以访问每个形状的`IsMoveFromRevision`和`IsMoveToRevision`属性来确定它是否被移动，如果是，从哪里移动，到哪里移动：

```csharp
doc = new Document(MyDir + "Revision shape.docx");

shapes = doc.GetChildNodes(NodeType.Shape, true).Cast<Shape>().ToList();
Assert.AreEqual(2, shapes.Count);

Assert. False(shapes[0].IsMoveFromRevision);
Assert.True(shapes[0].IsMoveToRevision);

Assert.True(shapes[1].IsMoveFromRevision);
Assert. False(shapes[1].IsMoveToRevision);
```