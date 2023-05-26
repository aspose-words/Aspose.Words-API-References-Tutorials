---
title: اضبط مستوى الضغط
linktitle: اضبط مستوى الضغط
second_title: Aspose.Words لمراجع .NET API
description: تعرف على كيفية تعيين مستوى الضغط عند حفظ مستند باستخدام Aspose.Words for .NET.
type: docs
weight: 10
url: /zh/net/programming-with-ooxmlsaveoptions/set-compression-level/
---
في هذا البرنامج التعليمي ، سوف نستكشف كود المصدر C # المقدم لضبط مستوى الضغط عند حفظ مستند باستخدام Aspose.Words for .NET. تتيح لك هذه الميزة التحكم في مستوى ضغط المستند الذي تم إنشاؤه.

## الخطوة الأولى: تهيئة البيئة

قبل أن تبدأ ، تأكد من إعداد بيئة التطوير الخاصة بك باستخدام Aspose.Words for .NET. تأكد من أنك أضفت المراجع الضرورية واستوردت مساحات الأسماء المناسبة.

## الخطوة الثانية: تحميل المستند

```csharp
// المسار إلى دليل المستندات الخاص بك
string dataDir = "YOUR DOCUMENTS DIRECTORY";

Document doc = new Document(dataDir + "Document.docx");
```

 في هذه الخطوة ، نقوم بتحميل المستند باستخدام ملف`Document` الطريقة وتمرير المسار إلى ملف DOCX للتحميل.

## الخطوة 3: تكوين خيارات النسخ الاحتياطي لـ OOXML

```csharp
OoxmlSaveOptions saveOptions = new OoxmlSaveOptions { CompressionLevel = CompressionLevel.SuperFast };
```

 في هذه الخطوة ، نقوم بتهيئة خيارات حفظ OOXML باستخدام امتداد`OoxmlSaveOptions` فصل. قمنا بتعيين مستوى الضغط على`SuperFast` للحصول على ضغط أسرع.

## الخطوة 4: احفظ المستند بمستوى الضغط المحدد

```csharp
doc.Save(dataDir + "WorkingWithOoxmlSaveOptions.SetCompressionLevel.docx", saveOptions);
```

 في هذه الخطوة الأخيرة ، نحفظ المستند باستخدام ملف`Save` الطريقة وتمرير المسار إلى ملف الإخراج بامتداد`.docx` بالإضافة إلى خيارات الحفظ المحددة.

يمكنك الآن تشغيل التعليمات البرمجية المصدر لضبط مستوى الضغط عند حفظ مستند. سيتم حفظ الملف الناتج في الدليل المحدد باسم "WorkingWithOoxmlSaveOptions.SetCompressionLevel.docx".

### نموذج التعليمات البرمجية المصدر لـ Set Compression Level باستخدام Aspose.Words for .NET 

```csharp

// المسار إلى دليل المستند الخاص بك
string dataDir = "YOUR DOCUMENT DIRECTORY"; 
 
Document doc = new Document(dataDir + "Document.docx");

OoxmlSaveOptions saveOptions = new OoxmlSaveOptions { CompressionLevel = CompressionLevel.SuperFast };

doc.Save(dataDir + "WorkingWithOoxmlSaveOptions.SetCompressionLevel.docx", saveOptions);
            
        
```

## خاتمة

في هذا البرنامج التعليمي ، استكشفنا وظيفة تعيين مستوى الضغط عند حفظ مستند باستخدام Aspose.Words for .NET. من خلال تحديد المستوى المناسب للضغط ، يمكنك تحسين حجم المستند وسرعة الإنشاء.

 ال`OoxmlSaveOptions`يوفر class المرونة للتحكم في مستوى الضغط عن طريق تعيين`CompressionLevel` إلى قيمة مناسبة ، مثل`SuperFast`. يتيح لك ذلك تحقيق التوازن الصحيح بين حجم الملف وسرعة النسخ الاحتياطي بناءً على احتياجاتك الخاصة.

يمكن أن يكون استخدام الضغط مفيدًا عندما تحتاج إلى تقليل حجم الملفات التي تم إنشاؤها ، خاصةً للمستندات الكبيرة. يمكن أن يؤدي ذلك إلى تسهيل تخزين المستندات ومشاركتها ونقلها.

يوفر Aspose.Words for .NET مجموعة من الخيارات والميزات القوية لمعالجة المستندات. باستخدام خيارات النسخ الاحتياطي المناسبة ، يمكنك تخصيص عملية إنشاء المستندات وتحسين أداء تطبيقك.

لا تتردد في استكشاف المزيد من ميزات Aspose.Words for .NET لتحسين سير عمل إنشاء المستندات.
