---
title: قم بتعيين معرف موفر التوقيع في مستند Word
linktitle: قم بتعيين معرف موفر التوقيع في مستند Word
second_title: واجهة برمجة تطبيقات معالجة المستندات Aspose.Words
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


## خاتمة

في هذا البرنامج التعليمي ، تعلمنا كيفية تعيين معرف موفر التوقيع لسطر التوقيع في مستند Word باستخدام Aspose.Words for .NET. باتباع الخطوات المقدمة ، يمكنك بسهولة تحميل المستند والوصول إلى سطر التوقيع وتعيين معرف الموفر وتوقيع المستند. تساعد القدرة على تعيين معرّف موفر التوقيع على تحديد هوية الموقّع وموثوقيته ، وتعزيز أمان وسلامة مستندات Word الخاصة بك. يوفر Aspose.Words for .NET واجهة برمجة تطبيقات قوية لمعالجة الكلمات مع التوقيعات الرقمية ، مما يسمح لك بتخصيص وإدارة عملية التوقيع بسهولة.

### التعليمات الخاصة بمعرف موفر التوقيع المحدد في مستند Word

#### س: ما هو معرف موفر التوقيع في مستند Word؟

ج: معرف موفر التوقيع في مستند Word هو معرف فريد يحدد موفر التوقيع الرقمي. يساعد في تحديد الكيان أو المنظمة المسؤولة عن إنشاء وإدارة التوقيع الرقمي.

#### س: كيف يمكنني تعيين معرف موفر التوقيع لسطر توقيع في مستند Word باستخدام Aspose.Words for .NET؟

ج: لتعيين معرف موفر التوقيع لسطر التوقيع في مستند Word باستخدام Aspose.Words for .NET ، يمكنك اتباع الخطوات التالية:
1.  قم بتحميل المستند باستخدام ملف`Document` class وحدد المسار إلى ملف المستند.
2.  قم بالوصول إلى سطر التوقيع باستخدام الطريقة أو الخاصية المناسبة. على سبيل المثال ، يمكنك استخدام ملفات`GetChild` طريقة لاسترداد شكل خط التوقيع.
3. استرجع معرف الموفر من سطر التوقيع.
4.  قم بإنشاء مثيل لـ`SignOptions`فئة وضبط`ProviderId` الخاصية إلى معرف المزود المسترجع.
5.  استخدم ال`DigitalSignatureUtil.Sign` طريقة لتوقيع الوثيقة ، مع توفير المعلمات الضرورية بما في ذلك`SignOptions` هدف.

#### س: كيف يمكنني الوصول إلى سطر التوقيع في مستند Word باستخدام Aspose.Words for .NET؟

 ج: للوصول إلى سطر التوقيع في مستند Word باستخدام Aspose.Words for .NET ، يمكنك استخدام الطريقة أو الخاصية المناسبة لاسترداد شكل سطر التوقيع من بنية المستند. على سبيل المثال ، يمكنك استخدام ملف`GetChild` طريقة مع المعلمات المناسبة للحصول على شكل خط التوقيع المطلوب.

#### س: هل يمكنني تعيين معرف موفر التوقيع للعديد من أسطر التوقيع في مستند Word؟

 ج: نعم ، يمكنك تعيين معرف موفر التوقيع لأسطر توقيع متعددة في مستند Word. يمكنك التكرار من خلال مجموعة أسطر التوقيع في المستند وتعيين معرف الموفر لكل سطر توقيع على حدة باستخدام`SignOptions.ProviderId` ملكية.

#### س: ما هو الغرض من معرف موفر التوقيع في مستند Word؟

ج: يخدم معرف موفر التوقيع في مستند Word الغرض من تحديد الكيان أو المؤسسة المسؤولة عن إنشاء التوقيع الرقمي وإدارته. يساعد في إثبات صحة التوقيع الرقمي وموثوقيته من خلال ربطه بمزود معين.

#### س: ما نوع الشهادات الرقمية التي يمكن استخدامها لتعيين معرف موفر التوقيع في مستند Word؟

ج: يمكنك استخدام الشهادات الرقمية X.509 مع معلومات الموفر المناسبة لتعيين معرف موفر التوقيع في مستند Word. يجب أن تكون الشهادة الرقمية صادرة عن مرجع مصدق موثوق به (CA) وأن تحتوي على البيانات الوصفية اللازمة لتعريف الموفر.