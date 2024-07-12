---
title: Установить форматирование строк таблицы
linktitle: Установить форматирование строк таблицы
second_title: API обработки документов Aspose.Words
description: Пошаговое руководство по настройке форматирования строк таблицы с помощью Aspose.Words для .NET.
type: docs
weight: 10
url: /ru/net/programming-with-table-styles-and-formatting/set-table-row-formatting/
---

В этом руководстве мы покажем вам пошаговый процесс настройки форматирования строк таблицы с помощью Aspose.Words для .NET. Мы объясним прилагаемый исходный код C# и предоставим вам подробное руководство, которое поможет вам понять и реализовать эту функцию в ваших собственных проектах. В конце этого руководства вы узнаете, как настроить высоту и отступы строки таблицы в документах Word с помощью Aspose.Words для .NET.

## Шаг 1. Определите каталог документов.
Во-первых, вам нужно установить путь к каталогу ваших документов. Это место, где вы хотите сохранить отредактированный документ Word. Замените «КАТАЛОГ ВАШИХ ДОКУМЕНТОВ» на соответствующий путь.

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
```

## Шаг 2. Создайте новый документ и конструктор документов.
 Далее вам нужно создать новый экземпляр`Document` класс и конструктор документа для этого документа.

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
```

## Шаг 3. Создайте новую таблицу и добавьте ячейку.
Чтобы начать создавать таблицу, мы используем команду`StartTable()` метода конструктора документа, затем добавляем ячейку в таблицу с помощью метода`InsertCell()` метод.

```csharp
Table table = builder. StartTable();
builder. InsertCell();
```

## Шаг 4. Определите форматирование строки.
 Теперь мы можем установить форматирование строки, обратившись к`RowFormat` объект`DocumentBuilder` объект. Мы можем установить высоту строки и поля (отступы), используя соответствующие свойства.

```csharp
RowFormat rowFormat = builder.RowFormat;
rowFormat. Height = 100;
rowFormat.HeightRule = HeightRule.Exactly;
```

## Шаг 5. Установите поля таблицы.
 Далее мы можем установить отступы таблицы, обратившись к соответствующим свойствам таблицы.`Table` объект. Эти поля будут применены ко всем строкам таблицы.

```csharp
table. LeftPadding = 30;
table. RightPadding = 30;
table. TopPadding = 30;
table. BottomPadding = 30;
```

## Шаг 6. Добавьте содержимое в строку
 Наконец, мы можем добавить содержимое в строку, используя конструктор документов.`Writeln()` метод.

```csharp
builder.Writeln("I'm a beautifully formatted line.");
```

## Шаг 7: Завершите таблицу и сохраните документ.
В

 конец, мы завершаем создание таблицы с помощью`EndRow()`и`EndTable()` метод, затем сохраняем измененный документ в файл.

```csharp
builder. EndRow();
builder. EndTable();
doc.Save(dataDir + "WorkingWithTableStylesAndFormatting.DocumentBuilderSetTableRowFormatting.docx");
```

### Пример исходного кода для установки форматирования строк таблицы с использованием Aspose.Words для .NET 

```csharp
	// Путь к каталогу ваших документов
	string dataDir = "YOUR DOCUMENT DIRECTORY";

	Document doc = new Document();
	DocumentBuilder builder = new DocumentBuilder(doc);
	Table table = builder.StartTable();
	builder.InsertCell();
	RowFormat rowFormat = builder.RowFormat;
	rowFormat.Height = 100;
	rowFormat.HeightRule = HeightRule.Exactly;
	// Эти свойства форматирования задаются для таблицы и применяются ко всем ее строкам.
	table.LeftPadding = 30;
	table.RightPadding = 30;
	table.TopPadding = 30;
	table.BottomPadding = 30;
	builder.Writeln("I'm a wonderful formatted row.");
	builder.EndRow();
	builder.EndTable();
	doc.Save(dataDir + "WorkingWithTableStylesAndFormatting.DocumentBuilderSetTableRowFormatting.docx");
```

## Заключение
В этом уроке мы узнали, как настроить форматирование строк таблицы с помощью Aspose.Words для .NET. Следуя этому пошаговому руководству, вы сможете легко настроить высоту строк и поля таблицы в документах Word. Aspose.Words предлагает мощный и гибкий API для управления и форматирования таблиц в ваших документах. Обладая этими знаниями, вы сможете настроить визуальное расположение таблиц в соответствии с вашими конкретными потребностями.