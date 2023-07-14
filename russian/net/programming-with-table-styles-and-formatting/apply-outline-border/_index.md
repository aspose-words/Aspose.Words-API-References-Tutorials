---
title: Применить границу контура
linktitle: Применить границу контура
second_title: API обработки документов Aspose.Words
description: Пошаговое руководство по применению границы контура к таблице с помощью Aspose.Words для .NET.
type: docs
weight: 10
url: /ru/net/programming-with-table-styles-and-formatting/apply-outline-border/
---

В этом руководстве мы пошагово проведем вас через процесс применения границы контура к таблице с помощью Aspose.Words для .NET. Мы объясним прилагаемый исходный код C# и предоставим вам исчерпывающее руководство, которое поможет вам понять и реализовать эту функцию в ваших собственных проектах. К концу этого руководства у вас будет четкое представление о том, как манипулировать границами таблиц в ваших документах Word с помощью Aspose.Words для .NET.

## Шаг 1: Определите каталог документов
Во-первых, вам нужно указать путь к каталогу ваших документов. Здесь хранится ваш документ Word. Замените «КАТАЛОГ ВАШИХ ДОКУМЕНТОВ» на соответствующий путь.

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
```

## Шаг 2: Загрузите документ
 Далее вам нужно загрузить документ Word в экземпляр`Document` сорт.

```csharp
Document doc = new Document(dataDir + "Tables.docx");
```

## Шаг 3: Доступ к таблице
 Чтобы применить границу контура, нам нужно получить доступ к таблице в документе.`Table` class представляет таблицу в Aspose.Words.

```csharp
Table table = (Table)doc.GetChild(NodeType.Table, 0, true);
```

## Шаг 4. Выровняйте таблицу по центру страницы
 Теперь мы можем выровнять таблицу по центру страницы с помощью`Alignment` свойство таблицы.

```csharp
table. Alignment = Table Alignment. Center;
```

## Шаг 5. Сотрите существующие границы таблицы
Чтобы начать с новой границы контура, нам сначала нужно стереть все существующие границы из таблицы. Это можно сделать с помощью`ClearBorders()` метод.

```csharp
table. ClearBorders();
```

## Шаг 6: Определите зеленую рамку вокруг таблицы
 Теперь мы можем установить зеленую рамку вокруг таблицы, используя`SetBorder()` метод для каждой стороны стола. В этом примере мы используем границу типа «Одинарная» толщиной 1,5 пункта и зеленого цвета.

```csharp
table.SetBorder(BorderType.Left, LineStyle.Single, 1.5, Color.Green, true);
table.SetBorder(BorderType.Right, LineStyle.Single, 1.5, Color.Green, true);
table.SetBorder(BorderType.Top, LineStyle.Single, 1.5, Color.Green, true);
table.SetBorder(BorderType.Bottom, LineStyle.Single, 1.5, Color.Green, true);
```

## Шаг 7: Заполните ячейки фоновым цветом
Чтобы улучшить визуальное представление таблицы, мы можем заполнить ячейки фоновым цветом.

идея. В этом примере мы используем светло-зеленый цвет.

```csharp
table.SetShading(TextureIndex.TextureSolid, Color.LightGreen, Color.Empty);
```

## Шаг 8: Сохраните измененный документ
Наконец, мы сохраняем измененный документ в файл. Вы можете выбрать подходящее имя и место для выходного документа.

```csharp
doc.Save(dataDir + "WorkingWithTableStylesAndFormatting.ApplyOutlineBorder.docx");
```

Поздравляем! Теперь вы применили границу контура к таблице, используя Aspose.Words для .NET.

### Пример исходного кода для применения границы контура с использованием Aspose.Words для .NET 

```csharp
	//Путь к вашему каталогу документов
	string dataDir = "YOUR DOCUMENT DIRECTORY";

	Document doc = new Document(dataDir + "Tables.docx");
	Table table = (Table) doc.GetChild(NodeType.Table, 0, true);
	// Выровняйте таблицу по центру страницы.
	table.Alignment = TableAlignment.Center;
	//Удалите все существующие границы из таблицы.
	table.ClearBorders();
	// Установите зеленую рамку вокруг стола, но не внутри.
	table.SetBorder(BorderType.Left, LineStyle.Single, 1.5, Color.Green, true);
	table.SetBorder(BorderType.Right, LineStyle.Single, 1.5, Color.Green, true);
	table.SetBorder(BorderType.Top, LineStyle.Single, 1.5, Color.Green, true);
	table.SetBorder(BorderType.Bottom, LineStyle.Single, 1.5, Color.Green, true);
	// Заполните ячейки светло-зеленым сплошным цветом.
	table.SetShading(TextureIndex.TextureSolid, Color.LightGreen, Color.Empty);
	doc.Save(dataDir + "WorkingWithTableStylesAndFormatting.ApplyOutlineBorder.docx");
```

## Заключение
В этом руководстве мы узнали, как применить границу контура к таблице с помощью Aspose.Words для .NET. Следуя этому пошаговому руководству, вы сможете легко интегрировать эту функциональность в свои проекты C#. Управление форматированием таблиц является важным аспектом обработки документов, и Aspose.Words предлагает для этого мощный и гибкий API. Обладая этими знаниями, вы сможете улучшить визуальное представление своих документов Word и выполнить определенные требования.