---
title: Подписание существующей строки подписи в документе Word
linktitle: Подписание существующей строки подписи в документе Word
second_title: API обработки документов Aspose.Words
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

## Заключение

В этом руководстве мы узнали, как подписать существующую строку подписи в документе Word с помощью Aspose.Words для .NET. Следуя предоставленным шагам, вы можете легко загрузить документ, получить доступ к существующей строке подписи, установить параметры подписи и подписать документ. Возможность подписывать существующую строку подписи предоставляет удобный способ добавления цифровых подписей в предопределенные области документов Word, обеспечивая целостность и аутентификацию документа. Aspose.Words для .NET предлагает мощный API для обработки текстов с цифровыми подписями, позволяющий настраивать процесс подписи и повышать безопасность ваших документов Word.

### Часто задаваемые вопросы

#### В: Что такое существующая строка подписи в документе Word?

О: Существующая строка подписи в документе Word — это предварительно определенная область, в которой может быть размещена подпись. Обычно он представлен фигурой или объектом в документе и служит обозначенным местом для подписывающей стороны, чтобы добавить свою цифровую подпись.

#### В: Как я могу подписать существующую строку подписи в документе Word, используя Aspose.Words для .NET?

О: Чтобы подписать существующую строку подписи в документе Word с помощью Aspose.Words for .NET, выполните следующие действия:
1.  Загрузите документ с помощью`Document` class и указать путь к файлу документа.
2.  Получите доступ к существующей строке подписи, используя соответствующий метод или свойство. Например, вы можете использовать`GetChild` метод для получения формы линии подписи.
3.  Создайте экземпляр`SignOptions`класс и установить`SignatureLineId` на идентификатор существующей строки подписи.
4.  Установить`SignatureLineImage` собственность`SignOptions` class к изображению, представляющему цифровую подпись.
5.  Загрузите сертификат подписи с помощью`CertificateHolder` class и предоставить необходимый сертификат и пароль.
6.  Использовать`DigitalSignatureUtil.Sign` способ подписать документ, предоставив необходимые параметры, включая`SignOptions` объект.

#### Вопрос. Как получить доступ к существующей строке подписи в документе Word с помощью Aspose.Words for .NET?

 О: Чтобы получить доступ к существующей строке подписи в документе Word с помощью Aspose.Words for .NET, вы можете использовать соответствующий метод или свойство для извлечения формы строки подписи из структуры документа. Например, вы можете использовать`GetChild` метод с соответствующими параметрами, чтобы получить желаемую форму линии подписи.

#### Вопрос. Можно ли настроить внешний вид цифровой подписи в существующей строке подписи?

О: Да, вы можете настроить внешний вид цифровой подписи в существующей строке подписи, предоставив файл изображения, представляющий подпись. Изображение может быть логотипом, рукописной подписью или любым другим графическим представлением подписи. Вы можете установить`SignatureLineImage` собственность`SignOptions` class к байтам файла изображения.

#### Вопрос. Можно ли подписать несколько существующих строк подписи в документе Word?
 О: Да, вы можете подписать несколько существующих строк подписи в документе Word. Вам необходимо выполнить шаги для каждой строки подписи в отдельности, установив соответствующий`SignatureLineId` и`SignatureLineImage` ценности в`SignOptions` объект для каждой строки подписи.

#### Вопрос. В каком формате должен быть файл изображения для цифровой подписи в существующей строке подписи?

 О: Файл изображения для цифровой подписи в существующей строке подписи может быть в различных форматах, таких как PNG, JPEG, BMP или GIF. Вы можете указать путь к файлу или прочитать байты файла изображения и назначить его`SignatureLineImage` собственность`SignOptions` сорт.