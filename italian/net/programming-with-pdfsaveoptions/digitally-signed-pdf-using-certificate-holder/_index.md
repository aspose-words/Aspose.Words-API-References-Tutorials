---
title: ملف PDF موقع رقميًا باستخدام حامل الشهادة
linktitle: ملف PDF موقع رقميًا باستخدام حامل الشهادة
second_title: Aspose.Words لمراجع .NET API
description: تعرف على كيفية توقيع ملف PDF رقميًا باستخدام حامل شهادة مع Aspose.Words for .NET.
type: docs
weight: 10
url: /it/net/programming-with-pdfsaveoptions/digitally-signed-pdf-using-certificate-holder/
---

في هذا البرنامج التعليمي ، سنوجهك عبر خطوات إنشاء ملف PDF موقع رقميًا باستخدام شهادة مع Aspose.Words for .NET. يضيف التوقيع الرقمي طبقة من الأمان والتكامل إلى وثيقة PDF. اتبع الخطوات التالية:

## الخطوة 1: إنشاء المستند وإضافة المحتوى

ابدأ بإنشاء مثيل لفئة المستند:

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
```

## الخطوة 2: أضف محتوى إلى المستند

 ثم استخدم ملف`DocumentBuilder` لإضافة محتوى إلى المستند. على سبيل المثال ، لإضافة فقرة تحتوي على النص "Test Signed PDF" ، استخدم امتداد`Writeln` طريقة:

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
