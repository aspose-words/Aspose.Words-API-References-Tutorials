---
title: Создайте таблицу со стилем
linktitle: Создайте таблицу со стилем
second_title: Справочник по API Aspose.Words для .NET
description: Пошаговое руководство по созданию таблицы с пользовательским стилем с помощью Aspose.Words для .NET.
type: docs
weight: 10
url: /ru/net/programming-with-table-styles-and-formatting/build-table-with-style/
---

В этом руководстве мы пошагово проведем вас через процесс создания стилизованной таблицы с помощью Aspose.Words для .NET. Мы объясним прилагаемый исходный код C# и предоставим вам исчерпывающее руководство, которое поможет вам понять и реализовать эту функцию в ваших собственных проектах. В конце этого руководства вы узнаете, как создать таблицу с собственным стилем в документах Word с помощью Aspose.Words для .NET.

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

## Шаг 3: Создайте новую таблицу и вставьте ячейку
 Чтобы начать построение таблицы, мы используем`StartTable()` метод конструктора документов, затем вставляем ячейку в таблицу с помощью`InsertCell()` метод.

```csharp
Table table = builder. StartTable();
builder. InsertCell();
```

## Шаг 4: Определите стиль таблицы
 Теперь мы можем установить стиль таблицы с помощью`StyleIdentifier` свойство. В этом примере мы используем стиль «MediumShading1Accent1».

```csharp
table.StyleIdentifier = StyleIdentifier.MediumShading1Accent1;
```

## Шаг 5: Примените параметры стиля к таблице
 Мы можем указать, какие характеристики должны быть отформатированы стилем, используя`StyleOptions`свойство массива. В этом примере мы применяем следующие параметры: «FirstColumn», «RowBands» и «FirstRow».

```csharp
table.StyleOptions = TableStyleOptions.FirstColumn | TableStyleOptions.RowBands | TableStyleOptions.FirstRow;
```

## Шаг 6. Автоматическая настройка размера таблицы
 Для автоматической настройки размера массива в зависимости от его содержимого мы используем функцию`AutoFit()` метод с`AutoFitBehavior.AutoFitToContents` поведение.

```csharp
table. AutoFit(AutoFitBehavior.AutoFitToContents);
```

## Шаг 7. Добавьте содержимое в ячейки
 Теперь мы можем добавлять содержимое в ячейки с помощью`Writeln()` и`InsertCell()` методы конструктора документов. В этом примере мы добавляем заголовки для «Товар» и «Количество (

кг)» и соответствующие данные.

```csharp
builder.Writeln("Item");
builder.CellFormat.RightPadding = 40;
builder. InsertCell();
builder. Writen("Quantity (kg)");
builder. EndRow();
builder. InsertCell();
builder.Writeln("Apples");
builder. InsertCell();
builder.Writeln("20");
builder. EndRow();
builder. InsertCell();
builder.Writeln("Bananas");
builder. InsertCell();
builder. Writen("40");
builder. EndRow();
builder. InsertCell();
builder.Writeln("Carrots");
builder. InsertCell();
builder.Writeln("50");
builder. EndRow();
```

## Шаг 8: Сохраните измененный документ
Наконец, мы сохраняем измененный документ в файл. Вы можете выбрать подходящее имя и место для выходного документа.

```csharp
doc.Save(dataDir + "WorkingWithTableStylesAndFormatting.BuildTableWithStyle.docx");
```

Поздравляем! Теперь вы создали таблицу с пользовательским стилем, используя Aspose.Words для .NET.

### Пример исходного кода для создания таблицы со стилем с использованием Aspose.Words для .NET 

```csharp
	// Путь к вашему каталогу документов
	string dataDir = "YOUR DOCUMENT DIRECTORY";

	Document doc = new Document();
	DocumentBuilder builder = new DocumentBuilder(doc);
	Table table = builder.StartTable();
	// Мы должны вставить хотя бы одну строку, прежде чем устанавливать форматирование таблицы.
	builder.InsertCell();
	// Установите используемый стиль таблицы на основе уникального идентификатора стиля.
	table.StyleIdentifier = StyleIdentifier.MediumShading1Accent1;
	// Примените, какие функции должны быть отформатированы стилем.
	table.StyleOptions =
		TableStyleOptions.FirstColumn | TableStyleOptions.RowBands | TableStyleOptions.FirstRow;
	table.AutoFit(AutoFitBehavior.AutoFitToContents);
	builder.Writeln("Item");
	builder.CellFormat.RightPadding = 40;
	builder.InsertCell();
	builder.Writeln("Quantity (kg)");
	builder.EndRow();
	builder.InsertCell();
	builder.Writeln("Apples");
	builder.InsertCell();
	builder.Writeln("20");
	builder.EndRow();
	builder.InsertCell();
	builder.Writeln("Bananas");
	builder.InsertCell();
	builder.Writeln("40");
	builder.EndRow();
	builder.InsertCell();
	builder.Writeln("Carrots");
	builder.InsertCell();
	builder.Writeln("50");
	builder.EndRow();
	doc.Save(dataDir + "WorkingWithTableStylesAndFormatting.BuildTableWithStyle.docx");
```

## Заключение
В этом руководстве мы узнали, как создать стилизованную таблицу с помощью Aspose.Words для .NET. Следуя этому пошаговому руководству, вы сможете легко настроить стиль таблиц в документах Word. Aspose.Words предлагает мощный и гибкий API для управления и форматирования таблиц в ваших документах. Обладая этими знаниями, вы сможете улучшить визуальное представление своих документов Word и удовлетворить определенные потребности.