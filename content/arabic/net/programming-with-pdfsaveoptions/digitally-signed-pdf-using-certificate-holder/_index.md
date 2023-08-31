---
title: أضف التوقيع الرقمي إلى PDF باستخدام Certificate Holder
linktitle: أضف التوقيع الرقمي إلى PDF باستخدام Certificate Holder
second_title: واجهة برمجة تطبيقات معالجة المستندات Aspose.Words
description: تعرف على كيفية إضافة التوقيع الرقمي إلى PDF باستخدام Certificate Holder with Aspose.Words for .NET.
type: docs
weight: 10
url: /ar/net/programming-with-pdfsaveoptions/digitally-signed-pdf-using-certificate-holder/
---

في هذا البرنامج التعليمي ، سنرشدك عبر خطوات إضافة توقيع رقمي إلى PDF باستخدام حامل الشهادة مع Aspose.Words for .NET. يضيف التوقيع الرقمي طبقة من الأمان والتكامل إلى وثيقة PDF. اتبع الخطوات التالية:

## الخطوة 1: إنشاء المستند وإضافة المحتوى

ابدأ بإنشاء مثيل لفئة المستند:

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
```

## الخطوة 2: أضف محتوى إلى المستند

 ثم استخدم ملف`DocumentBuilder`لإضافة محتوى إلى المستند. على سبيل المثال ، لإضافة فقرة تحتوي على النص "Test Signed PDF" ، استخدم امتداد`Writeln` طريقة:

```csharp
builder.Writeln("Test Signed PDF.");
```

يمكنك إضافة عناصر محتوى أخرى حسب الحاجة.

## الخطوة 3: تعيين خيارات حفظ PDF

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

## الخطوة 4: احفظ المستند بتنسيق PDF موقّع رقميًا

 استخدم ال`Save` طريقة لحفظ المستند بتنسيق PDF عن طريق تحديد خيارات الحفظ:

```csharp
doc.Save(dataDir + "WorkingWithPdfSaveOptions.DigitallySignedPdfUsingCertificateHolder.pdf", saveOptions);
```

تأكد من تحديد المسار الصحيح لحفظ ملف PDF الموقع رقميًا.

باتباع هذه الخطوات ، يمكنك بسهولة إنشاء ملف PDF موقّع رقميًا مع شهادة باستخدام Aspose.Words for .NET.

### مثال على شفرة المصدر لـ Pdf الموقّع رقميًا باستخدام حامل الشهادة باستخدام Aspose.Words for .NET

فيما يلي رمز المصدر الكامل لـ Pdf الموقّع رقميًا باستخدام حامل الشهادة من مستند باستخدام Aspose.Words for .NET:

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

في هذا البرنامج التعليمي ، استكشفنا خطوات إضافة توقيع رقمي إلى مستند PDF باستخدام شهادة مع Aspose.Words for .NET. يضيف التوقيع الرقمي طبقة من الأمان والتكامل إلى المستند ، مما يضمن مصداقيته ويجعل من الممكن اكتشاف أي تعديل لاحق. باتباع الخطوات المحددة ، يمكنك بسهولة إنشاء ملف PDF موقع رقميًا باستخدام شهادة مع Aspose.Words for .NET.

### أسئلة مكررة

#### س: ما هو التوقيع الرقمي ولماذا هو مهم في وثيقة PDF؟
ج: التوقيع الرقمي هو تقنية أمان تساعد على ضمان أصالة المستند الإلكتروني وسلامته وعدم التنصل منه ، مثل ملف PDF. يستخدم شهادة رقمية لإضافة طبقة أمان إلى المستند ، مما يساعد على التحقق من هوية المؤلف واكتشاف أي تغييرات لاحقة على المحتوى.

#### س: كيف يمكنني إضافة توقيع رقمي إلى مستند PDF باستخدام شهادة مع Aspose.Words for .NET؟
ج: لإضافة توقيع رقمي إلى مستند PDF باستخدام شهادة مع Aspose.Words for .NET ، اتبع الخطوات التالية:

 قم بإنشاء مثيل لـ`Document` فئة لتمثيل الوثيقة.

 استخدم ال`DocumentBuilder` فئة لإضافة المحتوى المطلوب إلى المستند.

 قم بإنشاء مثيل لـ`PdfSaveOptions` فئة وتحديد تفاصيل التوقيع الرقمي باستخدام`PdfDigitalSignatureDetails` فصل. ستحتاج إلى توفير المسار إلى الشهادة (`CertificateHolder.Create`) وكلمة المرور المرتبطة بها وسبب التوقيع والموقع.

 استخدم ال`Save` طريقة لحفظ المستند بتنسيق PDF مع تحديد خيارات الحفظ.

#### س: كيف أحصل على شهادة لإضافة توقيع رقمي إلى وثيقة PDF؟
ج: للحصول على شهادة لإضافة توقيع رقمي إلى مستند PDF ، يمكنك عادةً الاتصال بمرجع مصدق (CA) أو مزود خدمة ثقة. تصدر هذه الكيانات شهادات رقمية بعد التحقق من هويتك والتحقق من صحة طلبك. بمجرد حصولك على شهادة ، يمكنك استخدامها في التطبيق الخاص بك لإضافة توقيعات رقمية إلى مستندات PDF.

#### س: هل من الممكن تخصيص تفاصيل التوقيع الرقمي ، مثل السبب والموقع؟
 ج: نعم ، يمكنك تخصيص تفاصيل التوقيع الرقمي من خلال تحديد سبب وموقع التوقيع. في رمز المثال المقدم ، يمكنك تعديل قيم`reason` و`location` المعلمات عند إنشاء ملف`PdfDigitalSignatureDetails` هدف. تأكد من توفير المعلومات المناسبة لكل معلمة لتعكس سبب وموقع التوقيع في مستند PDF الخاص بك.