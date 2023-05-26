---
title: Построить таблицу
linktitle: Построить таблицу
second_title: Справочник по API Aspose.Words для .NET
description: Узнайте, как создать таблицу в документе Word с помощью Aspose.Words для .NET.
type: docs
weight: 10
url: /ru/net/add-content-using-documentbuilder/build-table/
---

В этом пошаговом руководстве вы узнаете, как создать таблицу в документе Word с помощью Aspose.Words для .NET. Мы проведем вас через весь процесс и предоставим необходимые фрагменты кода C#. К концу этого руководства вы сможете создать таблицу с пользовательским форматированием и содержимым, используя класс DocumentBuilder.

## Предпосылки
Прежде чем мы начнем, убедитесь, что у вас есть следующие предварительные условия:
- В вашей системе установлена библиотека Aspose.Words for .NET.

## Шаг 1: Создайте новый документ
Для начала создайте новый документ, используя класс Document:

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
```

## Шаг 2: Запустите таблицу
Затем используйте метод StartTable класса DocumentBuilder, чтобы начать построение таблицы:

```csharp
Table table = builder.StartTable();
```

## Шаг 3: вставьте ячейки и добавьте содержимое
Теперь вы можете вставлять ячейки в таблицу и добавлять в них содержимое с помощью методов InsertCell и Write класса DocumentBuilder. При необходимости настройте форматирование ячейки:

```csharp
builder.InsertCell();
builder.CellFormat.VerticalAlignment = CellVerticalAlignment.Center;
builder.Write("This is row 1 cell 1");

builder.InsertCell();
builder.Write("This is row 1 cell 2");
```

## Шаг 4: Завершите ряд
После добавления содержимого в ячейки первой строки используйте метод EndRow класса DocumentBuilder, чтобы завершить строку:

```csharp
builder.EndRow();
```

## Шаг 5. Настройте форматирование строк
Вы можете настроить форматирование строки, установив свойства объектов RowFormat и CellFormat:

```csharp
builder.InsertCell();
builder.RowFormat.Height = 100;
builder.RowFormat.HeightRule = HeightRule.Exactly;
builder.CellFormat.Orientation = TextOrientation.Upward;
builder.Writeln("This is row 2 cell 1");

builder.InsertCell();
builder.CellFormat.Orientation = TextOrientation.Downward;
builder.Writeln("This is row 2 cell 2");
```

## Шаг 6: Завершите таблицу
Для заполнения таблицы используйте метод EndTable класса DocumentBuilder:

```csharp
builder.EndTable();
```

### Пример исходного кода для построения таблицы с использованием Aspose.Words для .NET
Вот полный исходный код для построения таблицы с помощью Aspose.Words для .NET:

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

Table table = builder.StartTable();
builder.InsertCell();
table.AutoFit(AutoFitBehavior.FixedColumnWidths);

builder.CellFormat.VerticalAlignment = CellVerticalAlignment.Center;
builder.Write("This is row 1 cell 1");

builder.InsertCell();
builder.Write("This is row 1 cell 2");

builder.EndRow();

builder.InsertCell();

builder.RowFormat.Height = 100;
builder.RowFormat.HeightRule = HeightRule.Exactly;
builder.CellFormat.Orientation = TextOrientation.Upward;
builder.Writeln("This is row 2 cell 1");

builder.InsertCell();
builder.CellFormat.Orientation = TextOrientation.Downward;
builder.Writeln("This is row 2 cell 2");

builder.EndRow();
builder.EndTable();

doc.Save(ArtifactsDir + "AddContentUsingDocumentBuilder.BuildTable.docx");
```

## Заключение
Поздравляем! Вы успешно научились создавать таблицы в документе Word с помощью Aspose.Words для .NET. Следуя пошаговому руководству и используя предоставленный исходный код, теперь вы можете создавать таблицы с пользовательским форматированием.