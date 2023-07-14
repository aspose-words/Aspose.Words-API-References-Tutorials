---
title: ضغط الصور في مستند PDF
linktitle: ضغط الصور في مستند PDF
second_title: واجهة برمجة تطبيقات معالجة المستندات Aspose.Words
description: دليل خطوة بخطوة لضغط الصور في مستند PDF باستخدام Aspose.Words for .NET.
type: docs
weight: 10
url: /ar/net/programming-with-pdfsaveoptions/image-compression/
---

تقدم هذه المقالة دليلاً خطوة بخطوة حول كيفية استخدام ميزة ضغط الصور في مستند PDF مع Aspose.Words for .NET. سنشرح كل جزء من الكود بالتفصيل. في نهاية هذا البرنامج التعليمي ، ستتمكن من فهم كيفية ضغط الصور في مستند وإنشاء ملف PDF بضغط الصور المناسب.

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

## خاتمة

في هذا البرنامج التعليمي ، شرحنا كيفية ضغط الصور في مستند PDF باستخدام Aspose.Words for .NET. باتباع الخطوات الموضحة ، يمكنك بسهولة تقليل حجم الصور في مستند PDF الخاص بك وإنشاء ملف PDF بضغط الصور المناسب. استخدم ميزات ضغط الصور في Aspose.Words for .NET لتحسين حجم مستندات PDF مع الحفاظ على جودة الصورة.

### أسئلة مكررة

#### س: ما هو ضغط الصور في مستند PDF؟
ج: ضغط الصور في مستند PDF لتقليل حجم الصور المضمنة في مستند PDF لتقليل الحجم الكلي لملف PDF. هذا يقلل من مساحة التخزين المطلوبة ويحسن الأداء عند تحميل وعرض ملف PDF.

#### س: كيف يمكنني ضغط الصور في مستند PDF باستخدام Aspose.Words for .NET؟
ج: لضغط الصور في مستند PDF باستخدام Aspose.Words for .NET ، اتبع الخطوات التالية:

 قم بإنشاء مثيل لـ`Document` فئة تحدد المسار إلى مستند Word.

 قم بإنشاء مثيل لـ`PdfSaveOptions`فئة وضبط`ImageCompression` ملكية ل`PdfImageCompression.Jpeg` لاستخدام ضغط JPEG.

يمكنك أيضًا تعيين خيارات أخرى لضغط الصور ، مثل جودة JPEG ، وفقًا لاحتياجاتك.

 استخدم ال`Save` طريقة`Document`class لحفظ المستند بتنسيق PDF عن طريق تحديد خيارات الحفظ.

#### س: ما الفرق بين ضغط الصور القياسي وضغط الصور بتنسيق PDF / A-2u؟
ج: يؤدي ضغط الصور القياسي إلى تقليل حجم الصور في مستند PDF مع الاحتفاظ بحقول النموذج. يؤدي ذلك إلى تقليل الحجم الكلي لملف PDF دون المساس بوظائف حقل النموذج.

يعد ضغط الصور باستخدام PDF / A-2u خيارًا إضافيًا يسمح لك بإنشاء ملف PDF يتوافق مع معيار PDF / A-2u أثناء تطبيق ضغط الصورة. PDF / A-2u هو معيار ISO لمستندات PDF الأرشيفية ويضمن الحفاظ على المستندات على المدى الطويل.
