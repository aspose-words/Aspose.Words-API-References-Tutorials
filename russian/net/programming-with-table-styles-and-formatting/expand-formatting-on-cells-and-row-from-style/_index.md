---
title: Развернуть форматирование ячеек и строк из стиля
linktitle: Развернуть форматирование ячеек и строк из стиля
second_title: Справочник по API Aspose.Words для .NET
description: Пошаговое руководство по расширению форматирования ячеек и строк из стиля таблицы с использованием Aspose.Words для .NET.
type: docs
weight: 10
url: /ru/net/programming-with-table-styles-and-formatting/expand-formatting-on-cells-and-row-from-style/
---

В этом руководстве мы пошагово проведем вас через процесс расширения форматирования ячеек и строк из стиля с использованием Aspose.Words для .NET. Мы объясним прилагаемый исходный код C# и предоставим вам исчерпывающее руководство, которое поможет вам понять и реализовать эту функцию в ваших собственных проектах. В конце этого руководства вы узнаете, как применять форматирование стилей таблицы к определенным ячейкам и строкам в ваших документах Word с помощью Aspose.Words для .NET.


## Шаг 1: Определите каталог документов
Во-первых, вам нужно указать путь к каталогу ваших документов. Здесь находится ваш документ Word. Замените «КАТАЛОГ ВАШИХ ДОКУМЕНТОВ» на соответствующий путь.

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
```

## Шаг 2: Загрузите существующий документ
 Далее вам нужно загрузить существующий документ Word в экземпляр`Document` сорт.

```csharp
Document doc = new Document(dataDir + "Tables.docx");
```

## Шаг 3: Перейти к первой ячейке первой таблицы
 Для начала нам нужно перейти к первой ячейке первой таблицы в документе. Мы используем`GetChild()` и`FirstRow.FirstCell` методы для получения ссылки на первую ячейку.

```csharp
Table table = (Table)doc.GetChild(NodeType.Table, 0, true);
Cell firstCell = table.FirstRow.FirstCell;
```

## Шаг 4: Показать начальное форматирование ячейки
Перед расширением стилей таблицы мы отображаем текущий цвет фона ячейки. Это должно быть пустым, потому что текущее форматирование сохраняется в стиле таблицы.

```csharp
Color cellShadingBefore = firstCell.CellFormat.Shading.BackgroundPatternColor;
Console.WriteLine("Shading cell before style expansion: " + cellShadingBefore);
```

## Шаг 5. Разверните стили таблиц для прямого форматирования
 Теперь мы расширяем стили таблиц для прямого форматирования с помощью`ExpandTableStylesToDirectFormatting()` метод.

```csharp
doc.ExpandTableStylesToDirectFormatting();
```

## Шаг 6. Отображение форматирования ячейки после расширения стиля
Теперь мы отображаем цвет фона ячейки после расширения стилей таблицы. Синий цвет фона должен быть применен из стиля таблицы.

```csharp
Color cellShadingAfter = firstCell.CellFormat.Shading.BackgroundPatternColor;
Console.WriteLine("

Shading the cell after style expansion: " + cellShadingAfter);
```

### Пример исходного кода для расширения форматирования ячеек и строки из стиля с использованием Aspose.Words для .NET 

```csharp
	// Путь к вашему каталогу документов
	string dataDir = "YOUR DOCUMENT DIRECTORY";

	Document doc = new Document(dataDir + "Tables.docx");
	// Получить первую ячейку первой таблицы в документе.
	Table table = (Table) doc.GetChild(NodeType.Table, 0, true);
	Cell firstCell = table.FirstRow.FirstCell;
	// Сначала напечатайте цвет заливки ячейки.
	// Это поле должно быть пустым, так как текущее затенение сохраняется в стиле таблицы.
	Color cellShadingBefore = firstCell.CellFormat.Shading.BackgroundPatternColor;
	Console.WriteLine("Cell shading before style expansion: " + cellShadingBefore);
	doc.ExpandTableStylesToDirectFormatting();
	// Теперь распечатайте заливку ячейки после расширения стилей таблицы.
	// Синий цвет фонового узора должен был быть применен из стиля таблицы.
	Color cellShadingAfter = firstCell.CellFormat.Shading.BackgroundPatternColor;
	Console.WriteLine("Cell shading after style expansion: " + cellShadingAfter);
```

## Заключение
В этом руководстве мы узнали, как расширить форматирование ячеек и строк из стиля таблицы с помощью Aspose.Words для .NET. Следуя этому пошаговому руководству, вы сможете легко применить форматирование табличного стиля к определенным ячейкам и строкам в ваших документах Word. Aspose.Words предлагает мощный и гибкий API для управления и форматирования таблиц в ваших документах. Обладая этими знаниями, вы можете дополнительно настроить макет и представление ваших документов Word.