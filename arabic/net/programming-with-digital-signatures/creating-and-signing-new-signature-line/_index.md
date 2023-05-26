---
title: إنشاء وتوقيع خط توقيع جديد
linktitle: إنشاء وتوقيع خط توقيع جديد
second_title: Aspose.Words لمراجع .NET API
description: تعرف على كيفية إنشاء سطر توقيع جديد والتوقيع عليه في مستند Word باستخدام Aspose.Words for .NET.
type: docs
weight: 10
url: /ar/net/programming-with-digital-signatures/creating-and-signing-new-signature-line/
---

في هذا البرنامج التعليمي ، سنرشدك خلال الخطوات لاستخدام ميزة إنشاء سطر توقيع جديد وتوقيعه باستخدام Aspose.Words for .NET. تتيح لك هذه الميزة إدراج سطر توقيع في مستند Word ، وتعيين الخيارات المخصصة وتوقيع المستند. اتبع الخطوات التالية:

## الخطوة 1: إنشاء المستند والمولد

ابدأ بإنشاء مثيل لفئة Document وكائن DocumentBuilder:

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
```

## الخطوة 2: إدخال سطر التوقيع

استخدم طريقة InsertSignatureLine () لكائن DocumentBuilder لإدراج سطر توقيع جديد في المستند:

```csharp
SignatureLine signatureLine = builder.InsertSignatureLine(new SignatureLineOptions()).SignatureLine;
```

## الخطوة 3: احفظ المستند

احفظ المستند المعدل:

```csharp
doc.Save(dataDir + "SignDocuments.SignatureLine.docx");
```

تأكد من تحديد المسار الصحيح واسم الملف لحفظ المستند.

## الخطوة 4: توقيع الوثيقة

لتوقيع الوثيقة ، تحتاج إلى تعيين خيارات التوقيع واستخدام فئة DigitalSignatureUtil:

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

تأكد من تحديد المسارات الصحيحة للمستند وصورة خط التوقيع والمستند الموقع.

### مثال على شفرة المصدر لإنشاء وتوقيع سطر توقيع جديد باستخدام Aspose.Words for .NET

إليك شفرة المصدر الكاملة لإنشاء وتوقيع سطر توقيع جديد باستخدام Aspose.Words for .NET:

```csharp

	// المسار إلى دليل المستندات.
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

باتباع هذه الخطوات ، ستتمكن بسهولة من إنشاء وتوقيع سطر توقيع جديد في مستند Word الخاص بك باستخدام Aspose.Words for .NET.

