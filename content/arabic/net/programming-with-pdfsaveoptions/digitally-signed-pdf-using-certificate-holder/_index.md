---
title: أضف التوقيع الرقمي إلى PDF باستخدام حامل الشهادة
linktitle: أضف التوقيع الرقمي إلى PDF باستخدام حامل الشهادة
second_title: Aspose.Words واجهة برمجة تطبيقات معالجة المستندات
description: تعرف على كيفية إضافة التوقيع الرقمي إلى ملف PDF باستخدام حامل الشهادة مع Aspose.Words لـ .NET.
type: docs
weight: 10
url: /ar/net/programming-with-pdfsaveoptions/digitally-signed-pdf-using-certificate-holder/
---

في هذا البرنامج التعليمي، سنرشدك خلال خطوات إضافة توقيع رقمي إلى PDF باستخدام حامل الشهادة مع Aspose.Words for .NET. يضيف التوقيع الرقمي طبقة من الأمان والتكامل إلى مستند PDF. اتبع الخطوات التالية:

## الخطوة 1: إنشاء المستند وإضافة المحتوى

ابدأ بإنشاء مثيل لفئة المستند:

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
```

## الخطوة 2: إضافة محتوى إلى المستند

 ثم استخدم`DocumentBuilder`لإضافة محتوى إلى المستند. على سبيل المثال، لإضافة فقرة تحتوي على النص "اختبار PDF الموقع"، استخدم الخيار`Writeln` طريقة:

```csharp
builder.Writeln("Test Signed PDF.");
```

يمكنك إضافة عناصر محتوى أخرى حسب الحاجة.

## الخطوة 3: قم بتعيين خيارات حفظ PDF

قم بإنشاء مثيل لفئة PdfSaveOptions وحدد تفاصيل التوقيع الرقمي:

```csharp
PdfSaveOptions saveOptions = new PdfSaveOptions
{
	DigitalSignatureDetails = new PdfDigitalSignatureDetails(
		CertificateHolder.Create(MyDir + "morzal.pfx", "aw"), "reason", "location",
		DateTime.Now)
};
```

تأكد من تحديد المسار الصحيح لشهادتك وكلمة المرور المرتبطة بها. يمكنك أيضًا تخصيص سبب التوقيع وموقعه.

## الخطوة 4: احفظ المستند بصيغة PDF موقعة رقميًا

 استخدم ال`Save` طريقة حفظ المستند بصيغة PDF عن طريق تحديد خيارات الحفظ:

```csharp
doc.Save(dataDir + "WorkingWithPdfSaveOptions.DigitallySignedPdfUsingCertificateHolder.pdf", saveOptions);
```

تأكد من تحديد المسار الصحيح لحفظ ملف PDF الموقع رقميًا.

باتباع هذه الخطوات، يمكنك بسهولة إنشاء ملف PDF موقع رقميًا باستخدام شهادة باستخدام Aspose.Words for .NET.

### مثال على التعليمات البرمجية المصدر لملف Pdf الموقع رقميًا باستخدام حامل الشهادة باستخدام Aspose.Words لـ .NET

فيما يلي الكود المصدري الكامل لملف Pdf الموقع رقميًا باستخدام حامل الشهادة من مستند يستخدم Aspose.Words for .NET:

```csharp

            // المسار إلى دليل المستندات.
			string dataDir = "YOUR DOCUMENT DIRECTORY";
            Document doc = new Document();
            DocumentBuilder builder = new DocumentBuilder(doc);
            
            builder.Writeln("Test Signed PDF.");

            PdfSaveOptions saveOptions = new PdfSaveOptions
            {
                DigitalSignatureDetails = new PdfDigitalSignatureDetails(
                    CertificateHolder.Create(MyDir + "morzal.pfx", "aw"), "reason", "location",
                    DateTime.Now)
            };

            doc.Save(dataDir + "WorkingWithPdfSaveOptions.DigitallySignedPdfUsingCertificateHolder.pdf", saveOptions);
            
        
```
## خاتمة

في هذا البرنامج التعليمي، استكشفنا خطوات إضافة توقيع رقمي إلى مستند PDF باستخدام شهادة مع Aspose.Words for .NET. ويضيف التوقيع الرقمي طبقة من الأمان والسلامة إلى الوثيقة، مما يضمن صحتها ويجعل من الممكن اكتشاف أي تعديل لاحق. باتباع الخطوات المذكورة، يمكنك بسهولة إنشاء ملف PDF موقع رقميًا باستخدام شهادة مع Aspose.Words for .NET.

### أسئلة مكررة

#### س: ما هو التوقيع الرقمي ولماذا هو مهم في مستند PDF؟
ج: التوقيع الرقمي هو أسلوب أمني يساعد على ضمان صحة وسلامة وعدم رفض مستند إلكتروني، مثل ملف PDF. ويستخدم شهادة رقمية لإضافة طبقة من الأمان إلى المستند، مما يساعد في التحقق من هوية المؤلف واكتشاف أي تغييرات لاحقة على المحتوى.

#### س: كيف يمكنني إضافة توقيع رقمي إلى مستند PDF باستخدام شهادة مع Aspose.Words for .NET؟
ج: لإضافة توقيع رقمي إلى مستند PDF باستخدام شهادة مع Aspose.Words for .NET، اتبع الخطوات التالية:

 إنشاء مثيل لـ`Document` فئة لتمثيل الوثيقة.

 استخدم ال`DocumentBuilder` class لإضافة المحتوى المطلوب إلى المستند.

 إنشاء مثيل لـ`PdfSaveOptions` فئة وحدد تفاصيل التوقيع الرقمي باستخدام`PdfDigitalSignatureDetails` فصل. سوف تحتاج إلى توفير المسار إلى الشهادة (`CertificateHolder.Create`)، وكلمة المرور المرتبطة، وسبب التوقيع وموقعه.

 استخدم ال`Save` طريقة لحفظ المستند بتنسيق PDF مع تحديد خيارات الحفظ.

#### س: كيف يمكنني الحصول على شهادة لإضافة توقيع رقمي إلى مستند PDF؟
ج: للحصول على شهادة لإضافة توقيع رقمي إلى مستند PDF، يمكنك عادةً الاتصال بمرجع مصدق (CA) أو مزود خدمة ثقة. تقوم هذه الجهات بإصدار شهادات رقمية بعد التحقق من هويتك والتحقق من صحة طلبك. بمجرد حصولك على الشهادة، يمكنك استخدامها في التطبيق الخاص بك لإضافة التوقيعات الرقمية إلى مستندات PDF.

#### س: هل من الممكن تخصيص تفاصيل التوقيع الرقمي مثل السبب والموقع؟
 ج: نعم، يمكنك تخصيص تفاصيل التوقيع الرقمي من خلال تحديد سبب التوقيع ومكانه. في رمز المثال المقدم، يمكنك تعديل قيم`reason`و`location` المعلمات عند إنشاء`PdfDigitalSignatureDetails` هدف. تأكد من تقديم المعلومات المناسبة لكل معلمة لتعكس سبب التوقيع وموقعه في مستند PDF الخاص بك.