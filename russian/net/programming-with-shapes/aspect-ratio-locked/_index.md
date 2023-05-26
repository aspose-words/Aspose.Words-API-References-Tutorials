---
title: Соотношение сторон заблокировано
linktitle: Соотношение сторон заблокировано
second_title: Справочник по API Aspose.Words для .NET
description: Узнайте, как заблокировать или разблокировать соотношение сторон фигуры в документе Word с помощью Aspose.Words для .NET.
type: docs
weight: 10
url: /ru/net/programming-with-shapes/aspect-ratio-locked/
---

В этом руководстве объясняется, как заблокировать или разблокировать соотношение сторон фигуры в документе Word с помощью Aspose.Words для .NET. Заблокировав соотношение сторон, вы можете сохранить исходные пропорции фигуры при изменении ее размера.

## Предпосылки
Чтобы следовать этому руководству, вам необходимо иметь следующее:

- Установлена библиотека Aspose.Words for .NET.
- Базовые знания C# и работы с документами Word.

## Шаг 1. Настройте каталог документов
 Начните с настройки пути к каталогу документов. Заменять`"YOUR DOCUMENT DIRECTORY"`с фактическим путем к каталогу, в котором вы хотите сохранить документ.

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## Шаг 2: Создайте новый документ и DocumentBuilder
 Создайте новый экземпляр`Document` класс и`DocumentBuilder` объект для работы с документом.

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
```

## Шаг 3: Вставьте фигуру изображения
 Использовать`InsertImage` метод`DocumentBuilder` объект, чтобы вставить фигуру изображения в документ. Укажите путь к файлу изображения в качестве параметра.

```csharp
Shape shape = builder.InsertImage(ImagesDir + "Transparent background logo.png");
```

## Шаг 4: заблокируйте или разблокируйте соотношение сторон
 Установить`AspectRatioLocked` свойство формы к`true` или`false`чтобы заблокировать или разблокировать соотношение сторон соответственно.

```csharp
shape.AspectRatioLocked = false; // Разблокировать соотношение сторон
```

## Шаг 5: Сохраните документ
 Сохраните документ в указанную директорию с помощью`Save` метод. Укажите желаемое имя файла с соответствующим расширением файла. В этом примере мы сохраняем документ как «WorkingWithShapes.AspectRatioLocked.docx».

```csharp
doc.Save(dataDir + "WorkingWithShapes.AspectRatioLocked.docx");
```

### Пример исходного кода для блокировки соотношения сторон с использованием Aspose.Words для .NET 

```csharp
	// Путь к вашему каталогу документов
	string dataDir = "YOUR DOCUMENT DIRECTORY";

	Document doc = new Document();
	DocumentBuilder builder = new DocumentBuilder(doc);
	Shape shape = builder.InsertImage(ImagesDir + "Transparent background logo.png");
	shape.AspectRatioLocked = false;
	doc.Save(dataDir + "WorkingWithShapes.AspectRatioLocked.docx");
```

Вот и все! Вы успешно заблокировали или разблокировали соотношение сторон фигуры в документе Word с помощью Aspose.Words для .NET.