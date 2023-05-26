---
title: احصل على نطاق صفحات Tiff
linktitle: احصل على نطاق صفحات Tiff
second_title: Aspose.Words لمراجع .NET API
description: تعرف على كيفية استخراج مجموعة من صفحات TIFF باستخدام Aspose.Words for .NET. البرنامج التعليمي الكامل لملفات TIFF المخصصة.
type: docs
weight: 10
url: /ar/net/programming-with-imagesaveoptions/get-tiff-page-range/
---

في هذا البرنامج التعليمي ، سوف نستكشف الكود المصدري C # المقدم للحصول على مجموعة من صفحات TIFF مع Aspose.Words for .NET. تتيح لك هذه الميزة استخراج نطاق معين من الصفحات من مستند وحفظها كملف TIFF.

## الخطوة الأولى: تهيئة البيئة

قبل أن تبدأ ، تأكد من إعداد بيئة التطوير الخاصة بك باستخدام Aspose.Words for .NET. تأكد من أنك أضفت المراجع الضرورية واستوردت مساحات الأسماء المناسبة.

## الخطوة الثانية: تحميل المستند

```csharp
// المسار إلى دليل المستندات الخاص بك
string dataDir = "YOUR DOCUMENTS DIRECTORY";

Document doc = new Document(dataDir + "Rendering.docx");
```

 في هذه الخطوة ، نقوم بتحميل المستند باستخدام ملف`Document` الطريقة وتمرير المسار إلى ملف DOCX للتحميل.

## الخطوة 3: حفظ المستند كاملاً في TIFF

```csharp
doc.Save(dataDir + "WorkingWithImageSaveOptions.MultipageTiff.tiff");
```

 في هذه الخطوة ، نحفظ المستند كاملاً بتنسيق TIFF باستخدام امتداد`Save` الطريقة وتحديد المسار إلى ملف الإخراج بالملحق`.tiff`.

## الخطوة 4: تكوين خيارات النسخ الاحتياطي لنطاق الصفحات

```csharp
ImageSaveOptions saveOptions = new ImageSaveOptions(SaveFormat.Tiff)
{
PageSet = new PageSet(new PageRange(0, 1)),
TiffCompression = TiffCompression.Ccitt4,
Resolution = 160
};
```

 في هذه الخطوة ، نقوم بتكوين خيارات النسخ الاحتياطي لنطاق الصفحات المحدد. نخلق ملف`ImageSaveOptions` كائن يحدد تنسيق الحفظ المطلوب ، هنا "Tiff" لتنسيق TIFF. نحن نستخدم`PageSet` لتحديد نطاق الصفحات التي نريد استخراجها ، هنا من الصفحة 0 إلى الصفحة 1 (ضمناً). قمنا أيضًا بتعيين ضغط TIFF على`Ccitt4` والقرار إلى 160 نقطة في البوصة.

## الخطوة 5: حفظ نطاق الصفحات في TIFF

```csharp
doc.Save(dataDir + "WorkingWithImageSaveOptions.GetTiffPageRange.tiff", saveOptions);
```

 في هذه الخطوة الأخيرة ، نحفظ نطاق الصفحات المحدد بتنسيق TIFF باستخدام امتداد`Save`الطريقة وتمرير المسار إلى ملف الإخراج بامتداد`.tiff` بالإضافة إلى خيارات الحفظ المحددة.

يمكنك الآن تشغيل التعليمات البرمجية المصدر للحصول على نطاق معين من الصفحات من المستند الخاص بك وحفظها كملف TIFF. سيتم حفظ الملفات الناتجة في الدليل المحدد بالأسماء "WorkingWithImageSaveOptions.MultipageTiff.tiff" للمستند الكامل و "WorkingWithImageSaveOptions.GetTiffPageRange.tiff" لنطاق الصفحات المحدد.

### نموذج لشفرة مصدر للحصول على نطاق صفحات Tiff باستخدام Aspose.Words for .NET

```csharp 

// المسار إلى دليل المستند الخاص بك
string dataDir = "YOUR DOCUMENT DIRECTORY"; 

Document doc = new Document(dataDir + "Rendering.docx");

doc.Save(dataDir + "WorkingWithImageSaveOptions.MultipageTiff.tiff");



ImageSaveOptions saveOptions = new ImageSaveOptions(SaveFormat.Tiff)
{
	PageSet = new PageSet(new PageRange(0, 1)), TiffCompression = TiffCompression.Ccitt4, Resolution = 160
};

doc.Save(dataDir + "WorkingWithImageSaveOptions.GetTiffPageRange.tiff", saveOptions);
            
            
        
```

## خاتمة

في هذا البرنامج التعليمي ، استكشفنا وظيفة الحصول على مجموعة من صفحات TIFF باستخدام Aspose.Words for .NET. تعلمنا كيفية استخراج نطاق معين من الصفحات من مستند وحفظها كملف TIFF.

هذه الميزة مفيدة عندما تريد استخراج صفحات معينة فقط من مستند وحفظها بتنسيق صورة قياسي مثل TIFF. يمكنك أيضًا تخصيص خيارات الضغط والدقة للحصول على أفضل جودة لملفات TIFF.

تقدم Aspose.Words for .NET مجموعة واسعة من الميزات المتقدمة لمعالجة المستندات وإنشائها. يعد الحصول على نطاق صفحات TIFF أحد الأدوات القوية العديدة التي يضعها تحت تصرفك.

لا تتردد في دمج هذه الوظيفة في مشاريع Aspose.Words for .NET لاستخراج وحفظ نطاقات محددة من الصفحات من مستنداتك بتنسيق TIFF.