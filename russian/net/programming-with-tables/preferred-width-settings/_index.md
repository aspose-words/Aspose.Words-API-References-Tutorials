---
title: Предпочтительные настройки ширины
linktitle: Предпочтительные настройки ширины
second_title: Справочник по API Aspose.Words для .NET
description: Узнайте, как установить предпочтительную ширину ячеек таблицы в документе Word с помощью Aspose.Words для .NET.
type: docs
weight: 10
url: /ru/net/programming-with-tables/preferred-width-settings/
---

В этом руководстве мы узнаем, как установить предпочтительные параметры ширины для ячеек таблицы в документе Word, используя Aspose.Words для .NET. Мы будем следовать пошаговому руководству, чтобы понять код и реализовать эту функцию. К концу этого руководства вы сможете указать различную предпочтительную ширину для ячеек таблицы в документах Word.

## Шаг 1: Настройка проекта
1. Запустите Visual Studio и создайте новый проект C#.
2. Добавьте ссылку на библиотеку Aspose.Words для .NET.

## Шаг 2: Создание документа и инициализация генератора документов
Чтобы начать работу с документом и генератором документов, выполните следующие действия:

```csharp
// Путь к каталогу ваших документов
string dataDir = "YOUR DOCUMENTS DIRECTORY";

// Создание документа
Document doc = new Document();

// Инициализировать генератор документов
DocumentBuilder builder = new DocumentBuilder(doc);
```

Обязательно замените «КАТАЛОГ ВАШИХ ДОКУМЕНТОВ» на фактический путь к каталогу ваших документов.

## Шаг 3: Создание таблицы с предпочтительной шириной
Далее мы построим таблицу с тремя ячейками с разной предпочтительной шириной. Используйте следующий код:

```csharp
// Начало таблицы
builder. StartTable();

// Вставьте ячейку абсолютного размера
builder. InsertCell();
builder.CellFormat.PreferredWidth = PreferredWidth.FromPoints(40);
builder.CellFormat.Shading.BackgroundPatternColor = Color.LightYellow;
builder.Writeln("Cell with a width of 40 points");

// Вставьте ячейку относительного размера (в процентах)
builder. InsertCell();
builder.CellFormat.PreferredWidth = PreferredWidth.FromPercent(20);
builder.CellFormat.Shading.BackgroundPatternColor = Color.LightBlue;
builder.Writeln("Cell with 20% width");

// Вставить ячейку с автоматическим размером
builder. InsertCell();
builder.CellFormat.PreferredWidth = PreferredWidth.Auto;
builder.CellFormat.Shading.BackgroundPatternColor = Color.LightGreen;
builder.Writeln("Auto-size cell. The size of this cell is calculated from the preferred width of the table. In this case, the cell will fill the rest of the available space.");

// Конец таблицы
builder. EndTable();
```

Здесь мы используем конструктор документов для построения таблицы с тремя ячейками. Первая ячейка имеет предпочтительную ширину 40 пунктов, вторая ячейка имеет предпочтительную ширину 20% ширины таблицы, а третья ячейка имеет автоматическую предпочтительную ширину, которая настраивается.

  в зависимости от имеющегося места.

## Шаг 4: Сохранение измененного документа
Наконец, нам нужно сохранить измененный документ с предпочтительными настройками ширины, заданными для ячеек таблицы. Используйте следующий код:

```csharp
doc.Save(dataDir + "WorkingWithTables.PreferredWidthSettings.docx");
```

Обязательно укажите правильный путь и имя файла для выходного документа.

### Пример исходного кода для настроек предпочтительной ширины с использованием Aspose.Words для .NET 

```csharp
	// Путь к вашему каталогу документов
	string dataDir = "YOUR DOCUMENT DIRECTORY";

	Document doc = new Document();
	DocumentBuilder builder = new DocumentBuilder(doc);
	// Вставьте строку таблицы, состоящую из трех ячеек с разной предпочтительной шириной.
	builder.StartTable();
	// Вставьте ячейку абсолютного размера.
	builder.InsertCell();
	builder.CellFormat.PreferredWidth = PreferredWidth.FromPoints(40);
	builder.CellFormat.Shading.BackgroundPatternColor = Color.LightYellow;
	builder.Writeln("Cell at 40 points width");
	// Вставьте ячейку относительного (процентного) размера.
	builder.InsertCell();
	builder.CellFormat.PreferredWidth = PreferredWidth.FromPercent(20);
	builder.CellFormat.Shading.BackgroundPatternColor = Color.LightBlue;
	builder.Writeln("Cell at 20% width");
	// Вставьте ячейку с автоматическим размером.
	builder.InsertCell();
	builder.CellFormat.PreferredWidth = PreferredWidth.Auto;
	builder.CellFormat.Shading.BackgroundPatternColor = Color.LightGreen;
	builder.Writeln(
		"Cell automatically sized. The size of this cell is calculated from the table preferred width.");
	builder.Writeln("In this case the cell will fill up the rest of the available space.");
	doc.Save(dataDir + "WorkingWithTables.PreferredWidthSettings.docx");
```

## Заключение
В этом руководстве мы узнали, как установить предпочтительные параметры ширины для ячеек таблицы в документе Word с помощью Aspose.Words для .NET. Следуя этому пошаговому руководству и реализуя предоставленный код C#, вы можете настроить ширину ячеек таблицы в соответствии со своими потребностями в документах Word.