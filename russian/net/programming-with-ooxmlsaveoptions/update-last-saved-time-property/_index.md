---
title: تحديث خاصية الوقت المحفوظ الأخير
linktitle: تحديث خاصية الوقت المحفوظ الأخير
second_title: Aspose.Words لمراجع .NET API
description: تعرف على كيفية تحديث خاصية Last Saved Time تلقائيًا عند حفظ مستند باستخدام Aspose.Words for .NET.
type: docs
weight: 10
url: /ru/net/programming-with-ooxmlsaveoptions/update-last-saved-time-property/
---
في هذا البرنامج التعليمي ، سوف نستكشف كود المصدر C # المقدم لتحديث خاصية وقت الحفظ الأخيرة عند حفظ مستند باستخدام Aspose.Words for .NET. تتيح لك هذه الميزة تحديث خاصية وقت الحفظ الأخيرة للمستند الذي تم إنشاؤه تلقائيًا.

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
OoxmlSaveOptions saveOptions = new OoxmlSaveOptions { UpdateLastSavedTimeProperty = true };
```

 في هذه الخطوة ، نقوم بتهيئة خيارات حفظ OOXML باستخدام امتداد`OoxmlSaveOptions` فصل. نقوم بتمكين التحديث التلقائي لآخر خاصية توفير الوقت من خلال الإعداد`UpdateLastSavedTimeProperty` ل`true`.

## الخطوة 4: احفظ المستند بخاصية محدثة

```csharp
doc.Save(dataDir + "WorkingWithOoxmlSaveOptions.UpdateLastSavedTimeProperty.docx", saveOptions);
```

 في هذه الخطوة الأخيرة ، نحفظ المستند باستخدام ملف`Save` الطريقة وتمرير المسار إلى ملف الإخراج بامتداد`.docx` بالإضافة إلى خيارات الحفظ المحددة.

يمكنك الآن تشغيل التعليمات البرمجية المصدر لتحديث خاصية وقت الحفظ الأخيرة تلقائيًا عند حفظ مستند. سيتم حفظ الملف الناتج في الدليل المحدد بالاسم "WorkingWithOoxmlSaveOptions.UpdateLastSavedTimeProperty.docx".

### نموذج شفرة مصدر لتحديث خاصية آخر وقت تم توفيره باستخدام Aspose.Words for .NET 

```csharp

// المسار إلى دليل المستند الخاص بك
string dataDir = "YOUR DOCUMENT DIRECTORY"; 

Document doc = new Document(dataDir + "Document.docx");

OoxmlSaveOptions saveOptions = new OoxmlSaveOptions { UpdateLastSavedTimeProperty = true };

doc.Save(dataDir + "WorkingWithOoxmlSaveOptions.UpdateLastSavedTimeProperty.docx", saveOptions);
            
        
```

## خاتمة

في هذا البرنامج التعليمي ، استكشفنا ميزة التحديث التلقائي لخاصية توفير الوقت الأخيرة عند حفظ مستند باستخدام Aspose.Words for .NET. من خلال تمكين هذه الميزة مع خيارات حفظ OOXML ، يمكنك التأكد من تحديث خاصية وقت الحفظ الأخيرة تلقائيًا في المستند الذي تم إنشاؤه.

يمكن أن يكون تحديث خاصية وقت الحفظ الأخير مفيدًا لتعقب التغييرات وإصدارات المستند. كما أنه يتتبع آخر مرة تم فيها حفظ المستند ، مما قد يكون مفيدًا في سيناريوهات مختلفة.

يجعل Aspose.Words for .NET من السهل تحديث خاصية Last Backup Time تلقائيًا من خلال توفير خيارات نسخ احتياطي مرنة وفعالة. يمكنك دمج هذه الميزة في مشاريعك لضمان احتواء المستندات التي تم إنشاؤها على معلومات نسخ احتياطي دقيقة.