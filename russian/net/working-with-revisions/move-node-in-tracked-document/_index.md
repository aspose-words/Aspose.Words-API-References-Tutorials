---
title: Переместить узел в отслеживаемом документе
linktitle: Переместить узел в отслеживаемом документе
second_title: Справочник по API Aspose.Words для .NET
description: Перемещайте узлы в отслеживаемом документе с помощью Aspose.Words для .NET.
type: docs
weight: 10
url: /ru/net/working-with-revisions/move-node-in-tracked-document/
---

В этом пошаговом руководстве мы расскажем, как переместить узел в отслеживаемом документе Word с помощью Aspose.Words для .NET. Мы предоставим вам полный исходный код и покажем, как форматировать выходные данные уценки.

## Шаг 1: Создание документа

Первый шаг — создать новый документ и добавить абзацы.

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
builder.Writeln("Paragraph 1");
builder.Writeln("Paragraph 2");
builder.Writeln("Paragraph 3");
builder.Writeln("Paragraph 4");
builder.Writeln("Paragraph 5");
builder.Writeln("Paragraph 6");
Body body = doc.FirstSection.Body;
Console.WriteLine("Number of paragraphs: {0}", body.Paragraphs.Count);
```

## Шаг 2. Отслеживание изменений

Мы собираемся включить отслеживание изменений в документе.

```csharp
doc.StartTrackRevisions("Author", new DateTime(2020, 12, 23, 14, 0, 0));
```

## Шаг 3: Переместите узел

Мы будем перемещать узел (абзац) из одной позиции в другую при создании ревизий.

```csharp
Node node = body.Paragraphs[3];
Node endNode = body.Paragraphs[5].NextSibling;
Node referenceNode = body.Paragraphs[0];
while (node != endNode)
{
     Node nextNode = node. NextSibling;
     body. InsertBefore(node, referenceNode);
     node = nextNode;
}
```

## Шаг 4. Прекратите отслеживать отзывы

Мы перестанем отслеживать изменения в документе.

```csharp
doc.StopTrackRevisions();
```

## Шаг 5: Сохранение документа

 После вставки поля формы ввода текста сохраните документ в нужное место с помощью кнопки`Save` метод. Обязательно укажите правильный путь к файлу:

```csharp
Console.WriteLine("Paragraph count: {0}", body.Paragraphs.Count);
doc.Save(dataDir + "WorkingWithRevisions.MoveNodeInTrackedDocument.docx");
```


### Пример исходного кода для перемещения узла в отслеживаемом документе с использованием Aspose.Words для .NET

Вот полный исходный код для перемещения узла в отслеживаемом документе с помощью Aspose.Words для .NET:


```csharp
// Путь к каталогу документов.
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
builder.Writeln("Paragraph 1");
builder.Writeln("Paragraph 2");
builder.Writeln("Paragraph 3");
builder.Writeln("Paragraph 4");
builder.Writeln("Paragraph 5");
builder.Writeln("Paragraph 6");
Body body = doc.FirstSection.Body;
Console.WriteLine("Paragraph count: {0}", body.Paragraphs.Count);

// Начните отслеживать изменения.
doc.StartTrackRevisions("Author", new DateTime(2020, 12, 23, 14, 0, 0));

// Создание ревизий при перемещении узла из одного места в другое.
Node node = body.Paragraphs[3];
Node endNode = body.Paragraphs[5].NextSibling;
Node referenceNode = body.Paragraphs[0];
while (node != endNode)
{
	Node nextNode = node.NextSibling;
	body.InsertBefore(node, referenceNode);
	node = nextNode;
}

// Остановите процесс отслеживания изменений.
doc.StopTrackRevisions();

// В диапазоне перехода есть 3 дополнительных абзаца.
Console.WriteLine("Paragraph count: {0}", body.Paragraphs.Count);
doc.Save(dataDir + "WorkingWithRevisions.MoveNodeInTrackedDocument.docx");
```

