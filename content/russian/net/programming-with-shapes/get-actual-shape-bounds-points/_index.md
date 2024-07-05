---
title: Получите фактические точки границ формы
linktitle: Получите фактические точки границ формы
second_title: API обработки документов Aspose.Words
description: Узнайте, как получить фактические границы фигуры в точках (единицы измерения) в документе Word с помощью Aspose.Words для .NET.
type: docs
weight: 10
url: /ru/net/programming-with-shapes/get-actual-shape-bounds-points/
---

В этом руководстве объясняется, как получить фактические границы фигуры в точках (единицы измерения) в документе Word с помощью Aspose.Words для .NET. Границы представляют размер и положение фигуры в документе.

## Предварительные условия
Чтобы следовать этому руководству, вам необходимо иметь следующее:

- Установлена библиотека Aspose.Words для .NET.
- Базовые знания C# и обработки документов Word.

## Шаг 1. Создайте новый документ и DocumentBuilder
 Создайте новый экземпляр`Document` класс и`DocumentBuilder`объект для работы с документом.

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
```

## Шаг 2. Вставьте фигуру изображения
 Использовать`InsertImage` метод`DocumentBuilder` объект, чтобы вставить фигуру изображения в документ. Укажите путь к файлу изображения в качестве параметра.

```csharp
Shape shape = builder.InsertImage(ImagesDir + "Transparent background logo.png");
shape.AspectRatioLocked = false;
```

## Шаг 3. Получите фактические точки границ формы
 Доступ к фигурам`ShapeRenderer` используя`GetShapeRenderer` метод. Затем извлеките фактические границы фигуры в точках, используя метод`BoundsInPoints` свойство.

```csharp
Console.Write("\nGets the actual bounds of the shape in points: ");
Console.WriteLine(shape.GetShapeRenderer().BoundsInPoints);
```


### Пример исходного кода для получения фактических точек границ формы с использованием Aspose.Words для .NET 

```csharp
	Document doc = new Document();
	DocumentBuilder builder = new DocumentBuilder(doc);
	Shape shape = builder.InsertImage(ImagesDir + "Transparent background logo.png");
	shape.AspectRatioLocked = false;
	Console.Write("\nGets the actual bounds of the shape in points: ");
	Console.WriteLine(shape.GetShapeRenderer().BoundsInPoints);
```

Вот и все! Вы успешно получили фактические границы фигуры в точках в документе Word с помощью Aspose.Words для .NET.