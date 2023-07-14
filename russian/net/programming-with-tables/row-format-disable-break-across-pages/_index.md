---
title: Формат строки Отключить разрыв между страницами
linktitle: Формат строки Отключить разрыв между страницами
second_title: API обработки документов Aspose.Words
description: Узнайте, как отключить разрыв строки для таблицы на нескольких страницах в документе Word с помощью Aspose.Words для .NET.
type: docs
weight: 10
url: /ru/net/programming-with-tables/row-format-disable-break-across-pages/
---

В этом уроке мы узнаем, как отключить разрыв строки многостраничной таблицы в документе Word с помощью Aspose.Words для .NET. Мы будем следовать пошаговому руководству, чтобы понять код и реализовать эту функцию. К концу этого руководства вы сможете отключить разрыв строки для всех строк в таблице в документах Word.

## Шаг 1: Настройка проекта
1. Запустите Visual Studio и создайте новый проект C#.
2. Добавьте ссылку на библиотеку Aspose.Words для .NET.

## Шаг 2: Загрузка документа
Чтобы запустить Word Processing с документом, выполните следующие действия:

```csharp
// Путь к каталогу ваших документов
string dataDir = "YOUR DOCUMENTS DIRECTORY";

// Загрузите документ
Document doc = new Document(dataDir + "Table spanning two pages.docx");
```

Обязательно замените «КАТАЛОГ ВАШИХ ДОКУМЕНТОВ» на фактический путь к каталогу ваших документов и укажите правильное имя файла.

## Шаг 3. Отключите разрыв строки в таблице.
Далее мы отключим разрыв строк для всех строк в таблице. Используйте следующий код:

```csharp
// Получить таблицу
Table table = (Table) doc.GetChild(NodeType.Table, 0, true);

// Отключить разрыв строки для всех строк в таблице
foreach(Row row in table.Rows)
row.RowFormat.AllowBreakAcrossPages = false;
```

 Здесь мы используем документ для выборки первой таблицы, а затем перебираем все строки в таблице, используя цикл foreach. Внутри цикла мы отключаем разрыв строки для каждой строки, устанавливая`RowFormat.AllowBreakAcrossPages` собственность на`false`.

## Шаг 4: Сохранение измененного документа
Наконец, нам нужно сохранить измененный документ с отключенным разрывом строки таблицы. Используйте следующий код:

```csharp
doc.Save(dataDir + "WorkingWithTables.RowFormatDisableBreakAcrossPages.docx");
```

Обязательно укажите правильный путь и имя файла для выходного документа.

### Пример исходного кода для отключения разрывов между страницами в формате строки с использованием Aspose.Words для .NET 

```csharp
//Путь к вашему каталогу документов
string dataDir = "YOUR DOCUMENT DIRECTORY";

Document doc = new Document(dataDir + "Table spanning two pages.docx");
Table table = (Table) doc.GetChild(NodeType.Table, 0, true);
// Отключить разбивку по страницам для всех строк в таблице.
foreach (Row row in table.Rows)
	row.RowFormat.AllowBreakAcrossPages = false;
doc.Save(dataDir + "WorkingWithTables.RowFormatDisableBreakAcrossPages.docx");
```

## Заключение
В этом руководстве мы узнали, как отключить разрыв строки многостраничной таблицы в документе Word с помощью Aspose.Words для .NET. Следуя этому пошаговому руководству и реализуя предоставленный код C#, вы можете применить это отключение к своим таблицам в документах Word.