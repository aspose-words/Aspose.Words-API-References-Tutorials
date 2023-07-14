---
title: Позиция курсора
linktitle: Позиция курсора
second_title: API обработки документов Aspose.Words
description: Узнайте, как получить позицию курсора в документе Word с помощью Aspose.Words для .NET. Пошаговое руководство.
type: docs
weight: 10
url: /ru/net/add-content-using-documentbuilder/cursor-position/
---

В этом пошаговом примере вы узнаете о позиции курсора в документе Word, используя Aspose.Words для .NET. Мы проведем вас через весь процесс и предоставим необходимые фрагменты кода C#. К концу этого руководства вы сможете получить текущий узел и абзац, в котором находится курсор в документе.

## Предпосылки
Прежде чем мы начнем, убедитесь, что у вас есть следующие предварительные условия:
- В вашей системе установлена библиотека Aspose.Words for .NET.

## Шаг 1: Создайте новый документ и DocumentBuilder
Для начала создайте новый документ с помощью класса Document и инициализируйте объект DocumentBuilder:

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
```

## Шаг 2: доступ к текущему узлу и абзацу
Затем извлеките текущий узел и абзац, где находится курсор. Этого можно добиться с помощью свойств CurrentNode и CurrentParagraph класса DocumentBuilder:

```csharp
Node curNode = builder.CurrentNode;
Paragraph curParagraph = builder.CurrentParagraph;
```

## Шаг 3: Получить информацию о позиции курсора
Теперь вы можете получить информацию о позиции курсора. В следующем фрагменте кода мы печатаем текст текущего абзаца:

```csharp
Console.WriteLine("\nCursor move to paragraph: " + curParagraph.GetText());
```

### Пример исходного кода для позиции курсора с использованием Aspose.Words для .NET
Вот полный исходный код для понимания положения курсора с помощью Aspose.Words для .NET:

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

Node curNode = builder.CurrentNode;
Paragraph curParagraph = builder.CurrentParagraph;

Console.WriteLine("\nCursor move to paragraph: " + curParagraph.GetText());
```

## Заключение
Поздравляем! Вы успешно научились работать с позицией курсора в документе Word, используя Aspose.Words для .NET. Следуя пошаговому руководству и используя предоставленный исходный код, теперь вы можете получить текущий узел и абзац, в котором находится курсор в документе.

Понимание положения курсора полезно для различных сценариев, таких как управление содержимым документа на основе местоположения курсора или реализация пользовательских функций редактирования.

