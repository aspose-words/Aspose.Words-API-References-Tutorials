---
title: Форматированная таблица
linktitle: Форматированная таблица
second_title: API обработки документов Aspose.Words
description: Узнайте, как создавать и форматировать таблицы в документах Word с помощью Aspose.Words for .NET, с помощью этого подробного пошагового руководства.
type: docs
weight: 10
url: /ru/net/programming-with-tables/formatted-table/
---
## Введение

Программное создание и форматирование таблиц в документах Word может показаться сложной задачей, но с Aspose.Words for .NET она становится простой и управляемой. В этом уроке мы покажем вам, как создать форматированную таблицу в документе Word с помощью Aspose.Words для .NET. Мы рассмотрим все: от настройки среды до сохранения документа в красиво отформатированной таблице.

## Предварительные условия

Прежде чем углубиться в код, давайте убедимся, что у вас есть все необходимое:

1. Библиотека Aspose.Words для .NET: загрузите ее с сайта[здесь](https://releases.aspose.com/words/net/).
2. Среда разработки: IDE, например Visual Studio.
3. .NET Framework: убедитесь, что на вашем компьютере установлена .NET Framework.

## Импортировать пространства имен

Прежде чем писать реальный код, вам необходимо импортировать необходимые пространства имен:

```csharp
using System;
using System.Drawing;
using Aspose.Words;
using Aspose.Words.Tables;
```

## Шаг 1. Настройте каталог документов

Во-первых, вам необходимо определить путь, по которому будет сохранен ваш документ.

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

 Заменять`"YOUR DOCUMENT DIRECTORY"` с фактическим путем, по которому вы хотите сохранить документ.

## Шаг 2. Инициализируйте документ и DocumentBuilder

Теперь инициализируйте новый документ и объект DocumentBuilder.

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
```

`DocumentBuilder` — это вспомогательный класс, который упрощает процесс создания документов.

## Шаг 3: Запустите таблицу

 Затем начните создавать таблицу, используя`StartTable` метод.

```csharp
Table table = builder.StartTable();
builder.InsertCell();
```

Вставка ячейки необходима для начала таблицы.

## Шаг 4. Примените форматирование всей таблицы

Вы можете применить форматирование, которое повлияет на всю таблицу. Например, установка отступа слева:

```csharp
table.LeftIndent = 20.0;
```

## Шаг 5. Отформатируйте строку заголовка

Установите высоту, выравнивание и другие свойства для строки заголовка.

```csharp
builder.RowFormat.Height = 40.0;
builder.RowFormat.HeightRule = HeightRule.AtLeast;
builder.CellFormat.Shading.BackgroundPatternColor = Color.FromArgb(198, 217, 241);
builder.ParagraphFormat.Alignment = ParagraphAlignment.Center;
builder.Font.Size = 16;
builder.Font.Name = "Arial";
builder.Font.Bold = true;
builder.CellFormat.Width = 100.0;
builder.Write("Header Row,\n Cell 1");
```

На этом этапе мы выделяем строку заголовка, задав цвет фона, размер шрифта и выравнивание.

## Шаг 6. Вставьте дополнительные ячейки заголовка

Вставьте больше ячеек в строку заголовка:

```csharp
builder.InsertCell();
builder.Write("Header Row,\n Cell 2");
builder.InsertCell();
builder.CellFormat.Width = 200.0;
builder.Write("Header Row,\n Cell 3");
builder.EndRow();
```

## Шаг 7. Отформатируйте строки тела

После настройки заголовка отформатируйте тело таблицы:

```csharp
builder.CellFormat.Shading.BackgroundPatternColor = Color.White;
builder.CellFormat.Width = 100.0;
builder.CellFormat.VerticalAlignment = CellVerticalAlignment.Center;
builder.RowFormat.Height = 30.0;
builder.RowFormat.HeightRule = HeightRule.Auto;
```

## Шаг 8. Вставка строк тела

Вставьте строки тела с содержимым:

```csharp
builder.InsertCell();
builder.Font.Size = 12;
builder.Font.Bold = false;
builder.Write("Row 1, Cell 1 Content");
builder.InsertCell();
builder.Write("Row 1, Cell 2 Content");
builder.InsertCell();
builder.CellFormat.Width = 200.0;
builder.Write("Row 1, Cell 3 Content");
builder.EndRow();
```

Повторите для дополнительных рядов:

```csharp
builder.InsertCell();
builder.CellFormat.Width = 100.0;
builder.Write("Row 2, Cell 1 Content");
builder.InsertCell();
builder.Write("Row 2, Cell 2 Content");
builder.InsertCell();
builder.CellFormat.Width = 200.0;
builder.Write("Row 2, Cell 3 Content.");
builder.EndRow();
builder.EndTable();
```

## Шаг 9: Сохраните документ

Наконец, сохраните документ в указанном каталоге:

```csharp
doc.Save(dataDir + "WorkingWithTables.FormattedTable.docx");
```

Это создаст и сохранит документ Word с отформатированной таблицей.

## Заключение

И вот оно! Выполнив эти шаги, вы сможете создать хорошо отформатированную таблицу в документе Word, используя Aspose.Words для .NET. Эта мощная библиотека позволяет легко программно манипулировать документами Word, экономя ваше время и усилия.

## Часто задаваемые вопросы

### Что такое Aspose.Words для .NET?
Aspose.Words for .NET — это мощная библиотека для программного создания, редактирования и преобразования документов Word.

### Могу ли я использовать разные цвета для разных строк?
Да, вы можете применять различное форматирование, включая цвета, к разным строкам или ячейкам.

### Является ли Aspose.Words для .NET бесплатным?
 Aspose.Words for .NET — платная библиотека, но вы можете получить[бесплатная пробная версия](https://releases.aspose.com/).

### Как мне получить поддержку Aspose.Words для .NET?
 Вы можете получить поддержку от[Форумы сообщества Aspose](https://forum.aspose.com/c/words/8).

### Могу ли я создавать другие типы документов с помощью Aspose.Words для .NET?
Да, Aspose.Words for .NET поддерживает различные форматы документов, включая PDF, HTML и TXT.