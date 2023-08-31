---
title: ضبط مستوى الضغط
linktitle: ضبط مستوى الضغط
second_title: Aspose.Words واجهة برمجة تطبيقات معالجة المستندات
description: تعرف على كيفية ضبط مستوى الضغط عند حفظ مستند باستخدام Aspose.Words لـ .NET.
type: docs
weight: 10
url: /ar/net/programming-with-ooxmlsaveoptions/set-compression-level/
---
في هذا البرنامج التعليمي، سوف نستكشف التعليمات البرمجية المصدر لـ C# المتوفرة لتعيين مستوى الضغط عند حفظ مستند باستخدام Aspose.Words for .NET. تتيح لك هذه الميزة التحكم في مستوى ضغط المستند الذي تم إنشاؤه.

## الخطوة 1: تهيئة البيئة

قبل أن تبدأ، تأكد من إعداد بيئة التطوير الخاصة بك باستخدام Aspose.Words for .NET. تأكد من إضافة المراجع الضرورية واستيراد مساحات الأسماء المناسبة.

## الخطوة 2: تحميل الوثيقة

```csharp
// المسار إلى دليل المستندات الخاص بك
string dataDir = "YOUR DOCUMENTS DIRECTORY";

Document doc = new Document(dataDir + "Document.docx");
```

 في هذه الخطوة نقوم بتحميل المستند باستخدام ملف`Document` الطريقة وتمرير المسار إلى ملف DOCX للتحميل.

## الخطوة 3: تكوين خيارات النسخ الاحتياطي لـ OOXML

```csharp
OoxmlSaveOptions saveOptions = new OoxmlSaveOptions { CompressionLevel = CompressionLevel.SuperFast };
```

 في هذه الخطوة، نقوم بتكوين خيارات حفظ OOXML باستخدام ملف`OoxmlSaveOptions` فصل. قمنا بضبط مستوى الضغط على`SuperFast` للحصول على ضغط أسرع.

## الخطوة 4: احفظ المستند بمستوى الضغط المحدد

```csharp
doc.Save(dataDir + "WorkingWithOoxmlSaveOptions.SetCompressionLevel.docx", saveOptions);
```

 في هذه الخطوة الأخيرة، نقوم بحفظ المستند باستخدام الملف`Save` الطريقة وتمرير المسار إلى ملف الإخراج باستخدام الملف`.docx` الملحق، إلى جانب خيارات الحفظ المحددة.

يمكنك الآن تشغيل التعليمات البرمجية المصدر لتعيين مستوى الضغط عند حفظ مستند. سيتم حفظ الملف الناتج في الدليل المحدد بالاسم "WorkingWithOoxmlSaveOptions.SetCompressionLevel.docx".

### نموذج التعليمات البرمجية المصدر لتعيين مستوى الضغط باستخدام Aspose.Words لـ .NET 

```csharp

//المسار إلى دليل المستندات الخاص بك
string dataDir = "YOUR DOCUMENT DIRECTORY"; 
 
Document doc = new Document(dataDir + "Document.docx");

OoxmlSaveOptions saveOptions = new OoxmlSaveOptions { CompressionLevel = CompressionLevel.SuperFast };

doc.Save(dataDir + "WorkingWithOoxmlSaveOptions.SetCompressionLevel.docx", saveOptions);
            
        
```

## خاتمة

في هذا البرنامج التعليمي، اكتشفنا وظيفة تحديد مستوى الضغط عند حفظ مستند باستخدام Aspose.Words for .NET. ومن خلال تحديد مستوى الضغط المناسب، يمكنك تحسين حجم المستند وسرعة الإنشاء.

 ال`OoxmlSaveOptions`توفر الفئة المرونة للتحكم في مستوى الضغط عن طريق ضبط`CompressionLevel` الممتلكات إلى قيمة مناسبة، مثل`SuperFast`. يتيح لك ذلك تحقيق التوازن الصحيح بين حجم الملف وسرعة النسخ الاحتياطي بناءً على احتياجاتك المحددة.

يمكن أن يكون استخدام الضغط مفيدًا عندما تحتاج إلى تقليل حجم الملفات التي تم إنشاؤها، خاصة بالنسبة للمستندات الكبيرة. وهذا يمكن أن يسهل تخزين المستندات ومشاركتها ونقلها.

يقدم Aspose.Words for .NET مجموعة من الخيارات والميزات القوية لمعالجة المستندات. باستخدام خيارات النسخ الاحتياطي المناسبة، يمكنك تخصيص عملية إنشاء المستندات وتحسين أداء التطبيق الخاص بك.

لا تتردد في استكشاف المزيد من ميزات Aspose.Words for .NET لتحسين سير عمل إنشاء المستندات لديك.
