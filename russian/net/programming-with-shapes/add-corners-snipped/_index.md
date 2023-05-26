---
title: Добавить обрезанные углы
linktitle: Добавить обрезанные углы
second_title: Справочник по API Aspose.Words для .NET
description: Узнайте, как добавить фигуру с обрезанными углами в документ Word с помощью Aspose.Words для .NET.
type: docs
weight: 10
url: /ru/net/programming-with-shapes/add-corners-snipped/
---

 В этом руководстве объясняется, как добавить фигуру с обрезанными углами в документ Word с помощью Aspose.Words для .NET. Форму обрезанных углов можно настроить и вставить с помощью`InsertShape` метод.

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

## Шаг 3: Вставьте фигуру с обрезанными углами
 Использовать`InsertShape` метод`DocumentBuilder` объект, чтобы вставить фигуру с обрезанными углами. Укажите тип фигуры (в данном случае`ShapeType.TopCornersSnipped`) и укажите желаемый размер формы.

```csharp
builder.InsertShape(ShapeType.TopCornersSnipped, 50, 50);
```

## Шаг 4: Сохраните документ
 Сохраните документ в указанную директорию с помощью`Save` метод. Укажите желаемое имя файла с соответствующим расширением файла. В этом примере мы сохраняем документ как «WorkingWithShapes.AddCornersSnipped.docx».

```csharp
OoxmlSaveOptions saveOptions = new OoxmlSaveOptions(SaveFormat.Docx)
{
    Compliance = OoxmlCompliance.Iso29500_2008_Transitional
};
doc.Save(dataDir + "WorkingWithShapes.AddCornersSnipped.docx", saveOptions);
```

### Пример исходного кода для добавления отрезанных углов с использованием Aspose.Words для .NET 

```csharp
	// Путь к вашему каталогу документов
	string dataDir = "YOUR DOCUMENT DIRECTORY";

	Document doc = new Document();
	DocumentBuilder builder = new DocumentBuilder(doc);
	builder.InsertShape(ShapeType.TopCornersSnipped, 50, 50);
	OoxmlSaveOptions saveOptions = new OoxmlSaveOptions(SaveFormat.Docx)
	{
		Compliance = OoxmlCompliance.Iso29500_2008_Transitional
	};
	doc.Save(dataDir + "WorkingWithShapes.AddCornersSnipped.docx", saveOptions);

```

Вот и все! Вы успешно добавили фигуру с обрезанными углами в документ Word с помощью Aspose.Words для .NET.