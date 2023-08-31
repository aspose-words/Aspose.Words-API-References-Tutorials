---
title: احصل على نطاق صفحات Tiff
linktitle: احصل على نطاق صفحات Tiff
second_title: Aspose.Words واجهة برمجة تطبيقات معالجة المستندات
description: تعرف على كيفية استخراج نطاق من صفحات TIFF باستخدام Aspose.Words لـ .NET. البرنامج التعليمي الكامل لملفات TIFF المخصصة.
type: docs
weight: 10
url: /ar/net/programming-with-imagesaveoptions/get-tiff-page-range/
---

في هذا البرنامج التعليمي، سوف نستكشف كود مصدر C# المقدم للحصول على مجموعة من صفحات TIFF مع Aspose.Words for .NET. تتيح لك هذه الميزة استخراج نطاق معين من الصفحات من مستند وحفظها كملف TIFF.

## الخطوة 1: تهيئة البيئة

قبل أن تبدأ، تأكد من إعداد بيئة التطوير الخاصة بك باستخدام Aspose.Words for .NET. تأكد من إضافة المراجع الضرورية واستيراد مساحات الأسماء المناسبة.

## الخطوة 2: تحميل الوثيقة

```csharp
// المسار إلى دليل المستندات الخاص بك
string dataDir = "YOUR DOCUMENTS DIRECTORY";

Document doc = new Document(dataDir + "Rendering.docx");
```

 في هذه الخطوة نقوم بتحميل المستند باستخدام ملف`Document` الطريقة وتمرير المسار إلى ملف DOCX للتحميل.

## الخطوة 3: حفظ المستند الكامل في TIFF

```csharp
doc.Save(dataDir + "WorkingWithImageSaveOptions.MultipageTiff.tiff");
```

 في هذه الخطوة، نقوم بحفظ المستند الكامل بتنسيق TIFF باستخدام ملف`Save` الطريقة وتحديد المسار إلى ملف الإخراج بالملحق`.tiff`.

## الخطوة 4: تكوين خيارات النسخ الاحتياطي لنطاق الصفحات

```csharp
ImageSaveOptions saveOptions = new ImageSaveOptions(SaveFormat.Tiff)
{
PageSet = new PageSet(new PageRange(0, 1)),
TiffCompression = TiffCompression.Ccitt4,
Resolution = 160
};
```

 في هذه الخطوة، نقوم بتكوين خيارات النسخ الاحتياطي لنطاق الصفحات المحدد. نحن نخلق جديدا`ImageSaveOptions` كائن يحدد تنسيق الحفظ المطلوب، هنا "Tiff" لتنسيق TIFF. نحن نستخدم`PageSet` لتحديد نطاق الصفحات التي نريد استخراجها، هنا من الصفحة 0 إلى الصفحة 1 (ضمناً). قمنا أيضًا بتعيين ضغط TIFF على`Ccitt4` والقرار إلى 160 نقطة في البوصة.

## الخطوة 5: حفظ نطاق الصفحات في TIFF

```csharp
doc.Save(dataDir + "WorkingWithImageSaveOptions.GetTiffPageRange.tiff", saveOptions);
```

 في هذه الخطوة الأخيرة، نقوم بحفظ نطاق الصفحات المحدد بتنسيق TIFF باستخدام الملف`Save`الطريقة وتمرير المسار إلى ملف الإخراج باستخدام`.tiff` ملحق، جنبا إلى جنب مع خيارات الحفظ المحددة.

يمكنك الآن تشغيل التعليمات البرمجية المصدر للحصول على نطاق محدد من الصفحات من مستندك وحفظها كملف TIFF. سيتم حفظ الملفات الناتجة في الدليل المحدد بالأسماء "WorkingWithImageSaveOptions.MultipageTiff.tiff" للمستند الكامل و"WorkingWithImageSaveOptions.GetTiffPageRange.tiff" لنطاق الصفحات المحدد.

### نموذج التعليمات البرمجية المصدر لـ Get Tiff Page Range باستخدام Aspose.Words لـ .NET

```csharp 

//المسار إلى دليل المستندات الخاص بك
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

في هذا البرنامج التعليمي، اكتشفنا وظيفة الحصول على مجموعة من صفحات TIFF باستخدام Aspose.Words لـ .NET. لقد تعلمنا كيفية استخراج نطاق معين من الصفحات من مستند وحفظها كملف TIFF.

تكون هذه الميزة مفيدة عندما تريد استخراج صفحات معينة فقط من مستند وحفظها بتنسيق صورة قياسي مثل TIFF. يمكنك أيضًا تخصيص خيارات الضغط والدقة للحصول على ملفات TIFF بأفضل جودة.

يقدم Aspose.Words for .NET نطاقًا واسعًا من الميزات المتقدمة لمعالجة المستندات وإنشائها. يعد الحصول على نطاق صفحات TIFF أحد الأدوات القوية العديدة التي يضعها تحت تصرفك.

لا تتردد في دمج هذه الوظيفة في مشاريع Aspose.Words for .NET الخاصة بك لاستخراج وحفظ نطاقات محددة من الصفحات من مستنداتك بتنسيق TIFF.