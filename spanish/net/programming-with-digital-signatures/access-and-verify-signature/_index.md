---
title: الوصول والتحقق من التوقيع
linktitle: الوصول والتحقق من التوقيع
second_title: Aspose.Words لمراجع .NET API
description: تعرف على كيفية الوصول إلى التوقيعات الرقمية والتحقق منها في مستند Word باستخدام Aspose.Words for .NET.
type: docs
weight: 10
url: /es/net/programming-with-digital-signatures/access-and-verify-signature/
---
في هذا البرنامج التعليمي ، سنوجهك خلال الخطوات لاستخدام ميزة التحقق من الوصول والتوقيع في Aspose.Words for .NET. تتيح لك هذه الميزة الوصول إلى التوقيعات الرقمية في مستند Word والتحقق من صحتها. اتبع الخطوات التالية:

## الخطوة 1: تحميل المستند والوصول إلى التوقيعات

ابدأ بتحميل المستند الذي يحتوي على توقيعات رقمية:

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document doc = new Document(dataDir + "Digitally signed.docx");
```

## الخطوة 2: تصفح التوقيعات الرقمية

استخدم حلقة للتكرار خلال جميع التوقيعات الرقمية في المستند:

```csharp
foreach (DigitalSignature signature in doc.DigitalSignatures)
{
	// الوصول إلى معلومات التوقيع
	Console.WriteLine("*** Signature Found ***");
	Console.WriteLine("Is valid: " + signature.IsValid);
	// هذه الخاصية متاحة في مستندات MS Word فقط.
	Console.WriteLine("Reason for signing: " + signature.Comments); 
	Console.WriteLine("Time of signing: " + signature.SignTime);
	Console.WriteLine("Subject name: " + signature.CertificateHolder.Certificate.SubjectName.Name);
	Console.WriteLine("Issuer name: " + signature.CertificateHolder.Certificate.IssuerName.Name);
	Console.WriteLine();
}
```

تأكد من تخصيص رسائل العرض وفقًا لاحتياجاتك.

### مثال على شفرة المصدر للوصول والتحقق من التوقيع باستخدام Aspose.Words for .NET

فيما يلي رمز المصدر الكامل للوصول والتحقق من التوقيع باستخدام Aspose.Words for .NET:

```csharp
	
	// المسار إلى دليل المستندات.
	string dataDir = "YOUR DOCUMENT DIRECTORY";
	Document doc = new Document(dataDir + "Digitally signed.docx");

	foreach (DigitalSignature signature in doc.DigitalSignatures)
	{
		Console.WriteLine("*** Signature Found ***");
		Console.WriteLine("Is valid: " + signature.IsValid);
		// هذه الخاصية متاحة في مستندات MS Word فقط.
		Console.WriteLine("Reason for signing: " + signature.Comments); 
		Console.WriteLine("Time of signing: " + signature.SignTime);
		Console.WriteLine("Subject name: " + signature.CertificateHolder.Certificate.SubjectName.Name);
		Console.WriteLine("Issuer name: " + signature.CertificateHolder.Certificate.IssuerName.Name);
		Console.WriteLine();
	}

```

باتباع هذه الخطوات ، ستتمكن بسهولة من الوصول والتحقق من التوقيعات الرقمية في مستند Word الخاص بك باستخدام Aspose.Words for .NET.


