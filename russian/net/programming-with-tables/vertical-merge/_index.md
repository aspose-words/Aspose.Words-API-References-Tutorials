---
title: Вертикальное слияние
linktitle: Вертикальное слияние
second_title: Справочник по API Aspose.Words для .NET
description: Узнайте, как вертикально объединить ячейки в таблице в документе Word с помощью Aspose.Words для .NET.
type: docs
weight: 10
url: /ru/net/programming-with-tables/vertical-merge/
---

В этом уроке мы узнаем, как вертикально объединить ячейки в таблице в документе Word, используя Aspose.Words для .NET. Мы будем следовать пошаговому руководству, чтобы понять код и реализовать эту функцию. В конце этого руководства вы сможете выполнять вертикальное объединение ячеек в ваших таблицах в документах Word.

## Шаг 1: Настройка проекта
1. Запустите Visual Studio и создайте новый проект C#.
2. Добавьте ссылку на библиотеку Aspose.Words для .NET.

## Шаг 2: Загрузка документа
Чтобы начать работу с документом, выполните следующие действия:

```csharp
// Путь к каталогу ваших документов
string dataDir = "YOUR DOCUMENTS DIRECTORY";

// Создать новый документ
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
```

Обязательно замените «КАТАЛОГ ВАШИХ ДОКУМЕНТОВ» на фактический путь к каталогу ваших документов.

## Шаг 3: Объединение ячеек по вертикали
Далее мы объединим ячейки по вертикали в таблице. Используйте следующий код:

```csharp
// Вставить ячейку
builder. InsertCell();

// Примените вертикальное слияние к первой ячейке
builder.CellFormat.VerticalMerge = CellMerge.First;
builder.Write("Text in merged cells.");

// Вставить другую ячейку
builder. InsertCell();

// Не применять вертикальное слияние к ячейке
builder.CellFormat.VerticalMerge = CellMerge.None;
builder.Write("Text in a cell");
builder. EndRow();

// Вставить ячейку
builder. InsertCell();

// Применить вертикальное слияние с предыдущей ячейкой
builder.CellFormat.VerticalMerge = CellMerge.Previous;

// Вставить другую ячейку
builder. InsertCell();

// Не применять вертикальное слияние к ячейке
builder.CellFormat.VerticalMerge = CellMerge.None;
builder.Write("Text in another cell");
builder. EndRow();

//Завершить создание таблицы
builder. EndTable();
```

В этом коде мы используем конструктор DocumentBuilder для вставки ячеек в таблицу. Мы применяем вертикальное слияние к ячейкам, используя свойство CellFormat.VerticalMerge. Мы используем CellMerge.First для первого слияния ячеек, CellMerge.Previous для слияния с предыдущей ячейкой и CellMerge.None для отсутствия вертикального слияния.

## Шаг 4: Сохранение измененного документа
Наконец, нам нужно сохранить измененный документ с объединенными ячейками. Используйте следующий код:

```csharp
doc.Save(dataDir + "WorkingWithTables.VerticalMerge.docx");
```

Обязательно укажите правильный путь и имя файла для выходного документа.

### Пример исходного кода для вертикального слияния с использованием Aspose.Words для .NET 
```csharp
	// Путь к вашему каталогу документов
	string dataDir = "YOUR DOCUMENT DIRECTORY";

	Document doc = new Document();
	DocumentBuilder builder = new DocumentBuilder(doc);
	builder.InsertCell();
	builder.CellFormat.VerticalMerge = CellMerge.First;
	builder.Write("Text in merged cells.");
	builder.InsertCell();
	builder.CellFormat.VerticalMerge = CellMerge.None;
	builder.Write("Text in one cell");
	builder.EndRow();
	builder.InsertCell();
	// Эта ячейка вертикально объединена с ячейкой выше и должна быть пустой.
	builder.CellFormat.VerticalMerge = CellMerge.Previous;
	builder.InsertCell();
	builder.CellFormat.VerticalMerge = CellMerge.None;
	builder.Write("Text in another cell");
	builder.EndRow();
	builder.EndTable();
	doc.Save(dataDir + "WorkingWithTables.VerticalMerge.docx");
```

## Заключение
В этом уроке мы узнали, как вертикально объединить ячейки в таблице в документе Word, используя Aspose.Words для .NET. Следуя этому пошаговому руководству и реализуя предоставленный код C#, вы можете легко объединить ячейки по вертикали в своих таблицах.