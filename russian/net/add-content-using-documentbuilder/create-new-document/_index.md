---
title: Создать новый документ
linktitle: Создать новый документ
second_title: API обработки документов Aspose.Words
description: Узнайте, как создать новый документ Word и добавить содержимое с помощью Aspose.Words для .NET. Пошаговое руководство.
type: docs
weight: 10
url: /ru/net/add-content-using-documentbuilder/create-new-document/
---

В этом пошаговом руководстве вы узнаете, как создать новый документ Word с нуля, используя Aspose.Words для .NET. Мы проведем вас через весь процесс и предоставим необходимые фрагменты кода C#. К концу этого руководства вы сможете создать новый документ и добавить в него содержимое с помощью класса DocumentBuilder.

## Предпосылки
Прежде чем мы начнем, убедитесь, что у вас есть следующие предварительные условия:
- В вашей системе установлена библиотека Aspose.Words for .NET.

## Шаг 1: Создайте новый документ
Для начала создайте новый документ, используя класс Document:

```csharp
Document doc = new Document();
```

## Шаг 2. Добавьте содержимое в документ
Затем используйте объект DocumentBuilder, чтобы добавить содержимое в документ. Инициализируйте DocumentBuilder только что созданным документом:

```csharp
DocumentBuilder builder = new DocumentBuilder(doc);
builder.Writeln("Hello World!");
```

## Шаг 3: Сохраните документ
После добавления нужного содержимого сохраните документ в файл с помощью метода Save класса Document:

```csharp
doc.Save(ArtifactsDir + "AddContentUsingDocumentBuilder.CreateNewDocument.docx");
```

## Пример исходного кода для создания нового документа с использованием Aspose.Words для .NET
Вот полный исходный код для создания нового документа с помощью Aspose.Words для .NET:

```csharp
Document doc = new Document();

// Используйте конструктор документов, чтобы добавить содержимое в документ.
DocumentBuilder builder = new DocumentBuilder(doc);
builder.Writeln("Hello World!");

doc.Save(ArtifactsDir + "AddContentUsingDocumentBuilder.CreateNewDocument.docx");
```

## Заключение

Поздравляем! Вы успешно научились создавать новый документ Word с помощью Aspose.Words для .NET. Следуя пошаговому руководству и используя предоставленный исходный код, теперь вы можете программно создавать новые документы и добавлять в них содержимое с помощью класса DocumentBuilder.

Теперь вы можете уверенно создавать и настраивать документы Word в соответствии со своими конкретными требованиями.

### Пример исходного кода для создания нового документа с использованием Aspose.Words для .NET:

```csharp
Document doc = new Document();

// Используйте конструктор документов, чтобы добавить содержимое в документ.
DocumentBuilder builder = new DocumentBuilder(doc);
builder.Writeln("Hello World!");

doc.Save(ArtifactsDir + "AddContentUsingDocumentBuilder.CreateNewDocument.docx");
```

Не забудьте изменить путь и имя файла в коде, чтобы сохранить документ в нужном месте в вашей системе.

