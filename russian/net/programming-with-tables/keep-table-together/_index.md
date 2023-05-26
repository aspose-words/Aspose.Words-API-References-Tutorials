---
title: Держите стол вместе
linktitle: Держите стол вместе
second_title: Справочник по API Aspose.Words для .NET
description: Узнайте, как объединить таблицу в документе Word с помощью Aspose.Words для .NET.
type: docs
weight: 10
url: /ru/net/programming-with-tables/keep-table-together/
---

В этом уроке мы узнаем, как объединить таблицу в документе Word с помощью Aspose.Words для .NET. Мы будем следовать пошаговому руководству, чтобы понять код и реализовать эту функцию. К концу этого руководства вы сможете сохранить таблицу без изменений, не разбивая ее на несколько страниц в ваших документах Word.

## Шаг 1: Настройка проекта
1. Запустите Visual Studio и создайте новый проект C#.
2. Добавьте ссылку на библиотеку Aspose.Words для .NET.

## Шаг 2. Загрузка документа и получение таблицы
Чтобы начать работу с таблицей, нам нужно загрузить документ и получить таблицу, которую мы хотим сохранить вместе. Следуй этим шагам:

```csharp
// Путь к каталогу ваших документов
string dataDir = "YOUR DOCUMENTS DIRECTORY";

//Загрузите документ
Document doc = new Document(dataDir + "Table spanning two pages.docx");

// Получить таблицу
Table table = (Table)doc.GetChild(NodeType.Table, 0, true);
```

Обязательно замените «КАТАЛОГ ВАШИХ ДОКУМЕНТОВ» на фактический путь к каталогу ваших документов.

## Шаг 3: Включите опцию «KeepWithNext»
Чтобы сохранить таблицу вместе и предотвратить ее разбиение на несколько страниц, нам нужно включить опцию «KeepWithNext» для каждого абзаца в таблице, кроме последних абзацев последней строки таблицы. Используйте следующий код:

```csharp
foreach(Cell cell in table.GetChildNodes(NodeType.Cell, true))
{
cell.EnsureMinimum();
foreach(Paragraph para in cell.Paragraphs)
if (!(cell.ParentRow.IsLastRow && para.IsEndOfCell))
para.ParagraphFormat.KeepWithNext = true;
}
```

Здесь мы перебираем каждую ячейку в таблице и включаем опцию «KeepWithNext» для каждого абзаца в ячейке, кроме последних абзацев последней строки в таблице.

## Шаг 4: Сохранение измененного документа
Наконец, нам нужно сохранить измененный документ вместе с таблицей. Используйте следующий код:

```csharp
doc.Save(dataDir + "WorkingWithTables.KeepTableTogether.docx");
```

Обязательно укажите правильный путь и имя файла для выходного документа.

### Пример исходного кода для Keep Table Together с использованием Aspose.Words для .NET 

```csharp
	// Путь к вашему каталогу документов
	string dataDir = "YOUR DOCUMENT DIRECTORY";

	Document doc = new Document(dataDir + "Table spanning two pages.docx");
	Table table = (Table) doc.GetChild(NodeType.Table, 0, true);
	// Нам нужно включить KeepWithNext для каждого абзаца в таблице, чтобы он не разбивался по странице,
	// кроме последних абзацев в последней строке таблицы.
	foreach (Cell cell in table.GetChildNodes(NodeType.Cell, true))
	{
		cell.EnsureMinimum();
		foreach (Paragraph para in cell.Paragraphs)
			if (!(cell.ParentRow.IsLastRow && para.IsEndOfCell))
				para.ParagraphFormat.KeepWithNext = true;
	}
	doc.Save(dataDir + "WorkingWithTables.KeepTableTogether.docx");
```

## Заключение
В этом руководстве мы узнали, как объединить таблицу в документе Word с помощью Aspose.Words для .NET. Следуя этому пошаговому руководству и реализовав предоставленный код C#, вы сможете сохранить таблицу нетронутой и предотвратить ее разбиение на несколько страниц в ваших документах. Эта функция дает вам больший контроль над внешним видом и расположением таблиц в ваших документах.