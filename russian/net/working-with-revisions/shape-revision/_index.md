---
title: Изменение формы
linktitle: Изменение формы
second_title: Справочник по API Aspose.Words для .NET
description: Редактируйте фигуры в документе Word с помощью Aspose.Words для .NET.
type: docs
weight: 10
url: /ru/net/working-with-revisions/shape-revision/
---

В этом пошаговом руководстве мы расскажем, как вносить изменения в фигуры в документе Word с помощью Aspose.Words для .NET. Мы предоставим вам полный исходный код и покажем, как форматировать выходные данные уценки.

## Шаг 1. Создание документа и добавление фигур

Первый шаг — создать новый документ и добавить фигуры.

```csharp
Document doc = new Document();
Assert.False(doc.TrackRevisions);

Shape shape = new Shape(doc, ShapeType.Cube);
shape. WrapType = WrapType. Inline;
shape. Width = 100.0;
shape. Height = 100.0;
doc.FirstSection.Body.FirstParagraph.AppendChild(shape);
```

## Шаг 2. Отслеживайте изменения и добавляйте еще одну фигуру

Мы включим отслеживание изменений и добавим еще одну фигуру.

```csharp
doc.StartTrackRevisions("John Doe");

shape = new Shape(doc, ShapeType.Sun);
shape. WrapType = WrapType. Inline;
shape. Width = 100.0;
shape. Height = 100.0;
doc.FirstSection.Body.FirstParagraph.AppendChild(shape);
```

## Шаг 3. Получите коллекцию фигур и проверьте наличие изменений

Мы получим коллекцию фигур из документа и проверим ревизии, связанные с каждой фигурой.

```csharp
List<Shape> shapes = doc.GetChildNodes(NodeType.Shape, true).Cast<Shape>().ToList();
Assert.AreEqual(2, shapes.Count);

Assert.AreEqual(ShapeType.Cube, shapes[0].ShapeType);
Assert.True(shapes[0].IsDeleteRevision);

Assert.AreEqual(ShapeType.Sun, shapes[1].ShapeType);
Assert.True(shapes[1].IsInsertRevision);
```

## Шаг 4. Проверка изменений перемещения формы

Мы загрузим существующий документ, содержащий исправления смещения формы, и проверим связанные исправления.

```csharp
doc = new Document(MyDir + "Revision shape.docx");

shapes = doc.GetChildNodes(NodeType.Shape, true).Cast<Shape>().ToList();
Assert.AreEqual(2, shapes.Count);

Assert. False(shapes[0].IsMoveFromRevision);
Assert.True(shapes[0].IsMoveToRevision);

Assert.True(shapes[1].IsMoveFromRevision);
Assert. False(shapes[1].IsMoveToRevision);
```

### Пример исходного кода для Shape Revision с использованием Aspose.Words для .NET

Вот полный исходный код для внесения изменений в фигуры в документе с использованием Aspose.Words для .NET:

```csharp
Document doc = new Document();

// Вставьте встроенную фигуру без отслеживания изменений.
Assert.False(doc.TrackRevisions);
Shape shape = new Shape(doc, ShapeType.Cube);
shape.WrapType = WrapType.Inline;
shape.Width = 100.0;
shape.Height = 100.0;
doc.FirstSection.Body.FirstParagraph.AppendChild(shape);

// Начните отслеживать изменения, а затем вставьте другую фигуру.
doc.StartTrackRevisions("John Doe");
shape = new Shape(doc, ShapeType.Sun);
shape.WrapType = WrapType.Inline;
shape.Width = 100.0;
shape.Height = 100.0;
doc.FirstSection.Body.FirstParagraph.AppendChild(shape);

// Получите коллекцию фигур документа, которая включает только две добавленные нами фигуры.
List<Shape> shapes = doc.GetChildNodes(NodeType.Shape, true).Cast<Shape>().ToList();
Assert.AreEqual(2, shapes.Count);

// Удалите первую форму.
shapes[0].Remove();

// Поскольку мы удалили эту форму во время отслеживания изменений, она считается удаленной версией.
Assert.AreEqual(ShapeType.Cube, shapes[0].ShapeType);
Assert.True(shapes[0].IsDeleteRevision);

// И мы вставили другую фигуру, отслеживая изменения, так что эта форма будет считаться ревизией вставки.
Assert.AreEqual(ShapeType.Sun, shapes[1].ShapeType);
Assert.True(shapes[1].IsInsertRevision);

//В документе есть одна фигура, которая была перемещена, но ревизии перемещения фигуры будут иметь два экземпляра этой фигуры.
// Один будет фигурой в месте прибытия, а другой будет фигурой в исходном месте.
doc = new Document(MyDir + "Revision shape.docx");

shapes = doc.GetChildNodes(NodeType.Shape, true).Cast<Shape>().ToList();
Assert.AreEqual(2, shapes.Count);

// Это движение к пересмотру, а также форма в месте прибытия.
Assert.False(shapes[0].IsMoveFromRevision);
Assert.True(shapes[0].IsMoveToRevision);

// Это переход от ревизии, то есть формы в исходном месте.
Assert.True(shapes[1].IsMoveFromRevision);
Assert.False(shapes[1].IsMoveToRevision);
```

