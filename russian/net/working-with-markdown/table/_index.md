---
title: Стол
linktitle: Стол
second_title: Справочник по API Aspose.Words для .NET
description: Узнайте, как создать таблицу с помощью Aspose.Words для .NET. Пошаговое руководство.
type: docs
weight: 10
url: /ru/net/working-with-markdown/table/
---


В этом примере мы покажем вам, как создать таблицу с помощью Aspose.Words для .NET. Таблица — это структура данных, в которой информация организована в виде строк и столбцов.

## Шаг 1: Использование генератора документов

Во-первых, мы будем использовать генератор документов, чтобы добавить содержимое в наш документ.

```csharp
DocumentBuilder builder = new DocumentBuilder();
```


## Шаг 2. Добавьте ячейки и данные

 Мы добавим ячейки и данные в нашу таблицу, используя`InsertCell` метод и`Writeln` Метод генератора документов.

```csharp
builder. InsertCell();
builder.Writeln("a");
builder. InsertCell();
builder.Writeln("b");

builder. InsertCell();
builder.Writeln("c");
builder. InsertCell();
builder.Writeln("d");
```

### Пример исходного кода для создания таблицы с помощью Aspose.Words для .NET

```csharp
	// Используйте конструктор документов, чтобы добавить содержимое в документ.
	DocumentBuilder builder = new DocumentBuilder();

	// Добавьте первую строку.
	builder.InsertCell();
	builder.Writeln("a");
	builder.InsertCell();
	builder.Writeln("b");

	// Добавьте второй ряд.
	builder.InsertCell();
	builder.Writeln("c");
	builder.InsertCell();
	builder.Writeln("d");
            
```

Поздравляем! Теперь вы узнали, как создать таблицу с помощью Aspose.Words для .NET.
