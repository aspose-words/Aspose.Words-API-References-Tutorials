---
title: Добавить обрезанные углы
linktitle: Добавить обрезанные углы
second_title: API обработки документов Aspose.Words
description: Узнайте, как добавить фигуру со срезанными углами в документ Word с помощью Aspose.Words для .NET.
type: docs
weight: 10
url: /ru/net/programming-with-shapes/add-corners-snipped/
---

 В этом руководстве объясняется, как добавить фигуру с обрезанными углами в документ Word с помощью Aspose.Words для .NET. Форму обрезанных углов можно настроить и вставить с помощью`InsertShape` метод.

## Предварительные условия
Чтобы следовать этому руководству, вам необходимо иметь следующее:

- Установлена библиотека Aspose.Words для .NET.
- Базовые знания C# и обработки документов Word.

## Шаг 1. Настройте каталог документов
 Начните с настройки пути к каталогу ваших документов. Заменять`"YOUR DOCUMENT DIRECTORY"`с фактическим путем к каталогу, в котором вы хотите сохранить документ.

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## Шаг 2. Создайте новый документ и DocumentBuilder
 Создайте новый экземпляр`Document` класс и`DocumentBuilder` объект для работы с документом.

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
```

## Шаг 3. Вставьте фигуру с обрезанными углами
 Использовать`InsertShape` метод`DocumentBuilder` объект, чтобы вставить фигуру со срезанными углами. Укажите тип фигуры (в данном случае`ShapeType.TopCornersSnipped`) и укажите желаемый размер фигуры.

```csharp
builder.InsertShape(ShapeType.TopCornersSnipped, 50, 50);
```

## Шаг 4. Сохраните документ
 Сохраните документ в указанную директорию, используя команду`Save`метод. Укажите желаемое имя файла с соответствующим расширением. В этом примере мы сохраняем документ как «WorkingWithShapes.AddCornersSnipped.docx».

```csharp
OoxmlSaveOptions saveOptions = new OoxmlSaveOptions(SaveFormat.Docx)
{
    Compliance = OoxmlCompliance.Iso29500_2008_Transitional
};
doc.Save(dataDir + "WorkingWithShapes.AddCornersSnipped.docx", saveOptions);
```

### Пример исходного кода для добавления углов с использованием Aspose.Words для .NET 

```csharp
	// Путь к каталогу ваших документов
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

Вот и все! Вы успешно добавили форму с обрезанными углами в документ Word с помощью Aspose.Words для .NET.