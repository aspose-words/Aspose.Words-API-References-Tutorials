---
title: Расширение форматирования ячеек и строк из стиля
linktitle: Расширение форматирования ячеек и строк из стиля
second_title: API обработки документов Aspose.Words
description: Пошаговое руководство по расширению форматирования ячеек и строк из стиля таблицы с помощью Aspose.Words для .NET.
type: docs
weight: 10
url: /ru/net/programming-with-table-styles-and-formatting/expand-formatting-on-cells-and-row-from-style/
---

В этом руководстве мы покажем вам пошаговый процесс расширения форматирования ячеек и строк из стиля с помощью Aspose.Words для .NET. Мы объясним прилагаемый исходный код C# и предоставим вам подробное руководство, которое поможет вам понять и реализовать эту функцию в ваших собственных проектах. В конце этого руководства вы узнаете, как применить форматирование стиля таблицы к определенным ячейкам и строкам в документах Word с помощью Aspose.Words для .NET.


## Шаг 1. Определите каталог документов.
Во-первых, вам нужно установить путь к каталогу ваших документов. Здесь находится ваш документ Word. Замените «КАТАЛОГ ВАШИХ ДОКУМЕНТОВ» на соответствующий путь.

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
```

## Шаг 2. Загрузите существующий документ
 Далее вам необходимо загрузить существующий документ Word в экземпляр`Document` сорт.

```csharp
Document doc = new Document(dataDir + "Tables.docx");
```

## Шаг 3. Перейдите к первой ячейке первой таблицы.
 Для начала нам нужно перейти к первой ячейке первой таблицы в документе. Мы используем`GetChild()` и`FirstRow.FirstCell` методы для получения ссылки на первую ячейку.

```csharp
Table table = (Table)doc.GetChild(NodeType.Table, 0, true);
Cell firstCell = table.FirstRow.FirstCell;
```

## Шаг 4. Показ исходного форматирования ячейки
Прежде чем развернуть стили таблицы, мы отображаем текущий цвет фона ячейки. Оно должно быть пустым, поскольку текущее форматирование сохраняется в стиле таблицы.

```csharp
Color cellShadingBefore = firstCell.CellFormat.Shading.BackgroundPatternColor;
Console.WriteLine("Shading cell before style expansion: " + cellShadingBefore);
```

## Шаг 5. Расширьте стили таблиц до прямого форматирования
 Теперь мы расширяем стили таблицы для прямого форматирования, используя параметры документа.`ExpandTableStylesToDirectFormatting()` метод.

```csharp
doc.ExpandTableStylesToDirectFormatting();
```

## Шаг 6. Отображение форматирования ячеек после раскрытия стиля
Теперь мы отображаем цвет фона ячейки после расширения стилей таблицы. Синий цвет фона должен быть применен из стиля таблицы.

```csharp
Color cellShadingAfter = firstCell.CellFormat.Shading.BackgroundPatternColor;
Console.WriteLine("

Shading the cell after style expansion: " + cellShadingAfter);
```

### Пример исходного кода для расширения форматирования ячеек и строк из стиля с использованием Aspose.Words для .NET 

```csharp
	//Путь к каталогу ваших документов
	string dataDir = "YOUR DOCUMENT DIRECTORY";

	Document doc = new Document(dataDir + "Tables.docx");
	// Получите первую ячейку первой таблицы в документе.
	Table table = (Table) doc.GetChild(NodeType.Table, 0, true);
	Cell firstCell = table.FirstRow.FirstCell;
	// Сначала напечатайте цвет заливки ячейки.
	// Оно должно быть пустым, поскольку текущая заливка хранится в стиле таблицы.
	Color cellShadingBefore = firstCell.CellFormat.Shading.BackgroundPatternColor;
	Console.WriteLine("Cell shading before style expansion: " + cellShadingBefore);
	doc.ExpandTableStylesToDirectFormatting();
	// Теперь напечатайте заливку ячеек после расширения стилей таблицы.
	// Синий цвет фонового узора должен был быть применен из стиля таблицы.
	Color cellShadingAfter = firstCell.CellFormat.Shading.BackgroundPatternColor;
	Console.WriteLine("Cell shading after style expansion: " + cellShadingAfter);
```

## Заключение
В этом уроке мы узнали, как расширить форматирование ячеек и строк из стиля таблицы с помощью Aspose.Words для .NET. Следуя этому пошаговому руководству, вы сможете легко применить форматирование стиля таблицы к определенным ячейкам и строкам в документах Word. Aspose.Words предлагает мощный и гибкий API для управления и форматирования таблиц в ваших документах. Обладая этими знаниями, вы сможете дополнительно настроить макет и представление ваших документов Word.