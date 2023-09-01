---
title: تنسيق 1Bpp مفهرسة
linktitle: تنسيق 1Bpp مفهرسة
second_title: Aspose.Words واجهة برمجة تطبيقات معالجة المستندات
description: تعرف على كيفية تنسيق الصور بمعدل 1 نقطة في الثانية مفهرسة باستخدام Aspose.Words لـ .NET. برنامج تعليمي كامل للصور ذات عمق الألوان المنخفض.
type: docs
weight: 10
url: /ar/net/programming-with-imagesaveoptions/format-1bpp-indexed/
---
في هذا البرنامج التعليمي، سوف نستكشف كود مصدر C# المقدم لوظيفة "تنسيق 1Bpp Indexed" مع Aspose.Words for .NET. تتيح لك هذه الميزة تنسيق الصور في مستند بتنسيق PNG بعمق ألوان يبلغ 1 بت لكل بكسل (1 bpp) ووضع ألوان مفهرس.

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
ImageSaveOptions saveOptions = new ImageSaveOptions(SaveFormat.Png)
{
     PageSet = new PageSet(1),
     ImageColorMode = ImageColorMode.BlackAndWhite,
     PixelFormat = ImagePixelFormat.Format1bppIndexed
};
```

 في هذه الخطوة، نقوم بتكوين خيارات النسخ الاحتياطي للصور. نحن نخلق جديدا`ImageSaveOptions`كائن يحدد تنسيق الحفظ المطلوب، هنا "Png" لتنسيق PNG. نحدد أيضًا الصفحة المراد تضمينها في الصورة، ووضع الألوان بالأبيض والأسود وتنسيق 1 بكسل لكل نقطة في البوصة المفهرس.

## الخطوة 4: النسخ الاحتياطي للصور

```csharp
doc.Save(dataDir + "WorkingWithImageSaveOptions.Format1BppIndexed.Png", saveOptions);
```

 في هذه الخطوة الأخيرة، نقوم بحفظ صور المستند بتنسيق PNG باستخدام الملف`Save` الطريقة وتمرير المسار إلى ملف الإخراج، إلى جانب خيارات الحفظ المحددة.

يمكنك الآن تشغيل التعليمات البرمجية المصدر لتنسيق صور المستندات بتنسيق PNG بعمق ألوان مفهرس يبلغ 1 bpp. سيتم حفظ الملف الناتج في الدليل المحدد بالاسم "WorkingWithImageSaveOptions.Format1BppIndexed.Png".

### نموذج التعليمات البرمجية المصدر للتنسيق 1Bpp المفهرس باستخدام Aspose.Words لـ .NET

```csharp 
 
			 // المسار إلى دليل المستندات الخاص بك
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

في هذا البرنامج التعليمي، اكتشفنا ميزة التنسيق المفهرس 1Bpp باستخدام Aspose.Words لـ .NET. لقد تعلمنا كيفية تنسيق الصور في مستند بتنسيق PNG بعمق ألوان يبلغ 1 بت لكل بكسل (1 bpp) ووضع ألوان مفهرس.

تكون هذه الميزة مفيدة عندما تريد الحصول على صور ذات عمق ألوان منخفض وحجم ملف صغير. يسمح التنسيق المفهرس 1Bpp بتمثيل الصور باستخدام لوحة ألوان مفهرسة، والتي يمكن أن تكون مفيدة لبعض التطبيقات المحددة.

يقدم Aspose.Words for .NET نطاقًا واسعًا من الميزات المتقدمة لمعالجة المستندات وإنشائها. يعد تنسيق 1Bpp المفهرس أحد الأدوات القوية العديدة التي يضعها تحت تصرفك.