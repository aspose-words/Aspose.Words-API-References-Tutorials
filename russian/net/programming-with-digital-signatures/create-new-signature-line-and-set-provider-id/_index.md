---
title: Создайте новую строку подписи и установите идентификатор поставщика
linktitle: Создайте новую строку подписи и установите идентификатор поставщика
second_title: API обработки документов Aspose.Words
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

## Заключение

В этом руководстве мы рассмотрели функцию создания новой строки подписи и установки идентификатора поставщика в документе Word с помощью Aspose.Words для .NET. Следуя предоставленным шагам, вы можете легко вставить строку подписи с настраиваемыми параметрами и связать ее с конкретным поставщиком, используя идентификатор поставщика. Добавление строк подписи и настройка информации о поставщике повышают подлинность и надежность ваших документов. Aspose.Words для .NET предоставляет мощный API для обработки слов со строками подписи и цифровыми сертификатами в документах Word, что позволяет автоматизировать процесс подписания и гарантировать достоверность ваших документов.

### Часто задаваемые вопросы

#### В: Что такое идентификатор поставщика в строке подписи?

О. Идентификатор поставщика в строке подписи — это уникальный идентификатор, представляющий поставщика цифровой подписи. Это помогает определить источник или организацию, ответственную за подпись.

#### В: Как создать новую строку подписи в документе Word с помощью Aspose.Words for .NET?

О: Чтобы создать новую строку подписи в документе Word с помощью Aspose.Words for .NET, выполните следующие действия:
1.  Создайте экземпляр`Document` класс и`DocumentBuilder` объект.
2.  Создайте экземпляр`SignatureLineOptions` class и установите нужные параметры строки подписи.
3.  Использовать`InsertSignatureLine` метод`DocumentBuilder` объект для вставки строки подписи в документ.

#### В: Могу ли я настроить параметры строки подписи, такие как имя подписавшего, должность и инструкции?

 О: Да, вы можете настроить параметры строки подписи.`SignatureLineOptions` класс предоставляет свойства для установки желаемых параметров, таких как`Signer`, `SignerTitle`, `Instructions`, `AllowComments`и т. д. Вы можете изменить эти свойства перед вставкой строки подписи.

#### В: Какова цель установки идентификатора провайдера для строки подписи?

О: Установка идентификатора поставщика для строки подписи помогает определить источник или организацию, ответственную за цифровую подпись. Это позволяет связать подпись с конкретным поставщиком или объектом, предоставляя дополнительную информацию о происхождении и надежности подписи.

#### В: Как установить идентификатор провайдера для строки подписи с помощью Aspose.Words for .NET?

О: Чтобы установить идентификатор провайдера для строки подписи с помощью Aspose.Words for .NET, выполните следующие действия:
1.  После вставки строки подписи перейдите к`ProviderId`собственность`SignatureLine` объект.
2.  Установить`ProviderId` на желаемое значение идентификатора поставщика с помощью`Guid` тип данных.

#### В: Могу ли я подписать документ после создания новой строки подписи и установки идентификатора провайдера?

 О: Да, после создания новой строки подписи и установки идентификатора провайдера вы можете подписать документ. Чтобы подписать документ, вам необходимо установить параметры подписи, включая идентификатор строки подписи, идентификатор поставщика, комментарии и время подписания. Затем используйте`DigitalSignatureUtil.Sign` способ подписать документ с помощью цифрового сертификата.

#### Вопрос. Можно ли указать идентификатор поставщика для каждой строки подписи в документе Word?

О: Да, вы можете указать конкретный идентификатор поставщика для каждой строки подписи в документе Word. После вставки каждой строки подписи вы можете установить идентификатор поставщика для этой конкретной строки подписи, обратившись к`ProviderId` собственность соответствующих`SignatureLine` объект.

#### В: Как сохранить измененный документ после создания новой строки подписи и установки идентификатора провайдера?

 О: Чтобы сохранить измененный документ после создания новой строки подписи и установки идентификатора провайдера, вы можете использовать`Save` метод`Document` объект. Укажите правильный путь и имя файла для сохранения документа.

#### В: Какой формат файла поддерживает Aspose.Words for .NET для создания и подписания строк подписи?

О: Aspose.Words для .NET поддерживает создание и подписание строк подписи в формате файла DOCX. Вы можете создавать и подписывать строки подписи в файлах DOCX, используя предоставленные методы и классы.

#### В: Могу ли я изменить идентификатор провайдера или другие параметры строки подписи после того, как она была подписана?

О: После того, как строка подписи была подписана, она становится частью содержимого документа и не может быть изменена отдельно. Любые изменения в строке подписи, такие как изменение идентификатора поставщика или других параметров, потребуют удаления существующей подписи и создания новой строки подписи.