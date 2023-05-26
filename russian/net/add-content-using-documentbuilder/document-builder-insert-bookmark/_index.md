---
title: Конструктор документов Вставить закладку
linktitle: Конструктор документов Вставить закладку
second_title: Справочник по API Aspose.Words для .NET
description: Узнайте, как вставлять закладки в документы Word с помощью DocumentBuilder в Aspose.Words для .NET. Пошаговое руководство.
type: docs
weight: 10
url: /ru/net/add-content-using-documentbuilder/document-builder-insert-bookmark/
---

В этом подробном примере вы узнаете, как вставлять закладки в документ Word с помощью класса DocumentBuilder в Aspose.Words для .NET. Мы проведем вас через весь процесс и предоставим необходимые фрагменты кода C#. К концу этого руководства вы сможете создавать и управлять закладками в своих документах.

## Предпосылки
Прежде чем мы начнем, убедитесь, что у вас есть следующие предварительные условия:
- В вашей системе установлена библиотека Aspose.Words for .NET.

## Шаг 1: Создайте новый документ и DocumentBuilder
Для начала создайте новый документ с помощью класса Document и инициализируйте объект DocumentBuilder:

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
```

## Шаг 2. Вставьте закладку
Затем используйте методы StartBookmark и EndBookmark класса DocumentBuilder, чтобы вставить закладку в документ. Укажите уникальное имя закладки в качестве параметра:

```csharp
builder.StartBookmark("FineBookmark");
builder.Writeln("This is just a fine bookmark.");
builder.EndBookmark("FineBookmark");
```

## Шаг 3: Сохраните документ
После вставки закладки сохраните документ в файл с помощью метода Save класса Document:

```csharp
doc.Save(ArtifactsDir + "AddContentUsingDocumentBuilder.DocumentBuilderInsertBookmark.docx");
```

### Пример исходного кода для DocumentBuilder Вставить закладку с помощью Aspose.Words для .NET
Вот полный исходный код для вставки закладки с помощью класса DocumentBuilder в Aspose.Words для .NET:

```csharp
   
	Document doc = new Document();
	DocumentBuilder builder = new DocumentBuilder(doc);

	builder.StartBookmark("FineBookmark");
	builder.Writeln("This is just a fine bookmark.");
	builder.EndBookmark("FineBookmark");

	doc.Save(ArtifactsDir + "AddContentUsingDocumentBuilder.DocumentBuilderInsertBookmark.docx");
	 
```

## Заключение
Поздравляем! Вы успешно научились вставлять закладки в документ Word с помощью класса DocumentBuilder в Aspose.Words для .NET. Следуя пошаговому руководству и используя предоставленный исходный код, теперь вы можете создавать и управлять закладками в своих документах.

Закладки полезны для различных сценариев, таких как навигация по большим документам, ссылки на определенные разделы или программное управление содержимым в областях с закладками.

Не забудьте настроить код в соответствии с вашими конкретными требованиями и добавить в него дополнительные функции по мере необходимости.

