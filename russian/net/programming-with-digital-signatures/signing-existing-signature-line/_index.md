---
title: Подписание существующей строки подписи
linktitle: Подписание существующей строки подписи
second_title: Справочник по API Aspose.Words для .NET
description: Узнайте, как подписать существующую строку подписи в документе Word с помощью Aspose.Words для .NET.
type: docs
weight: 10
url: /ru/net/programming-with-digital-signatures/signing-existing-signature-line/
---

В этом руководстве мы покажем вам, как использовать функцию подписи существующей строки подписи с Aspose.Words для .NET. Эта функция позволяет поставить цифровую подпись на строку подписи, уже присутствующую в документе Word. Выполните следующие действия:

## Шаг 1: Загрузка документа и доступ к строке подписи

Начните с загрузки документа, содержащего существующую строку подписи:

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document doc = new Document(dataDir + "Signature line.docx");

SignatureLine signatureLine = ((Shape)doc.FirstSection.Body.GetChild(NodeType.Shape, 0, true)).SignatureLine;
```

## Шаг 2: Настройка параметров подписи

Создайте экземпляр класса SignOptions и задайте параметры подписи, включая идентификатор строки подписи и изображение строки подписи:

```csharp
SignOptions signOptions = new SignOptions
{
SignatureLineId = signatureLine.Id,
SignatureLineImage = File.ReadAllBytes(ImagesDir + "Enhanced Windows MetaFile.emf")
};
```

Обязательно укажите правильный путь к изображению строки подписи.

## Шаг 3: Загрузка сертификата

Начните с загрузки сертификата подписи с помощью класса CertificateHolder:

```csharp
CertificateHolder certHolder = CertificateHolder.Create(dataDir + "morzal.pfx", "aw");
```

Обязательно укажите правильный путь к сертификату и связанный с ним пароль.

## Шаг 4: Подписание существующей строки подписи

Используйте класс DigitalSignatureUtil, чтобы подписать существующую строку подписи:

```csharp
DigitalSignatureUtil.Sign(dataDir + "Digitally signed.docx",
	dataDir + "SignDocuments.SigningExistingSignatureLine.docx", certHolder, signOptions);
```

Обязательно укажите правильные пути к исходному документу, подписанному документу и сертификату.

### Пример исходного кода для подписания существующей строки подписи с использованием Aspose.Words для .NET

Вот полный исходный код для подписи существующей строки подписи с помощью Aspose.Words для .NET:


```csharp

	// Путь к каталогу документов.
	string dataDir = "YOUR DOCUMENT DIRECTORY";
	Document doc = new Document(dataDir + "Signature line.docx");
	
	SignatureLine signatureLine =
		((Shape) doc.FirstSection.Body.GetChild(NodeType.Shape, 0, true)).SignatureLine;

	SignOptions signOptions = new SignOptions
	{
		SignatureLineId = signatureLine.Id,
		SignatureLineImage = File.ReadAllBytes(ImagesDir + "Enhanced Windows MetaFile.emf")
	};

	CertificateHolder certHolder = CertificateHolder.Create(dataDir + "morzal.pfx", "aw");
	
	DigitalSignatureUtil.Sign(dataDir + "Digitally signed.docx",
		dataDir + "SignDocuments.SigningExistingSignatureLine.docx", certHolder, signOptions);
	

```

Следуя этим шагам, вы можете легко подписать существующую строку подписи в документе Word с помощью Aspose.Words для .NET.

