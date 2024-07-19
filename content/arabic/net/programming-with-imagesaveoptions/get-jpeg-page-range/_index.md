---
title: احصل على نطاق صفحات Jpeg
linktitle: احصل على نطاق صفحات Jpeg
second_title: Aspose.Words واجهة برمجة تطبيقات معالجة المستندات
description: تعرف على كيفية الحصول على مجموعة من صفحات JPEG باستخدام Aspose.Words لـ .NET. البرنامج التعليمي الكامل لاستخراج الصور المخصصة.
type: docs
weight: 10
url: /ar/net/programming-with-imagesaveoptions/get-jpeg-page-range/
---

في هذا البرنامج التعليمي، سوف نستكشف كود مصدر C# المقدم لميزة "الحصول على نطاق صفحات JPEG" مع Aspose.Words for .NET. تتيح لك هذه الميزة تحويل نطاق معين من صفحات المستند إلى صور بتنسيق JPEG.

## الخطوة 1: تهيئة البيئة

قبل أن تبدأ، تأكد من إعداد بيئة التطوير الخاصة بك باستخدام Aspose.Words for .NET. تأكد من إضافة المراجع الضرورية واستيراد مساحات الأسماء المناسبة.

## الخطوة 2: تحميل الوثيقة

```csharp
// المسار إلى دليل المستندات الخاص بك
string dataDir = "YOUR DOCUMENTS DIRECTORY";

Document doc = new Document(dataDir + "Rendering.docx");
```

 في هذه الخطوة نقوم بتحميل المستند باستخدام ملف`Document` الطريقة وتمرير المسار إلى ملف DOCX للتحميل.

## الخطوة 3: تكوين خيارات النسخ الاحتياطي للصورة

```csharp
ImageSaveOptions options = new ImageSaveOptions(SaveFormat.Jpeg);
options. PageSet = new PageSet(0);
options. ImageBrightness = 0.3f;
options. ImageContrast = 0.7f;
options. HorizontalResolution = 72f;
```

 في هذه الخطوة، نقوم بتكوين خيارات النسخ الاحتياطي للصور. نحن نخلق جديدا`ImageSaveOptions` كائن يحدد تنسيق الحفظ المطلوب، هنا "Jpeg" لتنسيق JPEG. قمنا أيضًا بتعيين نطاق الصفحات المراد تحويلها باستخدام ملف`PageSet`هدف. وأخيرا، نقوم بضبط سطوع الصورة وتباينها باستخدام`ImageBrightness`و`ImageContrast` الخصائص، على التوالي. نقوم أيضًا بتغيير الدقة الأفقية باستخدام`HorizontalResolution` ملكية.

## الخطوة 4: النسخ الاحتياطي للصور

```csharp
doc.Save(dataDir + "WorkingWithImageSaveOptions.GetJpegPageRange.jpeg", options);
```

 في هذه الخطوة الأخيرة، نقوم بحفظ الصور الخاصة بنطاق الصفحات المحدد بتنسيق JPEG باستخدام الملف`Save` الطريقة وتمرير المسار إلى ملف الإخراج، إلى جانب خيارات الحفظ المحددة.

يمكنك الآن تشغيل التعليمات البرمجية المصدر لتحويل نطاق معين من الصفحات في مستندك إلى صور JPEG. سيتم حفظ الملف الناتج في الدليل المحدد بالاسم "WorkingWithImageSaveOptions.GetJpegPageRange.jpeg".

### نموذج التعليمات البرمجية المصدر للحصول على نطاق صفحات Jpeg باستخدام Aspose.Words For .NET

```csharp 
 // المسار إلى دليل المستندات الخاص بك
 string dataDir = "YOUR DOCUMENT DIRECTORY"; 

Document doc = new Document(dataDir + "Rendering.docx");

ImageSaveOptions options = new ImageSaveOptions(SaveFormat.Jpeg);

// اضبط "PageSet" على "0" لتحويل الصفحة الأولى فقط من المستند.
options.PageSet = new PageSet(0);

// تغيير سطوع الصورة والتباين.
// كلاهما على مقياس 0-1 ويكون عند 0.5 بشكل افتراضي.
options.ImageBrightness = 0.3f;
options.ImageContrast = 0.7f;

// تغيير الدقة الأفقية.
// القيمة الافتراضية لهذه الخصائص هي 96.0، لدقة تبلغ 96 نقطة في البوصة.
options.HorizontalResolution = 72f;

doc.Save(dataDir + "WorkingWithImageSaveOptions.GetJpegPageRange.jpeg", options);
            
        
```

## خاتمة

في هذا البرنامج التعليمي، اكتشفنا وظيفة الحصول على نطاق صفحات JPEG باستخدام Aspose.Words لـ .NET. لقد تعلمنا كيفية تحويل نطاق معين من صفحات المستند إلى صور بتنسيق JPEG، مع تخصيص خيارات الحفظ.

تكون هذه الميزة مفيدة عندما تريد استخراج صفحات معينة من مستند وحفظها كصور JPEG. يمكنك أيضًا ضبط السطوع والتباين والدقة الأفقية للصور لتحقيق نتائج مخصصة.

يقدم Aspose.Words for .NET نطاقًا واسعًا من الميزات المتقدمة لمعالجة المستندات وإنشائها. يعد الحصول على نطاق صفحات JPEG أحد الأدوات القوية العديدة التي يضعها تحت تصرفك.

لا تتردد في دمج هذه الميزة في Aspose.Words لمشروعات .NET الخاصة بك للحصول على صور JPEG عالية الجودة من مستنداتك.