---
title: Подписать документ
linktitle: Подписать документ
second_title: Справочник по API Aspose.Words для .NET
description: Узнайте, как подписать документ Word цифровой подписью с помощью Aspose.Words для .NET.
type: docs
weight: 10
url: /ru/net/programming-with-digital-signatures/sign-document/
---

В этом руководстве мы покажем вам, как использовать функцию подписания документов с Aspose.Words для .NET. Эта функция позволяет подписывать документ Word цифровой подписью с помощью сертификата. Выполните следующие действия:

## Шаг 1: Загрузка сертификата

Начните с загрузки сертификата подписи с помощью класса CertificateHolder:

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
CertificateHolder certHolder = CertificateHolder.Create(dataDir + "morzal.pfx", "aw");
```

Обязательно укажите правильный путь к сертификату и связанный с ним пароль.

## Шаг 2: Подписание документа

Используйте класс DigitalSignatureUtil для подписи документа:

```csharp
DigitalSignatureUtil.Sign(dataDir + "Digitally signed.docx", dataDir + "Document.Signed.docx",
	certHolder);
```

Обязательно укажите правильные пути к исходному документу и подписанному документу.

### Пример исходного кода для подписания документа с использованием Aspose.Words для .NET

Вот полный исходный код для подписи документа с помощью Aspose.Words для .NET:

```csharp

	// Путь к каталогу документов.
	string dataDir = "YOUR DOCUMENT DIRECTORY";
	CertificateHolder certHolder = CertificateHolder.Create(dataDir + "morzal.pfx", "aw");
	
	DigitalSignatureUtil.Sign(dataDir + "Digitally signed.docx", dataDir + "Document.Signed.docx",
		certHolder);

```

Следуя этим шагам, вы можете легко подписать документ Word с помощью Aspose.Words для .NET.



