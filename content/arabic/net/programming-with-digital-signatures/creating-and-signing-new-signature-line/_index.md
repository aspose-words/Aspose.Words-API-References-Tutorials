---
title: إنشاء وتوقيع خط التوقيع الجديد
linktitle: إنشاء وتوقيع خط التوقيع الجديد
second_title: Aspose.Words واجهة برمجة تطبيقات معالجة المستندات
description: تعرف على كيفية إنشاء سطر توقيع جديد وتوقيعه في مستند Word باستخدام Aspose.Words for .NET.
type: docs
weight: 10
url: /ar/net/programming-with-digital-signatures/creating-and-signing-new-signature-line/
---
في هذا البرنامج التعليمي، سنرشدك خلال خطوات استخدام ميزة إنشاء سطر توقيع جديد وتوقيعه باستخدام Aspose.Words for .NET. تتيح لك هذه الميزة إدراج سطر توقيع في مستند Word وتعيين خيارات مخصصة وتوقيع المستند. اتبع الخطوات التالية:

## الخطوة 1: إنشاء المستند والمولد

ابدأ بإنشاء مثيل لفئة Document وكائن DocumentBuilder:

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
```

## الخطوة 2: إدخال سطر التوقيع

استخدم طريقة InsertSignatureLine() للكائن DocumentBuilder لإدراج سطر توقيع جديد في المستند:

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

لتوقيع المستند، تحتاج إلى ضبط خيارات التوقيع واستخدام فئة DigitalSignatureUtil:

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

تأكد من تحديد المسارات الصحيحة للمستند، وصورة سطر التوقيع، والمستند الموقع.

### مثال على التعليمات البرمجية المصدر لإنشاء سطر توقيع جديد وتوقيعه باستخدام Aspose.Words لـ .NET

إليك الكود المصدري الكامل لإنشاء سطر توقيع جديد وتوقيعه باستخدام Aspose.Words for .NET:

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

باتباع هذه الخطوات، ستتمكن بسهولة من إنشاء سطر توقيع جديد وتوقيعه في مستند Word الخاص بك باستخدام Aspose.Words for .NET.

## خاتمة

في هذا البرنامج التعليمي، تعلمنا كيفية إنشاء سطر توقيع جديد وتوقيعه في مستند Word باستخدام Aspose.Words for .NET. باتباع الخطوات المتوفرة، يمكنك بسهولة إدراج سطر توقيع في مستندك وتخصيص خياراته وتوقيع المستند باستخدام شهادة رقمية. تعمل إضافة خطوط التوقيع والتوقيعات الرقمية إلى مستنداتك على تعزيز صحتها وسلامتها، مما يجعلها أكثر أمانًا وجديرة بالثقة. يوفر Aspose.Words for .NET واجهة برمجة تطبيقات قوية لمعالجة الكلمات من خلال التوقيعات والشهادات الرقمية في مستندات Word، مما يسمح لك بأتمتة عملية التوقيع والتأكد من صحة مستنداتك.

### الأسئلة الشائعة

#### س: ما هو سطر التوقيع في مستند Word؟

ج: سطر التوقيع في مستند Word هو عنصر نائب يشير إلى المكان الذي يجب وضع التوقيع فيه. ويتضمن عادةً الاسم والعنوان والتاريخ، ويوفر مساحة للتوقيع المكتوب بخط اليد أو التوقيع الرقمي.

#### س: كيف يمكنني إنشاء سطر توقيع في مستند Word باستخدام Aspose.Words لـ .NET؟

ج: لإنشاء سطر توقيع في مستند Word باستخدام Aspose.Words لـ .NET، يمكنك اتباع الخطوات التالية:
1.  إنشاء مثيل لـ`Document` فئة و أ`DocumentBuilder` هدف.
2.  استخدم ال`InsertSignatureLine` طريقة`DocumentBuilder` كائن لإدراج سطر توقيع جديد في المستند.
3. احفظ المستند المعدل.

#### س: هل يمكنني تخصيص خيارات سطر التوقيع، مثل الاسم والعنوان والتاريخ؟

 ج: نعم، يمكنك تخصيص خيارات سطر التوقيع. ال`SignatureLineOptions` توفر الفئة خصائص لتعيين الخيارات المطلوبة، مثل`Signer`, `SignerTitle`, `ShowDate`وما إلى ذلك. يمكنك تعديل هذه الخصائص قبل إدراج سطر التوقيع.

#### س: كيف يمكنني التوقيع على المستند بعد إنشاء سطر التوقيع؟

 ج: لتوقيع المستند بعد إنشاء سطر التوقيع، تحتاج إلى ضبط خيارات التوقيع واستخدام`DigitalSignatureUtil` فصل. فيما يلي الخطوات:
1.  تعيين`SignatureLineId` الممتلكات في`SignOptions` الاعتراض على معرف سطر التوقيع.
2.  تعيين`SignatureLineImage` الممتلكات في`SignOptions` اعترض على صورة التوقيع الذي تريد استخدامه.
3.  قم بتحميل شهادة التوقيع باستخدام`CertificateHolder` فصل.
4.  استخدم ال`DigitalSignatureUtil.Sign` طريقة التوقيع على الوثيقة، وتوفير المعلمات اللازمة.

#### س: هل يمكنني استخدام صورة التوقيع الرقمي لتوقيع المستند؟

 ج: نعم، يمكنك استخدام صورة التوقيع الرقمي لتوقيع المستند. للقيام بذلك، تحتاج إلى توفير ملف الصورة في ملف`SignOptions` كائن باستخدام`SignatureLineImage`ملكية. يمكن أن تكون الصورة بأي تنسيق صورة مدعوم، مثل JPEG أو PNG أو EMF.

#### س: ما هو الغرض من إنشاء سطر توقيع جديد وتوقيعه في مستند Word؟

ج: يتيح لك إنشاء سطر توقيع جديد وتوقيعه في مستند Word باستخدام Aspose.Words for .NET إضافة عنصر نائب للتوقيع ثم توقيع المستند باستخدام شهادة رقمية. تضمن هذه العملية صحة الوثيقة وسلامتها، وتقديم دليل على الموافقة أو الموافقة.

#### س: هل يمكنني إنشاء أسطر توقيع متعددة وتوقيعها في مستند Word باستخدام Aspose.Words for .NET؟

ج: نعم، يمكنك إنشاء أسطر توقيع متعددة وتوقيعها في مستند Word باستخدام Aspose.Words for .NET. يمكن أن يكون لكل سطر توقيع معرّف وخيارات فريدة خاصة به. يمكنك تكرار الخطوات لإنشاء أسطر توقيع إضافية وتوقيعها في المستند.

#### س: هل يمكنني تعديل سطر التوقيع أو إضافة معلومات إضافية بعد التوقيع عليه؟

ج: بمجرد توقيع سطر التوقيع، يصبح جزءًا من محتوى المستند ولا يمكن تعديله بشكل منفصل. ومع ذلك، يمكنك إضافة معلومات أو محتوى إضافي بعد سطر التوقيع الموقع.

#### س: هل يمكنني التحقق من التوقيع الرقمي لمستند يحتوي على سطر توقيع؟

 ج: نعم، يوفر Aspose.Words for .NET وظيفة للتحقق من التوقيع الرقمي للمستند الذي يحتوي على سطر التوقيع. يمكنك استخدام ال`DigitalSignatureUtil.Verify` طريقة للتحقق من صحة وصحة التوقيع الرقمي.

#### س: ما هو تنسيق الملف الذي يدعمه Aspose.Words for .NET لإنشاء خطوط التوقيع وتوقيعها؟

ج: يدعم Aspose.Words for .NET إنشاء أسطر التوقيع وتوقيعها بتنسيق ملف DOCX. يمكنك إنشاء خطوط التوقيع وتوقيعها في ملفات DOCX باستخدام الطرق والفئات المتوفرة.