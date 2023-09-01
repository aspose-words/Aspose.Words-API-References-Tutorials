---
title: Многосекционный
linktitle: Многосекционный
second_title: API обработки документов Aspose.Words
description: Узнайте, как извлекать и обрабатывать теги структурированных документов из нескольких разделов в документе Word с помощью Aspose.Words для .NET.
type: docs
weight: 10
url: /ru/net/programming-with-sdt/multi-section/
---

В этом руководстве объясняется, как работать с многосекционными структурированными тегами документов в документе Word с использованием Aspose.Words для .NET. Вы можете получить и обработать теги разделов, присутствующие в документе.

## Предварительные условия
Чтобы следовать этому руководству, вам необходимо иметь следующее:

- Установлена библиотека Aspose.Words для .NET.
- Базовые знания C# и обработки документов Word.

## Шаг 1. Настройте каталог документов
 Начните с настройки пути к каталогу ваших документов. Заменять`"YOUR DOCUMENT DIRECTORY"` с фактическим путем к каталогу, в котором находится ваш документ.

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## Шаг 2. Загрузите документ и получите многораздельные теги
 Загрузите документ Word, используя`Document` конструктор, передавая путь к документу в качестве параметра. Получите все начальные узлы диапазона тегов структурированного документа в документе, используя метод`GetChildNodes` метод.

```csharp
Document doc = new Document(dataDir + "Multi-section structured document tags.docx");
NodeCollection tags = doc.GetChildNodes(NodeType.StructuredDocumentTagRangeStart, true);
```

## Шаг 3. Обработка многосекционных тегов
Выполните итерацию по коллекции начальных узлов диапазона тегов структурированного документа. В этом примере мы просто выводим на консоль заголовок каждого тега. Вы можете выполнить дальнейшую обработку в соответствии с вашими требованиями.

```csharp
foreach (StructuredDocumentTagRangeStart tag in tags)
    Console.WriteLine(tag.Title);
```

### Пример исходного кода для Multi Раздел с использованием Aspose.Words для .NET 

```csharp
	// Путь к каталогу ваших документов
	string dataDir = "YOUR DOCUMENT DIRECTORY";

	Document doc = new Document(dataDir + "Multi-section structured document tags.docx");
	NodeCollection tags = doc.GetChildNodes(NodeType.StructuredDocumentTagRangeStart, true);
	foreach (StructuredDocumentTagRangeStart tag in tags)
		Console.WriteLine(tag.Title);
```

Вот и все! Вы успешно получили и обработали многосекционные структурированные теги документа в документе Word с помощью Aspose.Words для .NET.