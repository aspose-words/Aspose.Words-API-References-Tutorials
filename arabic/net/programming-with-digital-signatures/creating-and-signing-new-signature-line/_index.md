---
title: إنشاء وتوقيع خط توقيع جديد
linktitle: إنشاء وتوقيع خط توقيع جديد
second_title: واجهة برمجة تطبيقات معالجة المستندات Aspose.Words
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

## خاتمة

في هذا البرنامج التعليمي ، تعلمنا كيفية إنشاء سطر توقيع جديد وتوقيعه في مستند Word باستخدام Aspose.Words for .NET. باتباع الخطوات المقدمة ، يمكنك بسهولة إدراج سطر توقيع في المستند الخاص بك ، وتخصيص خياراته ، وتوقيع المستند باستخدام شهادة رقمية. تعمل إضافة خطوط التوقيع والتوقيعات الرقمية إلى مستنداتك على تحسين مصداقيتها وسلامتها ، مما يجعلها أكثر أمانًا وموثوقية. يوفر Aspose.Words for .NET واجهة برمجة تطبيقات قوية لمعالجة الكلمات مع التوقيعات والشهادات الرقمية في مستندات Word ، مما يسمح لك بأتمتة عملية التوقيع وضمان صحة مستنداتك.

### التعليمات

#### س: ما هو سطر التوقيع في مستند Word؟

ج: سطر التوقيع في مستند Word هو عنصر نائب يشير إلى المكان الذي يجب وضع التوقيع فيه. يتضمن عادةً الاسم والعنوان والتاريخ ، ويوفر مساحة للتوقيع الرقمي أو المكتوب بخط اليد.

#### س: كيف يمكنني إنشاء سطر توقيع في مستند Word باستخدام Aspose.Words for .NET؟

ج: لإنشاء سطر توقيع في مستند Word باستخدام Aspose.Words for .NET ، يمكنك اتباع الخطوات التالية:
1.  قم بإنشاء مثيل لـ`Document` فئة وأ`DocumentBuilder` هدف.
2.  استخدم ال`InsertSignatureLine` طريقة`DocumentBuilder` لإدراج سطر توقيع جديد في المستند.
3. احفظ المستند المعدل.

#### س: هل يمكنني تخصيص خيارات سطر التوقيع ، مثل الاسم والعنوان والتاريخ؟

 ج: نعم ، يمكنك تخصيص خيارات سطر التوقيع. ال`SignatureLineOptions` توفر class خصائص لتعيين الخيارات المطلوبة ، مثل`Signer`, `SignerTitle`, `ShowDate`، إلخ. يمكنك تعديل هذه الخصائص قبل إدخال سطر التوقيع.

#### س: كيف يمكنني توقيع المستند بعد إنشاء سطر توقيع؟

 ج: لتوقيع المستند بعد إنشاء سطر توقيع ، تحتاج إلى تعيين خيارات التوقيع واستخدام ملف`DigitalSignatureUtil` فصل. فيما يلي الخطوات:
1.  تعيين`SignatureLineId` الممتلكات في`SignOptions` الاعتراض على معرف سطر التوقيع.
2.  تعيين`SignatureLineImage` الممتلكات في`SignOptions` تعترض على صورة التوقيع الذي تريد استخدامه.
3.  قم بتحميل شهادة التوقيع باستخدام ملف`CertificateHolder` فصل.
4.  استخدم ال`DigitalSignatureUtil.Sign` طريقة لتوقيع الوثيقة ، مع توفير المعلمات اللازمة.

#### س: هل يمكنني استخدام صورة توقيع رقمي لتوقيع المستند؟

 ج: نعم ، يمكنك استخدام صورة توقيع رقمي لتوقيع الوثيقة. للقيام بذلك ، تحتاج إلى توفير ملف الصورة بتنسيق`SignOptions` كائن باستخدام`SignatureLineImage`ملكية. يمكن أن تكون الصورة بأي تنسيق صورة مدعوم ، مثل JPEG أو PNG أو EMF.

#### س: ما هو الغرض من إنشاء سطر توقيع جديد وتوقيعه في مستند Word؟

ج: إنشاء وتوقيع سطر توقيع جديد في مستند Word باستخدام Aspose.Words for .NET يسمح لك بإضافة عنصر نائب للتوقيع ثم التوقيع على المستند باستخدام شهادة رقمية. تضمن هذه العملية صحة الوثيقة وسلامتها ، وتقدم دليلًا على الموافقة أو الاتفاق.

#### س: هل يمكنني إنشاء عدة أسطر توقيع وتوقيعها في مستند Word باستخدام Aspose.Words for .NET؟

ج: نعم ، يمكنك إنشاء عدة أسطر توقيع وتوقيعها في مستند Word باستخدام Aspose.Words for .NET. يمكن أن يكون لكل سطر توقيع معرف وخيارات فريدة خاصة به. يمكنك تكرار الخطوات لإنشاء وتوقيع أسطر توقيع إضافية في المستند.

#### س: هل يمكنني تعديل سطر التوقيع أو إضافة معلومات إضافية بعد التوقيع عليه؟

ج: بمجرد توقيع سطر التوقيع ، يصبح جزءًا من محتوى المستند ولا يمكن تعديله بشكل منفصل. ومع ذلك ، يمكنك إضافة معلومات أو محتوى إضافي بعد سطر التوقيع الموقع.

#### س: هل يمكنني التحقق من التوقيع الرقمي لمستند يحتوي على سطر توقيع؟

 ج: نعم ، يوفر Aspose.Words for .NET وظائف للتحقق من التوقيع الرقمي للمستند الذي يحتوي على سطر توقيع. يمكنك استخدام ال`DigitalSignatureUtil.Verify` طريقة للتحقق من صحة وصحة التوقيع الرقمي.

#### س: ما هو تنسيق الملف الذي يدعمه Aspose.Words for .NET لإنشاء أسطر التوقيع وتوقيعها؟

ج: يدعم Aspose.Words for .NET إنشاء أسطر التوقيع وتوقيعها بتنسيق ملف DOCX. يمكنك إنشاء وتوقيع أسطر التوقيع في ملفات DOCX باستخدام الأساليب والفئات المتوفرة.