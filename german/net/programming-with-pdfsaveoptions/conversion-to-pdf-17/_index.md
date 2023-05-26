---
title: التحويل إلى PDF 17
linktitle: التحويل إلى PDF 17
second_title: Aspose.Words لمراجع .NET API
description: تعرف على كيفية تحويل المستندات إلى PDF 1.7 باستخدام Aspose.Words for .NET.
type: docs
weight: 10
url: /de/net/programming-with-pdfsaveoptions/conversion-to-pdf-17/
---

في هذا البرنامج التعليمي ، سنرشدك عبر خطوات التحويل إلى PDF 1.7 باستخدام Aspose.Words for .NET. يتيح لك التحويل إلى PDF 1.7 إنشاء ملفات PDF تتوافق مع معيار PDF 1.7. اتبع الخطوات التالية:

## الخطوة 1: تحميل المستند

ابدأ بتحميل المستند الذي تريد تحويله إلى PDF:

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
Document doc = new Document(dataDir + "Rendering.docx");
```

تأكد من تحديد المسار الصحيح للمستند الخاص بك.

## الخطوة 2: تعيين خيارات تحويل PDF

قم بإنشاء مثيل لفئة PdfSaveOptions وحدد إصدار معيار PDF الذي تريد استخدامه:

```csharp
PdfSaveOptions saveOptions = new PdfSaveOptions { Compliance = PdfCompliance.Pdf17 };
```

يضمن هذا الخيار أن ملف PDF الذي تم إنشاؤه يتوافق مع معيار PDF 1.7.

## الخطوة 3: تحويل المستند إلى PDF

 استخدم ال`Save` طريقة تحويل المستند إلى PDF مع تحديد خيارات التحويل:

```csharp
doc.Save(dataDir + "WorkingWithPdfSaveOptions.ConversionToPdf17.pdf", saveOptions);
```

تأكد من تحديد المسار الصحيح لحفظ ملف PDF المحول.

### مثال على شفرة المصدر للتحويل إلى Pdf 17 باستخدام Aspose.Words for .NET

إليك التعليمات البرمجية المصدر الكاملة للتحويل إلى PDF 1.7 باستخدام Aspose.Words for .NET:

```csharp

	// المسار إلى دليل المستندات.
	string dataDir = "YOUR DOCUMENT DIRECTORY";
	Document doc = new Document(dataDir + "Rendering.docx");

	PdfSaveOptions saveOptions = new PdfSaveOptions { Compliance = PdfCompliance.Pdf17 };

	doc.Save(dataDir + "WorkingWithPdfSaveOptions.ConversionToPdf17.pdf", saveOptions);

```

باتباع هذه الخطوات ، يمكنك بسهولة التحويل إلى PDF 1.7 باستخدام Aspose.Words for .NET.

