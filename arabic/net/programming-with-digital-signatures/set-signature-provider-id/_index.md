---
title: قم بتعيين معرف موفر التوقيع
linktitle: قم بتعيين معرف موفر التوقيع
second_title: Aspose.Words لمراجع .NET API
description: تعرف على كيفية تعيين معرف موفر التوقيع في مستند Word باستخدام Aspose.Words for .NET.
type: docs
weight: 10
url: /ar/net/programming-with-digital-signatures/set-signature-provider-id/
---

في هذا البرنامج التعليمي ، سنوجهك عبر خطوات استخدام ميزة Set Signature Provider ID مع Aspose.Words for .NET. تتيح لك هذه الميزة تحديد معرف موفر التوقيع لسطر التوقيع في مستند Word. اتبع الخطوات التالية:

## الخطوة 1: تحميل المستند والوصول إلى سطر التوقيع

ابدأ بتحميل المستند الذي يحتوي على سطر التوقيع:

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document doc = new Document(dataDir + "Signature line.docx");

SignatureLine signatureLine = ((Shape)doc.FirstSection.Body.GetChild(NodeType.Shape, 0, true)).SignatureLine;
```

## الخطوة 2: تعيين خيارات التوقيع

قم بإنشاء مثيل لفئة SignOptions وقم بتعيين خيارات التوقيع ، بما في ذلك معرف الموفر:

```csharp
SignOptions signOptions = new SignOptions
{
ProviderId = signatureLine.ProviderId,
 SignatureLineId = signatureLine.Id
};
```

## الخطوة الثالثة: توقيع الوثيقة

لتوقيع الوثيقة ، يجب عليك استخدام فئة DigitalSignatureUtil وتحديد شهادة التوقيع:

```csharp
CertificateHolder certHolder = CertificateHolder.Create(dataDir + "morzal.pfx", "aw");

DigitalSignatureUtil.Sign(dataDir + "Digitally signed.docx",
	dataDir + "SignDocuments.SetSignatureProviderId.docx", certHolder, signOptions);
```

تأكد من تحديد المسارات الصحيحة للمستند والشهادة والمستند الموقع.

### مثال على شفرة المصدر لـ Set Signature Provider ID باستخدام Aspose.Words for .NET

إليك كود المصدر الكامل لتعيين معرف موفر التوقيع باستخدام Aspose.Words for .NET:

```csharp

	// المسار إلى دليل المستندات.
	string dataDir = "YOUR DOCUMENT DIRECTORY";
	Document doc = new Document(dataDir + "Signature line.docx");

	SignatureLine signatureLine =
		((Shape) doc.FirstSection.Body.GetChild(NodeType.Shape, 0, true)).SignatureLine;

	SignOptions signOptions = new SignOptions
	{
		ProviderId = signatureLine.ProviderId, SignatureLineId = signatureLine.Id
	};

	CertificateHolder certHolder = CertificateHolder.Create(dataDir + "morzal.pfx", "aw");

	DigitalSignatureUtil.Sign(dataDir + "Digitally signed.docx",
		dataDir + "SignDocuments.SetSignatureProviderId.docx", certHolder, signOptions);

```

قم بإنهاء "معرف موفر التوقيع" في مستند Word الخاص بك باستخدام Aspose.Words for .NET.

