---
title: Преобразование Docx в Mhtml и отправка электронной почты
linktitle: Преобразование Docx в Mhtml и отправка электронной почты
second_title: API обработки документов Aspose.Words
description: Узнайте, как конвертировать DOCX в MHTML и отправлять электронные письма с помощью Aspose.Words для .NET, в этом пошаговом руководстве. Повысьте свою производительность с помощью простой автоматизации.
type: docs
weight: 10
url: /ru/net/basic-conversions/docx-to-mhtml-and-sending-email/
---
## Введение

В современную цифровую эпоху преобразование документов из одного формата в другой и отправка их по электронной почте является распространенной задачей. В этой статье вы узнаете, как преобразовать файл DOCX в формат MHTML и затем отправить его по электронной почте с помощью Aspose.Words для .NET. Мы разберем каждый шаг в подробном и понятном руководстве, чтобы вы поняли процесс от начала до конца. Давайте погрузимся!

## Предварительные условия

Прежде чем мы начнем, убедитесь, что у вас есть следующие предварительные условия:

1. Aspose.Words for .NET: Загрузите и установите библиотеку Aspose.Words for .NET из[Страница релизов Aspose](https://releases.aspose.com/words/net/).
2.  Aspose.Email для .NET: Загрузите и установите библиотеку Aspose.Email для .NET из[Страница релизов Aspose](https://releases.aspose.com/email/net/).
3. .NET Framework: убедитесь, что на вашем компьютере установлена .NET Framework.
4. SMTP-сервер: для отправки электронной почты вам необходим доступ к SMTP-серверу.

## Импортировать пространства имен

Чтобы использовать Aspose.Words и Aspose.Email в своем проекте, вам необходимо импортировать необходимые пространства имен. Добавьте следующие директивы using в начало файла C#:

```csharp
using Aspose.Words;
using Aspose.Words.Saving;
using Aspose.Email;
using Aspose.Email.Mime;
using Aspose.Email.Clients.Smtp;
```

Давайте разобьем процесс на несколько этапов, чтобы вы четко поняли каждую часть.

## Шаг 1. Загрузите документ DOCX

 Сначала вам нужно загрузить документ DOCX, который вы хотите конвертировать. Использовать`Document` класс из Aspose.Words, чтобы загрузить файл DOCX.

```csharp
// Путь к каталогу документов.
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document doc = new Document(dataDir + "Document.docx");
```

## Шаг 2. Сохраните документ как MHTML.

 Затем сохраните загруженный документ как файл MHTML. Это делается с помощью`Save` метод`Document` сорт.

```csharp
Stream stream = new MemoryStream();
doc.Save(stream, SaveFormat.Mhtml);

// Перемотайте поток к началу, чтобы Aspose.Email мог его прочитать.
stream.Position = 0;
```

## Шаг 3. Создайте сообщение электронной почты

Теперь создайте сообщение электронной почты из потока MHTML, используя Aspose.Email. Вы будете использовать`MailMessage` класс для этой цели.

```csharp
// Создайте сообщение электронной почты Aspose.Email MIME из потока.
MailMessage message = MailMessage.Load(stream, new MhtmlLoadOptions());
message.From = "your_from@email.com";
message.To = "your_to@email.com";
message.Subject = "Aspose.Words + Aspose.Email MHTML Test Message";
```

## Шаг 4. Отправьте электронное письмо.

 Наконец, отправьте электронное письмо с помощью SMTP-клиента. Настройте SMTP-клиент, указав данные вашего SMTP-сервера, и используйте`Send` метод отправки сообщения.

```csharp
// Отправьте сообщение с помощью Aspose.Email.
SmtpClient client = new SmtpClient();
client.Host = "your_smtp.com";
client.Send(message);
```

## Заключение

Поздравляем! Вы успешно преобразовали документ DOCX в MHTML и отправили его по электронной почте с помощью Aspose.Words для .NET. Этот процесс включает загрузку документа, преобразование его в MHTML, создание сообщения электронной почты и его отправку с помощью SMTP-клиента. С помощью этих шагов вы можете легко автоматизировать преобразование и отправку документов по электронной почте в ваших приложениях.

## Часто задаваемые вопросы

### Могу ли я использовать этот метод для преобразования других форматов документов?
Да, Aspose.Words поддерживает различные форматы, и вы можете конвертировать такие документы, как DOC, DOCX, RTF и другие, в MHTML.

### Как добавить вложения к письму?
 Вы можете использовать`Attachments` собственность`MailMessage`class, чтобы добавлять вложения к электронной почте.

### Совместим ли Aspose.Words с .NET Core?
Да, Aspose.Words совместим с .NET Core. Вы также можете использовать его в приложениях .NET Core.

### Нужна ли мне лицензия на Aspose.Words и Aspose.Email?
 Да, обе библиотеки требуют лицензий. Вы можете получить временную лицензию в[Aspose страница покупки](https://purchase.aspose.com/temporary-license/) в целях оценки.

### Где я могу найти дополнительную документацию?
 Вы можете найти подробную документацию для Aspose.Words.[здесь](https://reference.aspose.com/words/net/) и для Aspose.Email[здесь](https://reference.aspose.com/email/net/).
