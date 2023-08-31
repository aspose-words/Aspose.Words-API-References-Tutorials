---
title: تحميل نطاق الصفحات لملف PDF
linktitle: تحميل نطاق الصفحات لملف PDF
second_title: Aspose.Words واجهة برمجة تطبيقات معالجة المستندات
description: دليل خطوة بخطوة لتحميل نطاق صفحات PDF محدد باستخدام Aspose.Words for .NET.
type: docs
weight: 10
url: /ar/net/programming-with-pdfloadoptions/load-page-range-of-pdf/
---

في هذا البرنامج التعليمي، سنرشدك إلى كيفية تحميل نطاق صفحات معين من مستند PDF باستخدام Aspose.Words for .NET. اتبع الخطوات التالية:

## الخطوة 1: تحميل مجموعة من صفحات PDF

استخدم الكود التالي لتحميل نطاق صفحات محدد من مستند PDF:

```csharp
// المسار إلى دليل المستندات.
string dataDir = "YOUR_DIRECTORY_OF_DOCUMENTS";

PdfLoadOptions loadOptions = new PdfLoadOptions { PageIndex = 0, PageCount = 1 };

Document doc = new Document(dataDir + "Pdf Document.pdf", loadOptions);
```

 في هذا المثال، نقوم بتحميل الصفحة الأولى من مستند PDF. يمكنك تغيير قيم`PageIndex` و`PageCount` إلى نطاق الصفحات المطلوب.

## الخطوة 2: حفظ الوثيقة

 وأخيرًا، يمكنك حفظ المستند الذي يحتوي على نطاق الصفحات المحدد باستخدام الملف`Save` طريقة:

```csharp
doc.Save(dataDir + "WorkingWithPdfLoadOptions.LoadPageRangeOfPdf.pdf");
```

تأكد من تحديد المسار الصحيح لحفظ المستند الذي تم تحريره.

هذا كل شئ ! لقد قمت الآن بتحميل نطاق صفحات محدد من مستند PDF باستخدام Aspose.Words for .NET.

### مثال على التعليمات البرمجية المصدر لتحميل نطاق الصفحات لملف Pdf باستخدام Aspose.Words لـ .NET

```csharp

	// المسار إلى دليل المستندات.
	string dataDir = "YOUR DOCUMENT DIRECTORY";
	PdfLoadOptions loadOptions = new PdfLoadOptions { PageIndex = 0, PageCount = 1 };

	
	Document doc = new Document(dataDir + "Pdf Document.pdf", loadOptions);

	doc.Save(dataDir + "WorkingWithPdfLoadOptions.LoadPageRangeOfPdf.pdf");
   
```
تذكر تحديد المسار الصحيح لدليل مستندات PDF الخاصة بك.



