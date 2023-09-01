---
title: احتفظ بأحرف التحكم القديمة
linktitle: احتفظ بأحرف التحكم القديمة
second_title: Aspose.Words واجهة برمجة تطبيقات معالجة المستندات
description: تعرف على كيفية الحفاظ على أحرف التحكم القديمة عند حفظ مستند باستخدام Aspose.Words لـ .NET.
type: docs
weight: 10
url: /ar/net/programming-with-ooxmlsaveoptions/keep-legacy-control-chars/
---

في هذا البرنامج التعليمي، سنستكشف التعليمات البرمجية المصدر لـ C# المتوفرة للحفاظ على أحرف التحكم القديمة عند حفظ مستند باستخدام Aspose.Words for .NET. تتيح لك هذه الميزة الاحتفاظ بأحرف التحكم الخاصة عند تحويل مستند أو حفظه.

## الخطوة 1: تهيئة البيئة

قبل أن تبدأ، تأكد من إعداد بيئة التطوير الخاصة بك باستخدام Aspose.Words for .NET. تأكد من إضافة المراجع الضرورية واستيراد مساحات الأسماء المناسبة.

## الخطوة 2: تحميل الوثيقة

```csharp
// المسار إلى دليل المستندات الخاص بك
string dataDir = "YOUR DOCUMENTS DIRECTORY";

Document doc = new Document(dataDir + "Legacy control character.doc");
```

 في هذه الخطوة نقوم بتحميل المستند باستخدام ملف`Document` الطريقة وتمرير المسار إلى الملف الذي يحتوي على أحرف التحكم الموروثة.

## الخطوة 3: تكوين خيارات النسخ الاحتياطي لـ OOXML

```csharp
OoxmlSaveOptions saveOptions = new OoxmlSaveOptions(SaveFormat.FlatOpc) { KeepLegacyControlChars = true };
```

في هذه الخطوة، نقوم بتكوين خيارات حفظ OOXML عن طريق إنشاء ملف جديد`OoxmlSaveOptions`هدف. نحدد تنسيق الحفظ المطلوب (هنا،`FlatOpc` ) وتمكين`KeepLegacyControlChars` خيار الاحتفاظ بأحرف التحكم القديمة.

## الخطوة 4: حفظ المستند بأحرف التحكم القديمة

```csharp
doc.Save(dataDir + "WorkingWithOoxmlSaveOptions.KeepLegacyControlChars.docx", saveOptions);
```

 في هذه الخطوة الأخيرة، نقوم بحفظ المستند باستخدام الملف`Save` الطريقة وتمرير المسار إلى ملف الإخراج باستخدام الملف`.docx` الملحق، إلى جانب خيارات الحفظ المحددة.

يمكنك الآن تشغيل التعليمات البرمجية المصدر للحفاظ على أحرف التحكم القديمة عند حفظ مستند. سيتم حفظ الملف الناتج في الدليل المحدد بالاسم "WorkingWithOoxmlSaveOptions.KeepLegacyControlChars.docx".

### نموذج التعليمات البرمجية المصدر للاحتفاظ بأحرف التحكم القديمة باستخدام Aspose.Words لـ .NET 
```csharp

// المسار إلى دليل المستندات الخاص بك
string dataDir = "YOUR DOCUMENT DIRECTORY"; 

Document doc = new Document(dataDir + "Legacy control character.doc");

OoxmlSaveOptions saveOptions = new OoxmlSaveOptions(SaveFormat.FlatOpc) { KeepLegacyControlChars = true };

doc.Save(dataDir + "WorkingWithOoxmlSaveOptions.KeepLegacyControlChars.docx", saveOptions);
            
        
```

## خاتمة

في هذا البرنامج التعليمي، اكتشفنا وظيفة الحفاظ على أحرف التحكم القديمة عند حفظ مستند باستخدام Aspose.Words for .NET. لقد تعلمنا كيفية الحفاظ على تلك الأحرف الخاصة التي قد تكون مهمة لتنسيق المستند أو عرضه بشكل صحيح.

 يعد الحفاظ على أحرف التحكم القديمة مفيدًا بشكل خاص عند معالجة الكلمات مع المستندات التي تستخدم ميزات قديمة أو محددة، مثل أحرف التحكم الخاصة. من خلال تمكين`KeepLegacyControlChars`الخيار عند حفظ المستند، فإنك تتأكد من الحفاظ على هذه الأحرف.

يوفر Aspose.Words for .NET مجموعة من خيارات النسخ الاحتياطي المرنة والقوية لتلبية احتياجات معالجة المستندات الخاصة بك. باستخدام الخيارات المناسبة، يمكنك تخصيص عملية النسخ الاحتياطي للحفاظ على الخصائص المحددة لمستنداتك.

لا تتردد في دمج هذه الوظيفة في مشروعات Aspose.Words for .NET الخاصة بك لضمان سلامة أحرف التحكم القديمة والحفاظ عليها في مستنداتك.