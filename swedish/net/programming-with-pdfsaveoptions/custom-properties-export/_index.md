---
title: تصدير خصائص مخصصة
linktitle: تصدير خصائص مخصصة
second_title: Aspose.Words لمراجع .NET API
description: تعرف على كيفية تصدير الخصائص المخصصة عند تحويل المستندات إلى PDF باستخدام Aspose.Words for .NET.
type: docs
weight: 10
url: /sv/net/programming-with-pdfsaveoptions/custom-properties-export/
---

في هذا البرنامج التعليمي ، سنرشدك خلال الخطوات لتصدير الخصائص المخصصة للمستند باستخدام Aspose.Words for .NET. يتيح لك تصدير الخصائص المخصصة تضمين معلومات إضافية في مستند PDF الذي تم إنشاؤه. اتبع الخطوات التالية:

## الخطوة 1: إنشاء مستند وإضافة خصائص مخصصة

ابدأ بإنشاء مثيل لفئة المستند:

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document doc = new Document();
```

## الخطوة 2: إضافة خصائص مخصصة
بعد ذلك ، أضف الخصائص المخصصة المطلوبة. على سبيل المثال ، لإضافة خاصية "شركة" بالقيمة "Aspose" ، استخدم`Add` طريقة مجموعة CustomDocumentProperties:

```csharp
doc.CustomDocumentProperties.Add("Company", "Aspose");
```

يمكنك إضافة العديد من الخصائص المخصصة حسب الحاجة.

## الخطوة 3: قم بتعيين خيارات تصدير PDF

قم بإنشاء مثيل لفئة PdfSaveOptions وحدد كيفية تصدير الخصائص المخصصة:

```csharp
PdfSaveOptions saveOptions = new PdfSaveOptions { CustomPropertiesExport = PdfCustomPropertiesExport.Standard };
```

يتحكم هذا الخيار في تصدير الخصائص المخصصة عند التحويل إلى PDF.

## الخطوة 4: تحويل المستند إلى PDF

 استخدم ال`Save` طريقة تحويل المستند إلى PDF مع تحديد خيارات التحويل:

```csharp
doc.Save(dataDir + "WorkingWithPdfSaveOptions.CustomPropertiesExport.pdf", saveOptions);
```

تأكد من تحديد المسار الصحيح لحفظ ملف PDF المحول.

### مثال على شفرة المصدر لتصدير الخصائص المخصصة باستخدام Aspose.Words for .NET

إليك التعليمات البرمجية المصدر الكاملة لتصدير الخصائص المخصصة من مستند باستخدام Aspose.Words for .NET:


```csharp

	// المسار إلى دليل المستندات.
	string dataDir = "YOUR DOCUMENT DIRECTORY";
	Document doc = new Document();
	doc.CustomDocumentProperties.Add("Company", "Aspose");

	PdfSaveOptions saveOptions = new PdfSaveOptions { CustomPropertiesExport = PdfCustomPropertiesExport.Standard };

	doc.Save(dataDir + "WorkingWithPdfSaveOptions.CustomPropertiesExport.pdf", saveOptions);

```

باتباع هذه الخطوات ، يمكنك بسهولة تصدير الخصائص المخصصة للمستند عند التحويل إلى PDF باستخدام Aspose.Words for .NET.

