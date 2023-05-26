---
title: إنشاء سطر توقيع جديد وتعيين معرف الموفر
linktitle: إنشاء سطر توقيع جديد وتعيين معرف الموفر
second_title: Aspose.Words لمراجع .NET API
description: تعرف على كيفية إنشاء سطر توقيع جديد وتعيين معرف الموفر في مستند Word باستخدام Aspose.Words for .NET.
type: docs
weight: 10
url: /ru/net/programming-with-digital-signatures/create-new-signature-line-and-set-provider-id/
---

في هذا البرنامج التعليمي ، سنرشدك خلال الخطوات لاستخدام ميزة إنشاء خط توقيع جديد وتعيين معرّف الموفر مع Aspose.Words for .NET. تتيح لك هذه الميزة إدراج سطر توقيع في مستند Word ، وتعيين الخيارات المخصصة وتوقيع المستند. اتبع الخطوات التالية:

## الخطوة 1: إنشاء المستند والمولد

ابدأ بإنشاء مثيل لفئة Document وكائن DocumentBuilder:

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
```

## الخطوة 2: تعيين خيارات خط التوقيع

قم بإنشاء مثيل لفئة SignatureLineOptions وقم بتعيين الخيارات المطلوبة:

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

## الخطوة 3: إدخال سطر التوقيع

استخدم طريقة InsertSignatureLine () لكائن DocumentBuilder لإدراج سطر التوقيع في المستند:

```csharp
SignatureLine signatureLine = builder.InsertSignatureLine(signatureLineOptions).SignatureLine;
```

## الخطوة 4: قم بتعيين معرف المزود

قم بتعيين معرف الموفر لسطر التوقيع باستخدام خاصية ProviderId:

```csharp
signatureLine.ProviderId = Guid.Parse("CF5A7BB4-8F3C-4756-9DF6-BEF7F13259A2");
```

تأكد من تحديد معرف الموفر الصحيح لحالة الاستخدام الخاصة بك.

## الخطوة 5: احفظ المستند

احفظ المستند المعدل:

```csharp
doc.Save(dataDir + "SignDocuments.SignatureLineProviderId.docx");
```

تأكد من تحديد المسار الصحيح واسم الملف لحفظ المستند.

## الخطوة السادسة: توقيع الوثيقة

لتوقيع الوثيقة ، تحتاج إلى تعيين خيارات التوقيع واستخدام فئة DigitalSignatureUtil:

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

تأكد من تحديد المسارات الصحيحة للمستند والشهادة والمستند الموقع.

### مثال على شفرة المصدر لـ Create New Signature Line And Set Provider ID باستخدام Aspose.Words for .NET

إليك شفرة المصدر الكاملة لإنشاء سطر توقيع جديد وتعيين معرف الموفر باستخدام Aspose.Words for .NET:

```csharp

	// المسار إلى دليل المستندات.
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

باتباع هذه الخطوات ، يمكنك بسهولة إنشاء سطر توقيع جديد وتعيين معرف الموفر في مستند Word الخاص بك باستخدام Aspose.Words for .NET.

