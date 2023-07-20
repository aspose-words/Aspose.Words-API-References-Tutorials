---
title: Форматировать таблицу и ячейку с разными границами
linktitle: Форматировать таблицу и ячейку с разными границами
second_title: API обработки документов Aspose.Words
description: Пошаговое руководство по форматированию таблицы и ячейки с разными границами с помощью Aspose.Words для .NET.
type: docs
weight: 10
url: /ru/net/programming-with-table-styles-and-formatting/format-table-and-cell-with-different-borders/
---

В этом руководстве мы проведем вас через пошаговый процесс форматирования таблицы и ячейки с разными границами с помощью Aspose.Words для .NET. Мы объясним прилагаемый исходный код C# и предоставим вам исчерпывающее руководство, которое поможет вам понять и реализовать эту функцию в ваших собственных проектах. В конце этого руководства вы узнаете, как применять пользовательские границы к определенным таблицам и ячейкам в ваших документах Word с помощью Aspose.Words для .NET.

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

## Шаг 3: Создайте новую таблицу и добавьте ячейки
Чтобы начать создание таблицы, мы используем`StartTable()` метод конструктора документов, затем добавляем ячейки в таблицу с помощью`InsertCell()` метод и записываем содержимое ячеек в метод`Writeln()` метод.

```csharp
Table table = builder. StartTable();
builder. InsertCell();
// Установите границы для всей таблицы.
table.SetBorders(LineStyle.Single, 2.0, Color.Black);
// Установите отступ для этой ячейки.
builder.CellFormat.Shading.BackgroundPatternColor = Color.Red;
builder.Writeln("Cell #1");
builder. InsertCell();
// Укажите другое заполнение ячейки для второй ячейки.
builder.CellFormat.Shading.BackgroundPatternColor = Color.Green;
builder.Writeln("Cell #2");
builder. EndRow();
// Очистите форматирование ячейки от предыдущих операций.
builder.CellFormat.ClearFormatting();
builder. InsertCell();
// Создайте более толстые границы для первой ячейки в этом ряду. Это будет по-другому
// относительно границ, определенных для таблицы.
builder.CellFormat.Borders.Left.LineWidth = 4.0;
builder.CellFormat.Borders.Right.LineWidth = 4.0;
builder.CellFormat.Borders.Top.LineWidth = 4.0;
builder.CellFormat.Borders.Bottom.LineWidth = 4.0;
builder.Writeln("Cell #3");
builder. InsertCell();
builder.CellFormat.ClearFormatting();
builder.Writeln("Cell #4");
```

## Шаг 4: Сохраните документ

  измененный
Наконец, сохраните измененный документ в файл. Вы можете выбрать подходящее имя и место для выходного документа.

```csharp
doc.Save(dataDir + "WorkingWithTableStylesAndFormatting.FormatTableAndCellWithDifferentBorders.docx");
```

Поздравляем! Теперь вы отформатировали таблицу и ячейку с разными границами, используя Aspose.Words для .NET.

### Пример исходного кода для форматирования таблицы и ячейки с разными границами с использованием Aspose.Words для .NET 

```csharp
	//Путь к вашему каталогу документов
	string dataDir = "YOUR DOCUMENT DIRECTORY";

	Document doc = new Document();
	DocumentBuilder builder = new DocumentBuilder(doc);
	Table table = builder.StartTable();
	builder.InsertCell();
	//Установите границы для всей таблицы.
	table.SetBorders(LineStyle.Single, 2.0, Color.Black);
	// Установите затенение ячейки для этой ячейки.
	builder.CellFormat.Shading.BackgroundPatternColor = Color.Red;
	builder.Writeln("Cell #1");
	builder.InsertCell();
	// Укажите другое затенение ячейки для второй ячейки.
	builder.CellFormat.Shading.BackgroundPatternColor = Color.Green;
	builder.Writeln("Cell #2");
	builder.EndRow();
	// Очистите форматирование ячейки от предыдущих операций.
	builder.CellFormat.ClearFormatting();
	builder.InsertCell();
	// Создайте большие границы для первой ячейки этой строки. Это будет по-другому
	// по сравнению с границами, установленными для таблицы.
	builder.CellFormat.Borders.Left.LineWidth = 4.0;
	builder.CellFormat.Borders.Right.LineWidth = 4.0;
	builder.CellFormat.Borders.Top.LineWidth = 4.0;
	builder.CellFormat.Borders.Bottom.LineWidth = 4.0;
	builder.Writeln("Cell #3");
	builder.InsertCell();
	builder.CellFormat.ClearFormatting();
	builder.Writeln("Cell #4");
	doc.Save(dataDir + "WorkingWithTableStylesAndFormatting.FormatTableAndCellWithDifferentBorders.docx");
```

## Заключение
В этом руководстве мы узнали, как отформатировать таблицу и ячейку с разными границами, используя Aspose.Words для .NET. Следуя этому пошаговому руководству, вы сможете легко настроить границы таблиц и ячеек в документах Word. Aspose.Words предлагает мощный и гибкий API для управления и форматирования таблиц в ваших документах. Обладая этими знаниями, вы сможете улучшить визуальное представление своих документов Word и удовлетворить определенные потребности.