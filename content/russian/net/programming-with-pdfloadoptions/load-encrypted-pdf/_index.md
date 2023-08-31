---
title: Загрузить зашифрованный PDF-файл
linktitle: Загрузить зашифрованный PDF-файл
second_title: API обработки документов Aspose.Words
description: Пошаговое руководство по загрузке зашифрованного PDF-файла с помощью Aspose.Words для .NET.
type: docs
weight: 10
url: /ru/net/programming-with-pdfloadoptions/load-encrypted-pdf/
---

При обработке текстов PDF-документов в приложении .NET может потребоваться загрузка PDF-файлов, защищенных паролем. Aspose.Words for .NET — это мощная библиотека, предоставляющая функциональные возможности для загрузки зашифрованных PDF-документов. В этой статье мы шаг за шагом покажем вам, как понять и использовать эту функцию.

## Понимание функции загрузки зашифрованных PDF-файлов

Функция загрузки зашифрованного PDF в Aspose.Words for .NET позволяет загружать PDF-файлы, защищенные паролем. Вы можете указать пароль при загрузке документа, чтобы иметь доступ к его содержимому и манипулировать им по мере необходимости.

## Шаг 1. Загрузка зашифрованного PDF-документа

Первым шагом является загрузка зашифрованного PDF-документа в ваше приложение. Вот как это сделать:

```csharp
// Путь к каталогу документов.
string dataDir = "YOUR_DIRECTORY_OF_DOCUMENTS";
Document doc = new Document(dataDir + "Document.pdf");
```

 Обязательно укажите правильный путь к зашифрованному PDF-файлу в`dataDir` переменная.

## Шаг 2. Шифрование PDF-документа

 Если вы также хотите зашифровать свой PDF-документ, вы можете сделать это с помощью`PdfSaveOptions` class и указав детали шифрования:

```csharp
PdfSaveOptions saveOptions = new PdfSaveOptions
{
EncryptionDetails = new PdfEncryptionDetails("Aspose", null)
};

```

Это создаст зашифрованную версию PDF-документа в указанном каталоге.

## Шаг 3. Сохранение зашифрованного PDF-документа

После загрузки и (при необходимости) шифрования PDF-документа вы можете сохранить его в другом формате или обработать дальше в соответствии с вашими конкретными потребностями.

```csharp
doc.Save(dataDir + "WorkingWithPdfLoadOptions.LoadEncryptedPdf.pdf", saveOptions);
```

## Шаг 5. Загрузка зашифрованного PDF-документа с паролем

Обслуживание

 Однако если вы хотите загрузить зашифрованный PDF-документ с паролем, вам необходимо использовать`PdfLoadOptions` class и укажите пароль при загрузке документа:

```csharp
PdfLoadOptions loadOptions = new PdfLoadOptions { Password = "Aspose", LoadFormat = LoadFormat.Pdf };

doc = new Document(dataDir + "WorkingWithPdfLoadOptions.LoadEncryptedPdf.pdf", loadOptions);
```

 Обязательно укажите правильный пароль в`Password` переменная.

### Пример исходного кода для загрузки зашифрованного PDF с использованием Aspose.Words для .NET

```csharp

	// Путь к каталогу документов.
	string dataDir = "YOUR DOCUMENT DIRECTORY";
	Document doc = new Document(dataDir + "Pdf Document.pdf");

	PdfSaveOptions saveOptions = new PdfSaveOptions
	{
		EncryptionDetails = new PdfEncryptionDetails("Aspose", null)
	};

	doc.Save(dataDir + "WorkingWithPdfLoadOptions.LoadEncryptedPdf.pdf", saveOptions);

	PdfLoadOptions loadOptions = new PdfLoadOptions { Password = "Aspose", LoadFormat = LoadFormat.Pdf };

	doc = new Document(dataDir + "WorkingWithPdfLoadOptions.LoadEncryptedPdf.pdf", loadOptions);
        
```

## Заключение

В этой статье мы рассмотрели, как использовать функцию загрузки зашифрованного PDF в Aspose.Words для .NET. Вы узнали, как загружать зашифрованные PDF-файлы, как зашифровать PDF-документ, как загружать зашифрованный PDF-файл с паролем и как генерировать выходные данные в формате Markdown. Эта функция чрезвычайно полезна при обработке текстов с защищенными PDF-документами.


