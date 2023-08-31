---
title: توقيع سطر التوقيع الموجود في مستند Word
linktitle: توقيع سطر التوقيع الموجود في مستند Word
second_title: واجهة برمجة تطبيقات معالجة المستندات Aspose.Words
description: تعرف على كيفية توقيع سطر توقيع موجود في مستند Word باستخدام Aspose.Words for .NET.
type: docs
weight: 10
url: /ar/net/programming-with-digital-signatures/signing-existing-signature-line/
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

## خاتمة

في هذا البرنامج التعليمي ، تعلمنا كيفية التوقيع على سطر توقيع موجود في مستند Word باستخدام Aspose.Words for .NET. باتباع الخطوات المقدمة ، يمكنك بسهولة تحميل المستند والوصول إلى سطر التوقيع الحالي وتعيين خيارات التوقيع وتوقيع المستند. توفر القدرة على توقيع سطر توقيع موجود طريقة ملائمة لإضافة توقيعات رقمية إلى مناطق محددة مسبقًا في مستندات Word الخاصة بك ، مما يضمن تكامل المستند والمصادقة عليه. يوفر Aspose.Words for .NET واجهة برمجة تطبيقات قوية لمعالجة الكلمات باستخدام التوقيعات الرقمية ، مما يسمح لك بتخصيص عملية التوقيع وتعزيز أمان مستندات Word الخاصة بك.

### التعليمات

#### س: ما هو سطر التوقيع الموجود في مستند Word؟

ج: سطر التوقيع الموجود في مستند Word هو منطقة محددة مسبقًا حيث يمكن وضع التوقيع. يتم تمثيله عادةً بشكل أو كائن في المستند ويعمل كمساحة مخصصة للموقِّع لإضافة توقيعه الرقمي.

#### س: كيف يمكنني التوقيع على سطر توقيع موجود في مستند Word باستخدام Aspose.Words for .NET؟

ج: لتوقيع سطر توقيع موجود في مستند Word باستخدام Aspose.Words for .NET ، يمكنك اتباع الخطوات التالية:
1.  قم بتحميل المستند باستخدام ملف`Document` class وحدد المسار إلى ملف المستند.
2.  الوصول إلى سطر التوقيع الحالي باستخدام الطريقة أو الخاصية المناسبة. على سبيل المثال ، يمكنك استخدام ملفات`GetChild` طريقة لاسترداد شكل خط التوقيع.
3.  قم بإنشاء مثيل لـ`SignOptions`فئة وضبط`SignatureLineId` الخاصية إلى معرف سطر التوقيع الحالي.
4.  تعيين`SignatureLineImage` ممتلكات`SignOptions` فئة للصورة التي تمثل التوقيع الرقمي.
5.  قم بتحميل شهادة التوقيع باستخدام ملف`CertificateHolder` فئة وتقديم الشهادة وكلمة المرور اللازمة.
6.  استخدم ال`DigitalSignatureUtil.Sign` طريقة لتوقيع الوثيقة ، مع توفير المعلمات الضرورية بما في ذلك`SignOptions` هدف.

#### س: كيف يمكنني الوصول إلى سطر التوقيع الموجود في مستند Word باستخدام Aspose.Words for .NET؟

 ج: للوصول إلى سطر التوقيع الموجود في مستند Word باستخدام Aspose.Words for .NET ، يمكنك استخدام الطريقة أو الخاصية المناسبة لاسترداد شكل سطر التوقيع من بنية المستند. على سبيل المثال ، يمكنك استخدام ملف`GetChild` طريقة مع المعلمات المناسبة للحصول على شكل خط التوقيع المطلوب.

#### س: هل يمكنني تخصيص مظهر التوقيع الرقمي في سطر توقيع موجود؟

ج: نعم ، يمكنك تخصيص مظهر التوقيع الرقمي في سطر توقيع موجود من خلال توفير ملف صورة يمثل التوقيع. يمكن أن تكون الصورة شعارًا أو توقيعًا بخط اليد أو أي تمثيل رسومي آخر للتوقيع. يمكنك ضبط ملف`SignatureLineImage` ممتلكات`SignOptions` فئة إلى بايت ملف الصورة.

#### س: هل يمكنني التوقيع على عدة أسطر توقيع موجودة في مستند Word؟
 ج: نعم ، يمكنك توقيع عدة أسطر توقيع موجودة في مستند Word. تحتاج إلى اتباع الخطوات لكل سطر توقيع على حدة ، وتحديد المناسب`SignatureLineId` و`SignatureLineImage` القيم في`SignOptions` كائن لكل سطر توقيع.

#### س: ما هو التنسيق الذي يجب أن يكون عليه ملف الصورة للتوقيع الرقمي في سطر توقيع موجود؟

 ج: يمكن أن يكون ملف الصورة للتوقيع الرقمي في سطر توقيع موجود بتنسيقات مختلفة ، مثل PNG أو JPEG أو BMP أو GIF. يمكنك تحديد مسار الملف أو قراءة وحدات البايت الخاصة بملف الصورة وتعيينها إلى ملف`SignatureLineImage` ممتلكات`SignOptions` فصل.
