---
title: Вставить горизонтальную линейку
linktitle: Вставить горизонтальную линейку
second_title: Справочник по API Aspose.Words для .NET
description: Узнайте, как вставлять горизонтальные линейки в документы Word с помощью Aspose.Words для .NET. Пошаговое руководство.
type: docs
weight: 10
url: /ru/net/add-content-using-documentbuilder/insert-horizontal-rule/
---

В этом подробном примере вы узнаете, как вставить горизонтальную линейку в документ Word с помощью Aspose.Words для .NET. Мы проведем вас через весь процесс и предоставим необходимые фрагменты кода C#. К концу этого руководства вы сможете добавлять горизонтальные линейки в свои документы для визуального разделения и организации.

## Предпосылки
Прежде чем мы начнем, убедитесь, что у вас есть следующие предварительные условия:
- В вашей системе установлена библиотека Aspose.Words for .NET.

## Шаг 1: Создайте новый документ и DocumentBuilder
Для начала создайте новый документ с помощью класса Document и инициализируйте объект DocumentBuilder:

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
```

## Шаг 2. Вставьте горизонтальное правило
Затем используйте метод Writeln класса DocumentBuilder, чтобы добавить описательный текст, а затем вставьте горизонтальную линейку:

```csharp
builder.Writeln("Insert a horizontal rule shape into the document.");
builder.InsertHorizontalRule();
```

## Шаг 3: Сохраните документ
После вставки горизонтальной линейки сохраните документ в файл с помощью метода Save класса Document:

```csharp
doc.Save(ArtifactsDir + "AddContentUsingDocumentBuilder.InsertHorizontalRule.docx");
```

### Пример исходного кода для вставки горизонтального правила с использованием Aspose.Words для .NET
Вот полный исходный код для вставки горизонтальной линейки с помощью Aspose.Words для .NET:
Горизонтальные правила полезны для различных сценариев, таких как разделение разделов, создание визуальных разрывов или выделение важной информации.

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

builder.Writeln("Insert a horizontal rule shape into the document.");
builder.InsertHorizontalRule();

doc.Save(ArtifactsDir + "AddContentUsingDocumentBuilder.InsertHorizontalRule.docx");
```

Не забудьте настроить код в соответствии с вашими конкретными требованиями и добавить в него дополнительные функции по мере необходимости.

## Заключение
Поздравляем! Вы успешно научились вставлять горизонтальную линейку в документ Word с помощью Aspose.Words для .NET. Следуя пошаговому руководству и используя предоставленный исходный код, теперь вы можете визуально разделять и упорядочивать документы с помощью горизонтальных правил.

