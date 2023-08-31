---
title: Вставить встроенное изображение в документ Word
linktitle: Вставить встроенное изображение в документ Word
second_title: API обработки документов Aspose.Words
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

### Часто задаваемые вопросы по вставке встроенного изображения в документ Word

#### Вопрос. Можно ли изменить размер встроенных изображений в документе Word?

О: Да, вы можете изменить размер встроенных изображений с помощью Aspose.Words для .NET. После вставки изображения вы можете управлять его размером, регулируя свойства ширины и высоты объекта Shape, представляющего изображение.

#### В: Можно ли добавить замещающий текст к встроенным изображениям в целях доступности?

О: Да, вы можете добавить замещающий текст к встроенным изображениям для повышения доступности. Aspose.Words для .NET поддерживает добавление замещающего текста к изображениям, позволяя программам чтения с экрана и другим вспомогательным технологиям описывать содержимое изображения для пользователей с ослабленным зрением.

#### В: Могу ли я применить форматирование или стили к встроенным изображениям?

О: Абсолютно! Aspose.Words для .NET предоставляет широкие возможности форматирования встроенных изображений. К изображениям можно применять различные стили, границы, эффекты и другие атрибуты форматирования, чтобы они соответствовали визуальному оформлению документа.

#### В: Поддерживает ли Aspose.Words for .NET вставку изображений из потока или массива байтов?

О: Да, вы можете вставлять встроенные изображения из потоков или байтовых массивов, используя Aspose.Words для .NET. Это позволяет вам работать с изображениями, загруженными из внешних источников или динамически сгенерированными изображениями.

#### В: Могу ли я вставлять изображения в определенные места внутри текстового содержимого?

О: Да, класс DocumentBuilder в Aspose.Words для .NET обеспечивает точный контроль над позицией вставки встроенных изображений. Вы можете указать точное место в тексте, где изображение должно быть вставлено.