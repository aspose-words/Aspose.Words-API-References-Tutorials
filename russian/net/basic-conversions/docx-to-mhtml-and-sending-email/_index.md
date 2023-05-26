---
title: Docx в Mhtml и отправка электронной почты
linktitle: Docx в Mhtml и отправка электронной почты
second_title: Справочник по API Aspose.Words для .NET
description: Узнайте, как конвертировать документы Word из Docx в MHTML и отправлять их по электронной почте с помощью Aspose.Words и Aspose.Email. Пошаговое руководство.
type: docs
weight: 10
url: /ru/net/basic-conversions/docx-to-mhtml-and-sending-email/
---

В этом пошаговом руководстве мы расскажем вам, как использовать Aspose.Words для .NET для преобразования документа Word в формате Docx в MHTML и отправки его по электронной почте с помощью Aspose.Email. Мы объясним предоставленный исходный код C# и покажем вам, как реализовать его в ваших собственных проектах.

Для начала убедитесь, что в вашей среде разработки установлены и настроены библиотеки Aspose.Words for .NET и Aspose.Email. Если вы еще этого не сделали, скачайте и установите библиотеки с их официальных сайтов.

## Шаг 1: Инициализация объекта документа

 Сначала инициализируйте`Document` объект с путем к исходному документу в формате Docx:

```csharp
Document doc = new Document(MyDir + "Document.docx");
```

## Шаг 2: Сохранение документа в формате MHTML

 Далее сохраните документ в`Stream` объект в формате MHTML:

```csharp
Stream stream = new MemoryStream();
doc.Save(stream, SaveFormat.Mhtml);
```

## Шаг 3: Перемотка потока

Так как Aspose.Email необходимо прочитать поток с начала, перемотаем поток на начало:

```csharp
stream.Position = 0;
```

## Шаг 4: Создание MIME-сообщения Aspose.Email

 Создать`MailMessage` объект из потока с помощью`MhtmlLoadOptions`:

```csharp
MailMessage message = MailMessage.Load(stream, new MhtmlLoadOptions());
message.From = "your_from@email.com";
message.To = "your_to@email.com";
message.Subject = "Aspose.Words + Aspose.Email MHTML Test Message";
```

Не стесняйтесь настраивать свойства сообщения, такие как отправитель, получатель и тема.

## Шаг 5: Отправка электронного письма

 Используйте Aspose.Email`SmtpClient` отправить письмо:

```csharp
SmtpClient client = new SmtpClient();
client.Host = "your_smtp.com";
client.Send(message);
```

Убедитесь, что вы указали правильный адрес хоста SMTP-сервера.

Вот и все! Вы успешно преобразовали документ Word в формате Docx в MHTML и отправили его по электронной почте с помощью Aspose.Words для .NET и Aspose.Email.

### Пример исходного кода для Docx в Mhtml и отправки электронной почты с использованием Aspose.Words для .NET

```csharp

	// Документ doc = новый документ (MyDir + "Document.docx");

	Stream stream = new MemoryStream();
	doc.Save(stream, SaveFormat.Mhtml);

	// Перемотайте поток в начало, чтобы Aspose.Email мог его прочитать.
	stream.Position = 0;

	// Создайте сообщение электронной почты MIME Aspose.Email из потока.
	MailMessage message = MailMessage.Load(stream, new MhtmlLoadOptions());
	message.From = "your_from@email.com";
	message.To = "your_to@email.com";
	message.Subject = "Aspose.Words + Aspose.Email MHTML Test Message";

	// Отправьте сообщение с помощью Aspose.Email.
	SmtpClient client = new SmtpClient();
	client.Host = "your_smtp.com";
	client.Send(message);
	
```

Не стесняйтесь использовать этот код в своих проектах и модифицировать его в соответствии с вашими конкретными требованиями.