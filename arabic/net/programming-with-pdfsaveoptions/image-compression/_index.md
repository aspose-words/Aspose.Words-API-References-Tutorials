---
title: ضغط الصورة
linktitle: ضغط الصورة
second_title: Aspose.Words لمراجع .NET API
description: دليل خطوة بخطوة لضغط الصور باستخدام Aspose.Words for .NET.
type: docs
weight: 10
url: /ar/net/programming-with-pdfsaveoptions/image-compression/
---

تقدم هذه المقالة دليلاً خطوة بخطوة حول كيفية استخدام ميزة ضغط الصور مع Aspose.Words for .NET. سنشرح كل جزء من الكود بالتفصيل. في نهاية هذا البرنامج التعليمي ، ستتمكن من فهم كيفية ضغط الصور في مستند وإنشاء ملف PDF بضغط الصور المناسب.

قبل أن تبدأ ، تأكد من تثبيت وتهيئة مكتبة Aspose.Words for .NET في مشروعك. يمكنك العثور على المكتبة وإرشادات التثبيت على موقع Aspose.

## الخطوة 1: تحديد دليل المستند

 للبدء ، تحتاج إلى تحديد المسار إلى الدليل حيث توجد مستنداتك. يستبدل`"YOUR DOCUMENT DIRECTORY"` مع المسار الفعلي إلى دليل المستندات الخاص بك.

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## الخطوة 2: قم بتحميل المستند

بعد ذلك ، نحتاج إلى تحميل المستند الذي نريد معالجته. في هذا المثال ، نفترض أن المستند يسمى "Rendering.docx" ويقع في دليل المستندات المحدد.

```csharp
Document doc = new Document(dataDir + "Rendering.docx");
```

## الخطوة 3: قم بتكوين خيارات الحفظ كملف PDF باستخدام ضغط الصور

 لضغط الصور عند التحويل إلى PDF ، نحتاج إلى تكوين ملف`PdfSaveOptions` هدف. يمكننا ضبط نوع ضغط الصور وجودة JPEG وخيارات التوافق مع PDF الأخرى إذا لزم الأمر.

```csharp
PdfSaveOptions saveOptions = new PdfSaveOptions
{
ImageCompression = PdfImageCompression.Jpeg,
PreserveFormFields = true
};
```

## الخطوة 4: احفظ المستند بصيغة PDF مع ضغط الصور

أخيرًا ، يمكننا حفظ المستند بتنسيق PDF باستخدام خيارات الحفظ التي تم تكوينها مسبقًا.

```csharp
doc.Save(dataDir + "WorkingWithPdfSaveOptions.PdfImageCompression.pdf", saveOptions);
```

## الخطوة 5: قم بتكوين خيارات الحفظ في PDF / A-2u بضغط الصور

إذا كنت تريد إنشاء ملف PDF متوافق مع PDF / A-2u بضغط الصور ، يمكنك تكوين خيارات الحفظ الإضافية.

```csharp
PdfSaveOptions saveOptionsA2U = new PdfSaveOptions
{
Compliance = PdfCompliance.PdfA2u,
ImageCompression = PdfImageCompression.Jpeg,
JpegQuality=100, // استخدم ضغط JPEG بجودة 50٪ لتقليل حجم الملف.
};
```

## الخطوة 6: احفظ المستند بصيغة PDF / A-2u بضغط الصورة

احفظ المستند بتنسيق PDF / A-2u باستخدام خيارات الحفظ الإضافية التي تم تكوينها مسبقًا.

```csharp
doc.Save(dataDir + "WorkingWithPdfSaveOptions.PdfImageCompression_A2u.pdf", saveOptionsA2U);
```



هذا كل شئ ! لقد نجحت في ضغط الصور في مستند وإنشاء ملف PDF بضغط الصور المناسب باستخدام Aspose.Words for .NET.

### عينة من التعليمات البرمجية المصدر لضغط الصور باستخدام Aspose.Words for .NET

```csharp

	// المسار إلى دليل المستندات.
	string dataDir = "YOUR DOCUMENT DIRECTORY";
	Document doc = new Document(dataDir + "Rendering.docx");

	PdfSaveOptions saveOptions = new PdfSaveOptions
	{
		ImageCompression = PdfImageCompression.Jpeg, PreserveFormFields = true
	};

	doc.Save(dataDir + "WorkingWithPdfSaveOptions.PdfImageCompression.pdf", saveOptions);

	PdfSaveOptions saveOptionsA2U = new PdfSaveOptions
	{
		Compliance = PdfCompliance.PdfA2u,
		ImageCompression = PdfImageCompression.Jpeg,
		JpegQuality = 100, // استخدم ضغط JPEG بجودة 50٪ لتقليل حجم الملف.
	};

	

	doc.Save(dataDir + "WorkingWithPdfSaveOptions.PdfImageCompression_A2u.pdf", saveOptionsA2U);
	
```
