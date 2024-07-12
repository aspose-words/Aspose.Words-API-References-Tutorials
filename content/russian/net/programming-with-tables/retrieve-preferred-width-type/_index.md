---
title: Получить предпочтительный тип ширины
linktitle: Получить предпочтительный тип ширины
second_title: API обработки документов Aspose.Words
description: Узнайте, как получить тип и предпочтительное значение ширины ячейки в таблице Word с помощью Aspose.Words для .NET.
type: docs
weight: 10
url: /ru/net/programming-with-tables/retrieve-preferred-width-type/
---

В этом уроке мы научимся получать предпочтительный тип ширины и его значение из ячейки таблицы в документе Word с помощью Aspose.Words для .NET. Мы будем следовать пошаговому руководству, чтобы понять код и реализовать эту функцию. В конце этого руководства вы сможете получить предпочтительный тип ширины (абсолютный, относительный или автоматический) и его значение для определенной ячейки в таблицах документов Word.

## Шаг 1: Настройка проекта
1. Запустите Visual Studio и создайте новый проект C#.
2. Добавьте ссылку на библиотеку Aspose.Words для .NET.

## Шаг 2: Загрузка документа
Чтобы начать обработку текста с документом, выполните следующие действия:

```csharp
// Путь к каталогу ваших документов
string dataDir = "YOUR DOCUMENTS DIRECTORY";

// Загрузите документ
Document doc = new Document(dataDir + "Tables.docx");
```

Обязательно замените «КАТАЛОГ ВАШИХ ДОКУМЕНТОВ» фактическим путем к каталогу ваших документов и укажите правильное имя файла.

## Шаг 3. Получение предпочтительного типа и значения ширины.
Далее мы получим предпочтительный тип ширины и его значение для конкретной ячейки таблицы. Используйте следующий код:

```csharp
// Получить таблицу
Table table = (Table) doc.GetChild(NodeType.Table, 0, true);

// Активировать автоматическую регулировку стола
table. AllowAutoFit = true;

//Получить первую ячейку первой строки
Cell firstCell = table.FirstRow.FirstCell;

// Получите предпочтительный тип ширины и его значение.
PreferredWidthType type = firstCell.CellFormat.PreferredWidth.Type;
double value = firstCell.CellFormat.PreferredWidth.Value;
```

 Здесь мы используем документ для получения первой таблицы, затем включаем автоматическую подгонку таблицы по`AllowAutoFit` свойство. Затем мы извлекаем первую ячейку первой строки таблицы. Из этой ячейки мы можем получить предпочтительный тип ширины с помощью`PreferredWidth.Type` имущество и его стоимость с учетом`PreferredWidth.Value` свойство.

### Пример исходного кода для получения предпочтительного типа ширины с использованием Aspose.Words для .NET 

```csharp
// Путь к каталогу ваших документов
string dataDir = "YOUR DOCUMENT DIRECTORY";

Document doc = new Document(dataDir + "Tables.docx");
Table table = (Table) doc.GetChild(NodeType.Table, 0, true);
table.AllowAutoFit = true;
Cell firstCell = table.FirstRow.FirstCell;
PreferredWidthType type = firstCell.CellFormat.PreferredWidth.Type;
double value = firstCell.CellFormat.PreferredWidth.Value;
```

## Заключение
В этом уроке мы узнали, как получить предпочтительный тип ширины и его значение из ячейки таблицы в документе Word с помощью Aspose.Words для .NET. Следуя этому пошаговому руководству и реализовав предоставленный код C#, вы сможете получить эту информацию для определенных ячеек в таблицах документов Word.