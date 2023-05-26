---
title: Заменить текст в таблице
linktitle: Заменить текст в таблице
second_title: Справочник по API Aspose.Words для .NET
description: Узнайте, как заменить текст в таблице в документе Word с помощью Aspose.Words для .NET.
type: docs
weight: 10
url: /ru/net/find-and-replace-text/replace-text-in-table/
---

В этой статье мы рассмотрим приведенный выше исходный код C#, чтобы понять, как использовать функцию «Заменить текст в таблице» в библиотеке Aspose.Words для .NET. Эта функция позволяет находить и заменять определенный текст внутри таблицы в документе Word.

## Предпосылки

- Базовые знания языка С#.
- Среда разработки .NET с установленной библиотекой Aspose.Words.

## Шаг 1. Загрузите документ

 Прежде чем мы начнем использовать замену текста в таблице, нам нужно загрузить документ в Aspose.Words для .NET. Это можно сделать с помощью`Document` class и указав путь к файлу документа:

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document doc = new Document(dataDir + "Tables.docx");
```

## Шаг 2: Получите доступ к доске

 После загрузки документа нам нужно перейти к таблице, в которой мы хотим выполнить замену текста. В нашем примере мы используем`GetChild` метод с`NodeType.Table` параметр для получения первой таблицы в документе:

```csharp
Table table = (Table)doc.GetChild(NodeType.Table, 0, true);
```

## Шаг 3: Выполните замену текста

 Теперь мы используем`Range.Replace` метод для выполнения замены текста в массиве. В нашем примере мы заменяем все вхождения слова «Морковь» на «Яйца», используя`FindReplaceOptions` вариант с`FindReplaceDirection.Forward` направление поиска. Дополнительно заменяем значение «50» на «20» в последней ячейке последней строки таблицы:

```csharp
table.Range.Replace("Carrots", "Eggs", new FindReplaceOptions(FindReplaceDirection.Forward));
table.LastRow.LastCell.Range.Replace("50", "20", new FindReplaceOptions(FindReplaceDirection.Forward));
```

## Шаг 4: Сохраните отредактированный документ

 Наконец, мы сохраняем измененный документ в указанный каталог, используя`Save` метод:

```csharp
doc.Save(dataDir + "FindAndReplace.ReplaceTextInTable.docx");
```

Aspose.Words для .NET Мы следовали пошаговому руководству, чтобы загрузить документ, получить доступ к таблице, выполнить замену текста и сохранить измененный документ.

### Пример исходного кода для замены текста в таблице с использованием Aspose.Words для .NET

Вот полный пример исходного кода для демонстрации использования замены текста в таблице с помощью Aspose.Words для .NET:

```csharp

	// Путь к каталогу документов.
	string dataDir = "YOUR DOCUMENT DIRECTORY";
	Document doc = new Document(dataDir + "Tables.docx");

	Table table = (Table)doc.GetChild(NodeType.Table, 0, true);

	table.Range.Replace("Carrots", "Eggs", new FindReplaceOptions(FindReplaceDirection.Forward));
	table.LastRow.LastCell.Range.Replace("50", "20", new FindReplaceOptions(FindReplaceDirection.Forward));

	doc.Save(dataDir + "FindAndReplace.ReplaceTextInTable.docx");
    
```

## Заключение

В этой статье мы изучили исходный код C#, чтобы понять, как использовать функцию Aspose «Заменить текст в таблице».
