---
title: Редакция формы
linktitle: Редакция формы
second_title: API обработки документов Aspose.Words
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

## Шаг 2. Отслеживайте изменения и добавьте еще одну фигуру.

Мы включим отслеживание изменений и добавим еще одну фигуру.

```csharp
doc.StartTrackRevisions("John Doe");

shape = new Shape(doc, ShapeType.Sun);
shape. WrapType = WrapType. Inline;
shape. Width = 100.0;
shape. Height = 100.0;
doc.FirstSection.Body.FirstParagraph.AppendChild(shape);
```

## Шаг 3. Получите коллекцию фигур и проверьте наличие изменений.

Мы получим коллекцию фигур из документа и проверим версии, связанные с каждой фигурой.

```csharp
List<Shape> shapes = doc.GetChildNodes(NodeType.Shape, true).Cast<Shape>().ToList();
Assert.AreEqual(2, shapes.Count);

Assert.AreEqual(ShapeType.Cube, shapes[0].ShapeType);
Assert.True(shapes[0].IsDeleteRevision);

Assert.AreEqual(ShapeType.Sun, shapes[1].ShapeType);
Assert.True(shapes[1].IsInsertRevision);
```

## Шаг 4. Проверка изменений перемещения фигуры

Мы собираемся загрузить существующий документ, содержащий версии смещения формы, и проверить связанные версии.

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

Вот полный исходный код для внесения изменений в фигуры в документе с помощью Aspose.Words для .NET:

```csharp
Document doc = new Document();

//Вставьте встроенную фигуру без отслеживания изменений.
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

// Получите коллекцию фигур документа, включающую только две добавленные нами фигуры.
List<Shape> shapes = doc.GetChildNodes(NodeType.Shape, true).Cast<Shape>().ToList();
Assert.AreEqual(2, shapes.Count);

// Удалите первую фигуру.
shapes[0].Remove();

// Поскольку мы удалили эту фигуру во время отслеживания изменений, она считается удаленной версией.
Assert.AreEqual(ShapeType.Cube, shapes[0].ShapeType);
Assert.True(shapes[0].IsDeleteRevision);

// И мы вставили еще одну фигуру, отслеживая изменения, поэтому эта фигура будет считаться вставленной версией.
Assert.AreEqual(ShapeType.Sun, shapes[1].ShapeType);
Assert.True(shapes[1].IsInsertRevision);

// В документе есть одна фигура, которая была перемещена, но версии перемещения фигуры будут содержать два экземпляра этой фигуры.
// Одна из них будет фигурой в пункте назначения, а другая — фигурой в исходном месте.
doc = new Document(MyDir + "Revision shape.docx");

shapes = doc.GetChildNodes(NodeType.Shape, true).Cast<Shape>().ToList();
Assert.AreEqual(2, shapes.Count);

// Это переход к пересмотру, а также форма в пункте назначения.
Assert.False(shapes[0].IsMoveFromRevision);
Assert.True(shapes[0].IsMoveToRevision);

// Это переход от редакции, которая представляет собой форму на исходном месте.
Assert.True(shapes[1].IsMoveFromRevision);
Assert.False(shapes[1].IsMoveToRevision);
```

## Заключение

В этом уроке мы узнали, как вносить изменения в фигуры в документе Word с помощью Aspose.Words для .NET. Выполнив этапы создания документа, включив отслеживание изменений, проверив изменения, связанные с каждой фигурой, и проверив изменения для перемещения фигур, мы смогли успешно управлять изменениями. Aspose.Words for .NET предлагает мощный API для обработки текстов с обзорами и формами в документах Word.

### Часто задаваемые вопросы

#### Вопрос: Как создать новый документ и добавить фигуры в Aspose.Words для .NET?

О: Чтобы создать новый документ и добавить фигуры в Aspose.Words for .NET, вы можете использовать следующий код. Здесь мы добавляем две фигуры, куб и солнце, в первый раздел документа:

```csharp
Document doc = new Document();
Assert.False(doc.TrackRevisions);

Shape shape = new Shape(doc, ShapeType.Cube);
shape. WrapType = WrapType. Inline;
shape. Width = 100.0;
shape. Height = 100.0;
doc.FirstSection.Body.FirstParagraph.AppendChild(shape);
```

#### Вопрос: Как включить отслеживание версий в Aspose.Words для .NET?

 О: Чтобы включить отслеживание версий в Aspose.Words для .NET, вы можете использовать`StartTrackRevisions` метод`Document` объект. Этот метод принимает имя автора ревизий в качестве параметра:

```csharp
doc.StartTrackRevisions("John Doe");
```

#### Вопрос: Как я могу проверить версии, связанные с каждой фигурой в документе Aspose.Words for .NET?

О: Чтобы проверить версии, связанные с каждой фигурой в документе Aspose.Words for .NET, вы можете получить коллекцию фигур документа, используя команду`GetChildNodes` метод с`NodeType.Shape` тип узла. Затем вы можете получить доступ к каждой фигуре`IsDeleteRevision`, `IsInsertRevision`, `IsMoveFromRevision` , и`IsMoveToRevision` свойства, чтобы определить, какой тип редакции связан с формой:

```csharp
List<Shape> shapes = doc.GetChildNodes(NodeType.Shape, true).Cast<Shape>().ToList();
Assert.AreEqual(2, shapes.Count);

Assert.AreEqual(ShapeType.Cube, shapes[0].ShapeType);
Assert.True(shapes[0].IsDeleteRevision);

Assert.AreEqual(ShapeType.Sun, shapes[1].ShapeType);
Assert.True(shapes[1].IsInsertRevision);
```

#### Вопрос: Как я могу проверить наличие изменений смещения фигур в документе Aspose.Words for .NET?

 О: Чтобы проверить наличие изменений смещения формы в документе Aspose.Words for .NET, вы можете загрузить существующий документ, содержащий изменения смещения формы. Затем вы можете получить доступ к каждой фигуре`IsMoveFromRevision`и`IsMoveToRevision` свойства, чтобы определить, перемещается ли он, и если да, то откуда и куда:

```csharp
doc = new Document(MyDir + "Revision shape.docx");

shapes = doc.GetChildNodes(NodeType.Shape, true).Cast<Shape>().ToList();
Assert.AreEqual(2, shapes.Count);

Assert. False(shapes[0].IsMoveFromRevision);
Assert.True(shapes[0].IsMoveToRevision);

Assert.True(shapes[1].IsMoveFromRevision);
Assert. False(shapes[1].IsMoveToRevision);
```