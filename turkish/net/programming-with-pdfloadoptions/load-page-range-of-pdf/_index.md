---
title: تحميل نطاق الصفحات من ملف PDF
linktitle: تحميل نطاق الصفحات من ملف PDF
second_title: Aspose.Words لمراجع .NET API
description: دليل تفصيلي خطوة بخطوة لتحميل نطاق معين من صفحات PDF باستخدام Aspose.Words for .NET.
type: docs
weight: 10
url: /tr/net/programming-with-pdfloadoptions/load-page-range-of-pdf/
---

في هذا البرنامج التعليمي ، سنرشدك إلى كيفية تحميل نطاق صفحات معين من مستند PDF باستخدام Aspose.Words for .NET. اتبع الخطوات التالية:

## الخطوة 1: تحميل مجموعة من صفحات PDF

استخدم الكود التالي لتحميل نطاق صفحات معين من مستند PDF:

```csharp
// المسار إلى دليل المستندات.
string dataDir = "YOUR_DIRECTORY_OF_DOCUMENTS";

PdfLoadOptions loadOptions = new PdfLoadOptions { PageIndex = 0, PageCount = 1 };

Document doc = new Document(dataDir + "Pdf Document.pdf", loadOptions);
```

 في هذا المثال ، نقوم بتحميل الصفحة الأولى من مستند PDF. يمكنك تغيير قيم`PageIndex` و`PageCount` إلى نطاق الصفحات المطلوب.

## الخطوة 2: حفظ المستند

 أخيرًا ، يمكنك حفظ المستند الذي يحتوي على نطاق الصفحات المحدد باستخدام امتداد`Save` طريقة:

```csharp
doc.Save(dataDir + "WorkingWithPdfLoadOptions.LoadPageRangeOfPdf.pdf");
```

تأكد من تحديد المسار الصحيح لحفظ المستند المحرر.

هذا كل شئ ! لقد قمت الآن بتحميل نطاق صفحات معين من مستند PDF باستخدام Aspose.Words for .NET.

### مثال على شفرة المصدر لتحميل نطاق الصفحات من ملف PDF باستخدام Aspose.Words for .NET

```csharp

	// المسار إلى دليل المستندات.
	string dataDir = "YOUR DOCUMENT DIRECTORY";
	PdfLoadOptions loadOptions = new PdfLoadOptions { PageIndex = 0, PageCount = 1 };

	
	Document doc = new Document(dataDir + "Pdf Document.pdf", loadOptions);

	doc.Save(dataDir + "WorkingWithPdfLoadOptions.LoadPageRangeOfPdf.pdf");
   
```
تذكر تحديد المسار الصحيح إلى دليل مستندات PDF الخاصة بك.



