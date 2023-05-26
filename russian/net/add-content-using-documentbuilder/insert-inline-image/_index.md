---
title: Вставить встроенное изображение
linktitle: Вставить встроенное изображение
second_title: Справочник по API Aspose.Words для .NET
description: Узнайте, как вставлять встроенные изображения в документы Word с помощью Aspose.Words для .NET.
type: docs
weight: 10
url: /ru/net/add-content-using-documentbuilder/insert-inline-image/
---

В этом всеобъемлющем руководстве вы узнаете, как вставлять встроенные изображения в документ Word с помощью Aspose.Words для .NET. Мы проведем вас через весь процесс и предоставим необходимые фрагменты кода C#. К концу этого руководства вы сможете добавлять изображения прямо в текст ваших документов.

## Предпосылки
Прежде чем мы начнем, убедитесь, что у вас есть следующие предварительные условия:
- В вашей системе установлена библиотека Aspose.Words for .NET.

## Шаг 1: Создайте новый документ и DocumentBuilder
Для начала создайте новый документ с помощью класса Document и инициализируйте объект DocumentBuilder:

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
```

## Шаг 2. Вставьте встроенное изображение
Затем используйте метод InsertImage класса DocumentBuilder, чтобы вставить встроенное изображение в документ. Укажите путь к файлу изображения в качестве параметра:

```csharp
builder.InsertImage(ImagesDir + "Transparent background logo.png");
```

## Шаг 3: Сохраните документ
После вставки встроенного изображения сохраните документ в файл с помощью метода Save класса Document:

```csharp
doc.Save(ArtifactsDir + "AddContentUsingDocumentBuilder.InsertInlineImage.docx");
```

### Пример исходного кода для вставки встроенного изображения с использованием Aspose.Words для .NET
Вот полный исходный код для вставки встроенного изображения с помощью Aspose.Words для .NET:

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

builder.InsertImage(ImagesDir + "Transparent background logo.png");

doc.Save(ArtifactsDir + "AddContentUsingDocumentBuilder.InsertInlineImage.docx");
```

## Заключение
Поздравляем! Вы успешно научились вставлять встроенные изображения в документ Word с помощью Aspose.Words для .NET. Следуя пошаговому руководству и используя предоставленный исходный код, теперь вы можете легко добавлять изображения в текст своих документов.

Встроенные изображения полезны для различных сценариев, таких как добавление иллюстраций, логотипов или других визуальных элементов непосредственно в поток документа.
