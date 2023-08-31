---
title: Установить форматирование строки таблицы
linktitle: Установить форматирование строки таблицы
second_title: API обработки документов Aspose.Words
description: Пошаговое руководство по настройке форматирования строк таблицы с помощью Aspose.Words для .NET.
type: docs
weight: 10
url: /ru/net/programming-with-table-styles-and-formatting/set-table-row-formatting/
---

В этом руководстве мы пошагово проведем вас через процесс настройки форматирования строк таблицы с помощью Aspose.Words для .NET. Мы объясним прилагаемый исходный код C# и предоставим вам исчерпывающее руководство, которое поможет вам понять и реализовать эту функцию в ваших собственных проектах. В конце этого руководства вы узнаете, как настроить высоту и отступы строки таблицы в документах Word с помощью Aspose.Words для .NET.

## Шаг 1: Определите каталог документов
Во-первых, вам нужно указать путь к каталогу ваших документов. Это место, где вы хотите сохранить отредактированный документ Word. Замените «КАТАЛОГ ВАШИХ ДОКУМЕНТОВ» на соответствующий путь.

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
```

## Шаг 2: Создайте новый документ и построитель документов
 Далее необходимо создать новый экземпляр`Document` класс и конструктор документа для этого документа.

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
```

## Шаг 3: Создайте новую таблицу и добавьте ячейку
Чтобы начать создание таблицы, мы используем`StartTable()` метод конструктора документа, то мы добавляем ячейку в таблицу с помощью метода`InsertCell()` метод.

```csharp
Table table = builder. StartTable();
builder. InsertCell();
```

## Шаг 4: Определите формат строки
 Теперь мы можем установить форматирование строки, обратившись к`RowFormat` объект`DocumentBuilder` объект. Мы можем установить высоту строки и поля (отступы), используя соответствующие свойства.

```csharp
RowFormat rowFormat = builder.RowFormat;
rowFormat. Height = 100;
rowFormat.HeightRule = HeightRule.Exactly;
```

## Шаг 5: Установите поля таблицы
 Затем мы можем установить отступы таблицы, обратившись к соответствующим свойствам`Table` объект. Эти поля будут применяться ко всем строкам таблицы.

```csharp
table. LeftPadding = 30;
table. RightPadding = 30;
table. TopPadding = 30;
table. BottomPadding = 30;
```

## Шаг 6. Добавьте содержимое в строку
 Наконец, мы можем добавить содержимое в строку с помощью конструктора документов.`Writeln()` метод.

```csharp
builder.Writeln("I'm a beautifully formatted line.");
```

## Шаг 7: Завершите таблицу и сохраните документ
В

 конец, мы заканчиваем создание таблицы с помощью`EndRow()` и`EndTable()` метод, затем мы сохраняем измененный документ в файл.

```csharp
builder. EndRow();
builder. EndTable();
doc.Save(dataDir + "WorkingWithTableStylesAndFormatting.DocumentBuilderSetTableRowFormatting.docx");
```

### Пример исходного кода для настройки форматирования строк таблицы с использованием Aspose.Words для .NET 

```csharp
	//Путь к вашему каталогу документов
	string dataDir = "YOUR DOCUMENT DIRECTORY";

	Document doc = new Document();
	DocumentBuilder builder = new DocumentBuilder(doc);
	Table table = builder.StartTable();
	builder.InsertCell();
	RowFormat rowFormat = builder.RowFormat;
	rowFormat.Height = 100;
	rowFormat.HeightRule = HeightRule.Exactly;
	// Эти свойства форматирования задаются для таблицы и применяются ко всем строкам в таблице.
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
В этом руководстве мы узнали, как настроить форматирование строк таблицы с помощью Aspose.Words для .NET. Следуя этому пошаговому руководству, вы сможете легко настроить высоту строки таблицы и поля в документах Word. Aspose.Words предлагает мощный и гибкий API для управления и форматирования таблиц в ваших документах. Обладая этими знаниями, вы можете настроить визуальный макет своих таблиц в соответствии со своими конкретными потребностями.