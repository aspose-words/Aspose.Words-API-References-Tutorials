---
title: Создание и подписание новой строки подписи
linktitle: Создание и подписание новой строки подписи
second_title: Справочник по API Aspose.Words для .NET
description: Узнайте, как создать и подписать новую строку подписи в документе Word с помощью Aspose.Words для .NET.
type: docs
weight: 10
url: /ru/net/programming-with-digital-signatures/creating-and-signing-new-signature-line/
---

В этом руководстве мы покажем вам, как использовать функцию создания и подписания новой строки подписи с помощью Aspose.Words для .NET. Эта функция позволяет вставлять строку подписи в документ Word, задавать пользовательские параметры и подписывать документ. Выполните следующие действия:

## Шаг 1: Создание документа и генератора

Начните с создания экземпляра класса Document и объекта DocumentBuilder:

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
```

## Шаг 2: Вставка строки подписи

Используйте метод InsertSignatureLine() объекта DocumentBuilder, чтобы вставить новую строку подписи в документ:

```csharp
SignatureLine signatureLine = builder.InsertSignatureLine(new SignatureLineOptions()).SignatureLine;
```

## Шаг 3: Сохраните документ

Сохраните измененный документ:

```csharp
doc.Save(dataDir + "SignDocuments.SignatureLine.docx");
```

Обязательно укажите правильный путь и имя файла для сохранения документа.

## Шаг 4: Подписание документа

Чтобы подписать документ, вам нужно установить параметры подписи и использовать класс DigitalSignatureUtil:

```csharp
SignOptions signOptions = new SignOptions
{
	SignatureLineId = signatureLine.Id,
	SignatureLineImage = File.ReadAllBytes(ImagesDir + "Enhanced Windows MetaFile.emf")
};

CertificateHolder certHolder = CertificateHolder.Create(MyDir + "morzal.pfx", "aw");

DigitalSignatureUtil.Sign(dataDir + "SignDocuments.SignatureLine.docx",
	dataDir + "SignDocuments.NewSignatureLine.docx", certHolder, signOptions);
```

Обязательно укажите правильные пути к документу, изображению строки подписи и подписанному документу.

### Пример исходного кода для создания и подписания новой строки подписи с использованием Aspose.Words для .NET

Вот полный исходный код для создания и подписания новой строки подписи с помощью Aspose.Words для .NET:

```csharp

	// Путь к каталогу документов.
	string dataDir = "YOUR DOCUMENT DIRECTORY";
	Document doc = new Document();
	DocumentBuilder builder = new DocumentBuilder(doc);

	SignatureLine signatureLine = builder.InsertSignatureLine(new SignatureLineOptions()).SignatureLine;
	
	doc.Save(dataDir + "SignDocuments.SignatureLine.docx");

	SignOptions signOptions = new SignOptions
	{
		SignatureLineId = signatureLine.Id,
		SignatureLineImage = File.ReadAllBytes(ImagesDir + "Enhanced Windows MetaFile.emf")
	};

	CertificateHolder certHolder = CertificateHolder.Create(MyDir + "morzal.pfx", "aw");
	
	DigitalSignatureUtil.Sign(dataDir + "SignDocuments.SignatureLine.docx",
		dataDir + "SignDocuments.NewSignatureLine.docx", certHolder, signOptions);

```

Выполнив эти шаги, вы сможете легко создать и подписать новую строку подписи в документе Word с помощью Aspose.Words для .NET.

