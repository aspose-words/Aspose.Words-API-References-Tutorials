---
title: Docx в Epub
linktitle: Docx в Epub
second_title: Справочник по API Aspose.Words для .NET
description: Узнайте, как конвертировать документы Word из формата Docx в формат Epub с помощью Aspose.Words для .NET. Пошаговое руководство с примером исходного кода.
type: docs
weight: 10
url: /ru/net/basic-conversions/docx-to-epub/
---

В этом пошаговом руководстве мы расскажем вам, как использовать Aspose.Words для .NET для преобразования документа Word из формата Docx в формат Epub. Мы объясним предоставленный исходный код C# и покажем вам, как реализовать его в ваших собственных проектах.

Для начала убедитесь, что Aspose.Words for .NET установлен и настроен в вашей среде разработки. Если вы этого не сделали, скачайте и установите библиотеку с официального сайта.

## Шаг 1: Инициализация объекта документа

 Во-первых, вам нужно инициализировать`Document` объект, указав путь к исходному документу в формате Docx. Заменять`"YOUR DOCUMENT DIRECTORY"` с фактическим путем к каталогу, в котором находится ваш документ, и`"Document.docx"` с именем вашего исходного документа. Вот фрагмент кода:

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document doc = new Document(dataDir + "Document.docx");
```

## Шаг 2. Преобразование документа в формат Epub

 Далее вы можете продолжить процесс конвертации. Позвоните`Save` метод на`Document` объект и укажите путь и имя файла для выходного документа в формате Epub. В этом примере мы сохраним его как`"BaseConversions.DocxToEpub.epub"`. Вот фрагмент кода:

```csharp
doc.Save(dataDir + "BaseConversions.DocxToEpub.epub");
```

Вот и все! Вы успешно преобразовали документ Word в формате Docx в формат Epub с помощью Aspose.Words для .NET.

### Пример исходного кода для Docx To Epub с использованием Aspose.Words для .NET

```csharp

	// Путь к каталогу документов.
	string dataDir = "YOUR DOCUMENT DIRECTORY";
	Document doc = new Document(dataDir + "Document.docx");

	doc.Save(dataDir + "BaseConversions.DocxToEpub.epub");

```

Не стесняйтесь использовать этот код в своих проектах и модифицировать его в соответствии с вашими конкретными требованиями.