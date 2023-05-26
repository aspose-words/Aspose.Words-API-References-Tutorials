---
title: Мульти раздел
linktitle: Мульти раздел
second_title: Справочник по API Aspose.Words для .NET
description: Узнайте, как извлекать и обрабатывать теги структурированного документа, состоящего из нескольких разделов, в документе Word с помощью Aspose.Words для .NET.
type: docs
weight: 10
url: /ru/net/programming-with-sdt/multi-section/
---

В этом руководстве объясняется, как работать с многосекционными тегами структурированного документа в документе Word с использованием Aspose.Words для .NET. Вы можете получить и обработать теги разделов, присутствующие в документе.

## Предпосылки
Чтобы следовать этому руководству, вам необходимо иметь следующее:

- Установлена библиотека Aspose.Words for .NET.
- Базовые знания C# и работы с документами Word.

## Шаг 1. Настройте каталог документов
 Начните с настройки пути к каталогу документов. Заменять`"YOUR DOCUMENT DIRECTORY"` с фактическим путем к каталогу, в котором находится ваш документ.

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## Шаг 2. Загрузите документ и извлеките теги, состоящие из нескольких разделов.
 Загрузите документ Word с помощью`Document` конструктор, передавая путь к документу в качестве параметра. Получить все начальные узлы диапазона тегов структурированного документа в документе с помощью`GetChildNodes` метод.

```csharp
Document doc = new Document(dataDir + "Multi-section structured document tags.docx");
NodeCollection tags = doc.GetChildNodes(NodeType.StructuredDocumentTagRangeStart, true);
```

## Шаг 3: Обработайте многосекционные теги
Повторите набор начальных узлов диапазона тегов структурированного документа. В этом примере мы просто выводим заголовок каждого тега на консоль. Вы можете выполнить дальнейшую обработку в соответствии с вашими требованиями.

```csharp
foreach (StructuredDocumentTagRangeStart tag in tags)
    Console.WriteLine(tag.Title);
```

### Пример исходного кода для Multi Section с использованием Aspose.Words для .NET 

```csharp
	// Путь к вашему каталогу документов
	string dataDir = "YOUR DOCUMENT DIRECTORY";

	Document doc = new Document(dataDir + "Multi-section structured document tags.docx");
	NodeCollection tags = doc.GetChildNodes(NodeType.StructuredDocumentTagRangeStart, true);
	foreach (StructuredDocumentTagRangeStart tag in tags)
		Console.WriteLine(tag.Title);
```

Вот и все! Вы успешно извлекли и обработали теги структурированного документа, состоящего из нескольких разделов, в документе Word с помощью Aspose.Words для .NET.