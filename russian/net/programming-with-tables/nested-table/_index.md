---
title: Вложенная таблица
linktitle: Вложенная таблица
second_title: API обработки документов Aspose.Words
description: Узнайте, как создать вложенную таблицу в документе Word с помощью Aspose.Words для .NET.
type: docs
weight: 10
url: /ru/net/programming-with-tables/nested-table/
---

В этом руководстве мы узнаем, как создать вложенную таблицу в документе Word с помощью Aspose.Words для .NET. Мы будем следовать пошаговому руководству, чтобы понять код и реализовать эту функцию. К концу этого руководства вы сможете программно создавать вложенные таблицы в документах Word.

## Шаг 1: Настройка проекта
1. Запустите Visual Studio и создайте новый проект C#.
2. Добавьте ссылку на библиотеку Aspose.Words для .NET.

## Шаг 2: Создание документа и инициализация генератора документов
Чтобы запустить Word Processing с документом и генератором документов, выполните следующие действия:

```csharp
// Путь к каталогу ваших документов
string dataDir = "YOUR DOCUMENTS DIRECTORY";

// Создание документа
Document doc = new Document();

// Инициализировать генератор документов
DocumentBuilder builder = new DocumentBuilder(doc);
```

Обязательно замените «КАТАЛОГ ВАШИХ ДОКУМЕНТОВ» на фактический путь к каталогу ваших документов.

## Шаг 3: Создание вложенной таблицы
Далее мы построим вложенную таблицу, вставив ячейки во внешнюю таблицу и создав новую таблицу внутри первой ячейки. Используйте следующий код:

```csharp
// Вставьте первую ячейку внешней таблицы
Cell cell = builder. InsertCell();
builder.Writeln("Cell 1 of the outer table");

// Вставьте вторую ячейку внешней таблицы
builder. InsertCell();
builder.Writeln("Cell 2 of the outer table");

// Завершение внешней таблицы
builder. EndTable();

// Перейти к первой ячейке внешней таблицы
builder.MoveTo(cell.FirstParagraph);

// Построить внутреннюю таблицу
builder. InsertCell();
builder.Writeln("Cell 1 of inner table");
builder. InsertCell();
builder.Writeln("Cell 2 of the inner table");

// Конец внутренней таблицы
builder. EndTable();
```

Здесь мы используем конструктор документов для вставки ячеек и содержимого во внешнюю таблицу. Затем мы перемещаем курсор построителя документа в первую ячейку внешней таблицы и создаем новую таблицу внутри, вставляя ячейки и содержимое.

## Шаг 4: Сохранение измененного документа
Наконец, нам нужно сохранить измененный документ с вложенной таблицей. Используйте следующий код:

```csharp
doc.Save(dataDir + "WorkingWithTables.NestedTable.docx");
```

Обязательно укажите правильный путь и имя файла для выходного документа.

### Пример исходного кода для вложенной таблицы с использованием Aspose.Words для .NET 

```csharp
	//Путь к вашему каталогу документов
	string dataDir = "YOUR DOCUMENT DIRECTORY";

	Document doc = new Document();
	DocumentBuilder builder = new DocumentBuilder(doc);
	Cell cell = builder.InsertCell();
	builder.Writeln("Outer Table Cell 1");
	builder.InsertCell();
	builder.Writeln("Outer Table Cell 2");
	// Этот вызов важен для создания вложенной таблицы в первой таблице.
	// Без этого вызова ячейки, вставленные ниже, будут присоединены к внешней таблице.
	builder.EndTable();
	// Перейти к первой ячейке внешней таблицы.
	builder.MoveTo(cell.FirstParagraph);
	// Постройте внутреннюю таблицу.
	builder.InsertCell();
	builder.Writeln("Inner Table Cell 1");
	builder.InsertCell();
	builder.Writeln("Inner Table Cell 2");
	builder.EndTable();
	doc.Save(dataDir + "WorkingWithTables.NestedTable.docx");
```

## Заключение
В этом руководстве мы узнали, как создать вложенную таблицу в документе Word с помощью Aspose.Words для .NET. Следуя этому пошаговому руководству и реализуя предоставленный код C#, вы можете программно создавать вложенные таблицы в соответствии с вашими конкретными потребностями в документах Word.
