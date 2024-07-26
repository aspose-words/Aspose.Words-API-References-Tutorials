---
title: احصل على نطاق صفحات Jpeg
linktitle: احصل على نطاق صفحات Jpeg
second_title: Aspose.Words واجهة برمجة تطبيقات معالجة المستندات
description: قم بتحويل صفحات معينة من مستندات Word إلى JPEG باستخدام إعدادات مخصصة باستخدام Aspose.Words لـ .NET. تعرف على كيفية ضبط السطوع والتباين والدقة خطوة بخطوة.
type: docs
weight: 10
url: /ar/net/programming-with-imagesaveoptions/get-jpeg-page-range/
---
## مقدمة

يمكن أن يكون تحويل مستندات Word إلى صور مفيدًا بشكل لا يصدق، سواء كنت تقوم بإنشاء صور مصغرة، أو معاينة المستندات عبر الإنترنت، أو مشاركة المحتوى بتنسيق يسهل الوصول إليه. باستخدام Aspose.Words for .NET، يمكنك بسهولة تحويل صفحات معينة من مستندات Word الخاصة بك إلى تنسيق JPEG مع تخصيص إعدادات متنوعة مثل السطوع والتباين والدقة. دعونا نتعمق في كيفية تحقيق ذلك خطوة بخطوة!

## المتطلبات الأساسية

قبل أن نبدأ، ستحتاج إلى بعض الأشياء:

-  Aspose.Words for .NET: تأكد من تثبيت Aspose.Words for .NET. أنت تستطيع[قم بتنزيله هنا](https://releases.aspose.com/words/net/).
- بيئة التطوير: بيئة تطوير AC# مثل Visual Studio.
- مستند نموذجي: مستند Word للعمل معه. يمكنك استخدام أي ملف .docx لهذا البرنامج التعليمي.
- المعرفة الأساسية بـ C#: الإلمام ببرمجة C#.

بمجرد أن تكون هذه الأشياء جاهزة، فلنبدأ!

## استيراد مساحات الأسماء

لاستخدام Aspose.Words لـ .NET، ستحتاج إلى استيراد مساحات الأسماء الضرورية في بداية التعليمات البرمجية الخاصة بك. وهذا يضمن لك الوصول إلى كافة الفئات والأساليب المطلوبة لمعالجة المستندات.

```csharp
using Aspose.Words;
using Aspose.Words.Saving;
```

## الخطوة 1: قم بتحميل المستند الخاص بك

أولاً، نحتاج إلى تحميل مستند Word الذي نريد تحويله. لنفترض أن وثيقتنا تحمل اسمًا`Rendering.docx` ويقع في الدليل المحدد بواسطة العنصر النائب`YOUR DOCUMENT DIRECTORY`.

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document doc = new Document(dataDir + "Rendering.docx");
```

 يقوم هذا الرمز بتهيئة المسار إلى المستند الخاص بك وتحميله في Aspose.Words`Document` هدف.

## الخطوة 2: إعداد ImageSaveOptions

 بعد ذلك، سنقوم بإعداد`ImageSaveOptions` لتحديد الطريقة التي نريد أن يتم بها إنشاء ملف JPEG الخاص بنا. يتضمن ذلك ضبط نطاق الصفحة وسطوع الصورة والتباين والدقة.

```csharp
ImageSaveOptions options = new ImageSaveOptions(SaveFormat.Jpeg);
options.PageSet = new PageSet(0); // تحويل الصفحة الأولى فقط
options.ImageBrightness = 0.3f;   // ضبط السطوع
options.ImageContrast = 0.7f;     // ضبط التباين
options.HorizontalResolution = 72f; // تعيين القرار
```

## الخطوة 3: احفظ المستند بتنسيق JPEG

وأخيرًا، نحفظ المستند كملف JPEG باستخدام الإعدادات التي حددناها.

```csharp
doc.Save(dataDir + "WorkingWithImageSaveOptions.GetJpegPageRange.jpeg", options);
```

 يحفظ هذا الرمز الصفحة الأولى من`Rendering.docx` كصورة JPEG مع إعدادات السطوع والتباين والدقة المحددة.

## خاتمة

وهناك لديك! لقد نجحت في تحويل صفحة معينة من مستند Word إلى صورة JPEG باستخدام إعدادات مخصصة باستخدام Aspose.Words for .NET. يمكن تخصيص هذه العملية لتناسب الاحتياجات المختلفة، سواء كنت تقوم بإعداد صور لموقع ويب، أو إنشاء معاينات للمستندات، أو أكثر.

## الأسئلة الشائعة

### هل يمكنني تحويل صفحات متعددة في وقت واحد؟
 نعم، يمكنك تحديد نطاق من الصفحات باستخدام`PageSet` الممتلكات في`ImageSaveOptions`.

### كيف أضبط جودة الصورة؟
 يمكنك ضبط جودة ملف JPEG باستخدام`JpegQuality` الممتلكات في`ImageSaveOptions`.

### هل يمكنني الحفظ بتنسيقات صور أخرى؟
 نعم، يدعم Aspose.Words تنسيقات الصور المختلفة مثل PNG، وBMP، وTIFF. غير ال`SaveFormat` في`ImageSaveOptions` وفقاً لذلك.

### هل هناك طريقة لمعاينة الصورة قبل الحفظ؟
ستحتاج إلى تنفيذ آلية معاينة بشكل منفصل، حيث أن Aspose.Words لا يوفر ميزة معاينة مدمجة.

### كيف يمكنني الحصول على ترخيص مؤقت لـ Aspose.Words؟
 يمكنك طلب أ[الترخيص المؤقت هنا](https://purchase.aspose.com/temporary-license/).