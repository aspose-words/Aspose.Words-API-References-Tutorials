---
title: Вставить таблицу напрямую
linktitle: Вставить таблицу напрямую
second_title: API обработки документов Aspose.Words
description: Узнайте, как вставить таблицу непосредственно в документ Word с помощью Aspose.Words для .NET.
type: docs
weight: 10
url: /ru/net/programming-with-tables/insert-table-directly/
---

В этом уроке мы узнаем, как напрямую вставить таблицу в документ Word с помощью Aspose.Words для .NET. Мы будем следовать пошаговому руководству, чтобы понять код и реализовать эту функцию. К концу этого руководства вы сможете программно вставлять таблицы непосредственно в документы Word.

## Шаг 1: Настройка проекта
1. Запустите Visual Studio и создайте новый проект C#.
2. Добавьте ссылку на библиотеку Aspose.Words для .NET.

## Шаг 2. Создание документа и таблицы
Чтобы запустить обработку слов с массивом, нам нужно создать новый документ и инициализировать массив. Следуй этим шагам:

```csharp
// Путь к каталогу ваших документов
string dataDir = "YOUR DOCUMENTS DIRECTORY";

// Создание документа
Document doc = new Document();

//Создайте массив
Table table = new Table(doc);
doc.FirstSection.Body.AppendChild(table);
```

Обязательно замените «КАТАЛОГ ВАШИХ ДОКУМЕНТОВ» фактическим путем к каталогу ваших документов.

## Шаг 3. Создание массива
Далее мы построим таблицу, добавив строки и ячейки. В качестве примера используйте следующий код:

```csharp
// Создайте первую строку
Row row = new Row(doc);
row.RowFormat.AllowBreakAcrossPages = true;
table.AppendChild(row);

// Создайте первую ячейку
Cell cell = new Cell(doc);
cell.CellFormat.Shading.BackgroundPatternColor = Color.LightBlue;
cell.CellFormat.Width = 80;
cell.AppendChild(new Paragraph(doc));
cell.FirstParagraph.AppendChild(new Run(doc, "Text in row 1, cell 1"));
row.AppendChild(cell);

// Дублируйте ячейку для второй ячейки в строке
row.AppendChild(cell.Clone(false));
row.LastCell.AppendChild(new Paragraph(doc));
row.LastCell.FirstParagraph.AppendChild(new Run(doc, "Text in row 1, cell 2"));
```

 Здесь мы создаем строку с`AllowBreakAcrossPages` свойство установлено в`true` чтобы разрешить разрыв страницы между строками. Затем мы создаем ячейку с цветным фоном, фиксированной шириной и указанным текстовым содержимым. Затем мы дублируем эту ячейку, чтобы создать вторую ячейку в строке.

## Шаг 4. Таблица автоподбора
Мы можем применить к таблице автоматические корректировки, чтобы отформатировать ее правильно. Используйте следующий код:

```csharp
table. AutoFit(AutoFitBehavior.FixedColumnWidths);
```

Эта строка кода применяет автоподбор на основе фиксированной ширины столбца.

## Шаг 5: Регистрация

  измененный документ
Наконец, нам нужно сохранить измененный документ с непосредственной вставкой таблицы. Используйте следующий код:

```csharp
doc.Save(dataDir + "WorkingWithTables.InsertTableDirectly.docx");
```

Обязательно укажите правильный путь и имя файла для выходного документа.

### Пример исходного кода для вставки таблицы напрямую с использованием Aspose.Words для .NET 

```csharp
	//Путь к каталогу ваших документов
	string dataDir = "YOUR DOCUMENT DIRECTORY";

	Document doc = new Document();
	// Начнем с создания объекта таблицы. Обратите внимание, что мы должны передать объект документа
	//конструктору каждого узла. Это потому, что каждый создаваемый нами узел должен принадлежать
	// к какому-то документу.
	Table table = new Table(doc);
	doc.FirstSection.Body.AppendChild(table);
	// Здесь мы могли бы вызвать SureMinimum, чтобы создать для нас строки и ячейки. Этот метод используется
	// чтобы убедиться, что указанный узел действителен. В этом случае допустимая таблица должна иметь хотя бы одну строку и одну ячейку.
	// Вместо этого мы создадим строку и таблицу самостоятельно.
	// Это был бы лучший способ сделать это, если бы мы создавали таблицу внутри алгоритма.
	Row row = new Row(doc);
	row.RowFormat.AllowBreakAcrossPages = true;
	table.AppendChild(row);
	// Теперь мы можем применить любые настройки автоподбора.
	table.AutoFit(AutoFitBehavior.FixedColumnWidths);
	Cell cell = new Cell(doc);
	cell.CellFormat.Shading.BackgroundPatternColor = Color.LightBlue;
	cell.CellFormat.Width = 80;
	cell.AppendChild(new Paragraph(doc));
	cell.FirstParagraph.AppendChild(new Run(doc, "Row 1, Cell 1 Text"));
	row.AppendChild(cell);
	// Затем мы повторим процесс для других ячеек и строк таблицы.
	// Мы также можем ускорить процесс, клонируя существующие ячейки и строки.
	row.AppendChild(cell.Clone(false));
	row.LastCell.AppendChild(new Paragraph(doc));
	row.LastCell.FirstParagraph.AppendChild(new Run(doc, "Row 1, Cell 2 Text"));
	doc.Save(dataDir + "WorkingWithTables.InsertTableDirectly.docx");
```

## Заключение
В этом уроке мы узнали, как напрямую вставить таблицу в документ Word с помощью Aspose.Words для .NET. Следуя этому пошаговому руководству и реализовав предоставленный код C#, вы сможете программно вставлять таблицы непосредственно в документы Word. Эта функция позволяет создавать и настраивать таблицы в соответствии с вашими конкретными потребностями.