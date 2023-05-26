---
title: تنسيق 1Bpp مفهرس
linktitle: تنسيق 1Bpp مفهرس
second_title: Aspose.Words لمراجع .NET API
description: تعرف على كيفية تنسيق الصور في 1 bpp مفهرسة باستخدام Aspose.Words for .NET. البرنامج التعليمي الكامل للصور ذات عمق الألوان المنخفض.
type: docs
weight: 10
url: /ar/net/programming-with-imagesaveoptions/format-1bpp-indexed/
---
في هذا البرنامج التعليمي ، سوف نستكشف كود المصدر C # المقدم لوظيفة "التنسيق 1Bpp المفهرسة" مع Aspose.Words for .NET. تتيح لك هذه الميزة تنسيق الصور في مستند بتنسيق PNG بعمق لون 1 بت لكل بكسل (1 بت لكل بكسل) ووضع ألوان مفهرسة.

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
ImageSaveOptions saveOptions = new ImageSaveOptions(SaveFormat.Png)
{
     PageSet = new PageSet(1),
     ImageColorMode = ImageColorMode.BlackAndWhite,
     PixelFormat = ImagePixelFormat.Format1bppIndexed
};
```

 في هذه الخطوة ، نقوم بتكوين خيارات النسخ الاحتياطي للصور. نخلق ملف`ImageSaveOptions`كائن يحدد تنسيق الحفظ المطلوب ، هنا "Png" لتنسيق PNG. نحدد أيضًا الصفحة المراد تضمينها في الصورة ، ووضع اللون الأسود والأبيض وتنسيق 1 bpp pixel المفهرس.

## الخطوة 4: نسخ الصور احتياطيًا

```csharp
doc.Save(dataDir + "WorkingWithImageSaveOptions.Format1BppIndexed.Png", saveOptions);
```

 في هذه الخطوة الأخيرة ، نقوم بحفظ صور المستند بتنسيق PNG باستخدام ملف`Save` الطريقة وتمرير المسار إلى ملف الإخراج ، جنبًا إلى جنب مع خيارات الحفظ المحددة.

يمكنك الآن تشغيل الكود المصدري لتنسيق صور المستند بتنسيق PNG بعمق لون 1 bpp مفهرس. سيتم حفظ الملف الناتج في الدليل المحدد باسم "WorkingWithImageSaveOptions.Format1BppIndexed.Png".

### نموذج التعليمات البرمجية المصدر لـ Format 1Bpp المفهرسة باستخدام Aspose.Words for .NET

```csharp 
 
			 // المسار إلى دليل المستند الخاص بك
			 string dataDir = "YOUR DOCUMENT DIRECTORY"; 
            
            Document doc = new Document(dataDir + "Rendering.docx");

            ImageSaveOptions saveOptions = new ImageSaveOptions(SaveFormat.Png)
            {
                PageSet = new PageSet(1),
                ImageColorMode = ImageColorMode.BlackAndWhite,
                PixelFormat = ImagePixelFormat.Format1bppIndexed
            };

            doc.Save(dataDir + "WorkingWithImageSaveOptions.Format1BppIndexed.Png", saveOptions);
            
        
```

### خاتمة

في هذا البرنامج التعليمي ، استكشفنا ميزة التنسيق المفهرس 1Bpp مع Aspose.Words for .NET. لقد تعلمنا كيفية تنسيق الصور في مستند بتنسيق PNG بعمق لون 1 بت لكل بكسل (1 بت لكل بكسل) ووضع ألوان مفهرس.

هذه الميزة مفيدة عندما تريد الحصول على صور ذات عمق ألوان منخفض وحجم ملف صغير. يسمح التنسيق المفهرس 1Bpp بتمثيل الصور باستخدام لوحة ألوان مفهرسة ، والتي يمكن أن تكون مفيدة لبعض التطبيقات المحددة.

تقدم Aspose.Words for .NET مجموعة كبيرة من الميزات المتقدمة لمعالجة المستندات وإنشائها. يعد التنسيق المفهرس 1Bpp أحد الأدوات القوية العديدة التي يضعها تحت تصرفك.