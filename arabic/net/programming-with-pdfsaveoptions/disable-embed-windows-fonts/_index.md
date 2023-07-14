---
title: تقليل حجم PDF عن طريق تعطيل الخطوط المضمنة
linktitle: تقليل حجم PDF عن طريق تعطيل الخطوط المضمنة
second_title: واجهة برمجة تطبيقات معالجة المستندات Aspose.Words
description: تعرف على كيفية تقليل حجم PDF باستخدام تعطيل تضمين خط Windows عند تحويل المستندات إلى PDF باستخدام Aspose.Words for .NET.
type: docs
weight: 10
url: /ar/net/programming-with-pdfsaveoptions/disable-embed-windows-fonts/
---

في هذا البرنامج التعليمي ، سنرشدك خلال الخطوات لتقليل حجم PDF مع تعطيل تضمين خط Windows في مستند PDF باستخدام Aspose.Words for .NET. من خلال تعطيل دمج الخط ، يمكنك تقليل حجم ملف PDF الذي تم إنشاؤه. اتبع الخطوات التالية:

## الخطوة 1: تحميل المستند

ابدأ بتحميل المستند الذي تريد تحويله إلى PDF:

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
Document doc = new Document(dataDir + "Rendering.docx");
```

تأكد من تحديد المسار الصحيح للمستند الخاص بك.

## الخطوة 2: تعيين خيارات حفظ PDF

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

### مثال على شفرة المصدر لـ Disable Embed Windows Fonts باستخدام Aspose.Words for .NET

إليك كود المصدر الكامل لتعطيل تضمين خطوط Windows في مستند PDF باستخدام Aspose.Words for .NET:

```csharp

	// المسار إلى دليل المستندات.
	string dataDir = "YOUR DOCUMENT DIRECTORY";
	Document doc = new Document(dataDir + "Rendering.docx");

	// سيتم حفظ ملف PDF الناتج بدون تضمين خطوط Windows القياسية.
	PdfSaveOptions saveOptions = new PdfSaveOptions { FontEmbeddingMode = PdfFontEmbeddingMode.EmbedNone };
	
	doc.Save(dataDir + "WorkingWithPdfSaveOptions.DisableEmbedWindowsFonts.pdf", saveOptions);

```
باتباع هذه الخطوات ، يمكنك بسهولة تعطيل دمج خطوط Windows في مستند PDF باستخدام Aspose.Words for .NET.


## خاتمة

في هذا البرنامج التعليمي ، تعلمنا كيفية تقليل حجم ملف PDF عن طريق تعطيل تضمين خطوط Windows باستخدام Aspose.Words for .NET. من خلال تعطيل دمج الخط ، يمكنك تقليل حجم ملف PDF الذي تم إنشاؤه ، مما يسهل تخزين الملفات ومشاركتها ونقلها. ومع ذلك ، من المهم ملاحظة أن تعطيل دمج خط Windows قد يتسبب في تغييرات في المظهر والتنسيق في مستند PDF النهائي. تأكد من مراعاة هذه العواقب عند استخدام هذه الميزة. لا تتردد في استكشاف المزيد من ميزات Aspose.Words for .NET لتحسين إنشاء ملفات PDF الخاصة بك.

### أسئلة مكررة

#### س: ما هو تعطيل تضمين خط Windows في مستند PDF ولماذا هو مهم؟
ج: تعطيل دمج خط Windows في مستند PDF هو عملية منع تضمين خطوط Windows في ملف PDF الذي تم إنشاؤه. يؤدي ذلك إلى تقليل حجم ملف PDF عن طريق إزالة بيانات خط Windows المضمنة. يمكن أن يكون هذا مهمًا لتقليل حجم ملفات PDF ، مما يسهل تخزينها ومشاركتها ونقلها بشكل أسرع.

#### س: كيف يمكنني تعطيل تضمين خط Windows في مستند PDF باستخدام Aspose.Words for .NET؟
ج: لتعطيل تضمين خطوط Windows في مستند PDF باستخدام Aspose.Words for .NET ، اتبع الخطوات التالية:

 قم بتحميل المستند الذي تريد تحويله إلى PDF باستخدام ملف`Document` الفصل الدراسي ومسار الوثيقة.

 قم بإنشاء مثيل لـ`PdfSaveOptions`فئة وضبط`FontEmbeddingMode` ملكية ل`PdfFontEmbeddingMode.EmbedNone`. يؤدي هذا إلى تعطيل دمج خطوط Windows في ملف PDF الذي تم إنشاؤه.

 استخدم ال`Save` طريقة`Document` لتحويل المستند إلى PDF مع تحديد خيارات التحويل التي تم تكوينها مسبقًا.

#### س: ما هي فوائد تعطيل تضمين خط Windows في مستند PDF؟
ج: فوائد تعطيل دمج خط Windows في مستند PDF هي:

تقليل حجم ملف PDF: من خلال تعطيل دمج خط Windows ، تتم إزالة بيانات خط Windows المضمنة ، مما يقلل من حجم ملف PDF الذي تم إنشاؤه.

تخزين أسهل: ملفات PDF الصغيرة أسهل في التخزين والحفظ والنقل.

مشاركة ونقل أسرع: يمكن مشاركة ملفات PDF الأصغر حجمًا ونقلها بشكل أسرع ، مما يوفر الوقت والموارد.

#### س: ما هي النتائج المترتبة على تعطيل تضمين خط Windows في مستند PDF؟
ج: يمكن أن يؤدي تعطيل دمج خطوط Windows في مستند PDF إلى عواقب مثل:

فقدان المظهر والتنسيق: إذا كانت خطوط Windows المحددة في المستند غير متوفرة على النظام حيث يتم فتح PDF ، فسيتم استخدام خطوط بديلة ، مما قد ينتج عنه مظهر وتنسيق غير صحيحين. تختلف في الشكل عن تلك المتوقعة.

مشاكل قابلية القراءة: إذا كانت الخطوط البديلة المستخدمة غير قابلة للقراءة مثل الخطوط الأصلية ، فقد يؤثر ذلك على سهولة قراءة النص في مستند PDF.