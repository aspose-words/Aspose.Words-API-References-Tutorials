---
title: ضغط الصور في وثيقة PDF
linktitle: ضغط الصور في وثيقة PDF
second_title: Aspose.Words واجهة برمجة تطبيقات معالجة المستندات
description: دليل خطوة بخطوة لضغط الصور في مستند PDF باستخدام Aspose.Words لـ .NET.
type: docs
weight: 10
url: /ar/net/programming-with-pdfsaveoptions/image-compression/
---

توفر هذه المقالة دليلاً خطوة بخطوة حول كيفية استخدام ميزة ضغط الصور في مستند PDF مع Aspose.Words for .NET. وسنشرح كل جزء من الكود بالتفصيل. في نهاية هذا البرنامج التعليمي، ستكون قادرًا على فهم كيفية ضغط الصور في مستند وإنشاء ملف PDF باستخدام ضغط الصور المناسب.

قبل البدء، تأكد من تثبيت وتكوين مكتبة Aspose.Words for .NET في مشروعك. يمكنك العثور على المكتبة وتعليمات التثبيت على موقع Aspose.

## الخطوة 1: تحديد دليل المستند

 للبدء، تحتاج إلى تحديد المسار إلى الدليل الذي توجد به مستنداتك. يستبدل`"YOUR DOCUMENT DIRECTORY"` بالمسار الفعلي إلى دليل المستندات الخاص بك.

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## الخطوة 2: تحميل الوثيقة

بعد ذلك، نحتاج إلى تحميل المستند الذي نريد معالجته. في هذا المثال، نفترض أن المستند يسمى "Rendering.docx" ويقع في دليل المستندات المحدد.

```csharp
Document doc = new Document(dataDir + "Rendering.docx");
```

## الخطوة 3: تكوين خيارات الحفظ بتنسيق PDF مع ضغط الصور

 لضغط الصور عند التحويل إلى PDF، نحتاج إلى تكوين ملف`PdfSaveOptions` هدف. يمكننا ضبط نوع ضغط الصورة وجودة JPEG وخيارات التوافق الأخرى مع PDF إذا لزم الأمر.

```csharp
PdfSaveOptions saveOptions = new PdfSaveOptions
{
ImageCompression = PdfImageCompression.Jpeg,
PreserveFormFields = true
};
```

## الخطوة 4: احفظ المستند بصيغة PDF مع ضغط الصور

أخيرًا، يمكننا حفظ المستند بتنسيق PDF باستخدام خيارات الحفظ التي تم تكوينها مسبقًا.

```csharp
doc.Save(dataDir + "WorkingWithPdfSaveOptions.PdfImageCompression.pdf", saveOptions);
```

## الخطوة 5: تكوين خيارات الحفظ إلى PDF/A-2u مع ضغط الصور

إذا كنت تريد إنشاء ملف PDF متوافق مع PDF/A-2u مع ضغط الصور، فيمكنك تكوين خيارات الحفظ الإضافية.

```csharp
PdfSaveOptions saveOptionsA2U = new PdfSaveOptions
{
Compliance = PdfCompliance.PdfA2u,
ImageCompression = PdfImageCompression.Jpeg,
JpegQuality=100, // استخدم ضغط JPEG بجودة 50% لتقليل حجم الملف.
};
```

## الخطوة 6: احفظ المستند بصيغة PDF/A-2u مع ضغط الصور

احفظ المستند بتنسيق PDF/A-2u باستخدام خيارات الحفظ الإضافية التي تم تكوينها مسبقًا.

```csharp
doc.Save(dataDir + "WorkingWithPdfSaveOptions.PdfImageCompression_A2u.pdf", saveOptionsA2U);
```



هذا كل شئ ! لقد نجحت في ضغط الصور الموجودة في مستند وإنشاء ملف PDF باستخدام ضغط الصور المناسب باستخدام Aspose.Words for .NET.

### نموذج التعليمات البرمجية المصدر لضغط الصور باستخدام Aspose.Words لـ .NET

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
		JpegQuality = 100, // استخدم ضغط JPEG بجودة 50% لتقليل حجم الملف.
	};

	

	doc.Save(dataDir + "WorkingWithPdfSaveOptions.PdfImageCompression_A2u.pdf", saveOptionsA2U);
	
```

## خاتمة

في هذا البرنامج التعليمي، شرحنا كيفية ضغط الصور في مستند PDF باستخدام Aspose.Words for .NET. باتباع الخطوات الموضحة، يمكنك بسهولة تقليل حجم الصور في مستند PDF الخاص بك وإنشاء ملف PDF مع ضغط الصور المناسب. استخدم ميزات ضغط الصور في Aspose.Words for .NET لتحسين حجم مستندات PDF الخاصة بك مع الحفاظ على جودة الصورة.

### أسئلة مكررة

#### س: ما هو ضغط الصور في وثيقة PDF؟
ج: إن ضغط الصور في مستند PDF هو تقليل حجم الصور المضمنة في مستند PDF لتقليل الحجم الإجمالي لملف PDF. يؤدي ذلك إلى تقليل مساحة التخزين المطلوبة وتحسين الأداء عند تحميل ملف PDF وعرضه.

#### س: كيف يمكنني ضغط الصور في مستند PDF باستخدام Aspose.Words for .NET؟
ج: لضغط الصور في مستند PDF باستخدام Aspose.Words لـ .NET، اتبع الخطوات التالية:

 إنشاء مثيل لـ`Document` فئة تحدد المسار إلى مستند Word.

 إنشاء مثيل لـ`PdfSaveOptions` فئة وتعيين`ImageCompression`الملكية ل`PdfImageCompression.Jpeg` لاستخدام ضغط JPEG.

يمكنك أيضًا تعيين خيارات أخرى لضغط الصور، مثل جودة JPEG، وفقًا لاحتياجاتك.

 استخدم ال`Save` طريقة`Document`فئة لحفظ المستند بتنسيق PDF عن طريق تحديد خيارات الحفظ.

#### س: ما الفرق بين ضغط الصور القياسي وضغط الصور PDF/A-2u؟
ج: يعمل ضغط الصور القياسي على تقليل حجم الصور في مستند PDF مع الحفاظ على حقول النموذج. يؤدي هذا إلى تقليل الحجم الإجمالي لملف PDF دون المساس بوظيفة حقل النموذج.

يعد ضغط الصور باستخدام PDF/A-2u خيارًا إضافيًا يسمح لك بإنشاء ملف PDF يتوافق مع معيار PDF/A-2u أثناء تطبيق ضغط الصور. PDF/A-2u هو معيار ISO لمستندات PDF الأرشيفية ويضمن الحفاظ على المستندات على المدى الطويل.
