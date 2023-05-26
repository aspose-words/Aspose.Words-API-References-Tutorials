---
title: Разделить таблицу
linktitle: Разделить таблицу
second_title: Справочник по API Aspose.Words для .NET
description: Узнайте, как разделить таблицу в документе Word с помощью Aspose.Words для .NET.
type: docs
weight: 10
url: /ru/net/programming-with-tables/split-table/
---

В этом уроке мы узнаем, как разделить таблицу в документе Word с помощью Aspose.Words для .NET. Мы будем следовать пошаговому руководству, чтобы понять код и реализовать эту функцию. В конце этого урока вы сможете разделить таблицу из определенной строки в ваших документах Word.

## Шаг 1: Настройка проекта
1. Запустите Visual Studio и создайте новый проект C#.
2. Добавьте ссылку на библиотеку Aspose.Words для .NET.

## Шаг 2: Загрузка документа
Чтобы начать работу с документом, выполните следующие действия:

```csharp
// Путь к каталогу ваших документов
string dataDir = "YOUR DOCUMENTS DIRECTORY";

//Загрузите документ
Document doc = new Document(dataDir + "Tables.docx");
```

Обязательно замените «КАТАЛОГ ВАШИХ ДОКУМЕНТОВ» на фактический путь к каталогу ваших документов и укажите правильное имя файла.

## Шаг 3: Разделение стола
Далее мы разделим таблицу из определенной строки. Используйте следующий код:

```csharp
// Получить первую таблицу
Table firstTable = (Table)doc.GetChild(NodeType.Table, 0, true);

// Определение линии, от которой разделить таблицу
Row row = firstTable.Rows[2];

// Создайте новый контейнер для разделенной таблицы
Table table = (Table)firstTable.Clone(false);

// Вставьте контейнер после исходной таблицы
firstTable.ParentNode.InsertAfter(table, firstTable);

// Добавьте буферный абзац, чтобы сохранить расстояние между таблицами
firstTable.ParentNode.InsertAfter(new Paragraph(doc), firstTable);

// Переместить строки из исходной таблицы в разделенную таблицу
Row currentRow;
do
{
currentRow = firstTable.LastRow;
table. PrependChild(currentRow);
} while (currentRow != row);
```

Здесь мы используем документ для извлечения первой таблицы из узла документа. Затем определяем строку, из которой хотим разделить таблицу, в данном примере это третья строка (индекс 2). Затем мы создаем новый контейнер, клонируя исходную таблицу, а затем вставляем его после исходной таблицы. Мы также добавляем буферный абзац, чтобы сохранить расстояние между двумя таблицами. Затем мы перемещаем строки из исходной таблицы в разделенную таблицу, используя цикл do-while, пока не достигнем указанной строки.

## Шаг 4: Сохранение измененного документа
Наконец, нам нужно сохранить

  документ изменен с помощью разделенной таблицы. Используйте следующий код:

```csharp
doc.Save(dataDir + "WorkingWithTables.SplitTable.docx");
```

Обязательно укажите правильный путь и имя файла для выходного документа.

### Пример исходного кода для разделения таблицы с использованием Aspose.Words для .NET 

```csharp
// Путь к вашему каталогу документов
string dataDir = "YOUR DOCUMENT DIRECTORY";

Document doc = new Document(dataDir + "Tables.docx");
Table firstTable = (Table) doc.GetChild(NodeType.Table, 0, true);
// Разделим таблицу по третьей строке (включительно).
Row row = firstTable.Rows[2];
// Создайте новый контейнер для разделенной таблицы.
Table table = (Table) firstTable.Clone(false);
// Вставьте контейнер после оригинала.
firstTable.ParentNode.InsertAfter(table, firstTable);
// Добавьте буферный абзац, чтобы таблицы оставались разделенными.
firstTable.ParentNode.InsertAfter(new Paragraph(doc), firstTable);
Row currentRow;
do
{
	currentRow = firstTable.LastRow;
	table.PrependChild(currentRow);
} while (currentRow != row);
doc.Save(dataDir + "WorkingWithTables.SplitTable.docx");
```

## Заключение
В этом руководстве мы узнали, как разделить таблицу в документе Word с помощью Aspose.Words для .NET. Следуя этому пошаговому руководству и реализуя предоставленный код C#, вы можете легко разделить таблицы из определенной строки в ваших документах Word.