---
title: Построить таблицу в документе Word
linktitle: Построить таблицу в документе Word
second_title: API обработки документов Aspose.Words
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

### Часто задаваемые вопросы по созданию таблицы в документе Word

#### В: Что такое Aspose.Words для .NET?

A: Aspose.Words for .NET — это мощная библиотека обработки документов, которая позволяет разработчикам программно создавать, читать, редактировать и преобразовывать документы Microsoft Word в приложениях .NET. Он предоставляет широкий спектр функций для работы с документами Word, таких как манипулирование текстом, создание таблиц, защита документов, форматирование и многое другое.

#### Q: Как я могу создать таблицу в документе Word, используя Aspose.Words для .NET?

О: Чтобы создать таблицу в документе Word с помощью Aspose.Words for .NET, выполните следующие действия:
1.  Создайте новый экземпляр`Document` класс и`DocumentBuilder` объект.
2.  Использовать`StartTable` метод`DocumentBuilder` класс, чтобы начать строить таблицу.
3. Вставьте ячейки в таблицу и добавьте содержимое, используя кнопку`InsertCell` и`Write` методы`DocumentBuilder` сорт.
4.  Завершите ряд, используя`EndRow` метод`DocumentBuilder` сорт.
5.  Настройте форматирование строки, установив свойства`RowFormat` и`CellFormat` объекты.
6.  Завершите таблицу с помощью`EndTable` метод`DocumentBuilder` сорт.
7. Сохраните документ.

#### Q: Как я могу настроить форматирование таблицы и ее ячеек?

 О: Вы можете настроить форматирование таблицы и ее ячеек, установив различные свойства`RowFormat` и`CellFormat` объекты. Например, вы можете настроить выравнивание ячеек, вертикальную и горизонтальную ориентацию текста, высоту ячейки, высоту строки и многое другое. Используя эти свойства, вы можете добиться желаемого внешнего вида таблицы и ее содержимого.

#### Вопрос. Можно ли создавать сложные таблицы с объединенными ячейками и другими расширенными функциями?

 О: Да, Aspose.Words для .NET предоставляет расширенные функции для построения сложных таблиц, включая поддержку объединенных ячеек, вложенных таблиц и сложных макетов таблиц. Вы можете использовать`MergeCells` способ объединения ячеек,`StartTable`метод для создания вложенных таблиц и другие методы для достижения желаемой структуры таблицы.

#### В: Совместим ли Aspose.Words for .NET с различными форматами документов Word?

О: Да, Aspose.Words для .NET совместим с различными форматами документов Word, включая DOC, DOCX, RTF и другими. Он поддерживает как устаревшие форматы (DOC), так и современные форматы на основе XML (DOCX) и позволяет без проблем работать с документами в разных форматах.

#### В: Где я могу найти дополнительную информацию и документацию по Aspose.Words для .NET?

 О: Подробную документацию и примеры кода можно найти на[ссылки на API](https://reference.aspose.com/words/net/). В документации содержится подробная информация о функциях библиотеки и о том, как их использовать в ваших приложениях .NET.