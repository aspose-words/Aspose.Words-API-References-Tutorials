---
title: Доступ и проверка подписи
linktitle: Доступ и проверка подписи
second_title: Справочник по API Aspose.Words для .NET
description: Узнайте, как получить доступ и проверить цифровые подписи в документе Word с помощью Aspose.Words для .NET.
type: docs
weight: 10
url: /ru/net/programming-with-digital-signatures/access-and-verify-signature/
---
В этом руководстве мы покажем вам, как использовать функцию проверки доступа и подписи Aspose.Words для .NET. Эта функция позволяет получить доступ к цифровым подписям в документе Word и проверить их действительность. Выполните следующие действия:

## Шаг 1. Загрузка документа и доступ к подписям

Начните с загрузки документа, содержащего цифровые подписи:

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document doc = new Document(dataDir + "Digitally signed.docx");
```

## Шаг 2. Просмотр цифровых подписей

Используйте цикл для перебора всех цифровых подписей в документе:

```csharp
foreach (DigitalSignature signature in doc.DigitalSignatures)
{
	// Доступ к информации о подписи
	Console.WriteLine("*** Signature Found ***");
	Console.WriteLine("Is valid: " + signature.IsValid);
	// Это свойство доступно только в документах MS Word.
	Console.WriteLine("Reason for signing: " + signature.Comments); 
	Console.WriteLine("Time of signing: " + signature.SignTime);
	Console.WriteLine("Subject name: " + signature.CertificateHolder.Certificate.SubjectName.Name);
	Console.WriteLine("Issuer name: " + signature.CertificateHolder.Certificate.IssuerName.Name);
	Console.WriteLine();
}
```

Обязательно настройте отображаемые сообщения в соответствии с вашими потребностями.

### Пример исходного кода для доступа и проверки подписи с использованием Aspose.Words для .NET

Вот полный исходный код для проверки доступа и подписи с использованием Aspose.Words для .NET:

```csharp
	
	// Путь к каталогу документов.
	string dataDir = "YOUR DOCUMENT DIRECTORY";
	Document doc = new Document(dataDir + "Digitally signed.docx");

	foreach (DigitalSignature signature in doc.DigitalSignatures)
	{
		Console.WriteLine("*** Signature Found ***");
		Console.WriteLine("Is valid: " + signature.IsValid);
		// Это свойство доступно только в документах MS Word.
		Console.WriteLine("Reason for signing: " + signature.Comments); 
		Console.WriteLine("Time of signing: " + signature.SignTime);
		Console.WriteLine("Subject name: " + signature.CertificateHolder.Certificate.SubjectName.Name);
		Console.WriteLine("Issuer name: " + signature.CertificateHolder.Certificate.IssuerName.Name);
		Console.WriteLine();
	}

```

Выполнив эти шаги, вы сможете легко получить доступ и проверить цифровые подписи в документе Word с помощью Aspose.Words для .NET.


