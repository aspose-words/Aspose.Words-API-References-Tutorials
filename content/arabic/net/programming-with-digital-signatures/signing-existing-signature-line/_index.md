---
title: توقيع سطر التوقيع الموجود في مستند Word
linktitle: توقيع سطر التوقيع الموجود في مستند Word
second_title: Aspose.Words واجهة برمجة تطبيقات معالجة المستندات
description: تعرف على كيفية توقيع سطر توقيع موجود في مستند Word باستخدام Aspose.Words for .NET.
type: docs
weight: 10
url: /ar/net/programming-with-digital-signatures/signing-existing-signature-line/
---
في هذا البرنامج التعليمي، سنرشدك خلال خطوات استخدام ميزة التوقيع لسطر التوقيع الموجود مع Aspose.Words for .NET. تتيح لك هذه الميزة التوقيع رقميًا على سطر التوقيع الموجود بالفعل في مستند Word. اتبع الخطوات التالية:

## الخطوة 1: تحميل المستند والوصول إلى سطر التوقيع

ابدأ بتحميل المستند الذي يحتوي على سطر التوقيع الحالي:

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document doc = new Document(dataDir + "Signature line.docx");

SignatureLine signatureLine = ((Shape)doc.FirstSection.Body.GetChild(NodeType.Shape, 0, true)).SignatureLine;
```

## الخطوة 2: تحديد خيارات التوقيع

قم بإنشاء مثيل لفئة SignOptions وقم بتعيين خيارات التوقيع، بما في ذلك معرف سطر التوقيع وصورة سطر التوقيع:

```csharp
SignOptions signOptions = new SignOptions
{
SignatureLineId = signatureLine.Id,
SignatureLineImage = File.ReadAllBytes(ImagesDir + "Enhanced Windows MetaFile.emf")
};
```

تأكد من تحديد المسار الصحيح لصورة سطر التوقيع.

## الخطوة 3: تحميل الشهادة

ابدأ بتحميل شهادة التوقيع باستخدام فئة CertifiedHolder:

```csharp
CertificateHolder certHolder = CertificateHolder.Create(dataDir + "morzal.pfx", "aw");
```

تأكد من تحديد المسار الصحيح لشهادتك وكلمة المرور المرتبطة بها.

## الخطوة 4: التوقيع على سطر التوقيع الحالي

استخدم فئة DigitalSignatureUtil لتوقيع سطر التوقيع الحالي:

```csharp
DigitalSignatureUtil.Sign(dataDir + "Digitally signed.docx",
	dataDir + "SignDocuments.SigningExistingSignatureLine.docx", certHolder, signOptions);
```

تأكد من تحديد المسارات الصحيحة للمستند المصدر والمستند الموقع والشهادة.

### مثال على التعليمات البرمجية المصدر لتوقيع سطر التوقيع الحالي باستخدام Aspose.Words لـ .NET

فيما يلي الكود المصدري الكامل لتوقيع سطر التوقيع الحالي باستخدام Aspose.Words for .NET:


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

باتباع هذه الخطوات، يمكنك بسهولة التوقيع على سطر توقيع موجود في مستند Word باستخدام Aspose.Words for .NET.

## خاتمة

في هذا البرنامج التعليمي، تعلمنا كيفية التوقيع على سطر توقيع موجود في مستند Word باستخدام Aspose.Words for .NET. باتباع الخطوات المتوفرة، يمكنك بسهولة تحميل المستند والوصول إلى سطر التوقيع الحالي وتعيين خيارات التوقيع وتوقيع المستند. توفر القدرة على التوقيع على سطر توقيع موجود طريقة مناسبة لإضافة التوقيعات الرقمية إلى مناطق محددة مسبقًا في مستندات Word، مما يضمن سلامة المستند ومصادقته. يوفر Aspose.Words for .NET واجهة برمجة تطبيقات قوية لمعالجة الكلمات باستخدام التوقيعات الرقمية، مما يسمح لك بتخصيص عملية التوقيع وتحسين أمان مستندات Word الخاصة بك.

### الأسئلة الشائعة

#### س: ما هو سطر التوقيع الموجود في مستند Word؟

ج: إن سطر التوقيع الموجود في مستند Word هو منطقة محددة مسبقًا حيث يمكن وضع التوقيع. يتم تمثيله عادةً بشكل أو كائن في المستند ويعمل كمساحة مخصصة للموقع لإضافة توقيعه الرقمي.

#### س: كيف يمكنني التوقيع على سطر توقيع موجود في مستند Word باستخدام Aspose.Words for .NET؟

ج: لتوقيع سطر توقيع موجود في مستند Word باستخدام Aspose.Words لـ .NET، يمكنك اتباع الخطوات التالية:
1.  قم بتحميل المستند باستخدام`Document` class وحدد المسار إلى ملف المستند.
2.  قم بالوصول إلى سطر التوقيع الحالي باستخدام الطريقة أو الخاصية المناسبة. على سبيل المثال، يمكنك استخدام`GetChild` طريقة لاسترداد شكل خط التوقيع.
3.  إنشاء مثيل لـ`SignOptions`فئة وتعيين`SignatureLineId` الخاصية لمعرف سطر التوقيع الموجود.
4.  تعيين`SignatureLineImage` ملكية`SignOptions` فئة إلى الصورة التي تمثل التوقيع الرقمي.
5.  قم بتحميل شهادة التوقيع باستخدام`CertificateHolder` فئة وتقديم الشهادة وكلمة المرور اللازمة.
6.  استخدم ال`DigitalSignatureUtil.Sign` طريقة التوقيع على الوثيقة، وتوفير المعلمات اللازمة بما في ذلك`SignOptions` هدف.

#### س: كيف يمكنني الوصول إلى سطر التوقيع الموجود في مستند Word باستخدام Aspose.Words for .NET؟

 ج: للوصول إلى سطر التوقيع الموجود في مستند Word باستخدام Aspose.Words لـ .NET، يمكنك استخدام الطريقة أو الخاصية المناسبة لاسترداد شكل سطر التوقيع من بنية المستند. على سبيل المثال، يمكنك استخدام`GetChild` الطريقة مع المعلمات المناسبة للحصول على شكل خط التوقيع المطلوب.

#### س: هل يمكنني تخصيص مظهر التوقيع الرقمي في سطر توقيع موجود؟

ج: نعم، يمكنك تخصيص مظهر التوقيع الرقمي في سطر التوقيع الموجود من خلال توفير ملف صورة يمثل التوقيع. يمكن أن تكون الصورة شعارًا أو توقيعًا مكتوبًا بخط اليد أو أي تمثيل رسومي آخر للتوقيع. يمكنك ضبط`SignatureLineImage` ملكية`SignOptions` فئة إلى بايت من ملف الصورة.

#### س: هل يمكنني التوقيع على عدة أسطر توقيع موجودة في مستند Word؟
 ج: نعم، يمكنك توقيع عدة أسطر توقيع موجودة في مستند Word. يتعين عليك اتباع الخطوات الخاصة بكل سطر توقيع على حدة، وتحديد السطر المناسب`SignatureLineId` و`SignatureLineImage` القيم في`SignOptions` كائن لكل سطر التوقيع.

#### س: ما هو التنسيق الذي يجب أن يكون عليه ملف الصورة للتوقيع الرقمي في سطر التوقيع الموجود؟

 ج: يمكن أن يكون ملف الصورة للتوقيع الرقمي في سطر التوقيع الحالي بتنسيقات مختلفة، مثل PNG، أو JPEG، أو BMP، أو GIF. يمكنك تحديد مسار الملف أو قراءة بايتات ملف الصورة وتعيينها إلى ملف`SignatureLineImage` ملكية`SignOptions` فصل.
