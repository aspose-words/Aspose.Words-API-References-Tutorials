---
title: الوصول والتحقق من التوقيع في مستند Word
linktitle: الوصول والتحقق من التوقيع في مستند Word
second_title: Aspose.Words واجهة برمجة تطبيقات معالجة المستندات
description: تعرف على كيفية الوصول إلى التوقيعات الرقمية والتحقق منها في مستند Word باستخدام Aspose.Words for .NET.
type: docs
weight: 10
url: /ar/net/programming-with-digital-signatures/access-and-verify-signature/
---
في هذا البرنامج التعليمي، سنرشدك خلال خطوات استخدام ميزة الوصول والتحقق من التوقيع في Aspose.Words for .NET. تتيح لك هذه الميزة الوصول إلى التوقيعات الرقمية في مستند Word والتحقق من صحتها. اتبع الخطوات التالية:

## الخطوة 1: تحميل المستند والوصول إلى التوقيعات

ابدأ بتحميل المستند الذي يحتوي على التوقيعات الرقمية:

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document doc = new Document(dataDir + "Digitally signed.docx");
```

## الخطوة 2: تصفح التوقيعات الرقمية

استخدم حلقة للتنقل عبر كافة التوقيعات الرقمية في المستند:

```csharp
foreach (DigitalSignature signature in doc.DigitalSignatures)
{
	// الوصول إلى معلومات التوقيع
	Console.WriteLine("* Signature Found *");
	Console.WriteLine("Is valid: " + signature.IsValid);
	// هذه الخاصية متاحة في مستندات MS Word فقط.
	Console.WriteLine("Reason for signing: " + signature.Comments); 
	Console.WriteLine("Time of signing: " + signature.SignTime);
	Console.WriteLine("Subject name: " + signature.CertificateHolder.Certificate.SubjectName.Name);
	Console.WriteLine("Issuer name: " + signature.CertificateHolder.Certificate.IssuerName.Name);
	Console.WriteLine();
}
```

تأكد من تخصيص رسائل العرض وفقًا لاحتياجاتك.

### مثال على التعليمات البرمجية المصدر للوصول والتحقق من التوقيع باستخدام Aspose.Words لـ .NET

فيما يلي الكود المصدري الكامل للوصول والتحقق من التوقيع باستخدام Aspose.Words for .NET:

```csharp
	
	// المسار إلى دليل المستندات.
	string dataDir = "YOUR DOCUMENT DIRECTORY";
	Document doc = new Document(dataDir + "Digitally signed.docx");

	foreach (DigitalSignature signature in doc.DigitalSignatures)
	{
		Console.WriteLine("* Signature Found *");
		Console.WriteLine("Is valid: " + signature.IsValid);
		// هذه الخاصية متاحة في مستندات MS Word فقط.
		Console.WriteLine("Reason for signing: " + signature.Comments); 
		Console.WriteLine("Time of signing: " + signature.SignTime);
		Console.WriteLine("Subject name: " + signature.CertificateHolder.Certificate.SubjectName.Name);
		Console.WriteLine("Issuer name: " + signature.CertificateHolder.Certificate.IssuerName.Name);
		Console.WriteLine();
	}

```

باتباع هذه الخطوات، ستتمكن بسهولة من الوصول إلى التوقيعات الرقمية والتحقق منها في مستند Word الخاص بك باستخدام Aspose.Words for .NET.

## خاتمة

في هذا البرنامج التعليمي، اكتشفنا ميزة الوصول إلى التوقيعات الرقمية والتحقق منها في مستند Word باستخدام Aspose.Words for .NET. باتباع الخطوات المقدمة، يمكنك بسهولة تحميل مستند والوصول إلى التوقيعات الرقمية الخاصة به والتحقق من صحتها. توفر القدرة على الوصول إلى التوقيعات الرقمية والتحقق منها طريقة لضمان سلامة وأصالة مستندات Word الخاصة بك. يوفر Aspose.Words for .NET واجهة برمجة تطبيقات قوية لمعالجة الكلمات باستخدام التوقيعات الرقمية، مما يسمح لك بأتمتة عملية التحقق وتعزيز أمان مستنداتك.

### الأسئلة الشائعة

#### س: ما هي التوقيعات الرقمية في مستند Word؟

ج: التوقيعات الرقمية في مستند Word هي توقيعات إلكترونية توفر طريقة للتحقق من سلامة المستند وأصله. ويتم إنشاؤها باستخدام الشهادات الرقمية وخوارزميات التشفير، مما يسمح للمستلمين بالتحقق من أن المستند لم يتم تغييره وأنه يأتي من مصدر موثوق به.

#### س: كيف يمكنني الوصول إلى التوقيعات الرقمية في مستند Word باستخدام Aspose.Words for .NET؟

ج: للوصول إلى التوقيعات الرقمية في مستند Word باستخدام Aspose.Words لـ .NET، يمكنك اتباع الخطوات التالية:
1.  قم بتحميل المستند باستخدام`Document` class وحدد المسار إلى ملف المستند.
2.  استخدم حلقة للتكرار من خلال`DigitalSignatures` جمع الوثيقة. يمثل كل تكرار توقيعًا رقميًا.

#### س: ما هي المعلومات التي يمكنني الوصول إليها من التوقيع الرقمي في مستند Word؟

ج: من التوقيع الرقمي في مستند Word، يمكنك الوصول إلى معلومات متنوعة، مثل:
- الصلاحية: التحقق من صحة التوقيع.
- التعليقات: احصل على سبب التوقيع الذي حدده الموقع.
- وقت التوقيع: احصل على الوقت الذي تم فيه توقيع المستند.
- اسم الموضوع: استرداد اسم الموقع أو موضوع الشهادة.
- اسم المُصدر: احصل على اسم مُصدر الشهادة.

#### س: هل يمكنني التحقق من صحة التوقيع الرقمي في مستند Word باستخدام Aspose.Words for .NET؟

 ج: نعم، يمكنك التحقق من صحة التوقيع الرقمي في مستند Word باستخدام Aspose.Words for .NET. من خلال الوصول إلى`IsValid` ملكية`DigitalSignature` الكائن، يمكنك تحديد ما إذا كان التوقيع صالحًا أم لا.

#### س: كيف يمكنني التحقق من صحة التوقيعات الرقمية في مستند Word باستخدام Aspose.Words for .NET؟

ج: للتحقق من صحة التوقيعات الرقمية في مستند Word باستخدام Aspose.Words لـ .NET، يمكنك اتباع الخطوات التالية:
1.  الوصول إلى`DigitalSignatures` جمع الوثيقة.
2.  كرر من خلال كل`DigitalSignature` كائن في المجموعة.
3.  استخدم ال`IsValid` ملكية`DigitalSignature` كائن للتحقق مما إذا كان التوقيع صالحًا.

#### س: هل يمكنني استرداد تعليقات الموقّع أو سبب التوقيع من توقيع رقمي في مستند Word؟

ج: نعم، يمكنك استرداد تعليقات الموقع أو سبب التوقيع من التوقيع الرقمي في مستند Word. ال`Comments` ملكية`DigitalSignature` يوفر الكائن إمكانية الوصول إلى التعليقات المحددة بواسطة الموقع أثناء عملية التوقيع.

#### س: ما نوع المستندات التي تدعمها ميزة التحقق من التوقيع في Aspose.Words for .NET؟

ج: تدعم ميزة التحقق من التوقيع في Aspose.Words for .NET التحقق من التوقيعات الرقمية في مستندات Word بتنسيق ملف DOCX. يمكنك استخدام هذه الميزة للتحقق من التوقيعات في ملفات DOCX.

#### س: كيف يمكنني الوصول إلى تفاصيل الشهادة الخاصة بالتوقيع الرقمي في مستند Word باستخدام Aspose.Words for .NET؟

 ج: للوصول إلى تفاصيل الشهادة الخاصة بالتوقيع الرقمي في مستند Word باستخدام Aspose.Words for .NET، يمكنك الوصول إلى`CertificateHolder` ملكية`DigitalSignature` هدف. من`CertificateHolder` الكائن، يمكنك استرداد تفاصيل مختلفة للشهادة، مثل اسم الموضوع واسم المُصدر.

#### س: هل يمكنني تخصيص عرض أو معالجة التوقيعات الرقمية في مستند Word باستخدام Aspose.Words for .NET؟

 ج: نعم، يمكنك تخصيص عرض أو معالجة التوقيعات الرقمية في مستند Word باستخدام Aspose.Words for .NET. من خلال الوصول إلى خصائص وطرق`DigitalSignature` الكائن، يمكنك استخراج المعلومات المطلوبة، أو إجراء عمليات تحقق إضافية، أو دمج عملية التحقق من التوقيع في سير عمل التطبيق الخاص بك.

#### س: هل من الممكن التحقق من التوقيعات الرقمية المتعددة في مستند Word باستخدام Aspose.Words لـ .NET؟

 ج: نعم، من الممكن التحقق من التوقيعات الرقمية المتعددة في مستند Word باستخدام Aspose.Words for .NET. من خلال التكرار من خلال`DigitalSignatures` عند جمع المستند، يمكنك الوصول إلى كل توقيع رقمي والتحقق منه على حدة.

