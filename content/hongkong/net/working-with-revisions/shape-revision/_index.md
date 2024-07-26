---
title: 形狀修正
linktitle: 形狀修正
second_title: Aspose.Words 文件處理 API
description: 使用 Aspose.Words for .NET 修改 Word 文件中的形狀。
type: docs
weight: 10
url: /zh-hant/net/working-with-revisions/shape-revision/
---

在本逐步指南中，我們將引導您了解如何使用 Aspose.Words for .NET 對 Word 文件中的形狀進行修改。我們將為您提供完整的原始程式碼，並向您展示如何格式化 Markdown 輸出。

## 第 1 步：建立文件並新增形狀

第一步是建立一個新文件並添加形狀。

```csharp
Document doc = new Document();
Assert.False(doc.TrackRevisions);

Shape shape = new Shape(doc, ShapeType.Cube);
shape. WrapType = WrapType. Inline;
shape. Width = 100.0;
shape. Height = 100.0;
doc.FirstSection.Body.FirstParagraph.AppendChild(shape);
```

## 第 2 步：追蹤修訂並新增另一個形狀

我們將開啟修訂追蹤並新增另一個形狀。

```csharp
doc.StartTrackRevisions("John Doe");

shape = new Shape(doc, ShapeType.Sun);
shape. WrapType = WrapType. Inline;
shape. Width = 100.0;
shape. Height = 100.0;
doc.FirstSection.Body.FirstParagraph.AppendChild(shape);
```

## 第 3 步：取得形狀集合並檢查修訂情況

我們將從文件中取得形狀集合併檢查與每個形狀相關的修訂。

```csharp
List<Shape> shapes = doc.GetChildNodes(NodeType.Shape, true).Cast<Shape>().ToList();
Assert.AreEqual(2, shapes.Count);

Assert.AreEqual(ShapeType.Cube, shapes[0].ShapeType);
Assert.True(shapes[0].IsDeleteRevision);

Assert.AreEqual(ShapeType.Sun, shapes[1].ShapeType);
Assert.True(shapes[1].IsInsertRevision);
```

## 第 4 步：檢查形狀移動修訂

我們將載入包含形狀位移修訂的現有文件並檢查相關修訂。

```csharp
doc = new Document(MyDir + "Revision shape.docx");

shapes = doc.GetChildNodes(NodeType.Shape, true).Cast<Shape>().ToList();
Assert.AreEqual(2, shapes.Count);

Assert. False(shapes[0].IsMoveFromRevision);
Assert.True(shapes[0].IsMoveToRevision);

Assert.True(shapes[1].IsMoveFromRevision);
Assert. False(shapes[1].IsMoveToRevision);
```

### 使用 Aspose.Words for .NET 進行形狀修訂的範例原始程式碼

以下是使用 Aspose.Words for .NET 修改文件中的形狀的完整原始碼：

```csharp
Document doc = new Document();

//插入內聯形狀而不追蹤修訂。
Assert.False(doc.TrackRevisions);
Shape shape = new Shape(doc, ShapeType.Cube);
shape.WrapType = WrapType.Inline;
shape.Width = 100.0;
shape.Height = 100.0;
doc.FirstSection.Body.FirstParagraph.AppendChild(shape);

//開始追蹤修訂，然後插入另一個形狀。
doc.StartTrackRevisions("John Doe");
shape = new Shape(doc, ShapeType.Sun);
shape.WrapType = WrapType.Inline;
shape.Width = 100.0;
shape.Height = 100.0;
doc.FirstSection.Body.FirstParagraph.AppendChild(shape);

//取得文件的形狀集合，其中僅包含我們新增的兩個形狀。
List<Shape> shapes = doc.GetChildNodes(NodeType.Shape, true).Cast<Shape>().ToList();
Assert.AreEqual(2, shapes.Count);

//刪除第一個形狀。
shapes[0].Remove();

//因為我們在追蹤更改時刪除了該形狀，所以該形狀算作刪除修訂。
Assert.AreEqual(ShapeType.Cube, shapes[0].ShapeType);
Assert.True(shapes[0].IsDeleteRevision);

//我們在追蹤更改時插入了另一個形狀，因此該形狀將被視為插入修訂。
Assert.AreEqual(ShapeType.Sun, shapes[1].ShapeType);
Assert.True(shapes[1].IsInsertRevision);

//該文件有一個已移動的形狀，但形狀移動修訂將有該形狀的兩個實例。
//一個是其到達目的地的形狀，另一個是其原始位置的形狀。
doc = new Document(MyDir + "Revision shape.docx");

shapes = doc.GetChildNodes(NodeType.Shape, true).Cast<Shape>().ToList();
Assert.AreEqual(2, shapes.Count);

//這是修正的過程，也是到達目的地的形狀。
Assert.False(shapes[0].IsMoveFromRevision);
Assert.True(shapes[0].IsMoveToRevision);

//這是修訂後的移動，即其原始位置的形狀。
Assert.True(shapes[1].IsMoveFromRevision);
Assert.False(shapes[1].IsMoveToRevision);
```

## 結論

在本教學中，我們學習如何使用 Aspose.Words for .NET 對 Word 文件中的形狀進行修改。透過遵循建立文件、啟用修訂追蹤、檢查與每個形狀關聯的修訂以及檢查移動形狀的修訂的步驟，我們能夠成功管理修訂。 Aspose.Words for .NET 提供了強大的 API，用於文字處理，包括 Word 文件中的評論和表單。

### 常見問題解答

#### Q：如何在 Aspose.Words for .NET 中建立新文件並新增形狀？

答：要在 Aspose.Words for .NET 中建立新文件並新增形狀，您可以使用下列程式碼。這裡我們在文件的第一部分添加兩個形狀，一個立方體和一個太陽：

```csharp
Document doc = new Document();
Assert.False(doc.TrackRevisions);

Shape shape = new Shape(doc, ShapeType.Cube);
shape. WrapType = WrapType. Inline;
shape. Width = 100.0;
shape. Height = 100.0;
doc.FirstSection.Body.FirstParagraph.AppendChild(shape);
```

#### Q：如何在 Aspose.Words for .NET 中啟用修訂追蹤？

答：要在 Aspose.Words for .NET 中啟用修訂跟踪，您可以使用`StartTrackRevisions`的方法`Document`目的。此方法將修訂作者的姓名作為參數：

```csharp
doc.StartTrackRevisions("John Doe");
```

#### Q：如何檢查與 Aspose.Words for .NET 文件中每個形狀相關的修訂？

答：若要檢查與 Aspose.Words for .NET 文件中每個形狀關聯的修訂，您可以使用下列命令取得文件的形狀集合：`GetChildNodes`方法與`NodeType.Shape`節點類型。然後您可以訪問每個形狀的`IsDeleteRevision`, `IsInsertRevision`, `IsMoveFromRevision`， 和`IsMoveToRevision`屬性來決定與形狀關聯的修訂類型：

```csharp
List<Shape> shapes = doc.GetChildNodes(NodeType.Shape, true).Cast<Shape>().ToList();
Assert.AreEqual(2, shapes.Count);

Assert.AreEqual(ShapeType.Cube, shapes[0].ShapeType);
Assert.True(shapes[0].IsDeleteRevision);

Assert.AreEqual(ShapeType.Sun, shapes[1].ShapeType);
Assert.True(shapes[1].IsInsertRevision);
```

#### Q：如何檢查 Aspose.Words for .NET 文件中形狀的位移修訂？

答：若要檢查 Aspose.Words for .NET 文件中的形狀位移修訂，您可以載入包含形狀位移修訂的現有文件。然後您可以訪問每個形狀的`IsMoveFromRevision`和`IsMoveToRevision`屬性來確定它是否正在移動，如果是，則從何處移動到何處：

```csharp
doc = new Document(MyDir + "Revision shape.docx");

shapes = doc.GetChildNodes(NodeType.Shape, true).Cast<Shape>().ToList();
Assert.AreEqual(2, shapes.Count);

Assert. False(shapes[0].IsMoveFromRevision);
Assert.True(shapes[0].IsMoveToRevision);

Assert.True(shapes[1].IsMoveFromRevision);
Assert. False(shapes[1].IsMoveToRevision);
```