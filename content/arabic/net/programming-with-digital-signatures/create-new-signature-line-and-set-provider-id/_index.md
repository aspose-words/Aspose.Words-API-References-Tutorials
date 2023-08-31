---
title: إنشاء سطر توقيع جديد وتعيين معرف الموفر
linktitle: إنشاء سطر توقيع جديد وتعيين معرف الموفر
second_title: Aspose.Words واجهة برمجة تطبيقات معالجة المستندات
description: تعرف على كيفية إنشاء سطر توقيع جديد وتعيين معرف الموفر في مستند Word باستخدام Aspose.Words for .NET.
type: docs
weight: 10
url: /ar/net/programming-with-digital-signatures/create-new-signature-line-and-set-provider-id/
---
في هذا البرنامج التعليمي، سنرشدك خلال خطوات استخدام ميزة إنشاء سطر توقيع جديد وتعيين معرف الموفر مع Aspose.Words for .NET. تتيح لك هذه الميزة إدراج سطر توقيع في مستند Word وتعيين خيارات مخصصة وتوقيع المستند. اتبع الخطوات التالية:

## الخطوة 1: إنشاء المستند والمولد

ابدأ بإنشاء مثيل لفئة Document وكائن DocumentBuilder:

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
```

## الخطوة 2: ضبط خيارات خط التوقيع

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

استخدم طريقة InsertSignatureLine() للكائن DocumentBuilder لإدراج سطر التوقيع في المستند:

```csharp
SignatureLine signatureLine = builder.InsertSignatureLine(signatureLineOptions).SignatureLine;
```

## الخطوة 4: تعيين معرف الموفر

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

## الخطوة 6: توقيع الوثيقة

لتوقيع المستند، تحتاج إلى ضبط خيارات التوقيع واستخدام فئة DigitalSignatureUtil:

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

### مثال على التعليمات البرمجية المصدر لإنشاء سطر توقيع جديد وتعيين معرف الموفر باستخدام Aspose.Words لـ .NET

فيما يلي الكود المصدري الكامل لإنشاء سطر توقيع جديد وتعيين معرف الموفر باستخدام Aspose.Words لـ .NET:

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

باتباع هذه الخطوات، يمكنك بسهولة إنشاء سطر توقيع جديد وتعيين معرف الموفر في مستند Word الخاص بك باستخدام Aspose.Words for .NET.

## خاتمة

في هذا البرنامج التعليمي، اكتشفنا ميزة إنشاء سطر توقيع جديد وتعيين معرف الموفر في مستند Word باستخدام Aspose.Words for .NET. باتباع الخطوات المتوفرة، يمكنك بسهولة إدراج سطر توقيع بخيارات مخصصة وربطه بموفر معين باستخدام معرف الموفر. تعمل إضافة أسطر التوقيع وتخصيص معلومات الموفر على تحسين صحة مستنداتك ومصداقيتها. يوفر Aspose.Words for .NET واجهة برمجة تطبيقات قوية لمعالجة الكلمات مع خطوط التوقيع والشهادات الرقمية في مستندات Word، مما يتيح لك أتمتة عملية التوقيع والتأكد من صحة مستنداتك.

### الأسئلة الشائعة

#### س: ما هو معرف المزود الموجود في سطر التوقيع؟

ج: معرف الموفر الموجود في سطر التوقيع هو معرف فريد يمثل موفر التوقيع الرقمي. فهو يساعد على تحديد المصدر أو المنظمة المسؤولة عن التوقيع.

#### س: كيف يمكنني إنشاء سطر توقيع جديد في مستند Word باستخدام Aspose.Words لـ .NET؟

ج: لإنشاء سطر توقيع جديد في مستند Word باستخدام Aspose.Words لـ .NET، يمكنك اتباع الخطوات التالية:
1.  إنشاء مثيل لـ`Document` فئة و أ`DocumentBuilder` هدف.
2.  إنشاء مثيل لـ`SignatureLineOptions` فئة وضبط خيارات سطر التوقيع المطلوب.
3.  استخدم ال`InsertSignatureLine` طريقة`DocumentBuilder` كائن لإدراج سطر التوقيع في المستند.

#### س: هل يمكنني تخصيص خيارات سطر التوقيع، مثل اسم الموقع والمسمى الوظيفي والتعليمات؟

 ج: نعم، يمكنك تخصيص خيارات سطر التوقيع. ال`SignatureLineOptions` توفر الفئة خصائص لتعيين الخيارات المطلوبة، مثل`Signer`, `SignerTitle`, `Instructions`, `AllowComments`وما إلى ذلك. يمكنك تعديل هذه الخصائص قبل إدراج سطر التوقيع.

#### س: ما هو الغرض من تحديد معرف المزود لخط التوقيع؟

ج: يساعد تعيين معرف الموفر لخط التوقيع في تحديد المصدر أو المؤسسة المسؤولة عن التوقيع الرقمي. فهو يسمح لك بربط التوقيع بمزود أو كيان محدد، مما يوفر معلومات إضافية حول أصل التوقيع ومصداقيته.

#### س: كيف يمكنني تعيين معرف الموفر لخط التوقيع باستخدام Aspose.Words for .NET؟

ج: لتعيين معرف الموفر لسطر التوقيع باستخدام Aspose.Words لـ .NET، يمكنك اتباع الخطوات التالية:
1.  بعد إدخال سطر التوقيع، قم بالوصول إلى`ProviderId` ملكية`SignatureLine` هدف.
2.  تعيين`ProviderId` الخاصية إلى قيمة معرف الموفر المطلوب باستخدام`Guid` نوع البيانات.

#### س: هل يمكنني التوقيع على المستند بعد إنشاء سطر توقيع جديد وتعيين معرف المزود؟

 ج: نعم، بعد إنشاء سطر توقيع جديد وتعيين معرف المزود، يمكنك توقيع المستند. لتوقيع المستند، يتعين عليك تعيين خيارات التوقيع، بما في ذلك معرف سطر التوقيع، ومعرف الموفر، والتعليقات، ووقت التوقيع. ثم استخدم`DigitalSignatureUtil.Sign` طريقة توقيع المستند باستخدام شهادة رقمية.

#### س: هل يمكنني تحديد معرف موفر محدد لكل سطر توقيع في مستند Word؟

ج: نعم، يمكنك تحديد معرف موفر محدد لكل سطر توقيع في مستند Word. بعد إدراج كل سطر توقيع، يمكنك تعيين معرف الموفر لخط التوقيع المحدد هذا عن طريق الوصول إلى`ProviderId` ممتلكات المعنيين`SignatureLine` هدف.

#### س: كيف يمكنني حفظ المستند المعدل بعد إنشاء سطر توقيع جديد وتعيين معرف المزود؟

 ج: لحفظ المستند المعدل بعد إنشاء سطر توقيع جديد وتعيين معرف الموفر، يمكنك استخدام`Save` طريقة`Document` هدف. حدد المسار الصحيح واسم الملف لحفظ المستند.

#### س: ما هو تنسيق الملف الذي يدعمه Aspose.Words for .NET لإنشاء خطوط التوقيع وتوقيعها؟

ج: يدعم Aspose.Words for .NET إنشاء أسطر التوقيع وتوقيعها بتنسيق ملف DOCX. يمكنك إنشاء خطوط التوقيع وتوقيعها في ملفات DOCX باستخدام الطرق والفئات المتوفرة.

#### س: هل يمكنني تعديل معرف الموفر أو الخيارات الأخرى لسطر التوقيع بعد التوقيع عليه؟

ج: بمجرد توقيع سطر التوقيع، يصبح جزءًا من محتوى المستند ولا يمكن تعديله بشكل منفصل. قد تتطلب أي تعديلات على سطر التوقيع، مثل تغيير معرف الموفر أو خيارات أخرى، إزالة التوقيع الحالي وإنشاء سطر توقيع جديد.