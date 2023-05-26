---
title: توقيع خط التوقيع الحالي
linktitle: توقيع خط التوقيع الحالي
second_title: Aspose.Words لمراجع .NET API
description: تعرف على كيفية توقيع سطر توقيع موجود في مستند Word باستخدام Aspose.Words for .NET.
type: docs
weight: 10
url: /de/net/programming-with-digital-signatures/signing-existing-signature-line/
---

في هذا البرنامج التعليمي ، سنرشدك خلال الخطوات لاستخدام ميزة التوقيع لسطر التوقيع الحالي مع Aspose.Words for .NET. تتيح لك هذه الميزة التوقيع رقميًا على سطر توقيع موجود بالفعل في مستند Word. اتبع الخطوات التالية:

## الخطوة 1: تحميل المستند والوصول إلى سطر التوقيع

ابدأ بتحميل المستند الذي يحتوي على سطر التوقيع الموجود:

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document doc = new Document(dataDir + "Signature line.docx");

SignatureLine signatureLine = ((Shape)doc.FirstSection.Body.GetChild(NodeType.Shape, 0, true)).SignatureLine;
```

## الخطوة 2: تعيين خيارات التوقيع

قم بإنشاء مثيل لفئة SignOptions وقم بتعيين خيارات التوقيع ، بما في ذلك معرف سطر التوقيع وصورة خط التوقيع:

```csharp
SignOptions signOptions = new SignOptions
{
SignatureLineId = signatureLine.Id,
SignatureLineImage = File.ReadAllBytes(ImagesDir + "Enhanced Windows MetaFile.emf")
};
```

تأكد من تحديد المسار الصحيح لصورة خط التوقيع.

## الخطوة الثالثة: تحميل الشهادة

ابدأ بتحميل شهادة التوقيع باستخدام فئة CertificateHolder:

```csharp
CertificateHolder certHolder = CertificateHolder.Create(dataDir + "morzal.pfx", "aw");
```

تأكد من تحديد المسار الصحيح لشهادتك وكلمة المرور المرتبطة بها.

## الخطوة 4: توقيع سطر التوقيع الحالي

استخدم فئة DigitalSignatureUtil لتوقيع سطر التوقيع الموجود:

```csharp
DigitalSignatureUtil.Sign(dataDir + "Digitally signed.docx",
	dataDir + "SignDocuments.SigningExistingSignatureLine.docx", certHolder, signOptions);
```

تأكد من تحديد المسارات الصحيحة للمستند المصدر والمستند الموقع والشهادة.

### مثال على شفرة المصدر لتوقيع سطر التوقيع الحالي باستخدام Aspose.Words for .NET

إليك كود المصدر الكامل لتوقيع سطر توقيع موجود مع Aspose.Words for .NET:


```csharp

	// المسار إلى دليل المستندات.
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

باتباع هذه الخطوات ، يمكنك بسهولة توقيع سطر توقيع موجود في مستند Word باستخدام Aspose.Words for .NET.

