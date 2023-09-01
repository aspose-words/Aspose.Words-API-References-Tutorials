---
title: تقليل حجم PDF عن طريق تعطيل الخطوط المضمنة
linktitle: تقليل حجم PDF عن طريق تعطيل الخطوط المضمنة
second_title: Aspose.Words واجهة برمجة تطبيقات معالجة المستندات
description: تعرف على كيفية تقليل حجم ملف PDF من خلال تعطيل تضمين خطوط Windows عند تحويل المستندات إلى PDF باستخدام Aspose.Words for .NET.
type: docs
weight: 10
url: /ar/net/programming-with-pdfsaveoptions/disable-embed-windows-fonts/
---

في هذا البرنامج التعليمي، سنرشدك خلال خطوات تقليل حجم PDF مع تعطيل تضمين خط Windows في مستند PDF باستخدام Aspose.Words for .NET. من خلال تعطيل تضمين الخط، يمكنك تقليل حجم ملف PDF الذي تم إنشاؤه. اتبع الخطوات التالية:

## الخطوة 1: تحميل الوثيقة

ابدأ بتحميل المستند الذي تريد تحويله إلى PDF:

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
Document doc = new Document(dataDir + "Rendering.docx");
```

تأكد من تحديد المسار الصحيح للمستند الخاص بك.

## الخطوة 2: قم بتعيين خيارات حفظ PDF

قم بإنشاء مثيل لفئة PdfSaveOptions وحدد كيفية تضمين الخطوط:

```csharp
PdfSaveOptions saveOptions = new PdfSaveOptions { FontEmbeddingMode = PdfFontEmbeddingMode.EmbedNone };
```

يتيح لك هذا الخيار إلغاء تنشيط تكامل خطوط Windows في ملف PDF الذي تم إنشاؤه.

## الخطوة 3: تحويل المستند إلى PDF

 استخدم ال`Save` طريقة تحويل المستند إلى PDF مع تحديد خيارات التحويل:

```csharp
doc.Save(dataDir + "WorkingWithPdfSaveOptions.DisableEmbedWindowsFonts.pdf", saveOptions);
```

تأكد من تحديد المسار الصحيح لحفظ ملف PDF المحول.

### مثال على التعليمات البرمجية المصدر لتعطيل تضمين خطوط Windows باستخدام Aspose.Words لـ .NET

فيما يلي الكود المصدري الكامل لتعطيل تضمين خطوط Windows في مستند PDF باستخدام Aspose.Words for .NET:

```csharp

	// المسار إلى دليل المستندات.
	string dataDir = "YOUR DOCUMENT DIRECTORY";
	Document doc = new Document(dataDir + "Rendering.docx");

	// سيتم حفظ ملف PDF الناتج دون تضمين خطوط Windows القياسية.
	PdfSaveOptions saveOptions = new PdfSaveOptions { FontEmbeddingMode = PdfFontEmbeddingMode.EmbedNone };
	
	doc.Save(dataDir + "WorkingWithPdfSaveOptions.DisableEmbedWindowsFonts.pdf", saveOptions);

```
باتباع هذه الخطوات، يمكنك بسهولة تعطيل تضمين خطوط Windows في مستند PDF باستخدام Aspose.Words for .NET.


## خاتمة

في هذا البرنامج التعليمي، تعلمنا كيفية تقليل حجم ملف PDF عن طريق تعطيل تضمين خطوط Windows باستخدام Aspose.Words for .NET. من خلال تعطيل تضمين الخط، يمكنك تقليل حجم ملف PDF الذي تم إنشاؤه، مما يسهل تخزين الملفات ومشاركتها ونقلها. ومع ذلك، من المهم ملاحظة أن تعطيل تضمين خطوط Windows قد يتسبب في حدوث تغييرات في المظهر والتنسيق في مستند PDF النهائي. تأكد من مراعاة هذه العواقب عند استخدام هذه الميزة. لا تتردد في استكشاف المزيد من ميزات Aspose.Words for .NET لتحسين إنشاء ملفات PDF الخاصة بك.

### أسئلة مكررة

#### س: ما هو تعطيل تضمين خطوط Windows في مستند PDF وما سبب أهميته؟
ج: إن تعطيل تضمين خطوط Windows في مستند PDF هو عملية منع تضمين خطوط Windows في ملف PDF الذي تم إنشاؤه. يؤدي هذا إلى تقليل حجم ملف PDF عن طريق إزالة بيانات خط Windows المضمنة. قد يكون هذا مهمًا لتقليل حجم ملفات PDF، مما يسهل تخزينها ومشاركتها ونقلها بشكل أسرع.

#### س: كيف يمكنني تعطيل تضمين خطوط Windows في مستند PDF باستخدام Aspose.Words for .NET؟
ج: لتعطيل تضمين خطوط Windows في مستند PDF باستخدام Aspose.Words لـ .NET، اتبع الخطوات التالية:

 قم بتحميل المستند الذي تريد تحويله إلى PDF باستخدام الملف`Document` مسار الطبقة والوثيقة.

 إنشاء مثيل لـ`PdfSaveOptions` فئة وتعيين`FontEmbeddingMode` الملكية ل`PdfFontEmbeddingMode.EmbedNone`. يؤدي هذا إلى تعطيل تضمين خطوط Windows في ملف PDF الذي تم إنشاؤه.

 استخدم ال`Save` طريقة`Document` كائن لتحويل المستند إلى PDF مع تحديد خيارات التحويل التي تم تكوينها مسبقًا.

#### س: ما هي فوائد تعطيل تضمين خطوط Windows في مستند PDF؟
ج: فوائد تعطيل تضمين خطوط Windows في مستند PDF هي:

تقليل حجم ملف PDF: عن طريق تعطيل تضمين خط Windows، تتم إزالة بيانات خط Windows المضمنة، مما يقلل حجم ملف PDF الذي تم إنشاؤه.

تخزين أسهل: من السهل تخزين ملفات PDF الصغيرة وحفظها ونقلها.

مشاركة ونقل أسرع: يمكن مشاركة ملفات PDF الصغيرة ونقلها بشكل أسرع، مما يوفر الوقت والموارد.

#### س: ما هي عواقب تعطيل تضمين خطوط Windows في مستند PDF؟
ج: يمكن أن يؤدي تعطيل تضمين خطوط Windows في مستند PDF إلى عواقب مثل:

فقدان المظهر والتنسيق: إذا كانت خطوط Windows المحددة في المستند غير متوفرة على النظام الذي تم فتح ملف PDF فيه، فسيتم استخدام خطوط بديلة، مما قد يؤدي إلى ظهور وتنسيق غير صحيح. مختلفة في الشكل عن تلك المتوقعة.

مشكلات إمكانية القراءة: إذا كانت الخطوط البديلة المستخدمة غير قابلة للقراءة مثل الخطوط الأصلية، فقد يؤثر ذلك على إمكانية قراءة النص في مستند PDF.