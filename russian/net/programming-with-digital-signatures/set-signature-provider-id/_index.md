---
title: Установить идентификатор поставщика подписи
linktitle: Установить идентификатор поставщика подписи
second_title: Справочник по API Aspose.Words для .NET
description: Узнайте, как установить идентификатор поставщика подписи в документе Word с помощью Aspose.Words для .NET.
type: docs
weight: 10
url: /ru/net/programming-with-digital-signatures/set-signature-provider-id/
---

В этом руководстве мы покажем вам, как использовать функцию «Установить идентификатор поставщика подписи» с Aspose.Words для .NET. Эта функция позволяет указать идентификатор поставщика подписи для строки подписи в документе Word. Выполните следующие действия:

## Шаг 1: Загрузка документа и доступ к строке подписи

Начните с загрузки документа, содержащего строку подписи:

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document doc = new Document(dataDir + "Signature line.docx");

SignatureLine signatureLine = ((Shape)doc.FirstSection.Body.GetChild(NodeType.Shape, 0, true)).SignatureLine;
```

## Шаг 2: Настройка параметров подписи

Создайте экземпляр класса SignOptions и задайте параметры подписи, включая идентификатор поставщика:

```csharp
SignOptions signOptions = new SignOptions
{
ProviderId = signatureLine.ProviderId,
 SignatureLineId = signatureLine.Id
};
```

## Шаг 3: Подписание документа

Чтобы подписать документ, необходимо использовать класс DigitalSignatureUtil и указать сертификат подписи:

```csharp
CertificateHolder certHolder = CertificateHolder.Create(dataDir + "morzal.pfx", "aw");

DigitalSignatureUtil.Sign(dataDir + "Digitally signed.docx",
	dataDir + "SignDocuments.SetSignatureProviderId.docx", certHolder, signOptions);
```

Обязательно укажите правильные пути к документу, сертификату и подписанному документу.

### Пример исходного кода для установки идентификатора поставщика подписи с использованием Aspose.Words для .NET

Вот полный исходный код для установки идентификатора поставщика подписи с помощью Aspose.Words для .NET:

```csharp

	// Путь к каталогу документов.
	string dataDir = "YOUR DOCUMENT DIRECTORY";
	Document doc = new Document(dataDir + "Signature line.docx");

	SignatureLine signatureLine =
		((Shape) doc.FirstSection.Body.GetChild(NodeType.Shape, 0, true)).SignatureLine;

	SignOptions signOptions = new SignOptions
	{
		ProviderId = signatureLine.ProviderId, SignatureLineId = signatureLine.Id
	};

	CertificateHolder certHolder = CertificateHolder.Create(dataDir + "morzal.pfx", "aw");

	DigitalSignatureUtil.Sign(dataDir + "Digitally signed.docx",
		dataDir + "SignDocuments.SetSignatureProviderId.docx", certHolder, signOptions);

```

Завершите идентификатор поставщика подписи в документе Word с помощью Aspose.Words для .NET.

