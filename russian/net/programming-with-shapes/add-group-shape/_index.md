---
title: Добавить фигуру группы
linktitle: Добавить фигуру группы
second_title: Справочник по API Aspose.Words для .NET
description: Узнайте, как добавить групповую фигуру с несколькими фигурами в документ Word с помощью Aspose.Words для .NET.
type: docs
weight: 10
url: /ru/net/programming-with-shapes/add-group-shape/
---

В этом руководстве объясняется, как добавить групповую фигуру, содержащую несколько фигур, в документ Word с помощью Aspose.Words для .NET. Групповые фигуры позволяют комбинировать несколько фигур и управлять ими как единым объектом.

## Предпосылки
Чтобы следовать этому руководству, вам необходимо иметь следующее:

- Установлена библиотека Aspose.Words for .NET.
- Базовые знания C# и работы с документами Word.

## Шаг 1. Настройте каталог документов
 Начните с настройки пути к каталогу документов. Заменять`"YOUR DOCUMENT DIRECTORY"`с фактическим путем к каталогу, в котором вы хотите сохранить документ.

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## Шаг 2: Создайте новый документ и GroupShape
 Создайте новый экземпляр`Document` класс и`GroupShape` объект для работы с документом.

```csharp
Document doc = new Document();
doc.EnsureMinimum();
GroupShape groupShape = new GroupShape(doc);
```

## Шаг 3: Создайте и добавьте фигуры в GroupShape
 Создавайте отдельные формы, такие как`accentBorderShape` и`actionButtonShape` используя`Shape` сорт. Настройте их свойства по желанию. Добавьте эти фигуры к`groupShape` объект.

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

## Шаг 4: Установите размеры для GroupShape
 Задайте ширину, высоту и размер координат для`groupShape`.

```csharp
groupShape.Width = 200;
groupShape.Height = 200;
groupShape.CoordSize = new Size(200, 200);
```

## Шаг 5: Вставьте GroupShape в документ
 Создать`DocumentBuilder` объект и вставьте`groupShape` в документ с помощью`InsertNode` метод.

```csharp
DocumentBuilder builder = new DocumentBuilder(doc);
builder.InsertNode(groupShape);
```

## Шаг 6: Сохраните документ
 Сохраните документ в указанную директорию с помощью`Save`метод. Укажите желаемое имя файла с соответствующим расширением файла. В этом примере мы сохраняем документ как «WorkingWithShapes.AddGroupShape.docx».

```csharp
doc.Save(dataDir + "WorkingWithShapes.AddGroupShape.docx");
```

### Пример исходного кода для добавления формы группы с использованием Aspose.Words для .NET 

```csharp
	// Путь к вашему каталогу документов
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

Вот и все! Вы успешно добавили фигуру группы, содержащую несколько фигур, в документ Word с помощью Aspose.W.