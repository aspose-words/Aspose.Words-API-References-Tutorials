---
title: Горизонтальное слияние
linktitle: Горизонтальное слияние
second_title: API обработки документов Aspose.Words
description: Узнайте, как горизонтально объединить ячейки в таблице Word с помощью Aspose.Words для .NET.
type: docs
weight: 10
url: /ru/net/programming-with-tables/horizontal-merge/
---

В этом уроке мы научимся горизонтально объединять ячейки таблицы в документе Word с помощью Aspose.Words для .NET. Мы будем следовать пошаговому руководству, чтобы понять код и реализовать эту функцию. К концу этого руководства вы сможете программно объединять ячейки в таблицах Word по горизонтали.

## Шаг 1: Настройка проекта
1. Запустите Visual Studio и создайте новый проект C#.
2. Добавьте ссылку на библиотеку Aspose.Words для .NET.

## Шаг 2. Создание документа и инициализация генератора документов
Чтобы запустить обработку слов с таблицей и ячейками, нам нужно создать новый документ и инициализировать генератор документов. Следуй этим шагам:

```csharp
// Путь к каталогу ваших документов
string dataDir = "YOUR DOCUMENTS DIRECTORY";

// Создайте документ и инициализируйте генератор документов.
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
```

Обязательно замените «КАТАЛОГ ВАШИХ ДОКУМЕНТОВ» фактическим путем к каталогу ваших документов.

## Шаг 3: Построение таблицы с горизонтальным объединением ячеек
Далее мы построим таблицу и применим горизонтальное слияние ячеек, используя свойства, предоставляемые Aspose.Words для .NET. Используйте следующий код:

```csharp
builder. InsertCell();
builder.CellFormat.HorizontalMerge = CellMerge.First;
builder.Write("Text in merged cells.");
builder. InsertCell();
builder.CellFormat.HorizontalMerge = CellMerge.Previous;
// Эта ячейка объединена с предыдущей и должна быть пустой.
builder. EndRow();

builder. InsertCell();
builder.CellFormat.HorizontalMerge = CellMerge.None;
builder.Write("Text in a cell.");
builder. InsertCell();
builder.Write("Text in another cell.");
builder. EndRow();
builder. EndTable();
```

 Здесь мы используем построитель документов для построения таблицы и установки свойств горизонтального слияния ячеек. Мы используем`HorizontalMerge` собственность`CellFormat` объект, чтобы указать тип горизонтального слияния, применяемый к каждой ячейке. С использованием`CellMerge.First` мы объединяем первую ячейку со следующей, используя при этом`CellMerge.Previous` мы объединяем текущую ячейку с предыдущей ячейкой.`CellMerge.None` указывает, что ячейку не следует объединять.

## Шаг 4. Сохранение измененного документа.
Наконец, нам нужно сохранить измененный документ со объединенными по горизонтали ячейками. Используйте следующий код:

```csharp
doc.Save(data

Dir + "WorkingWithTables.HorizontalMerge.docx");
```

Обязательно укажите правильный путь и имя файла для выходного документа.

### Пример исходного кода для горизонтального слияния с использованием Aspose.Words для .NET 

```csharp
	// Путь к каталогу ваших документов
	string dataDir = "YOUR DOCUMENT DIRECTORY";

	Document doc = new Document();
	DocumentBuilder builder = new DocumentBuilder(doc);
	builder.InsertCell();
	builder.CellFormat.HorizontalMerge = CellMerge.First;
	builder.Write("Text in merged cells.");
	builder.InsertCell();
	// Эта ячейка объединяется с предыдущей и должна быть пустой.
	builder.CellFormat.HorizontalMerge = CellMerge.Previous;
	builder.EndRow();
	builder.InsertCell();
	builder.CellFormat.HorizontalMerge = CellMerge.None;
	builder.Write("Text in one cell.");
	builder.InsertCell();
	builder.Write("Text in another cell.");
	builder.EndRow();
	builder.EndTable();
	doc.Save(dataDir + "WorkingWithTables.HorizontalMerge.docx");
```

## Заключение
В этом уроке мы узнали, как горизонтально объединить ячейки таблицы в документе Word с помощью Aspose.Words для .NET. Следуя этому пошаговому руководству и реализовав предоставленный код C#, вы можете программно применять горизонтальное слияние ячеек в таблицах Word. Эта функция позволяет создавать более сложные макеты таблиц и лучше организовывать данные.