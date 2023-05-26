---
title: توقيع الوثيقة
linktitle: توقيع الوثيقة
second_title: Aspose.Words لمراجع .NET API
description: تعرف على كيفية توقيع مستند Word رقميًا باستخدام Aspose.Words for .NET.
type: docs
weight: 10
url: /ru/net/programming-with-digital-signatures/sign-document/
---

في هذا البرنامج التعليمي ، سنرشدك عبر خطوات استخدام ميزة توقيع المستند مع Aspose.Words for .NET. تتيح لك هذه الميزة التوقيع رقميًا على مستند Word باستخدام شهادة. اتبع الخطوات التالية:

## الخطوة الأولى: تحميل الشهادة

ابدأ بتحميل شهادة التوقيع باستخدام فئة CertificateHolder:

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
CertificateHolder certHolder = CertificateHolder.Create(dataDir + "morzal.pfx", "aw");
```

تأكد من تحديد المسار الصحيح لشهادتك وكلمة المرور المرتبطة بها.

## الخطوة الثانية: توقيع الوثيقة

استخدم فئة DigitalSignatureUtil لتوقيع الوثيقة:

```csharp
DigitalSignatureUtil.Sign(dataDir + "Digitally signed.docx", dataDir + "Document.Signed.docx",
	certHolder);
```

تأكد من تحديد المسارات الصحيحة للمستند المصدر والمستند الموقع.

### مثال على الكود المصدري لتوقيع الوثيقة باستخدام Aspose.Words for .NET

فيما يلي الكود المصدري الكامل للتوقيع على مستند باستخدام Aspose.Words for .NET:

```csharp

	// المسار إلى دليل المستندات.
	string dataDir = "YOUR DOCUMENT DIRECTORY";
	CertificateHolder certHolder = CertificateHolder.Create(dataDir + "morzal.pfx", "aw");
	
	DigitalSignatureUtil.Sign(dataDir + "Digitally signed.docx", dataDir + "Document.Signed.docx",
		certHolder);

```

باتباع هذه الخطوات ، يمكنك بسهولة توقيع مستند Word باستخدام Aspose.Words for .NET.



