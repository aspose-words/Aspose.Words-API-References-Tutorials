---
title: Объединить строки
linktitle: Объединить строки
second_title: API обработки документов Aspose.Words
description: Узнайте, как объединить строки таблицы в документе Word с помощью Aspose.Words для .NET.
type: docs
weight: 10
url: /ru/net/programming-with-tables/combine-rows/
---

В этом руководстве мы узнаем, как использовать Aspose.Words для .NET для объединения строк таблиц в документе Word. Мы будем следовать пошаговому руководству, чтобы понять код и реализовать эту функцию. В конце этого руководства вы сможете программно манипулировать и объединять строки таблиц в документах Word.

## Шаг 1: Настройка проекта
1. Запустите Visual Studio и создайте новый проект C#.
2. Добавьте ссылку на библиотеку Aspose.Words для .NET.

## Шаг 2: Загрузка документа и доступ к таблицам
Чтобы запустить Word Processing с таблицами, нам нужно загрузить содержащий их документ и получить к ним доступ. Следуй этим шагам:

```csharp
// Путь к каталогу ваших документов
string dataDir = "YOUR DOCUMENTS DIRECTORY";

// Загрузите документ
Document doc = new Document(dataDir + "Tables.docx");

// Доступ к таблицам
Table firstTable = (Table)doc.GetChild(NodeType.Table, 0, true);
Table secondTable = (Table)doc.GetChild(NodeType.Table, 1, true);
```

Обязательно замените «КАТАЛОГ ВАШИХ ДОКУМЕНТОВ» на фактический путь к каталогу ваших документов.

## Шаг 3: Объединение строк таблицы
Далее мы объединим строки второй таблицы в конец первой таблицы. Используйте следующий код:

```csharp
// Комбинация строк таблицы
while (secondTable.HasChildNodes)
     firstTable.Rows.Add(secondTable.FirstRow);
secondTable.Remove();
```

 Здесь мы используем`while` цикл для перебора всех строк второго массива и добавления их в конец первого массива с помощью`Add` метод. Далее мы удаляем вторую таблицу из документа с помощью`Remove` метод.

## Шаг 4: Сохранение измененного документа
Наконец, нам нужно сохранить измененный документ с объединенными строками таблицы. Используйте следующий код:

```csharp
// Сохраните измененный документ
doc.Save(dataDir + "WorkingWithTables.CombineRows.docx");
```

Обязательно укажите правильный путь и имя файла для выходного документа.

### Пример исходного кода для объединения строк с использованием Aspose.Words для .NET 

```csharp
	//Путь к вашему каталогу документов
	string dataDir = "YOUR DOCUMENT DIRECTORY";

	Document doc = new Document(dataDir + "Tables.docx");
	// Строки из второй таблицы будут добавлены в конец первой таблицы.
	Table firstTable = (Table) doc.GetChild(NodeType.Table, 0, true);
	Table secondTable = (Table) doc.GetChild(NodeType.Table, 1, true);
	// Добавить все строки из текущей таблицы в следующие таблицы
	// с разным количеством ячеек и шириной могут быть объединены в одну таблицу.
	while (secondTable.HasChildNodes)
		firstTable.Rows.Add(secondTable.FirstRow);
	secondTable.Remove();
	doc.Save(dataDir + "WorkingWithTables.CombineRows.docx");
```

## Заключение
В этом руководстве мы узнали, как объединять строки таблиц в документе Word с помощью Aspose.Words для .NET. Следуя этому пошаговому руководству и реализовав предоставленный код C#, вы сможете программно управлять строками таблицы в документах Word. Эта функция позволяет эффективно объединять и организовывать данные в таблицу.