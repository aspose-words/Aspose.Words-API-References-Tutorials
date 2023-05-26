---
title: Создайте новую строку подписи и установите идентификатор поставщика
linktitle: Создайте новую строку подписи и установите идентификатор поставщика
second_title: Справочник по API Aspose.Words для .NET
description: Узнайте, как создать новую строку подписи и установить идентификатор поставщика в документе Word с помощью Aspose.Words для .NET.
type: docs
weight: 10
url: /ru/net/programming-with-digital-signatures/create-new-signature-line-and-set-provider-id/
---

В этом руководстве мы покажем вам, как использовать функцию «Создать новую строку подписи» и «Установить идентификатор поставщика» с Aspose.Words для .NET. Эта функция позволяет вставлять строку подписи в документ Word, задавать пользовательские параметры и подписывать документ. Выполните следующие действия:

## Шаг 1: Создание документа и генератора

Начните с создания экземпляра класса Document и объекта DocumentBuilder:

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
```

## Шаг 2: Настройка параметров строки подписи

Создайте экземпляр класса SignatureLineOptions и установите нужные параметры:

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

## Шаг 3: Вставка строки подписи

Используйте метод InsertSignatureLine() объекта DocumentBuilder, чтобы вставить строку подписи в документ:

```csharp
SignatureLine signatureLine = builder.InsertSignatureLine(signatureLineOptions).SignatureLine;
```

## Шаг 4: Установите идентификатор поставщика

Задайте идентификатор провайдера для строки подписи с помощью свойства ProviderId:

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

Чтобы подписать документ, вам нужно установить параметры подписи и использовать класс DigitalSignatureUtil:

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

Вот полный исходный код для создания новой строки подписи и установки идентификатора поставщика с помощью Aspose.Words для .NET:

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

Следуя этим шагам, вы можете легко создать новую строку подписи и установить идентификатор поставщика в документе Word с помощью Aspose.Words для .NET.

