---
title: قم بتحسين حجم ملف PDF من خلال تخطي الخطوط Arial & Times Roman المضمنة
linktitle: قم بتحسين حجم ملف PDF من خلال تخطي الخطوط Arial & Times Roman المضمنة
second_title: Aspose.Words واجهة برمجة تطبيقات معالجة المستندات
description: دليل خطوة بخطوة لإنشاء ملف PDF محسّن دون تضمين خطوط Arial وTimes Roman باستخدام Aspose.Words for .NET.
type: docs
weight: 10
url: /ar/net/programming-with-pdfsaveoptions/skip-embedded-arial-and-times-roman-fonts/
---

توفر هذه المقالة دليلاً خطوة بخطوة حول كيفية استخدام الميزة لتحسين حجم PDF عن طريق تخطي خطوط Arial وTimes Roman المضمنة إلى حجم ملف التعريف باستخدام Aspose.Words for .NET. وسنشرح كل جزء من الكود بالتفصيل. في نهاية هذا البرنامج التعليمي، ستتمكن من فهم كيفية تكوين خيار وضع تضمين الخط في مستند وإنشاء ملف PDF دون تضمين خطوط Arial وTimes Roman.

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

## الخطوة 3: تكوين خيارات الحفظ بتنسيق PDF مع تضمين الخط

 لتخطي تضمين الخطوط Arial وTimes Roman في ملف PDF الذي تم إنشاؤه، نحتاج إلى تكوين`PdfSaveOptions` الكائن وتعيين`FontEmbeddingMode`الملكية ل`PdfFontEmbeddingMode.EmbedAll`.

```csharp
PdfSaveOptions saveOptions = new PdfSaveOptions { FontEmbeddingMode = PdfFontEmbeddingMode.EmbedAll };
```

## الخطوة 4: احفظ المستند بصيغة PDF بدون الخطوط المضمنة

أخيرًا، يمكننا حفظ المستند بتنسيق PDF باستخدام خيارات الحفظ التي تم تكوينها مسبقًا.

```csharp
doc.Save(dataDir + "WorkingWithPdfSaveOptions.SkipEmbeddedArialAndTimesRomanFonts.pdf", saveOptions);
```

هذا كل شئ ! لقد نجحت في إنشاء ملف PDF دون تضمين خطوط Arial وTimes Roman باستخدام Aspose.Words for .NET.

### مثال على التعليمات البرمجية المصدر لتخطي خطوط Arial وTimes Roman المضمنة بحجم ملف التعريف باستخدام Aspose.Words for .NET

```csharp

	// المسار إلى دليل المستندات.
	string dataDir = "YOUR DOCUMENT DIRECTORY";
	Document doc = new Document(dataDir + "Rendering.docx");

	PdfSaveOptions saveOptions = new PdfSaveOptions { FontEmbeddingMode = PdfFontEmbeddingMode.EmbedAll };

	doc.Save(dataDir + "WorkingWithPdfSaveOptions.SkipEmbeddedArialAndTimesRomanFonts.pdf", saveOptions);
   
```

## خاتمة

في هذا البرنامج التعليمي، شرحنا كيفية تعطيل تضمين خطوط Arial وTimes Roman في مستند PDF باستخدام Aspose.Words for .NET. باتباع الخطوات الموضحة، يمكنك إنشاء ملف PDF دون تضمين هذه الخطوط المحددة، مما يمكن أن يساعد في تقليل حجم الملف وضمان توافق أفضل للمستندات عبر الأنظمة الأساسية المختلفة. تأكد من مراعاة عواقب تعطيل تضمين الخط عند استخدام هذه الميزة. لا تتردد في استكشاف المزيد من ميزات Aspose.Words for .NET لتحسين إنشاء ملفات PDF الخاصة بك.

### أسئلة مكررة

#### س: ما هو تعطيل تضمين الخطوط Arial وTimes Roman في مستند PDF وما سبب أهميته؟
ج: إن تعطيل تضمين خطوط Arial وTimes Roman في مستند PDF هو عملية عدم تضمين هذه الخطوط في ملف PDF الذي تم إنشاؤه. قد يكون هذا أمرًا مهمًا لتقليل حجم ملف PDF عن طريق تجنب تضمين الخطوط المتوفرة بالفعل بشكل شائع في أنظمة قارئ PDF. يمكن أن يساعد أيضًا في ضمان توافق أفضل ومظهر متسق لمستند PDF عبر الأجهزة والأنظمة الأساسية المختلفة.

#### س: كيف يمكنني تكوين Aspose.Words لـ .NET بحيث لا يقوم بتضمين خطوط Arial وTimes Roman في مستند PDF؟
ج: لتكوين Aspose.Words لـ .NET بحيث لا يقوم بتضمين خطوط Arial وTimes Roman في مستند PDF، اتبع الخطوات التالية:

 قم بتعيين مسار الدليل حيث توجد مستنداتك عن طريق الاستبدال`"YOUR DOCUMENT DIRECTORY"` بالمسار الفعلي لدليل المستندات الخاص بك.

 قم بتحميل المستند الذي تريد معالجته باستخدام ملف`Document` الفئة ومسار المستند المحدد.

 إنشاء مثيل لـ`PdfSaveOptions` فئة وتعيين`FontEmbeddingMode`الملكية ل`PdfFontEmbeddingMode.EmbedAll`. سيؤدي هذا إلى تضمين جميع الخطوط باستثناء Arial وTimes Roman في ملف PDF الذي تم إنشاؤه.

 استخدم ال`Save` طريقة`Document` كائن لحفظ المستند بتنسيق PDF مع تحديد خيارات الحفظ التي تم تكوينها مسبقًا.

#### س: ما هي فوائد تعطيل تضمين الخط Arial وTimes Roman في مستند PDF؟
ج: فوائد تعطيل تضمين الخطوط Arial وTimes Roman في مستند PDF هي:

تقليل حجم ملف PDF: من خلال تجنب تضمين الخطوط المتوفرة بشكل شائع مثل Arial وTimes Roman، يمكن تقليل حجم ملف PDF، مما يسهل تخزين الملفات ومشاركتها ونقلها.

توافق أفضل: باستخدام الخطوط المتوفرة بشكل شائع على أنظمة قارئ PDF، فإنك تضمن توافقًا أفضل ومظهرًا أفضل للمستند على الأجهزة والأنظمة الأساسية المختلفة.

#### س: ما هي عواقب تعطيل تضمين خطوط Arial وTimes Roman في مستند PDF؟
ج: إن عواقب تعطيل تضمين خطوط Arial وTimes Roman في مستند PDF هي كما يلي:

مظهر مختلف: إذا لم تكن الخطوط Arial وTimes Roman متوفرة على النظام الذي تم فتح ملف PDF فيه، فسيتم استخدام خطوط بديلة، مما قد يؤدي إلى مظهر مختلف عن المقصود.

مشكلات سهولة القراءة: قد لا تكون الخطوط البديلة المستخدمة قابلة للقراءة مثل الخطوط الأصلية، مما قد يؤثر على سهولة قراءة المستند.