---
title: Повторять строки на последующих страницах
linktitle: Повторять строки на последующих страницах
second_title: API обработки документов Aspose.Words
description: Узнайте, как повторять строки таблицы на последующих страницах документа Word с помощью Aspose.Words для .NET.
type: docs
weight: 10
url: /ru/net/programming-with-tables/repeat-rows-on-subsequent-pages/
---

В этом уроке мы научимся повторять строки таблицы на последующих страницах документа Word с помощью Aspose.Words для .NET. Мы будем следовать пошаговому руководству, чтобы понять код и реализовать эту функцию. К концу этого руководства вы сможете указывать строки, которые будут повторяться на последующих страницах таблицы в документах Word.

## Шаг 1: Настройка проекта
1. Запустите Visual Studio и создайте новый проект C#.
2. Добавьте ссылку на библиотеку Aspose.Words для .NET.

## Шаг 2. Создание документа и инициализация генератора документов
Чтобы запустить обработку слов с помощью документа и генератора документов, выполните следующие действия:

```csharp
// Путь к каталогу ваших документов
string dataDir = "YOUR DOCUMENTS DIRECTORY";

// Создание документа
Document doc = new Document();

// Инициализировать генератор документов
DocumentBuilder builder = new DocumentBuilder(doc);
```

Обязательно замените «КАТАЛОГ ВАШИХ ДОКУМЕНТОВ» фактическим путем к каталогу ваших документов.

## Шаг 3. Построение таблицы с повторяющимися строками.
Далее построим таблицу с повторяющимися строками на последующих страницах. Используйте следующий код:

```csharp
// Начало таблицы
builder. StartTable();

// Настройка параметров первой строки (строки заголовка)
builder.RowFormat.HeadingFormat = true;
builder.ParagraphFormat.Alignment = ParagraphAlignment.Center;
builder.CellFormat.Width = 100;

// Вставьте первую ячейку первой строки
builder. InsertCell();
builder.Writeln("Header line 1");
builder. EndRow();

// Вставьте вторую ячейку первой строки
builder. InsertCell();
builder.Writeln("Header line 2");
builder. EndRow();

// Настройте параметры следующих строк
builder.CellFormat.Width = 50;
builder.ParagraphFormat.ClearFormatting();

// Цикл для вставки ячеек в следующие строки
for (int i = 0; i < 50; i++)
{
builder. InsertCell();
builder.RowFormat.HeadingFormat = false;
builder.Write("Text column 1");
builder. InsertCell();
builder.Write("Text column 2");
builder. EndRow();
}

// Конец таблицы
builder. EndTable();
```

 Здесь мы используем построитель документов для построения таблицы с двумя строками заголовков и несколькими строками данных.`RowFormat.HeadingFormat`Параметры используются для обозначения строк заголовка, которые должны повторяться на последующих страницах.

## Шаг 4. Сохранение измененного документа.
Наконец США

  необходимо сохранить измененный документ с повторением строк заголовка на последующих страницах таблицы. Используйте следующий код:

```csharp
doc.Save(dataDir + "WorkingWithTables.RepeatRowsOnSubsequentPages.docx");
```

Обязательно укажите правильный путь и имя файла для выходного документа.

### Пример исходного кода для повторения строк на последующих страницах с использованием Aspose.Words для .NET 

```csharp
// Путь к каталогу ваших документов
string dataDir = "YOUR DOCUMENT DIRECTORY";

Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
builder.StartTable();
builder.RowFormat.HeadingFormat = true;
builder.ParagraphFormat.Alignment = ParagraphAlignment.Center;
builder.CellFormat.Width = 100;
builder.InsertCell();
builder.Writeln("Heading row 1");
builder.EndRow();
builder.InsertCell();
builder.Writeln("Heading row 2");
builder.EndRow();
builder.CellFormat.Width = 50;
builder.ParagraphFormat.ClearFormatting();
for (int i = 0; i < 50; i++)
{
	builder.InsertCell();
	builder.RowFormat.HeadingFormat = false;
	builder.Write("Column 1 Text");
	builder.InsertCell();
	builder.Write("Column 2 Text");
	builder.EndRow();
}
doc.Save(dataDir + "WorkingWithTables.RepeatRowsOnSubsequentPages.docx");
```

## Заключение
В этом уроке мы научились повторять строки таблицы на последующих страницах документа Word с помощью Aspose.Words для .NET. Следуя этому пошаговому руководству и реализовав предоставленный код C#, вы можете указать, какие строки следует повторять в соответствии с вашими конкретными потребностями в документах Word.