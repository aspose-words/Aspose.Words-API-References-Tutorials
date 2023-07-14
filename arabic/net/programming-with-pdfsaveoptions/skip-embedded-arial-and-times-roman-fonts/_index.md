---
title: قم بتحسين حجم PDF باستخدام تخطي الخطوط Arial & Times الرومانية المضمنة
linktitle: قم بتحسين حجم PDF باستخدام تخطي الخطوط Arial & Times الرومانية المضمنة
second_title: واجهة برمجة تطبيقات معالجة المستندات Aspose.Words
description: دليل خطوة بخطوة لإنشاء ملف PDF محسن بدون تضمين خطوط Arial و Times Roman باستخدام Aspose.Words for .NET.
type: docs
weight: 10
url: /ar/net/programming-with-pdfsaveoptions/skip-embedded-arial-and-times-roman-fonts/
---

توفر هذه المقالة دليلًا تفصيليًا حول كيفية استخدام الميزة لتحسين حجم PDF عن طريق تخطي خطوط Arial و Times Roman المضمنة إلى حجم ملف التعريف باستخدام Aspose.Words for .NET. سنشرح كل جزء من الكود بالتفصيل. في نهاية هذا البرنامج التعليمي ، ستتمكن من فهم كيفية تكوين خيار وضع دمج الخط في مستند وإنشاء ملف PDF بدون تضمين خطوط Arial و Times Roman.

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

## الخطوة 3: تكوين خيارات الحفظ كملف PDF مع دمج الخط

 لتخطي تضمين خطوط Arial و Times Roman في ملف PDF الذي تم إنشاؤه ، نحتاج إلى تكوين ملف`PdfSaveOptions` كائن وتعيين`FontEmbeddingMode` ملكية ل`PdfFontEmbeddingMode.EmbedAll`.

```csharp
PdfSaveOptions saveOptions = new PdfSaveOptions { FontEmbeddingMode = PdfFontEmbeddingMode.EmbedAll };
```

## الخطوة 4: احفظ المستند كملف PDF بدون خطوط مضمنة

أخيرًا ، يمكننا حفظ المستند بتنسيق PDF باستخدام خيارات الحفظ التي تم تكوينها مسبقًا.

```csharp
doc.Save(dataDir + "WorkingWithPdfSaveOptions.SkipEmbeddedArialAndTimesRomanFonts.pdf", saveOptions);
```

هذا كل شئ ! لقد نجحت في إنشاء ملف PDF بدون تضمين خطوط Arial و Times Roman باستخدام Aspose.Words for .NET.

### مثال على كود المصدر لتخطي خطوط Arial و Times Roman المضمنة بحجم ملف التعريف باستخدام Aspose.Words for .NET

```csharp

	// المسار إلى دليل المستندات.
	string dataDir = "YOUR DOCUMENT DIRECTORY";
	Document doc = new Document(dataDir + "Rendering.docx");

	PdfSaveOptions saveOptions = new PdfSaveOptions { FontEmbeddingMode = PdfFontEmbeddingMode.EmbedAll };

	doc.Save(dataDir + "WorkingWithPdfSaveOptions.SkipEmbeddedArialAndTimesRomanFonts.pdf", saveOptions);
   
```

## خاتمة

في هذا البرنامج التعليمي ، شرحنا كيفية تعطيل دمج خطوط Arial و Times Roman في مستند PDF باستخدام Aspose.Words for .NET. باتباع الخطوات الموضحة ، يمكنك إنشاء ملف PDF بدون دمج هذه الخطوط المحددة ، مما يساعد في تقليل حجم الملف وضمان توافق أفضل للمستندات عبر الأنظمة الأساسية المختلفة. تأكد من مراعاة نتائج تعطيل تضمين الخط عند استخدام هذه الميزة. لا تتردد في استكشاف المزيد من ميزات Aspose.Words for .NET لتحسين إنشاء ملفات PDF الخاصة بك.

### أسئلة مكررة

#### س: ما المقصود بتعطيل تضمين خط Arial و Times Roman في مستند PDF ولماذا يعد أمرًا مهمًا؟
ج: تعطيل دمج خطوط Arial و Times Roman في مستند PDF هو عملية عدم تضمين هذه الخطوط في ملف PDF الذي تم إنشاؤه. قد يكون هذا مهمًا لتقليل حجم ملف PDF عن طريق تجنب تضمين الخطوط المتوفرة بالفعل بشكل شائع على أنظمة قارئ PDF. يمكن أن يساعد أيضًا في ضمان توافق أفضل ومظهر متسق لمستند PDF عبر الأجهزة والأنظمة الأساسية المختلفة.

#### س: كيف يمكنني تكوين Aspose.Words for .NET لعدم تضمين خطوط Arial و Times Roman في مستند PDF؟
ج: لتكوين Aspose.Words for .NET لعدم تضمين خطوط Arial و Times Roman في مستند PDF ، اتبع الخطوات التالية:

 قم بتعيين مسار الدليل حيث توجد المستندات الخاصة بك عن طريق الاستبدال`"YOUR DOCUMENT DIRECTORY"` مع المسار الفعلي لدليل المستندات الخاص بك.

 قم بتحميل المستند الذي تريد معالجته باستخدام ملف`Document` فئة ومسار المستند المحدد.

 قم بإنشاء مثيل لـ`PdfSaveOptions`فئة وضبط`FontEmbeddingMode` ملكية ل`PdfFontEmbeddingMode.EmbedAll`. سيؤدي ذلك إلى تضمين كل الخطوط باستثناء Arial و Times Roman في ملف PDF الذي تم إنشاؤه.

 استخدم ال`Save` طريقة`Document` كائن لحفظ المستند بتنسيق PDF مع تحديد خيارات الحفظ التي تم تكوينها مسبقًا.

#### س: ما هي فوائد تعطيل دمج خط Arial و Times Roman في مستند PDF؟
ج: فوائد تعطيل دمج خط Arial و Times Roman في مستند PDF هي:

تقليل حجم ملف PDF: من خلال تجنب تضمين الخطوط المتاحة بشكل شائع مثل Arial و Times Roman ، يمكن تقليل حجم ملف PDF ، مما يسهل تخزين الملفات ومشاركتها ونقلها.

توافق أفضل: باستخدام الخطوط المتوفرة بشكل شائع في أنظمة قارئ PDF ، فإنك تضمن توافقًا أفضل ومظهرًا أفضل للمستند على الأجهزة والأنظمة الأساسية المختلفة.

#### س: ما هي النتائج المترتبة على تعطيل تضمين خطوط Arial و Times Roman في مستند PDF؟
ج: نتائج تعطيل دمج خطوط Arial و Times Roman في مستند PDF هي كما يلي:

مظهر مختلف: إذا كانت الخطوط Arial و Times Roman غير متوفرة على النظام حيث يتم فتح PDF ، فسيتم استخدام خطوط بديلة ، مما قد ينتج عنه مظهر مختلف عن المقصود.

مشاكل قابلية القراءة: قد لا تكون الخطوط البديلة المستخدمة قابلة للقراءة مثل الخطوط الأصلية ، مما قد يؤثر على سهولة قراءة المستند.