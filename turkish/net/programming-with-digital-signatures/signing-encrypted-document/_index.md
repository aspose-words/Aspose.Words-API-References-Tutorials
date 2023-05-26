---
title: توقيع وثيقة مشفرة
linktitle: توقيع وثيقة مشفرة
second_title: Aspose.Words لمراجع .NET API
description: تعرف على كيفية التوقيع رقميًا على مستند مشفر باستخدام Aspose.Words for .NET.
type: docs
weight: 10
url: /tr/net/programming-with-digital-signatures/signing-encrypted-document/
---

في هذا البرنامج التعليمي ، سنوجهك عبر خطوات استخدام ميزة توقيع مستند مشفر باستخدام Aspose.Words for .NET. تتيح لك هذه الميزة التوقيع رقميًا على مستند Word المشفر باستخدام كلمة مرور فك التشفير. اتبع الخطوات التالية:

## الخطوة 1: تعيين خيارات التوقيع

قم بإنشاء مثيل لفئة SignOptions وقم بتعيين كلمة مرور فك التشفير:

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
SignOptions signOptions = new SignOptions { DecryptionPassword = "decryptionpassword" };
```

تأكد من تحديد كلمة مرور فك التشفير الصحيحة للمستند المشفر.

## الخطوة الثانية: تحميل الشهادة

ابدأ بتحميل شهادة التوقيع باستخدام فئة CertificateHolder:

```csharp
CertificateHolder certHolder = CertificateHolder.Create(dataDir + "morzal.pfx", "aw");
```

تأكد من تحديد المسار الصحيح لشهادتك وكلمة المرور المرتبطة بها.

## الخطوة الثالثة: توقيع الوثيقة المشفرة

استخدم فئة DigitalSignatureUtil لتوقيع المستند المشفر:

```csharp
DigitalSignatureUtil.Sign(dataDir + "Digitally signed.docx", dataDir + "Document.EncryptedDocument.docx",
	certHolder, signOptions);
```

تأكد من تحديد المسارات الصحيحة للمستند المشفر والمستند الموقع والشهادة.

### مثال على شفرة المصدر لتوقيع المستند المشفر باستخدام Aspose.Words for .NET

فيما يلي رمز المصدر الكامل لتوقيع مستند مشفر باستخدام Aspose.Words for .NET:

```csharp

	// المسار إلى دليل المستندات.
	string dataDir = "YOUR DOCUMENT DIRECTORY";
	SignOptions signOptions = new SignOptions { DecryptionPassword = "decryptionPassword" };

	CertificateHolder certHolder = CertificateHolder.Create(dataDir + "morzal.pfx", "aw");
	
	DigitalSignatureUtil.Sign(dataDir + "Digitally signed.docx", dataDir + "Document.EncryptedDocument.docx",
		certHolder, signOptions);
	

```
باتباع هذه الخطوات ، يمكنك بسهولة توقيع مستند Word مشفر باستخدام Aspose.Words for .NET.

