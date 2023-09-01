---
title: Построить таблицу в документе Word
linktitle: Построить таблицу в документе Word
second_title: API обработки документов Aspose.Words
description: Узнайте, как построить таблицу в документе Word с помощью Aspose.Words для .NET.
type: docs
weight: 10
url: /ru/net/add-content-using-documentbuilder/build-table/
---
В этом пошаговом руководстве вы узнаете, как создать таблицу в документе Word с помощью Aspose.Words для .NET. Мы проведем вас через этот процесс и предоставим необходимые фрагменты кода C#. К концу этого руководства вы сможете создавать таблицы с собственным форматированием и содержимым, используя класс DocumentBuilder.

## Предварительные условия
Прежде чем мы начнем, убедитесь, что у вас есть следующие предварительные условия:
- Библиотека Aspose.Words for .NET, установленная в вашей системе.

## Шаг 1. Создайте новый документ
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

## Шаг 3. Вставьте ячейки и добавьте контент
Теперь вы можете вставлять ячейки в таблицу и добавлять в них содержимое, используя методы InsertCell и Write класса DocumentBuilder. Настройте форматирование ячеек по мере необходимости:

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
Вы можете настроить форматирование строки, задав свойства объектов RowFormat и CellFormat:

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
Вот полный исходный код для построения таблицы с использованием Aspose.Words для .NET:

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
Поздравляем! Вы успешно научились создавать таблицу в документе Word с помощью Aspose.Words для .NET. Следуя пошаговому руководству и используя предоставленный исходный код, вы теперь можете создавать таблицы с произвольным форматированием.

### Часто задаваемые вопросы по таблице сборки в документе Word

#### Вопрос: Что такое Aspose.Words для .NET?

О: Aspose.Words for .NET — это мощная библиотека обработки документов, которая позволяет разработчикам программно создавать, читать, редактировать и конвертировать документы Microsoft Word в приложениях .NET. Он предоставляет широкий спектр функций для работы с документами Word, таких как манипулирование текстом, создание таблиц, защита документов, форматирование и многое другое.

#### Вопрос: Как построить таблицу в документе Word с помощью Aspose.Words for .NET?

О: Чтобы построить таблицу в документе Word с помощью Aspose.Words for .NET, вы можете выполнить следующие действия:
1.  Создайте новый экземпляр`Document` класс и`DocumentBuilder` объект.
2.  Использовать`StartTable` метод`DocumentBuilder`class, чтобы начать создавать таблицу.
3.  Вставьте ячейки в таблицу и добавьте содержимое, используя`InsertCell` и`Write` методы`DocumentBuilder` сорт.
4.  Завершите ряд, используя`EndRow` метод`DocumentBuilder` сорт.
5.  Настройте форматирование строк, задав свойства`RowFormat` и`CellFormat` объекты.
6.  Завершите таблицу, используя`EndTable` метод`DocumentBuilder` сорт.
7. Сохраните документ.

#### Вопрос: Как настроить форматирование таблицы и ее ячеек?

 О: Вы можете настроить форматирование таблицы и ее ячеек, задав различные свойства`RowFormat` и`CellFormat` объекты. Например, вы можете настроить выравнивание ячеек, вертикальную и горизонтальную ориентацию текста, высоту ячейки, высоту строки и многое другое. Используя эти свойства, вы можете добиться желаемого внешнего вида таблицы и ее содержимого.

#### Вопрос: Могу ли я создавать сложные таблицы с объединенными ячейками и другими расширенными функциями?

 О: Да, Aspose.Words for .NET предоставляет расширенные функции для создания сложных таблиц, включая поддержку объединенных ячеек, вложенных таблиц и сложных макетов таблиц. Вы можете использовать`MergeCells` метод объединения ячеек,`StartTable`метод для создания вложенных таблиц и другие методы для достижения желаемой структуры таблицы.

#### Вопрос: Совместим ли Aspose.Words для .NET с различными форматами документов Word?

О: Да, Aspose.Words for .NET совместим с различными форматами документов Word, включая DOC, DOCX, RTF и другими. Он поддерживает как устаревшие форматы (DOC), так и современные форматы на основе XML (DOCX) и позволяет без проблем работать с документами разных форматов.

#### Вопрос: Где я могу найти дополнительную информацию и документацию по Aspose.Words для .NET?

 О: Подробную документацию и примеры кода можно найти на сайте[Ссылки на API](https://reference.aspose.com/words/net/). В документации будет представлена подробная информация о функциях библиотеки и о том, как их использовать в ваших .NET-приложениях.