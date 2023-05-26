---
title: Docx в байт
linktitle: Docx в байт
second_title: Справочник по API Aspose.Words для .NET
description: Узнайте, как преобразовать документы Word из Docx в массив байтов с помощью Aspose.Words для .NET. Пошаговое руководство с примером исходного кода.
type: docs
weight: 10
url: /ru/net/basic-conversions/docx-to-byte/
---

В этом пошаговом руководстве мы расскажем вам, как использовать Aspose.Words для .NET для преобразования документа Word в формате Docx в массив байтов. Мы объясним предоставленный исходный код C# и покажем вам, как реализовать его в ваших собственных проектах.

Для начала убедитесь, что Aspose.Words for .NET установлен и настроен в вашей среде разработки. Если вы этого не сделали, скачайте и установите библиотеку с официального сайта.

## Шаг 1: Инициализация MemoryStream

 Сначала создайте экземпляр`MemoryStream` класс для хранения преобразованного документа в виде массива байтов:

```csharp
MemoryStream outStream = new MemoryStream();
```

## Шаг 2: Сохранение документа в MemoryStream

 Далее используйте`Save` метод`Document` класс, чтобы сохранить документ в`MemoryStream` в формате docx:

```csharp
doc.Save(outStream, SaveFormat.Docx);
```

## Шаг 3: Преобразование MemoryStream в байтовый массив

 Чтобы преобразовать`MemoryStream` содержащий документ Docx в массив байтов, используйте метод`ToArray` метод:

```csharp
byte[] docBytes = outStream.ToArray();
```

## Шаг 4: Инициализация MemoryStream из байтового массива

 Теперь инициализируйте новый экземпляр`MemoryStream`используя массив байтов, полученный на предыдущем шаге:

```csharp
MemoryStream inStream = new MemoryStream(docBytes);
```

## Шаг 5: Создание документа из MemoryStream

 Наконец, создайте новый`Document` объект из`MemoryStream`:

```csharp
Document docFromBytes = new Document(inStream);
```

Вот и все! Вы успешно преобразовали документ Word в формате Docx в массив байтов с помощью Aspose.Words для .NET.

### Пример исходного кода для Docx To Byte с использованием Aspose.Words для .NET

```csharp

	// Поток Памяти outStream = новый Поток Памяти();
	doc.Save(outStream, SaveFormat.Docx);

	byte[] docBytes = outStream.ToArray();
	MemoryStream inStream = new MemoryStream(docBytes);

	Document docFromBytes = new Document(inStream);
	
```

Не стесняйтесь использовать этот код в своих проектах и модифицировать его в соответствии с вашими конкретными требованиями.