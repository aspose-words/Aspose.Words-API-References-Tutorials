---
title: Добавить форму группы
linktitle: Добавить форму группы
second_title: API обработки документов Aspose.Words
description: Узнайте, как добавить фигуру группы с несколькими фигурами в документ Word с помощью Aspose.Words для .NET.
type: docs
weight: 10
url: /ru/net/programming-with-shapes/add-group-shape/
---

В этом руководстве объясняется, как добавить групповую фигуру, содержащую несколько фигур, в документ Word с помощью Aspose.Words для .NET. Групповые фигуры позволяют комбинировать несколько фигур и манипулировать ими как единым объектом.

## Предварительные условия
Чтобы следовать этому руководству, вам необходимо иметь следующее:

- Установлена библиотека Aspose.Words для .NET.
- Базовые знания C# и обработки документов Word.

## Шаг 1. Настройте каталог документов
 Начните с настройки пути к каталогу ваших документов. Заменять`"YOUR DOCUMENT DIRECTORY"` с фактическим путем к каталогу, в котором вы хотите сохранить документ.

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## Шаг 2. Создайте новый документ и GroupShape.
 Создайте новый экземпляр`Document` класс и`GroupShape` объект для работы с документом.

```csharp
Document doc = new Document();
doc.EnsureMinimum();
GroupShape groupShape = new GroupShape(doc);
```

## Шаг 3. Создайте и добавьте фигуры в GroupShape
 Создавайте отдельные фигуры, например`accentBorderShape`и`actionButtonShape` используя`Shape` сорт. Настройте их свойства по своему усмотрению. Добавьте эти фигуры в`groupShape` объект.

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

## Шаг 4. Установите размеры для GroupShape
 Установите ширину, высоту и размер координат для`groupShape`.

```csharp
groupShape.Width = 200;
groupShape.Height = 200;
groupShape.CoordSize = new Size(200, 200);
```

## Шаг 5. Вставьте GroupShape в документ
 Создать`DocumentBuilder` объект и вставьте`groupShape` в документ с помощью`InsertNode` метод.

```csharp
DocumentBuilder builder = new DocumentBuilder(doc);
builder.InsertNode(groupShape);
```

## Шаг 6: Сохраните документ
 Сохраните документ в указанную директорию, используя команду`Save` метод. Укажите желаемое имя файла с соответствующим расширением. В этом примере мы сохраняем документ как «WorkingWithShapes.AddGroupShape.docx».

```csharp
doc.Save(dataDir + "WorkingWithShapes.AddGroupShape.docx");
```

### Пример исходного кода для добавления фигуры группы с использованием Aspose.Words для .NET 

```csharp
	// Путь к каталогу ваших документов
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

Вот и все! Вы успешно добавили групповую фигуру, содержащую несколько фигур, в документ Word с помощью Aspose.W.