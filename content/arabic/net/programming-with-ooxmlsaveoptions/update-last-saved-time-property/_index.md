---
title: تحديث خاصية الوقت المحفوظ الأخير
linktitle: تحديث خاصية الوقت المحفوظ الأخير
second_title: Aspose.Words واجهة برمجة تطبيقات معالجة المستندات
description: تعرف على كيفية تحديث خاصية آخر وقت تم حفظه تلقائيًا عند حفظ مستند باستخدام Aspose.Words for .NET.
type: docs
weight: 10
url: /ar/net/programming-with-ooxmlsaveoptions/update-last-saved-time-property/
---
في هذا البرنامج التعليمي، سوف نستكشف كود مصدر C# المقدم لتحديث خاصية توفير الوقت الأخيرة عند حفظ مستند باستخدام Aspose.Words for .NET. تسمح لك هذه الميزة بالتحديث التلقائي لخاصية توفير الوقت الأخيرة للمستند الذي تم إنشاؤه.

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
OoxmlSaveOptions saveOptions = new OoxmlSaveOptions { UpdateLastSavedTimeProperty = true };
```

 في هذه الخطوة، نقوم بتكوين خيارات حفظ OOXML باستخدام ملف`OoxmlSaveOptions` فصل. نقوم بتمكين التحديث التلقائي لخاصية توفير الوقت الأخيرة من خلال الإعداد`UpdateLastSavedTimeProperty` ل`true`.

## الخطوة 4: احفظ المستند بالخاصية المحدثة

```csharp
doc.Save(dataDir + "WorkingWithOoxmlSaveOptions.UpdateLastSavedTimeProperty.docx", saveOptions);
```

 في هذه الخطوة الأخيرة، نقوم بحفظ المستند باستخدام الملف`Save` الطريقة وتمرير المسار إلى ملف الإخراج باستخدام الملف`.docx` الملحق، إلى جانب خيارات الحفظ المحددة.

يمكنك الآن تشغيل التعليمات البرمجية المصدر لتحديث خاصية توفير الوقت الأخيرة تلقائيًا عند حفظ مستند. سيتم حفظ الملف الناتج في الدليل المحدد بالاسم "WorkingWithOoxmlSaveOptions.UpdateLastSavedTimeProperty.docx".

### نموذج التعليمات البرمجية المصدر لخاصية تحديث آخر وقت محفوظ باستخدام Aspose.Words لـ .NET 

```csharp

// المسار إلى دليل المستندات الخاص بك
string dataDir = "YOUR DOCUMENT DIRECTORY"; 

Document doc = new Document(dataDir + "Document.docx");

OoxmlSaveOptions saveOptions = new OoxmlSaveOptions { UpdateLastSavedTimeProperty = true };

doc.Save(dataDir + "WorkingWithOoxmlSaveOptions.UpdateLastSavedTimeProperty.docx", saveOptions);
            
        
```

## خاتمة

في هذا البرنامج التعليمي، اكتشفنا ميزة التحديث التلقائي لخاصية توفير الوقت الأخير عند حفظ مستند باستخدام Aspose.Words for .NET. من خلال تمكين هذه الميزة مع خيارات حفظ OOXML، يمكنك التأكد من تحديث خاصية حفظ الوقت الأخيرة تلقائيًا في المستند الذي تم إنشاؤه.

يمكن أن يكون تحديث خاصية توفير الوقت الأخير مفيدًا لتتبع التغييرات وإصدارات المستند. كما أنه يتتبع آخر مرة تم فيها حفظ المستند، وهو ما قد يكون مفيدًا في سيناريوهات مختلفة.

يسهّل Aspose.Words for .NET تحديث خاصية Last Backup Time تلقائيًا من خلال توفير خيارات نسخ احتياطي مرنة وقوية. يمكنك دمج هذه الميزة في مشاريعك للتأكد من أن المستندات التي تم إنشاؤها تحتوي على معلومات نسخ احتياطي دقيقة.