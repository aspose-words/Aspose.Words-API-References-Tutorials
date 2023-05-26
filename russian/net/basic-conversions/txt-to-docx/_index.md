---
title: Отправьте текст в документ
linktitle: Отправьте текст в документ
second_title: Справочник по API Aspose.Words для .NET
description: Узнайте, как конвертировать текстовые файлы (Txt) в документы Word (Docx) с помощью Aspose.Words для .NET. Пошаговое руководство с примером кода.
type: docs
weight: 10
url: /ru/net/basic-conversions/txt-to-docx/
---

В этом пошаговом руководстве мы расскажем вам, как использовать Aspose.Words для .NET для преобразования простого текстового файла (Txt) в документ Word в формате Docx. Мы объясним предоставленный исходный код C# и покажем вам, как реализовать его в ваших собственных проектах.

Для начала убедитесь, что Aspose.Words for .NET установлен и настроен в вашей среде разработки. Если вы этого не сделали, скачайте и установите библиотеку с официального сайта.

## Шаг 1: Инициализация объекта документа

 Сначала инициализируйте`Document` объект, указав путь к вашему текстовому файлу:

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document doc = new Document(MyDir + "English text.txt");
```

## Шаг 2: Сохранение документа в формате Docx

 Далее сохраните документ в формате Docx, вызвав`Save` метод на`Document`объект и указать путь и имя файла для выходного документа Docx:

```csharp
doc.Save(dataDir + "BaseConversions.TxtToDocx.docx");
```

Вот и все! Вы успешно преобразовали обычный текстовый файл (Txt) в документ Word в формате Docx с помощью Aspose.Words для .NET.

### Пример исходного кода для Txt To Docx с использованием Aspose.Words для .NET

```csharp

	// Путь к каталогу документов.
	string dataDir = "YOUR DOCUMENT DIRECTORY";
	// Кодировка текстового файла определяется автоматически.
	Document doc = new Document(MyDir + "English text.txt");

	doc.Save(dataDir + "BaseConversions.TxtToDocx.docx");

```

Не стесняйтесь использовать этот код в своих проектах и модифицировать его в соответствии с вашими конкретными требованиями.