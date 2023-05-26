---
title: Подписание зашифрованного документа
linktitle: Подписание зашифрованного документа
second_title: Справочник по API Aspose.Words для .NET
description: Узнайте, как поставить цифровую подпись на зашифрованный документ с помощью Aspose.Words для .NET.
type: docs
weight: 10
url: /ru/net/programming-with-digital-signatures/signing-encrypted-document/
---

В этом руководстве мы покажем вам, как использовать функцию подписи зашифрованного документа с помощью Aspose.Words для .NET. Эта функция позволяет ставить цифровую подпись в документе Word, зашифрованном с помощью пароля для расшифровки. Выполните следующие действия:

## Шаг 1: Настройка параметров подписи

Создайте экземпляр класса SignOptions и установите пароль для расшифровки:

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
SignOptions signOptions = new SignOptions { DecryptionPassword = "decryptionpassword" };
```

Обязательно укажите правильный пароль для расшифровки зашифрованного документа.

## Шаг 2: Загрузка сертификата

Начните с загрузки сертификата подписи с помощью класса CertificateHolder:

```csharp
CertificateHolder certHolder = CertificateHolder.Create(dataDir + "morzal.pfx", "aw");
```

Обязательно укажите правильный путь к сертификату и связанный с ним пароль.

## Шаг 3: Подписание зашифрованного документа

Используйте класс DigitalSignatureUtil для подписи зашифрованного документа:

```csharp
DigitalSignatureUtil.Sign(dataDir + "Digitally signed.docx", dataDir + "Document.EncryptedDocument.docx",
	certHolder, signOptions);
```

Обязательно укажите правильные пути для зашифрованного документа, подписанного документа и сертификата.

### Пример исходного кода для подписания зашифрованного документа с использованием Aspose.Words для .NET

Вот полный исходный код для подписи зашифрованного документа с помощью Aspose.Words для .NET:

```csharp

	// Путь к каталогу документов.
	string dataDir = "YOUR DOCUMENT DIRECTORY";
	SignOptions signOptions = new SignOptions { DecryptionPassword = "decryptionPassword" };

	CertificateHolder certHolder = CertificateHolder.Create(dataDir + "morzal.pfx", "aw");
	
	DigitalSignatureUtil.Sign(dataDir + "Digitally signed.docx", dataDir + "Document.EncryptedDocument.docx",
		certHolder, signOptions);
	

```
Следуя этим шагам, вы можете легко подписать зашифрованный документ Word с помощью Aspose.Words для .NET.

