---
title: Docx в PDF
linktitle: Docx в PDF
second_title: Справочник по API Aspose.Words для .NET
description: Узнайте, как конвертировать документы Word из Docx в PDF с помощью Aspose.Words для .NET. Пошаговое руководство с примером исходного кода.
type: docs
weight: 10
url: /ru/net/basic-conversions/docx-to-pdf/
---

В этом пошаговом руководстве мы расскажем вам, как использовать Aspose.Words для .NET для преобразования документа Word в формате Docx в PDF. Мы объясним предоставленный исходный код C# и покажем вам, как реализовать его в ваших собственных проектах.

Для начала убедитесь, что Aspose.Words for .NET установлен и настроен в вашей среде разработки. Если вы этого не сделали, скачайте и установите библиотеку с официального сайта.

## Шаг 1: Инициализация объекта документа

 Сначала инициализируйте`Document` объект с путем к исходному документу в формате Docx:

```csharp
Document doc = new Document(MyDir + "Document.docx");
```

## Шаг 2: Сохранение документа в формате PDF

 Далее сохраните документ в формате PDF, вызвав`Save` метод на`Document` объект и указать путь и имя файла для выходного PDF-документа:

```csharp
doc.Save(MyDir + "BaseConversions.DocxToPdf.pdf");
```

Вот и все! Вы успешно преобразовали документ Word в формате Docx в PDF с помощью Aspose.Words для .NET.

### Пример исходного кода для Docx To Pdf с использованием Aspose.Words для .NET

```csharp

	Document doc = new Document(MyDir + "Document.docx");

	doc.Save(MyDir + "BaseConversions.DocxToPdf.pdf");
	
```

Не стесняйтесь использовать этот код в своих проектах и модифицировать его в соответствии с вашими конкретными требованиями.
