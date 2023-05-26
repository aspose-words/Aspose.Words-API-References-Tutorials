---
title: PDF-файл с цифровой подписью с использованием держателя сертификата
linktitle: PDF-файл с цифровой подписью с использованием держателя сертификата
second_title: Справочник по API Aspose.Words для .NET
description: Узнайте, как подписать PDF-файл цифровой подписью с помощью держателя сертификата с помощью Aspose.Words для .NET.
type: docs
weight: 10
url: /ru/net/programming-with-pdfsaveoptions/digitally-signed-pdf-using-certificate-holder/
---

В этом руководстве мы покажем вам, как создать PDF-файл с цифровой подписью с использованием сертификата Aspose.Words для .NET. Цифровая подпись добавляет уровень безопасности и целостности PDF-документу. Выполните следующие действия:

## Шаг 1. Создание документа и добавление содержимого

Начните с создания экземпляра класса Document:

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
```

## Шаг 2. Добавьте содержимое в документ

 Затем используйте`DocumentBuilder` для добавления содержимого в документ. Например, чтобы добавить абзац, содержащий текст «Пробная подпись PDF», используйте кнопку`Writeln` метод:

```csharp
builder.Writeln("Test Signed PDF.");
```

При необходимости вы можете добавить другие элементы контента.

## Шаг 3. Установите параметры сохранения PDF

Создайте экземпляр класса PdfSaveOptions и укажите данные цифровой подписи:

```csharp
PdfSaveOptions saveOptions = new PdfSaveOptions
{
	DigitalSignatureDetails = new PdfDigitalSignatureDetails(
		CertificateHolder.Create(MyDir + "morzal.pfx", "aw"), "reason", "location",
		DateTime.Now)
};
```

Обязательно укажите правильный путь к сертификату и связанный с ним пароль. Вы также можете настроить причину и место подписи.

## Шаг 4. Сохраните документ как PDF с цифровой подписью

 Использовать`Save` метод сохранения документа в формате PDF, указав параметры сохранения:

```csharp
doc.Save(dataDir + "WorkingWithPdfSaveOptions.DigitallySignedPdfUsingCertificateHolder.pdf", saveOptions);
```

Обязательно укажите правильный путь для сохранения PDF-файла с цифровой подписью.

Следуя этим шагам, вы можете легко создать PDF-файл с цифровой подписью и сертификатом, используя Aspose.Words для .NET.

### Пример исходного кода для Pdf с цифровой подписью с использованием держателя сертификата с использованием Aspose.Words для .NET

Вот полный исходный код для цифровой подписи Pdf с использованием держателя сертификата из документа с использованием Aspose.Words для .NET:

```csharp

            // Путь к каталогу документов.
			string dataDir = "YOUR DOCUMENT DIRECTORY";
            Document doc = new Document();
            DocumentBuilder builder = new DocumentBuilder(doc);
            
            builder.Writeln("Test Signed PDF.");

            PdfSaveOptions saveOptions = new PdfSaveOptions
            {
                DigitalSignatureDetails = new PdfDigitalSignatureDetails(
                    CertificateHolder.Create(MyDir + "morzal.pfx", "aw"), "reason", "location",
                    DateTime.Now)
            };

            doc.Save(dataDir + "WorkingWithPdfSaveOptions.DigitallySignedPdfUsingCertificateHolder.pdf", saveOptions);
            
        
```
