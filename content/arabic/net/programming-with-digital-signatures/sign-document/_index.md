---
title: التوقيع على مستند Word
linktitle: التوقيع على مستند Word
second_title: واجهة برمجة تطبيقات معالجة المستندات Aspose.Words
description: تعرف على كيفية توقيع مستند Word رقميًا باستخدام Aspose.Words for .NET.
type: docs
weight: 10
url: /ar/net/programming-with-digital-signatures/sign-document/
---
في هذا البرنامج التعليمي ، سنرشدك عبر خطوات استخدام ميزة توقيع المستند مع Aspose.Words for .NET. تتيح لك هذه الميزة التوقيع رقميًا على مستند Word باستخدام شهادة. اتبع الخطوات التالية:

## الخطوة الأولى: تحميل الشهادة

ابدأ بتحميل شهادة التوقيع باستخدام فئة CertificateHolder:

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
CertificateHolder certHolder = CertificateHolder.Create(dataDir + "morzal.pfx", "aw");
```

تأكد من تحديد المسار الصحيح لشهادتك وكلمة المرور المرتبطة بها.

## الخطوة الثانية: توقيع الوثيقة

استخدم فئة DigitalSignatureUtil لتوقيع الوثيقة:

```csharp
DigitalSignatureUtil.Sign(dataDir + "Digitally signed.docx", dataDir + "Document.Signed.docx",
	certHolder);
```

تأكد من تحديد المسارات الصحيحة للمستند المصدر والمستند الموقع.

### مثال على الكود المصدري لتوقيع الوثيقة باستخدام Aspose.Words for .NET

فيما يلي الكود المصدري الكامل للتوقيع على مستند باستخدام Aspose.Words for .NET:

```csharp

	// المسار إلى دليل المستندات.
	string dataDir = "YOUR DOCUMENT DIRECTORY";
	CertificateHolder certHolder = CertificateHolder.Create(dataDir + "morzal.pfx", "aw");
	
	DigitalSignatureUtil.Sign(dataDir + "Digitally signed.docx", dataDir + "Document.Signed.docx",
		certHolder);

```

باتباع هذه الخطوات ، يمكنك بسهولة توقيع مستند Word باستخدام Aspose.Words for .NET.

## خاتمة

 في هذا البرنامج التعليمي ، استكشفنا ميزة توقيع المستند في Aspose.Words for .NET. عن طريق تحميل شهادة توقيع واستخدام ملف`DigitalSignatureUtil.Sign` الطريقة ، يمكننا توقيع مستند Word رقميًا. يوفر توقيع المستند المصادقة ويضمن سلامة محتويات المستند ، مما يجعله ميزة قيّمة لإدارة المستندات بشكل آمن وجدير بالثقة.

### الأسئلة الشائعة لوثيقة كلمة التوقيع

#### س: ما المقصود بتسجيل المستند في Aspose.Words for .NET؟

ج: يشير توقيع المستند في Aspose.Words for .NET إلى عملية التوقيع رقميًا على مستند Word باستخدام شهادة. تضيف هذه الميزة توقيعًا رقميًا إلى المستند ، مما يوفر أصالة محتويات المستند وتكاملها وعدم التنصل منها.

#### س: كيف يمكنني تحميل شهادة التوقيع في Aspose.Words for .NET؟

 ج: لتحميل شهادة التوقيع في Aspose.Words for .NET ، يمكنك استخدام`CertificateHolder` فصل. قم بإنشاء مثيل لـ`CertificateHolder` من خلال توفير المسار إلى ملف الشهادة وكلمة المرور المرتبطة. هذا مثال:

```csharp
CertificateHolder certHolder = CertificateHolder.Create("path/to/certificate.pfx", "password");
```

تأكد من توفير المسار الصحيح لشهادتك وكلمة المرور المرتبطة بها.

#### س: كيف أقوم بالتوقيع على مستند Word باستخدام Aspose.Words for .NET؟

 ج: لتوقيع مستند Word باستخدام Aspose.Words for .NET ، يمكنك استخدام`DigitalSignatureUtil` فصل. اتصل ب`Sign` الطريقة ، التي توفر المسار إلى المستند المصدر ، والمسار إلى المستند الموقع (الإخراج) ، و`CertificateHolder` هدف. هذا مثال:

```csharp
DigitalSignatureUtil.Sign("path/to/source/document.docx", "path/to/signed/document.docx", certHolder);
```

تأكد من توفير المسارات الصحيحة للمستند المصدر والمستند الموقع (الإخراج).

#### س: ما هو الغرض من توقيع الوثيقة؟

ج: يُعد توقيع المستند بمثابة وسيلة للتأكد من أصالة المستند وسلامته. من خلال التوقيع رقميًا على مستند ، يمكنك تقديم دليل على أصله ، والتحقق من عدم تغيير محتوياته ، وإثبات عدم التنصل. يشيع استخدام توقيع المستند في المستندات القانونية والمالية والحساسة.

#### س: هل يمكنني استخدام أي شهادة لتسجيل المستندات في Aspose.Words for .NET؟

ج: لتسجيل المستندات في Aspose.Words for .NET ، تحتاج إلى استخدام شهادة X.509 صالحة. يمكن الحصول على هذه الشهادة من مرجع مصدق موثوق به (CA) أو يمكن استخدام شهادة موقعة ذاتيًا لأغراض الاختبار.

#### س: ما هو تنسيق الملف الذي يدعمه Aspose.Words لـ .NET لتوقيع الوثيقة؟

 ج: يدعم Aspose.Words for .NET توقيع المستندات لمستندات Word بتنسيق ملف DOCX. يمكنك تسجيل ملفات DOCX باستخدام امتداد`DigitalSignatureUtil` الدرجة والشهادة المناسبة.

#### س: هل يمكنني توقيع عدة مستندات Word باستخدام نفس الشهادة؟

ج: نعم ، يمكنك توقيع عدة مستندات Word باستخدام نفس الشهادة. بمجرد تحميل الشهادة باستخدام ملف`CertificateHolder` class ، يمكنك إعادة استخدامه لتوقيع مستندات متعددة عن طريق استدعاء`DigitalSignatureUtil.Sign` طريقة ذات مصدر مختلف ومسارات وثيقة موقعة.

#### س: هل يعدّل توقيع المستند المستند الأصلي؟

ج: توقيع المستند مع Aspose.Words for .NET لا يعدل المستند الأصلي. بدلاً من ذلك ، يقوم بإنشاء نسخة موقعة رقمياً من المستند ، مع ترك المستند الأصلي كما هو. تحتوي النسخة الموقعة رقميًا على التوقيع الرقمي الإضافي ، مما يضمن سلامة محتويات المستند.

#### س: هل يمكنني التحقق من التوقيع الرقمي لوثيقة موقعة باستخدام Aspose.Words for .NET؟

 ج: نعم ، يوفر Aspose.Words for .NET وظائف للتحقق من التوقيع الرقمي لوثيقة موقعة. يمكنك استخدام ال`DigitalSignatureUtil.Verify` طريقة للتحقق من صحة وصحة التوقيع الرقمي.