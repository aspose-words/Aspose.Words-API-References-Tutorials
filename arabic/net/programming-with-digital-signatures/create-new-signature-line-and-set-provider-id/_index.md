---
title: إنشاء سطر توقيع جديد وتعيين معرف الموفر
linktitle: إنشاء سطر توقيع جديد وتعيين معرف الموفر
second_title: واجهة برمجة تطبيقات معالجة المستندات Aspose.Words
description: تعرف على كيفية إنشاء سطر توقيع جديد وتعيين معرف الموفر في مستند Word باستخدام Aspose.Words for .NET.
type: docs
weight: 10
url: /ar/net/programming-with-digital-signatures/create-new-signature-line-and-set-provider-id/
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

## خاتمة

في هذا البرنامج التعليمي ، استكشفنا ميزة إنشاء سطر توقيع جديد وتعيين معرف الموفر في مستند Word باستخدام Aspose.Words for .NET. باتباع الخطوات المقدمة ، يمكنك بسهولة إدراج سطر توقيع بخيارات مخصصة وربطه بموفر معين باستخدام معرف الموفر. تعمل إضافة أسطر التوقيع وتخصيص معلومات الموفر على تحسين مصداقية مستنداتك وموثوقيتها. يوفر Aspose.Words for .NET واجهة برمجة تطبيقات قوية لمعالجة الكلمات مع خطوط توقيع وشهادات رقمية في مستندات Word ، مما يتيح لك أتمتة عملية التوقيع وضمان صحة مستنداتك.

### التعليمات

#### س: ما هو معرف الموفر في سطر التوقيع؟

ج: معرف الموفر في سطر التوقيع هو معرف فريد يمثل موفر التوقيع الرقمي. يساعد في تحديد المصدر أو المنظمة المسؤولة عن التوقيع.

#### س: كيف يمكنني إنشاء سطر توقيع جديد في مستند Word باستخدام Aspose.Words for .NET؟

ج: لإنشاء سطر توقيع جديد في مستند Word باستخدام Aspose.Words for .NET ، يمكنك اتباع الخطوات التالية:
1.  قم بإنشاء مثيل لـ`Document` فئة وأ`DocumentBuilder` هدف.
2.  قم بإنشاء مثيل لـ`SignatureLineOptions` فئة وتعيين خيارات خط التوقيع المطلوبة.
3.  استخدم ال`InsertSignatureLine` طريقة`DocumentBuilder` كائن لإدراج سطر التوقيع في المستند.

#### س: هل يمكنني تخصيص خيارات سطر التوقيع ، مثل اسم الموقع والعنوان والتعليمات؟

 ج: نعم ، يمكنك تخصيص خيارات سطر التوقيع. ال`SignatureLineOptions` توفر class خصائص لتعيين الخيارات المطلوبة ، مثل`Signer`, `SignerTitle`, `Instructions`, `AllowComments`، إلخ. يمكنك تعديل هذه الخصائص قبل إدخال سطر التوقيع.

#### س: ما هو الغرض من تعيين معرف الموفر لسطر التوقيع؟

ج: يساعد تعيين معرف الموفر لسطر التوقيع في تحديد المصدر أو المؤسسة المسؤولة عن التوقيع الرقمي. يسمح لك بربط التوقيع بموفر أو كيان معين ، مما يوفر معلومات إضافية حول أصل التوقيع وموثوقيته.

#### س: كيف يمكنني تعيين معرف الموفر لسطر التوقيع باستخدام Aspose.Words for .NET؟

ج: لتعيين معرف الموفر لسطر التوقيع باستخدام Aspose.Words for .NET ، يمكنك اتباع الخطوات التالية:
1.  بعد إدخال سطر التوقيع ، قم بالوصول إلى`ProviderId` ممتلكات`SignatureLine` هدف.
2.  تعيين`ProviderId` إلى قيمة معرف الموفر المطلوب باستخدام`Guid` نوع البيانات.

#### س: هل يمكنني توقيع المستند بعد إنشاء سطر توقيع جديد وتعيين معرف الموفر؟

 ج: نعم ، بعد إنشاء سطر توقيع جديد وتعيين معرف الموفر ، يمكنك توقيع المستند. لتوقيع المستند ، تحتاج إلى تعيين خيارات التوقيع ، بما في ذلك معرف سطر التوقيع ومعرف الموفر والتعليقات ووقت التوقيع. ثم استخدم ملف`DigitalSignatureUtil.Sign` طريقة لتوقيع الوثيقة باستخدام شهادة رقمية.

#### س: هل يمكنني تحديد معرف موفر معين لكل سطر توقيع في مستند Word؟

ج: نعم ، يمكنك تحديد معرف موفر معين لكل سطر توقيع في مستند Word. بعد إدراج كل سطر توقيع ، يمكنك تعيين معرف الموفر لسطر التوقيع المحدد هذا عن طريق الوصول إلى ملف`ProviderId` ممتلكات كل منهما`SignatureLine` هدف.

#### س: كيف يمكنني حفظ المستند المعدل بعد إنشاء سطر توقيع جديد وتعيين معرف الموفر؟

 ج: لحفظ المستند المعدل بعد إنشاء سطر توقيع جديد وتعيين معرف الموفر ، يمكنك استخدام`Save` طريقة`Document` هدف. حدد المسار الصحيح واسم الملف لحفظ المستند.

#### س: ما هو تنسيق الملف الذي يدعمه Aspose.Words for .NET لإنشاء أسطر التوقيع وتوقيعها؟

ج: يدعم Aspose.Words for .NET إنشاء أسطر التوقيع وتوقيعها بتنسيق ملف DOCX. يمكنك إنشاء وتوقيع أسطر التوقيع في ملفات DOCX باستخدام الأساليب والفئات المتوفرة.

#### س: هل يمكنني تعديل معرف الموفر أو الخيارات الأخرى لسطر التوقيع بعد التوقيع عليه؟

ج: بمجرد توقيع سطر التوقيع ، يصبح جزءًا من محتوى المستند ولا يمكن تعديله بشكل منفصل. قد تتطلب أي تعديلات على سطر التوقيع ، مثل تغيير معرف الموفر أو خيارات أخرى ، إزالة التوقيع الحالي وإنشاء سطر توقيع جديد.