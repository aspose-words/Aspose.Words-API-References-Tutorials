---
title: Вставить плавающее изображение
linktitle: Вставить плавающее изображение
second_title: Справочник по API Aspose.Words для .NET
description: Узнайте, как вставлять плавающие изображения в документы Word с помощью Aspose.Words для .NET. Пошаговое руководство.
type: docs
weight: 10
url: /ru/net/add-content-using-documentbuilder/insert-floating-image/
---

В этом подробном примере вы узнаете, как вставить плавающее изображение в документ Word с помощью Aspose.Words для .NET. Мы проведем вас через весь процесс и предоставим необходимые фрагменты кода C#. К концу этого руководства вы сможете добавлять изображения с настраиваемыми параметрами позиционирования и обтекания в свои документы.

## Предпосылки
Прежде чем мы начнем, убедитесь, что у вас есть следующие предварительные условия:
- В вашей системе установлена библиотека Aspose.Words for .NET.

## Шаг 1: Создайте новый документ и DocumentBuilder
Для начала создайте новый документ с помощью класса Document и инициализируйте объект DocumentBuilder:

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
```

## Шаг 2. Вставьте плавающее изображение
Затем используйте метод InsertImage класса DocumentBuilder, чтобы вставить плавающее изображение. Укажите путь к файлу изображения, относительное положение по горизонтали и вертикали, ширину, высоту и параметры обтекания в качестве параметров:

```csharp
builder.InsertImage(ImagesDir + "Transparent background logo.png",
	RelativeHorizontalPosition.Margin,
	100,
	RelativeVerticalPosition.Margin,
	100,
	200,
	100,
	WrapType.Square);
```

## Шаг 3: Сохраните документ
После вставки плавающего изображения сохраните документ в файл с помощью метода Save класса Document:

```csharp
doc.Save(ArtifactsDir + "AddContentUsingDocumentBuilder.InsertFloatingImage.docx");
```

## Пример исходного кода для вставки плавающего изображения с использованием Aspose.Words для .NET
Вот полный исходный код для вставки плавающего изображения с помощью Aspose.Words для .NET:
Плавающие изображения полезны для различных сценариев, таких как добавление логотипов, иллюстраций или декоративных элементов, которые можно размещать независимо от текста документа.

```csharp

	Document doc = new Document();
	DocumentBuilder builder = new DocumentBuilder(doc);

	builder.InsertImage(ImagesDir + "Transparent background logo.png",
		RelativeHorizontalPosition.Margin,
		100,
		RelativeVerticalPosition.Margin,
		100,
		200,
		100,
		WrapType.Square);

	doc.Save(ArtifactsDir + "AddContentUsingDocumentBuilder.InsertFloatingImage.docx");
	
```

Не забудьте настроить код в соответствии с вашими конкретными требованиями, включая путь к файлу изображения и желаемые параметры позиционирования и переноса.

## Заключение
Поздравляем! Вы успешно научились вставлять плавающее изображение в документ Word с помощью Aspose.Words для .NET. Следуя пошаговому руководству и используя предоставленный исходный код, теперь вы можете улучшить свои документы с помощью визуально привлекательных и настраиваемых плавающих изображений.

