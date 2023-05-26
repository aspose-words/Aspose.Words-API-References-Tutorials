---
title: احصل على نطاق صفحات Jpeg
linktitle: احصل على نطاق صفحات Jpeg
second_title: Aspose.Words لمراجع .NET API
description: تعرف على كيفية الحصول على مجموعة من صفحات JPEG باستخدام Aspose.Words for .NET. البرنامج التعليمي الكامل لاستخراج الصور المخصصة.
type: docs
weight: 10
url: /es/net/programming-with-imagesaveoptions/get-jpeg-page-range/
---

في هذا البرنامج التعليمي ، سوف نستكشف كود المصدر C # المقدم لميزة "Get Range of JPEG Pages" مع Aspose.Words for .NET. تتيح لك هذه الميزة تحويل نطاق معين من صفحات المستند إلى صور بتنسيق JPEG.

## الخطوة الأولى: تهيئة البيئة

قبل أن تبدأ ، تأكد من إعداد بيئة التطوير الخاصة بك باستخدام Aspose.Words for .NET. تأكد من أنك أضفت المراجع الضرورية واستوردت مساحات الأسماء المناسبة.

## الخطوة الثانية: تحميل المستند

```csharp
// المسار إلى دليل المستندات الخاص بك
string dataDir = "YOUR DOCUMENTS DIRECTORY";

Document doc = new Document(dataDir + "Rendering.docx");
```

 في هذه الخطوة ، نقوم بتحميل المستند باستخدام ملف`Document` الطريقة وتمرير المسار إلى ملف DOCX للتحميل.

## الخطوة 3: تكوين خيارات النسخ الاحتياطي للصور

```csharp
ImageSaveOptions options = new ImageSaveOptions(SaveFormat.Jpeg);
options. PageSet = new PageSet(0);
options. ImageBrightness = 0.3f;
options. ImageContrast = 0.7f;
options. HorizontalResolution = 72f;
```

 في هذه الخطوة ، نقوم بتكوين خيارات النسخ الاحتياطي للصور. نخلق ملف`ImageSaveOptions` كائن يحدد تنسيق الحفظ المطلوب ، هنا "Jpeg" لتنسيق JPEG. نقوم أيضًا بتعيين نطاق الصفحات للتحويل باستخدام امتداد`PageSet`هدف. أخيرًا ، نقوم بضبط سطوع الصورة وتباينها باستخدام ملف`ImageBrightness` و`ImageContrast` الخصائص ، على التوالي. نقوم أيضًا بتغيير الدقة الأفقية باستخدام`HorizontalResolution` ملكية.

## الخطوة 4: نسخ الصور احتياطيًا

```csharp
doc.Save(dataDir + "WorkingWithImageSaveOptions.GetJpegPageRange.jpeg", options);
```

 في هذه الخطوة الأخيرة ، نقوم بحفظ الصور الخاصة بنطاق الصفحات المحدد بتنسيق JPEG باستخدام ملف`Save` الطريقة وتمرير المسار إلى ملف الإخراج ، جنبًا إلى جنب مع خيارات الحفظ المحددة.

يمكنك الآن تشغيل الكود المصدري لتحويل نطاق معين من الصفحات في مستندك إلى صور JPEG. سيتم حفظ الملف الناتج في الدليل المحدد بالاسم "WorkingWithImageSaveOptions.GetJpegPageRange.jpeg".

### نموذج لشفرة مصدر للحصول على نطاق صفحات Jpeg باستخدام Aspose.Words For .NET

```csharp 
 // المسار إلى دليل المستند الخاص بك
 string dataDir = "YOUR DOCUMENT DIRECTORY"; 

Document doc = new Document(dataDir + "Rendering.docx");

ImageSaveOptions options = new ImageSaveOptions(SaveFormat.Jpeg);

// اضبط "PageSet" على "0" لتحويل الصفحة الأولى فقط من المستند.
options.PageSet = new PageSet(0);

// قم بتغيير سطوع الصورة وتباينها.
// كلاهما على مقياس 0-1 وهما 0.5 افتراضيًا.
options.ImageBrightness = 0.3f;
options.ImageContrast = 0.7f;

// تغيير الدقة الأفقية.
// القيمة الافتراضية لهذه الخصائص هي 96.0 ، لدقة 96 نقطة في البوصة.
options.HorizontalResolution = 72f;

doc.Save(dataDir + "WorkingWithImageSaveOptions.GetJpegPageRange.jpeg", options);
            
        
```

## خاتمة

في هذا البرنامج التعليمي ، استكشفنا وظيفة الحصول على نطاق صفحات JPEG باستخدام Aspose.Words for .NET. لقد تعلمنا كيفية تحويل نطاق معين من صفحات المستند إلى صور بتنسيق JPEG ، أثناء تخصيص خيارات الحفظ.

هذه الميزة مفيدة عندما تريد استخراج صفحات معينة من مستند وحفظها كصور JPEG. يمكنك أيضًا ضبط السطوع والتباين والدقة الأفقية للصور لتحقيق نتائج مخصصة.

تقدم Aspose.Words for .NET مجموعة واسعة من الميزات المتقدمة لمعالجة المستندات وإنشائها. يعد الحصول على نطاق صفحات JPEG أحد الأدوات القوية العديدة التي يضعها تحت تصرفك.

لا تتردد في دمج هذه الميزة في Aspose.Words لمشاريع .NET للحصول على صور JPEG عالية الجودة من مستنداتك.