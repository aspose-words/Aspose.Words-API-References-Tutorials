---
title: PDF в Jpeg
linktitle: PDF в Jpeg
second_title: Справочник по API Aspose.Words для .NET
description: Узнайте, как конвертировать документы PDF в изображения JPEG с помощью Aspose.Words для .NET. Пошаговое руководство с примером исходного кода.
type: docs
weight: 10
url: /ru/net/basic-conversions/pdf-to-jpeg/
---

В этом пошаговом руководстве мы расскажем вам, как использовать Aspose.Words для .NET для преобразования документа PDF в изображения JPEG. Мы объясним предоставленный исходный код C# и покажем вам, как реализовать его в ваших собственных проектах.

Для начала убедитесь, что Aspose.Words for .NET установлен и настроен в вашей среде разработки. Если вы этого не сделали, скачайте и установите библиотеку с официального сайта.

## Шаг 1: Инициализация объекта документа

 Сначала инициализируйте`Document` объект, указав путь к вашему PDF-документу:

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document doc = new Document(MyDir + "Pdf Document.pdf");
```

## Шаг 2: Сохранение документа в виде изображений Jpeg

 Затем сохраните документ как изображения Jpeg, вызвав`Save` метод на`Document` объект и предоставление пути и имени файла для выходных изображений Jpeg:

```csharp
doc.Save(dataDir + "BaseConversions.PdfToJpeg.jpeg");
```

Вот и все! Вы успешно преобразовали документ PDF в изображения Jpeg с помощью Aspose.Words для .NET.

### Пример исходного кода для Pdf To Jpeg с использованием Aspose.Words для .NET

```csharp

	// Путь к каталогу документов.
	string dataDir = "YOUR DOCUMENT DIRECTORY";
	Document doc = new Document(MyDir + "Pdf Document.pdf");

	doc.Save(dataDir + "BaseConversions.PdfToJpeg.jpeg");

```

Не стесняйтесь использовать этот код в своих проектах и модифицировать его в соответствии с вашими конкретными требованиями.