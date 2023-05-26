---
title: اختزال الصور
linktitle: اختزال الصور
second_title: Aspose.Words لمراجع .NET API
description: تعرف على كيفية تقليل دقة الصورة عند التحويل إلى PDF باستخدام Aspose.Words for .NET.
type: docs
weight: 10
url: /zh/net/programming-with-pdfsaveoptions/downsampling-images/
---

في هذا البرنامج التعليمي ، سنرشدك عبر الخطوات لتقليل دقة الصورة عند التحويل إلى PDF باستخدام Aspose.Words for .NET. هذا يقلل من حجم ملف PDF الذي تم إنشاؤه. اتبع الخطوات التالية:

## الخطوة 1: تحميل المستند

ابدأ بتحميل المستند الذي تريد تحويله إلى PDF:

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
Document doc = new Document(dataDir + "Rendering.docx");
```

تأكد من تحديد المسار الصحيح للمستند الخاص بك.

## الخطوة 2: تكوين خيارات حفظ PDF

قم بإنشاء مثيل لفئة PdfSaveOptions وقم بتعيين خيارات تصغير حجم الصورة:

```csharp
PdfSaveOptions saveOptions = new PdfSaveOptions
{
DownsampleOptions = { Resolution = 36, ResolutionThreshold = 128 }
};
```

 ال`Resolution` تحدد الخاصية الدقة المستهدفة للصور و`ResolutionThreshold` تحدد الخاصية الحد الأدنى من الدقة التي لن يتم تصغير الصور دونها.

## الخطوة 3: تحويل المستند إلى PDF

 استخدم ال`Save` طريقة لتحويل المستند إلى PDF مع تحديد خيارات الحفظ:

```csharp
doc.Save(dataDir + "WorkingWithPdfSaveOptions.DownsamplingImages.pdf", saveOptions);
```

تأكد من تحديد المسار الصحيح لحفظ ملف PDF المحول.

### مثال على شفرة المصدر لاختزال الصور باستخدام Aspose.Words for .NET

```csharp

	// المسار إلى دليل المستندات.
	string dataDir = "YOUR DOCUMENT DIRECTORY";
	Document doc = new Document(dataDir + "Rendering.docx");

	//يمكننا تعيين حد أدنى للاختزال.
	// ستمنع هذه القيمة الصورة الثانية في مستند الإدخال من الاختزال.
	PdfSaveOptions saveOptions = new PdfSaveOptions
	{
		DownsampleOptions = { Resolution = 36, ResolutionThreshold = 128 }
	};

	doc.Save(dataDir + "WorkingWithPdfSaveOptions.DownsamplingImages.pdf", saveOptions);

```

باتباع هذه الخطوات ، يمكنك بسهولة تقليل دقة الصورة عند التحويل إلى PDF باستخدام Aspose.Words for .NET.


