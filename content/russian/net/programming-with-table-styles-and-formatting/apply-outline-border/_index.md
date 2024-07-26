---
title: Применить контурную границу
linktitle: Применить контурную границу
second_title: API обработки документов Aspose.Words
description: Пошаговое руководство по применению контурной границы к таблице с помощью Aspose.Words для .NET.
type: docs
weight: 10
url: /ru/net/programming-with-table-styles-and-formatting/apply-outline-border/
---

В этом уроке мы покажем вам пошаговый процесс применения контурной границы к таблице с помощью Aspose.Words для .NET. Мы объясним прилагаемый исходный код C# и предоставим вам подробное руководство, которое поможет вам понять и реализовать эту функцию в ваших собственных проектах. К концу этого руководства вы получите четкое представление о том, как манипулировать границами таблиц в документах Word с помощью Aspose.Words для .NET.

## Шаг 1. Определите каталог документов.
Во-первых, вам нужно установить путь к каталогу ваших документов. Здесь хранится ваш документ Word. Замените «КАТАЛОГ ВАШИХ ДОКУМЕНТОВ» на соответствующий путь.

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
```

## Шаг 2. Загрузите документ
 Далее вам необходимо загрузить документ Word в экземпляр`Document` сорт.

```csharp
Document doc = new Document(dataDir + "Tables.docx");
```

## Шаг 3: Получите доступ к таблице
 Чтобы применить контурную рамку, нам нужно получить доступ к таблице в документе.`Table` класс представляет таблицу в Aspose.Words.

```csharp
Table table = (Table)doc.GetChild(NodeType.Table, 0, true);
```

## Шаг 4. Выровняйте таблицу по центру страницы.
 Теперь мы можем выровнять таблицу по центру страницы, используя`Alignment` свойство таблицы.

```csharp
table. Alignment = Table Alignment. Center;
```

## Шаг 5. Удалите существующие границы таблицы.
Чтобы начать с новой границы контура, нам сначала нужно стереть все существующие границы таблицы. Это можно сделать с помощью`ClearBorders()` метод.

```csharp
table. ClearBorders();
```

## Шаг 6. Определите зеленую рамку вокруг стола.
 Теперь мы можем установить зеленую рамку вокруг стола, используя`SetBorder()` метод для каждой стороны таблицы. В этом примере мы используем рамку типа «Одиночная» толщиной 1,5 пункта и зеленого цвета.

```csharp
table.SetBorder(BorderType.Left, LineStyle.Single, 1.5, Color.Green, true);
table.SetBorder(BorderType.Right, LineStyle.Single, 1.5, Color.Green, true);
table.SetBorder(BorderType.Top, LineStyle.Single, 1.5, Color.Green, true);
table.SetBorder(BorderType.Bottom, LineStyle.Single, 1.5, Color.Green, true);
```

## Шаг 7. Заполните ячейки цветом фона.
Чтобы улучшить визуальное представление таблицы, мы можем заполнить ячейки фоновым цветом.

идея. В этом примере мы используем светло-зеленый цвет.

```csharp
table.SetShading(TextureIndex.TextureSolid, Color.LightGreen, Color.Empty);
```

## Шаг 8. Сохраните измененный документ.
Наконец, мы сохраняем измененный документ в файл. Вы можете выбрать подходящее имя и местоположение для выходного документа.

```csharp
doc.Save(dataDir + "WorkingWithTableStylesAndFormatting.ApplyOutlineBorder.docx");
```

Поздравляем! Теперь вы применили контурную рамку к таблице с помощью Aspose.Words для .NET.

### Пример исходного кода для применения границы контура с использованием Aspose.Words для .NET 

```csharp
	// Путь к каталогу ваших документов
	string dataDir = "YOUR DOCUMENT DIRECTORY";

	Document doc = new Document(dataDir + "Tables.docx");
	Table table = (Table) doc.GetChild(NodeType.Table, 0, true);
	// Выровняйте таблицу по центру страницы.
	table.Alignment = TableAlignment.Center;
	//Удалите все существующие границы таблицы.
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
В этом уроке мы узнали, как применить контурную рамку к таблице с помощью Aspose.Words для .NET. Следуя этому пошаговому руководству, вы сможете легко интегрировать эту функцию в свои проекты C#. Управление форматированием таблиц является важным аспектом обработки документов, и Aspose.Words предлагает мощный и гибкий API для достижения этой цели. Благодаря этим знаниям вы сможете улучшить визуальное представление ваших документов Word и удовлетворить конкретные требования.