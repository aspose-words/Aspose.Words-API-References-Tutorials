---
title: Форматированная таблица
linktitle: Форматированная таблица
second_title: API обработки документов Aspose.Words
description: Узнайте, как создать форматированную таблицу в документе Word с помощью Aspose.Words для .NET.
type: docs
weight: 10
url: /ru/net/programming-with-tables/formatted-table/
---

В этом уроке мы узнаем, как создать форматированную таблицу в документе Word с помощью Aspose.Words для .NET. Мы будем следовать пошаговому руководству, чтобы понять код и реализовать эту функцию. В конце этого руководства вы сможете программно создавать таблицы с произвольным форматированием в своих документах Word.

## Шаг 1: Настройка проекта
1. Запустите Visual Studio и создайте новый проект C#.
2. Добавьте ссылку на библиотеку Aspose.Words для .NET.

## Шаг 2: Создание документа и инициализация генератора документов
Чтобы начать построение форматированной таблицы, нам нужно создать новый документ и инициализировать генератор документов. Следуй этим шагам:

```csharp
// Путь к каталогу ваших документов
string dataDir = "YOUR DOCUMENTS DIRECTORY";

// Создайте документ и инициализируйте генератор документов
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
```

Обязательно замените «КАТАЛОГ ВАШИХ ДОКУМЕНТОВ» на фактический путь к каталогу ваших документов.

## Шаг 3: Создание форматированной таблицы
Далее мы построим отформатированную таблицу, используя методы, предоставляемые компоновщиком документов. Используйте следующий код:

```csharp
// Начать построение массива
Table table = builder. StartTable();

// Построение строки заголовка таблицы
builder. InsertCell();
table. LeftIndent = 20.0;
builder.RowFormat.Height = 40.0;
builder.RowFormat.HeightRule = HeightRule.AtLeast;
builder.CellFormat.Shading.BackgroundPatternColor = Color.FromArgb(198, 217, 241);
builder.ParagraphFormat.Alignment = ParagraphAlignment.Center;
builder.Font.Size = 16;
builder.Font.Name = "Arial";
builder.Font.Bold = true;
builder.CellFormat.Width = 100.0;
builder.Write("Header Row,\n Cell 1");

builder. InsertCell();
builder.Write("Header Row,\n Cell 2");

builder. InsertCell();
builder.CellFormat.Width = 200.0;
builder.Write("Header Row,\n Cell 3");

builder. EndRow();

// Построение тела массива
builder.CellFormat.Shading.BackgroundPatternColor = Color.White;
builder.CellFormat.Width = 100.0;
builder.CellFormat.VerticalAlignment = CellVerticalAlignment.Center;
builder.RowFormat.Height = 30.0;
builder.RowFormat.HeightRule = HeightRule.Auto;

builder. InsertCell();
builder.Font.Size = 12;
builder.Font.Bold = false;
builder.Write("Content Line 1, Cell 1");

builder. InsertCell();
builder.Write("Content Line 1, Cell 2");

builder. InsertCell();
builder.CellFormat.Width = 200.0;
builder.Write("Content Line 1, Cell

3");

builder. EndRow();

builder. InsertCell();
builder.CellFormat.Width = 100.0;
builder.Write("Content Line 2, Cell 1");

builder. InsertCell();
builder.Write("Content Line 2, Cell 2");

builder. InsertCell();
builder.CellFormat.Width = 200.0;
builder.Write("Content Line 2, Cell 3");

builder. EndRow();

// Конец построения массива
builder. EndTable();
```

 Здесь мы используем конструктор документов для пошагового построения таблицы. Мы начинаем со звонка`StartTable()` для инициализации таблицы. Затем мы используем`InsertCell()` вставить ячейки и`Write()` чтобы добавить содержимое в каждую ячейку. Мы также используем различные свойства форматирования для определения форматирования строк таблицы, ячеек и текста.

## Шаг 4: Сохраните документ
Наконец, нам нужно сохранить документ, содержащий отформатированную таблицу. Используйте следующий код:

```csharp
// Сохраните документ
doc.Save(dataDir + "WorkingWithTables.FormattedTable.docx");
```

Обязательно укажите правильный путь и имя файла для выходного документа.

### Пример исходного кода для форматированной таблицы с использованием Aspose.Words для .NET 

```csharp
	//Путь к вашему каталогу документов
	string dataDir = "YOUR DOCUMENT DIRECTORY";

	Document doc = new Document();
	DocumentBuilder builder = new DocumentBuilder(doc);
	Table table = builder.StartTable();
	builder.InsertCell();
	// Форматирование всей таблицы должно применяться после того, как в таблице присутствует хотя бы одна строка.
	table.LeftIndent = 20.0;
	// Установите высоту и определите правило высоты для строки заголовка.
	builder.RowFormat.Height = 40.0;
	builder.RowFormat.HeightRule = HeightRule.AtLeast;
	builder.CellFormat.Shading.BackgroundPatternColor = Color.FromArgb(198, 217, 241);
	builder.ParagraphFormat.Alignment = ParagraphAlignment.Center;
	builder.Font.Size = 16;
	builder.Font.Name = "Arial";
	builder.Font.Bold = true;
	builder.CellFormat.Width = 100.0;
	builder.Write("Header Row,\n Cell 1");
	// Нам не нужно указывать ширину этой ячейки, потому что она унаследована от предыдущей ячейки.
	builder.InsertCell();
	builder.Write("Header Row,\n Cell 2");
	builder.InsertCell();
	builder.CellFormat.Width = 200.0;
	builder.Write("Header Row,\n Cell 3");
	builder.EndRow();
	builder.CellFormat.Shading.BackgroundPatternColor = Color.White;
	builder.CellFormat.Width = 100.0;
	builder.CellFormat.VerticalAlignment = CellVerticalAlignment.Center;
	// Сбросьте высоту и определите другое правило высоты для тела таблицы.
	builder.RowFormat.Height = 30.0;
	builder.RowFormat.HeightRule = HeightRule.Auto;
	builder.InsertCell();
	// Сбросить форматирование шрифта.
	builder.Font.Size = 12;
	builder.Font.Bold = false;
	builder.Write("Row 1, Cell 1 Content");
	builder.InsertCell();
	builder.Write("Row 1, Cell 2 Content");
	builder.InsertCell();
	builder.CellFormat.Width = 200.0;
	builder.Write("Row 1, Cell 3 Content");
	builder.EndRow();
	builder.InsertCell();
	builder.CellFormat.Width = 100.0;
	builder.Write("Row 2, Cell 1 Content");
	builder.InsertCell();
	builder.Write("Row 2, Cell 2 Content");
	builder.InsertCell();
	builder.CellFormat.Width = 200.0;
	builder.Write("Row 2, Cell 3 Content.");
	builder.EndRow();
	builder.EndTable();
	doc.Save(dataDir + "WorkingWithTables.FormattedTable.docx");
```

## Заключение
В этом руководстве мы узнали, как создать форматированную таблицу в документе Word с помощью Aspose.Words для .NET. Следуя этому пошаговому руководству и реализуя предоставленный код C#, вы можете программно создавать настраиваемые таблицы с определенным форматированием в своих документах Word. Эта функция позволяет вам представлять и структурировать ваши данные в визуально привлекательном и организованном виде.