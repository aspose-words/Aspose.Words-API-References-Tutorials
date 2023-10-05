---
title: Переместить узел в отслеживаемом документе
linktitle: Переместить узел в отслеживаемом документе
second_title: API обработки документов Aspose.Words
description: Перемещайте узлы в отслеживаемом документе с помощью Aspose.Words для .NET.
type: docs
weight: 10
url: /ru/net/working-with-revisions/move-node-in-tracked-document/
---

В этом пошаговом руководстве мы расскажем, как переместить узел в отслеживаемом документе Word с помощью Aspose.Words для .NET. Мы предоставим вам полный исходный код и покажем, как форматировать выходные данные уценки.

## Шаг 1: Создание документа

Первым шагом является создание нового документа и добавление абзацев.

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

## Шаг 2. Отслеживайте изменения

Мы собираемся включить отслеживание изменений в документе.

```csharp
doc.StartTrackRevisions("Author", new DateTime(2020, 12, 23, 14, 0, 0));
```

## Шаг 3. Переместите узел

Мы будем перемещать узел (абзац) из одной позиции в другую при генерации ревизий.

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

## Шаг 4. Прекратите отслеживать отзывы

Мы прекратим отслеживать изменения в документе.

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

// Создание редакций при перемещении узла из одного места в другое.
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

// В диапазоне перехода есть еще 3 абзаца.
Console.WriteLine("Paragraph count: {0}", body.Paragraphs.Count);
doc.Save(dataDir + "WorkingWithRevisions.MoveNodeInTrackedDocument.docx");
```

## Заключение

В этом уроке мы узнали, как переместить узел в отслеживаемом документе Word с помощью Aspose.Words для .NET. Выполнив шаги по созданию документа, включению отслеживания редакций, перемещению узла и остановке отслеживания редакций, мы смогли успешно выполнить эту манипуляцию. Aspose.Words for .NET — это мощный инструмент для обработки текстов с документами Word, предлагающий расширенные функции для управления версиями. Теперь вы можете использовать эти знания для перемещения узлов в своих собственных документах Word и отслеживания изменений с помощью Aspose.Words для .NET.

### Часто задаваемые вопросы

#### Вопрос: Как включить отслеживание изменений в документе Aspose.Words for .NET?

О: Чтобы включить отслеживание изменений в документе Aspose.Words for .NET, вы можете использовать`StartTrackRevisions` метод`Document` объект. Этот метод принимает в качестве параметров имя автора изменений и дату начала отслеживания изменений.

```csharp
doc.StartTrackRevisions("Author", new DateTime(2020, 12, 23, 14, 0, 0));
```

#### Вопрос: Как переместить узел в отслеживаемом документе, не создавая изменений?

 О: Если вы хотите переместить узел в отслеживаемом документе без создания изменений, вы можете использовать команду`Remove` и`InsertAfter` или`InsertBefore` методы`Node` объект. Например, чтобы переместить абзац за другим абзацем, вы можете использовать следующий код:

```csharp
Node nodeToMove = document.FirstSection.Body.Paragraphs[0];
Node referenceNode = document.FirstSection.Body.Paragraphs[1];
nodeToMove.Remove();
document.FirstSection.Body.InsertAfter(nodeToMove, referenceNode);
```

#### Вопрос: Как я могу остановить отслеживание изменений в документе Aspose.Words for .NET?

 О: Чтобы прекратить отслеживание изменений в документе Aspose.Words for .NET, вы можете использовать`StopTrackRevisions` метод`Document` объект.

```csharp
doc.StopTrackRevisions();
```