---
title: قم بتعيين معرف موفر التوقيع في مستند Word
linktitle: قم بتعيين معرف موفر التوقيع في مستند Word
second_title: Aspose.Words واجهة برمجة تطبيقات معالجة المستندات
description: تعرف على كيفية تعيين معرف موفر التوقيع في مستند Word باستخدام Aspose.Words for .NET.
type: docs
weight: 10
url: /ar/net/programming-with-digital-signatures/set-signature-provider-id/
---
في هذا البرنامج التعليمي، سنرشدك خلال خطوات استخدام ميزة Set Signature Provider ID مع Aspose.Words for .NET. تتيح لك هذه الميزة تحديد معرف موفر التوقيع لسطر التوقيع في مستند Word. اتبع الخطوات التالية:

## الخطوة 1: تحميل المستند والوصول إلى سطر التوقيع

ابدأ بتحميل المستند الذي يحتوي على سطر التوقيع:

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document doc = new Document(dataDir + "Signature line.docx");

SignatureLine signatureLine = ((Shape)doc.FirstSection.Body.GetChild(NodeType.Shape, 0, true)).SignatureLine;
```

## الخطوة 2: تحديد خيارات التوقيع

قم بإنشاء مثيل لفئة SignOptions وقم بتعيين خيارات التوقيع، بما في ذلك معرف الموفر:

```csharp
SignOptions signOptions = new SignOptions
{
ProviderId = signatureLine.ProviderId,
 SignatureLineId = signatureLine.Id
};
```

## الخطوة 3: توقيع الوثيقة

لتوقيع المستند، يجب عليك استخدام فئة DigitalSignatureUtil وتحديد شهادة التوقيع:

```csharp
CertificateHolder certHolder = CertificateHolder.Create(dataDir + "morzal.pfx", "aw");

DigitalSignatureUtil.Sign(dataDir + "Digitally signed.docx",
	dataDir + "SignDocuments.SetSignatureProviderId.docx", certHolder, signOptions);
```

تأكد من تحديد المسارات الصحيحة للمستند والشهادة والمستند الموقع.

### مثال على التعليمات البرمجية المصدر لتعيين معرف موفر التوقيع باستخدام Aspose.Words لـ .NET

فيما يلي الكود المصدري الكامل لتعيين معرف موفر التوقيع باستخدام Aspose.Words لـ .NET:

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

قم بإنهاء معرف موفر التوقيع في مستند Word الخاص بك باستخدام Aspose.Words لـ .NET.


## خاتمة

في هذا البرنامج التعليمي، تعلمنا كيفية تعيين معرف موفر التوقيع لسطر التوقيع في مستند Word باستخدام Aspose.Words for .NET. باتباع الخطوات المتوفرة، يمكنك بسهولة تحميل المستند والوصول إلى سطر التوقيع وتعيين معرف الموفر وتوقيع المستند. تساعد القدرة على تعيين معرف موفر التوقيع في تحديد هوية الموقّع وجدارته بالثقة، مما يعزز أمان وسلامة مستندات Word الخاصة بك. يوفر Aspose.Words for .NET واجهة برمجة تطبيقات قوية لمعالجة الكلمات باستخدام التوقيعات الرقمية، مما يسمح لك بتخصيص عملية التوقيع وإدارتها بسهولة.

### الأسئلة الشائعة لتعيين معرف موفر التوقيع في مستند Word

#### س: ما هو معرف موفر التوقيع في مستند Word؟

ج: معرف موفر التوقيع في مستند Word هو معرف فريد يحدد موفر التوقيع الرقمي. فهو يساعد على تحديد الكيان أو المنظمة المسؤولة عن إنشاء وإدارة التوقيع الرقمي.

#### س: كيف يمكنني تعيين معرف موفر التوقيع لسطر التوقيع في مستند Word باستخدام Aspose.Words for .NET؟

ج: لتعيين معرف موفر التوقيع لسطر التوقيع في مستند Word باستخدام Aspose.Words لـ .NET، يمكنك اتباع الخطوات التالية:
1.  قم بتحميل المستند باستخدام`Document` class وحدد المسار إلى ملف المستند.
2.  قم بالوصول إلى سطر التوقيع باستخدام الطريقة أو الخاصية المناسبة. على سبيل المثال، يمكنك استخدام`GetChild` طريقة لاسترداد شكل خط التوقيع.
3. استرداد معرف المزود من سطر التوقيع.
4.  إنشاء مثيل لـ`SignOptions` فئة وتعيين`ProviderId` الخاصية إلى معرف الموفر المسترد.
5.  استخدم ال`DigitalSignatureUtil.Sign` طريقة التوقيع على الوثيقة، وتوفير المعلمات اللازمة بما في ذلك`SignOptions` هدف.

#### س: كيف يمكنني الوصول إلى سطر التوقيع في مستند Word باستخدام Aspose.Words for .NET؟

 ج: للوصول إلى سطر التوقيع في مستند Word باستخدام Aspose.Words لـ .NET، يمكنك استخدام الطريقة أو الخاصية المناسبة لاسترداد شكل سطر التوقيع من بنية المستند. على سبيل المثال، يمكنك استخدام`GetChild` الطريقة مع المعلمات المناسبة للحصول على شكل خط التوقيع المطلوب.

#### س: هل يمكنني تعيين معرف موفر التوقيع لعدة أسطر توقيع في مستند Word؟

 ج: نعم، يمكنك تعيين معرف موفر التوقيع لعدة أسطر توقيع في مستند Word. يمكنك التكرار من خلال مجموعة أسطر التوقيع في المستند وتعيين معرف الموفر لكل سطر توقيع على حدة باستخدام`SignOptions.ProviderId` ملكية.

#### س: ما هو الغرض من معرف موفر التوقيع في مستند Word؟

ج: يخدم معرف موفر التوقيع في مستند Word غرض تحديد الكيان أو المؤسسة المسؤولة عن إنشاء التوقيع الرقمي وإدارته. فهو يساعد في إثبات صحة التوقيع الرقمي ومصداقيته من خلال ربطه بموفر معين.

#### س: ما نوع الشهادات الرقمية التي يمكن استخدامها لتعيين معرف موفر التوقيع في مستند Word؟

ج: يمكنك استخدام شهادات X.509 الرقمية مع معلومات الموفر المناسبة لتعيين معرف موفر التوقيع في مستند Word. يجب أن يتم إصدار الشهادة الرقمية من قبل مرجع مصدق موثوق به (CA) وأن تحتوي على بيانات التعريف اللازمة لتحديد الموفر.