---
title: Создать стиль таблицы
linktitle: Создать стиль таблицы
second_title: API обработки документов Aspose.Words
description: Пошаговое руководство по созданию пользовательского стиля таблицы с помощью Aspose.Words для .NET.
type: docs
weight: 10
url: /ru/net/programming-with-table-styles-and-formatting/create-table-style/
---

В этом руководстве мы пошагово проведем вас через процесс создания стиля таблицы с помощью Aspose.Words для .NET. Мы объясним прилагаемый исходный код C# и предоставим вам исчерпывающее руководство, которое поможет вам понять и реализовать эту функцию в ваших собственных проектах. В конце этого руководства вы узнаете, как создать собственный стиль для таблиц в документах Word с помощью Aspose.Words для .NET.

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
Чтобы начать создание таблицы, мы используем`StartTable()` метод конструктора документов, затем добавляем ячейки в таблицу с помощью`InsertCell()` метод и записываем содержимое ячеек в метод`Write()` метод.

```csharp
Table table = builder. StartTable();
builder. InsertCell();
builder.Write("Name");
builder. InsertCell();
builder.Write("Value");
builder. EndRow();
builder. InsertCell();
builder. InsertCell();
builder. EndTable();
```

## Шаг 4: Создайте стиль таблицы
 Теперь мы можем создать стиль таблицы, используя`TableStyle` класс и`Add()` метод из документа`s `Коллекция стилей. Мы определяем свойства стиля, такие как границы, поля и отступы.

```csharp
TableStyle tableStyle = (TableStyle)doc.Styles.Add(StyleType.Table, "MyTableStyle1");
tableStyle.Borders.LineStyle = LineStyle.Double;
tableStyle.Borders.LineWidth = 1;
tableStyle. LeftPadding = 18;
tableStyle. RightPadding = 18;
tableStyle.TopPadding = 12;
tableStyle.BottomPadding = 12;
```

## Шаг 5: Примените стиль таблицы к таблице
 Наконец, мы применяем стиль таблицы, который мы создали, к таблице, используя`Style` свойство таблицы.

```csharp
table.Style = tableStyle;
```

## Шаг 6: Сохраните измененный документ
Наконец, сохраните измененный документ в файл. Вы можете выбрать подходящее имя и место для выходного документа.

```csharp


doc.Save(dataDir + "WorkingWithTableStylesAndFormatting.CreateTableStyle.docx");
```

Поздравляем! Теперь вы создали собственный стиль для своей таблицы, используя Aspose.Words для .NET.

### Пример исходного кода для создания стиля таблицы с использованием Aspose.Words для .NET 

```csharp
	//Путь к вашему каталогу документов
	string dataDir = "YOUR DOCUMENT DIRECTORY";

	Document doc = new Document();
	DocumentBuilder builder = new DocumentBuilder(doc);
	Table table = builder.StartTable();
	builder.InsertCell();
	builder.Write("Name");
	builder.InsertCell();
	builder.Write("Value");
	builder.EndRow();
	builder.InsertCell();
	builder.InsertCell();
	builder.EndTable();
	TableStyle tableStyle = (TableStyle) doc.Styles.Add(StyleType.Table, "MyTableStyle1");
	tableStyle.Borders.LineStyle = LineStyle.Double;
	tableStyle.Borders.LineWidth = 1;
	tableStyle.LeftPadding = 18;
	tableStyle.RightPadding = 18;
	tableStyle.TopPadding = 12;
	tableStyle.BottomPadding = 12;
	table.Style = tableStyle;
	doc.Save(dataDir + "WorkingWithTableStylesAndFormatting.CreateTableStyle.docx");
```

## Заключение
В этом руководстве мы узнали, как создать стиль таблицы с помощью Aspose.Words для .NET. Следуя этому пошаговому руководству, вы сможете легко настроить стиль таблиц в документах Word. Aspose.Words предлагает мощный и гибкий API для управления и форматирования таблиц в ваших документах. Обладая этими знаниями, вы сможете улучшить визуальное представление своих документов Word и удовлетворить определенные потребности.