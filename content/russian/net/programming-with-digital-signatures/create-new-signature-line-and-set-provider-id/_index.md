---
title: Создайте новую строку подписи и установите идентификатор поставщика
linktitle: Создайте новую строку подписи и установите идентификатор поставщика
second_title: API обработки документов Aspose.Words
description: Узнайте, как создать новую строку подписи и установить идентификатор поставщика в документе Word с помощью Aspose.Words для .NET.
type: docs
weight: 10
url: /ru/net/programming-with-digital-signatures/create-new-signature-line-and-set-provider-id/
---
В этом руководстве мы покажем вам, как использовать функцию «Создать новую строку подписи и установить идентификатор провайдера» с Aspose.Words для .NET. Эта функция позволяет вам вставить строку подписи в документ Word, установить дополнительные параметры и подписать документ. Выполните следующие действия:

## Шаг 1. Создание документа и генератора

Начните с создания экземпляра класса Document и объекта DocumentBuilder:

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
```

## Шаг 2. Настройка параметров строки подписи

Создайте экземпляр класса SignatureLineOptions и задайте нужные параметры:

```csharp
SignatureLineOptions signatureLineOptions = new SignatureLineOptions
{
Sign = "vderyushev",
SignerTitle = "QA",
Email = "vderyushev@aspose.com",
ShowDate=true,
Default Instructions = false,
Instructions = "Please sign here.",
AllowComments = true
};
```

## Шаг 3. Вставка строки подписи.

Используйте метод InsertSignatureLine() объекта DocumentBuilder, чтобы вставить строку подписи в документ:

```csharp
SignatureLine signatureLine = builder.InsertSignatureLine(signatureLineOptions).SignatureLine;
```

## Шаг 4. Установите идентификатор поставщика

Задайте идентификатор провайдера для строки подписи, используя свойство ProviderId:

```csharp
signatureLine.ProviderId = Guid.Parse("CF5A7BB4-8F3C-4756-9DF6-BEF7F13259A2");
```

Обязательно укажите правильный идентификатор поставщика для вашего варианта использования.

## Шаг 5: Сохраните документ

Сохраните измененный документ:

```csharp
doc.Save(dataDir + "SignDocuments.SignatureLineProviderId.docx");
```

Обязательно укажите правильный путь и имя файла для сохранения документа.

## Шаг 6: Подписание документа

Чтобы подписать документ, вам необходимо установить параметры подписи и использовать класс DigitalSignatureUtil:

```csharp
SignOptions signOptions = new SignOptions
{
SignatureLineId = signatureLine.Id,
ProviderId = signatureLine.ProviderId,
Comments = "Document was signed by vderyushev",
SignTime = DateTime.Now
};

CertificateHolder certHolder = CertificateHolder.Create(MyDir + "morzal.pfx", "aw");

DigitalSignatureUtil.Sign(dataDir + "SignDocuments.SignatureLineProviderId.docx", 
	dataDir + "SignDocuments.CreateNewSignatureLineAndSetProviderId.docx", certHolder, signOptions)
```

Обязательно укажите правильные пути к документу, сертификату и подписанному документу.

### Пример исходного кода для создания новой строки подписи и установки идентификатора поставщика с использованием Aspose.Words для .NET

Вот полный исходный код для создания новой строки подписи и установки идентификатора провайдера с помощью Aspose.Words для .NET:

```csharp

	// Путь к каталогу документов.
	string dataDir = "YOUR DOCUMENT DIRECTORY";
	Document doc = new Document();
	DocumentBuilder builder = new DocumentBuilder(doc);

	SignatureLineOptions signatureLineOptions = new SignatureLineOptions
	{
		Signer = "vderyushev",
		SignerTitle = "QA",
		Email = "vderyushev@aspose.com",
		ShowDate = true,
		DefaultInstructions = false,
		Instructions = "Please sign here.",
		AllowComments = true
	};

	SignatureLine signatureLine = builder.InsertSignatureLine(signatureLineOptions).SignatureLine;
	signatureLine.ProviderId = Guid.Parse("CF5A7BB4-8F3C-4756-9DF6-BEF7F13259A2");
	
	doc.Save(dataDir + "SignDocuments.SignatureLineProviderId.docx");

	SignOptions signOptions = new SignOptions
	{
		SignatureLineId = signatureLine.Id,
		ProviderId = signatureLine.ProviderId,
		Comments = "Document was signed by vderyushev",
		SignTime = DateTime.Now
	};

	CertificateHolder certHolder = CertificateHolder.Create(MyDir + "morzal.pfx", "aw");

	DigitalSignatureUtil.Sign(dataDir + "SignDocuments.SignatureLineProviderId.docx", 
		dataDir + "SignDocuments.CreateNewSignatureLineAndSetProviderId.docx", certHolder, signOptions);

```

Выполнив эти шаги, вы можете легко создать новую строку подписи и установить идентификатор провайдера в своем документе Word с помощью Aspose.Words для .NET.

## Заключение

В этом руководстве мы рассмотрели возможность создания новой строки подписи и установки идентификатора провайдера в документе Word с помощью Aspose.Words для .NET. Следуя предоставленным инструкциям, вы можете легко вставить строку подписи с настраиваемыми параметрами и связать ее с конкретным поставщиком, используя идентификатор поставщика. Добавление строк подписи и настройка информации о поставщике повышает подлинность и надежность ваших документов. Aspose.Words for .NET предоставляет мощный API для обработки текстов со строками подписи и цифровыми сертификатами в документах Word, что позволяет автоматизировать процесс подписания и гарантировать достоверность ваших документов.

### Часто задаваемые вопросы

#### Вопрос: Что такое идентификатор провайдера в строке подписи?

О: Идентификатор поставщика в строке подписи — это уникальный идентификатор, представляющий поставщика цифровой подписи. Это помогает определить источник или организацию, ответственную за подпись.

#### Вопрос: Как создать новую строку подписи в документе Word с помощью Aspose.Words for .NET?

О: Чтобы создать новую строку подписи в документе Word с помощью Aspose.Words for .NET, вы можете выполнить следующие действия:
1.  Создайте экземпляр`Document` класс и`DocumentBuilder` объект.
2.  Создайте экземпляр`SignatureLineOptions` class и установите нужные параметры строки подписи.
3.  Использовать`InsertSignatureLine` метод`DocumentBuilder` объект для вставки строки подписи в документ.

#### Вопрос: Могу ли я настроить параметры строки подписи, такие как имя подписывающего лица, должность и инструкции?

 О: Да, вы можете настроить параметры строки подписи.`SignatureLineOptions` класс предоставляет свойства для установки желаемых параметров, таких как`Signer`, `SignerTitle`, `Instructions`, `AllowComments`и т. д. Вы можете изменить эти свойства перед вставкой строки подписи.

#### Вопрос: Какова цель установки идентификатора провайдера для строки подписи?

Ответ: Установка идентификатора поставщика для строки подписи помогает определить источник или организацию, ответственную за цифровую подпись. Он позволяет связать подпись с конкретным поставщиком или организацией, предоставляя дополнительную информацию о происхождении и достоверности подписи.

#### Вопрос: Как установить идентификатор провайдера для строки подписи с помощью Aspose.Words for .NET?

О: Чтобы установить идентификатор провайдера для строки подписи с помощью Aspose.Words for .NET, вы можете выполнить следующие действия:
1.  После вставки строки подписи откройте`ProviderId` собственность`SignatureLine` объект.
2.  Установить`ProviderId` свойству желаемое значение идентификатора поставщика с помощью`Guid` тип данных.

#### Вопрос: Могу ли я подписать документ после создания новой строки подписи и указания идентификатора провайдера?

 О: Да, после создания новой строки подписи и установки идентификатора провайдера вы можете подписать документ. Чтобы подписать документ, вам необходимо установить параметры подписи, включая идентификатор строки подписи, идентификатор поставщика, комментарии и время подписи. Затем используйте`DigitalSignatureUtil.Sign` метод подписи документа с использованием цифрового сертификата.

#### Вопрос: Могу ли я указать конкретный идентификатор поставщика для каждой строки подписи в документе Word?

О: Да, вы можете указать конкретный идентификатор провайдера для каждой строки подписи в документе Word. После вставки каждой строки подписи вы можете установить идентификатор поставщика для этой конкретной строки подписи, открыв`ProviderId` собственность соответствующего`SignatureLine` объект.

#### Вопрос: Как сохранить измененный документ после создания новой строки подписи и установки идентификатора провайдера?

 О: Чтобы сохранить измененный документ после создания новой строки подписи и установки идентификатора провайдера, вы можете использовать команду`Save` метод`Document` объект. Укажите правильный путь и имя файла для сохранения документа.

#### Вопрос: Какой формат файлов поддерживает Aspose.Words for .NET для создания и подписания строк подписи?

О: Aspose.Words for .NET поддерживает создание и подписание строк подписи в формате файла DOCX. Вы можете создавать и подписывать строки подписи в файлах DOCX, используя предоставленные методы и классы.

#### Вопрос: Могу ли я изменить идентификатор провайдера или другие параметры строки подписи после ее подписания?

О: После подписания строки подписи она становится частью содержимого документа и не может быть изменена отдельно. Любые изменения в строке подписи, такие как изменение идентификатора поставщика или других параметров, потребуют удаления существующей подписи и создания новой строки подписи.