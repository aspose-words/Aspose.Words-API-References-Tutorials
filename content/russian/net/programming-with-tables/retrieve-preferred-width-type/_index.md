---
title: Получить предпочтительный тип ширины
linktitle: Получить предпочтительный тип ширины
second_title: API обработки документов Aspose.Words
description: Узнайте, как получить тип и предпочтительное значение ширины ячейки в таблице Word с помощью Aspose.Words для .NET.
type: docs
weight: 10
url: /ru/net/programming-with-tables/retrieve-preferred-width-type/
---

В этом руководстве мы узнаем, как получить предпочтительный тип ширины и его значение из ячейки таблицы в документе Word, используя Aspose.Words для .NET. Мы будем следовать пошаговому руководству, чтобы понять код и реализовать эту функцию. В конце этого руководства вы сможете получить предпочтительный тип ширины (абсолютный, относительный или автоматический) и его значение для определенной ячейки в таблицах документа Word.

## Шаг 1: Настройка проекта
1. Запустите Visual Studio и создайте новый проект C#.
2. Добавьте ссылку на библиотеку Aspose.Words для .NET.

## Шаг 2: Загрузка документа
Чтобы запустить Word Processing с документом, выполните следующие действия:

```csharp
// Путь к каталогу ваших документов
string dataDir = "YOUR DOCUMENTS DIRECTORY";

// Загрузите документ
Document doc = new Document(dataDir + "Tables.docx");
```

Обязательно замените «КАТАЛОГ ВАШИХ ДОКУМЕНТОВ» на фактический путь к каталогу ваших документов и укажите правильное имя файла.

## Шаг 3: Получение предпочтительного типа и значения ширины
Далее мы получим предпочтительный тип ширины и его значение для конкретной ячейки таблицы. Используйте следующий код:

```csharp
// Получить таблицу
Table table = (Table) doc.GetChild(NodeType.Table, 0, true);

// Активировать автоматическую корректировку стола
table. AllowAutoFit = true;

// Получить первую ячейку первой строки
Cell firstCell = table.FirstRow.FirstCell;

// Получить предпочтительный тип ширины и его значение
PreferredWidthType type = firstCell.CellFormat.PreferredWidth.Type;
double value = firstCell.CellFormat.PreferredWidth.Value;
```

Здесь мы используем документ для получения первой таблицы, затем мы включаем автоматическую подгонку таблицы с помощью`AllowAutoFit` свойство. Затем мы извлекаем первую ячейку первой строки таблицы. Из этой ячейки мы можем получить предпочтительный тип ширины с помощью`PreferredWidth.Type` имущества и его стоимости с`PreferredWidth.Value` свойство.

### Пример исходного кода для извлечения предпочтительного типа ширины с использованием Aspose.Words для .NET 

```csharp
//Путь к вашему каталогу документов
string dataDir = "YOUR DOCUMENT DIRECTORY";

Document doc = new Document(dataDir + "Tables.docx");
Table table = (Table) doc.GetChild(NodeType.Table, 0, true);
table.AllowAutoFit = true;
Cell firstCell = table.FirstRow.FirstCell;
PreferredWidthType type = firstCell.CellFormat.PreferredWidth.Type;
double value = firstCell.CellFormat.PreferredWidth.Value;
```

## Заключение
В этом руководстве мы узнали, как получить предпочтительный тип ширины и его значение из ячейки таблицы в документе Word с помощью Aspose.Words для .NET. Следуя этому пошаговому руководству и реализуя предоставленный код C#, вы можете получить эту информацию для определенных ячеек в таблицах документов Word.