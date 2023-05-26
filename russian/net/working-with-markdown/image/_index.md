---
title: Изображение
linktitle: Изображение
second_title: Справочник по API Aspose.Words для .NET
description: Узнайте, как вставлять и настраивать изображения с помощью Aspose.Words для .NET. Пошаговое руководство.
type: docs
weight: 10
url: /ru/net/working-with-markdown/image/
---

В этом примере мы объясним, как использовать функцию изображения с Aspose.Words для .NET. Рисунки позволяют вставлять в документ иллюстрации и графику.

## Шаг 1: Использование генератора документов

Во-первых, мы будем использовать генератор документов, чтобы добавить содержимое в наш документ.

```csharp
DocumentBuilder builder = new DocumentBuilder();
```

## Шаг 2. Вставка изображения

 Мы можем вставить изображение с помощью`Shape` class и указав тип изображения, здесь`ShapeType.Image` Мы также устанавливаем тип переноса изображения на`WrapType.Inline`.

```csharp
Shape shape = new Shape(builder.Document, ShapeType.Image);
shape. WrapType = WrapType. Inline;
```

## Шаг 3: Настройка изображения

 Настраиваем изображение, указав его полный путь, например`"/attachment/1456/pic001.png"`, и добавить заголовок к изображению.

```csharp
shape.ImageData.SourceFullName = "/attachment/1456/pic001.png";
shape.ImageData.Title = "Title";
```

### Пример исходного кода для изображений с Aspose.Words для .NET

```csharp
	// Используйте конструктор документов, чтобы добавить содержимое в документ.
	DocumentBuilder builder = new DocumentBuilder();

	// Вставить изображение.
	Shape shape = new Shape(builder.Document, ShapeType.Image);
	shape.WrapType = WrapType.Inline;
	shape.ImageData.SourceFullName = "/attachment/1456/pic001.png";
	shape.ImageData.Title = "title";
	builder.InsertNode(shape);
            
```

Поздравляем! Теперь вы узнали, как использовать функцию изображений с Aspose.Words для .NET.

