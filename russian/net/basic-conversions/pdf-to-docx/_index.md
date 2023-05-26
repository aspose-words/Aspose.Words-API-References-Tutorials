---
title: PDF в документ
linktitle: PDF в документ
second_title: Справочник по API Aspose.Words для .NET
description: Узнайте, как конвертировать PDF-документы в формат Docx с помощью Aspose.Words для .NET. Пошаговое руководство с примером исходного кода.
type: docs
weight: 10
url: /ru/net/basic-conversions/pdf-to-docx/
---

В этом пошаговом руководстве мы расскажем вам, как использовать Aspose.Words для .NET для преобразования документа PDF в формат Docx. Мы объясним предоставленный исходный код C# и покажем вам, как реализовать его в ваших собственных проектах.

Для начала убедитесь, что Aspose.Words for .NET установлен и настроен в вашей среде разработки. Если вы этого не сделали, скачайте и установите библиотеку с официального сайта.

## Шаг 1: Инициализация объекта документа

 Сначала инициализируйте`Document` объект, указав путь к вашему PDF-документу:

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document doc = new Document(MyDir + "Pdf Document.pdf");
```

## Шаг 2: Сохранение документа в формате Docx

 Далее сохраните документ в формате Docx, вызвав`Save` метод на`Document`объект и указать путь и имя файла для выходного документа Docx:

```csharp
doc.Save(dataDir + "BaseConversions.PdfToDocx.docx");
```

Вот и все! Вы успешно преобразовали документ PDF в формат Docx с помощью Aspose.Words для .NET.

### Пример исходного кода для Pdf To Docx с использованием Aspose.Words для .NET

```csharp

	// Путь к каталогу документов.
	string dataDir = "YOUR DOCUMENT DIRECTORY";
	Document doc = new Document(MyDir + "Pdf Document.pdf");

	doc.Save(dataDir + "BaseConversions.PdfToDocx.docx");
	
```

Не стесняйтесь использовать этот код в своих проектах и модифицировать его в соответствии с вашими конкретными требованиями.