---
title: Вставить разрыв
linktitle: Вставить разрыв
second_title: Справочник по API Aspose.Words для .NET
description: Узнайте, как вставлять разрывы страниц в документы Word с помощью Aspose.Words для .NET. Пошаговое руководство.
type: docs
weight: 10
url: /ru/net/add-content-using-documentbuilder/insert-break/
---

В этом подробном примере вы узнаете, как вставлять разрывы страниц в документ Word с помощью метода InsertBreak в Aspose.Words для .NET. Мы проведем вас через весь процесс и предоставим необходимые фрагменты кода C#. К концу этого руководства вы сможете контролировать разрывы страниц в своем документе.

## Предпосылки
Прежде чем мы начнем, убедитесь, что у вас есть следующие предварительные условия:
- В вашей системе установлена библиотека Aspose.Words for .NET.

## Шаг 1: Создайте новый документ и DocumentBuilder
Для начала создайте новый документ с помощью класса Document и инициализируйте объект DocumentBuilder:

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
```

## Шаг 2. Вставьте содержимое и разрывы страниц
Затем используйте метод Writeln класса DocumentBuilder, чтобы добавить содержимое в документ. Чтобы вставить разрыв страницы, используйте метод InsertBreak с параметром BreakType.PageBreak:

```csharp
builder.Writeln("This is page 1.");
builder.InsertBreak(BreakType.PageBreak);

builder.Writeln("This is page 2.");
builder.InsertBreak(BreakType.PageBreak);

builder.Writeln("This is page 3.");
```

## Шаг 3: Сохраните документ
После вставки содержимого и разрывов страниц сохраните документ в файл с помощью метода Save класса Document:

```csharp
doc.Save(ArtifactsDir + "AddContentUsingDocumentBuilder.InsertBreak.docx");
```

### Пример исходного кода для разрыва вставки с использованием Aspose.Words для .NET
Вот полный исходный код для вставки разрывов страниц с помощью Aspose.Words для .NET:

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

builder.Writeln("This is page 1.");
builder.InsertBreak(BreakType.PageBreak);

builder.Writeln("This is page 2.");
builder.InsertBreak(BreakType.PageBreak);

builder.Writeln("This is page 3.");

doc.Save(ArtifactsDir + "AddContentUsingDocumentBuilder.InsertBreak.docx");
```

Не забудьте настроить код в соответствии с вашими конкретными требованиями и добавить в него дополнительные функции по мере необходимости.


## Заключение
Поздравляем! Вы успешно научились вставлять разрывы страниц в документ Word с помощью Aspose.Words для .NET. Следуя пошаговому руководству и используя предоставленный исходный код, теперь вы можете управлять нумерацией страниц и макетом документа, вставляя разрывы страниц в нужных местах.
