---
title: الحفاظ على أحرف التحكم القديمة
linktitle: الحفاظ على أحرف التحكم القديمة
second_title: Aspose.Words لمراجع .NET API
description: تعرف على كيفية الاحتفاظ بأحرف التحكم القديمة عند حفظ مستند باستخدام Aspose.Words for .NET.
type: docs
weight: 10
url: /sv/net/programming-with-ooxmlsaveoptions/keep-legacy-control-chars/
---

في هذا البرنامج التعليمي ، سوف نستكشف الكود المصدري C # المقدم للاحتفاظ بأحرف التحكم القديمة عند حفظ مستند باستخدام Aspose.Words for .NET. تتيح لك هذه الميزة الاحتفاظ بأحرف تحكم خاصة عند تحويل مستند أو حفظه.

## الخطوة الأولى: تهيئة البيئة

قبل أن تبدأ ، تأكد من إعداد بيئة التطوير الخاصة بك باستخدام Aspose.Words for .NET. تأكد من أنك أضفت المراجع الضرورية واستوردت مساحات الأسماء المناسبة.

## الخطوة الثانية: تحميل المستند

```csharp
// المسار إلى دليل المستندات الخاص بك
string dataDir = "YOUR DOCUMENTS DIRECTORY";

Document doc = new Document(dataDir + "Legacy control character.doc");
```

 في هذه الخطوة ، نقوم بتحميل المستند باستخدام ملف`Document` الطريقة وتمرير المسار إلى الملف الذي يحتوي على أحرف التحكم الموروثة.

## الخطوة 3: تكوين خيارات النسخ الاحتياطي لـ OOXML

```csharp
OoxmlSaveOptions saveOptions = new OoxmlSaveOptions(SaveFormat.FlatOpc) { KeepLegacyControlChars = true };
```

في هذه الخطوة ، نقوم بتهيئة خيارات حفظ OOXML عن طريق إنشاء ملف`OoxmlSaveOptions`هدف. نحدد تنسيق الحفظ المطلوب (هنا ،`FlatOpc` ) وتمكين`KeepLegacyControlChars` خيار للحفاظ على شخصيات التحكم القديمة.

## الخطوة 4: حفظ المستند بأحرف تحكم قديمة

```csharp
doc.Save(dataDir + "WorkingWithOoxmlSaveOptions.KeepLegacyControlChars.docx", saveOptions);
```

 في هذه الخطوة الأخيرة ، نحفظ المستند باستخدام ملف`Save` الطريقة وتمرير المسار إلى ملف الإخراج بامتداد`.docx` بالإضافة إلى خيارات الحفظ المحددة.

يمكنك الآن تشغيل التعليمات البرمجية المصدر للحفاظ على أحرف التحكم القديمة عند حفظ مستند. سيتم حفظ الملف الناتج في الدليل المحدد باسم "WorkingWithOoxmlSaveOptions.KeepLegacyControlChars.docx".

### عينة من التعليمات البرمجية المصدر لـ Keep Legacy Control Chars باستخدام Aspose.Words for .NET 
```csharp

// المسار إلى دليل المستند الخاص بك
string dataDir = "YOUR DOCUMENT DIRECTORY"; 

Document doc = new Document(dataDir + "Legacy control character.doc");

OoxmlSaveOptions saveOptions = new OoxmlSaveOptions(SaveFormat.FlatOpc) { KeepLegacyControlChars = true };

doc.Save(dataDir + "WorkingWithOoxmlSaveOptions.KeepLegacyControlChars.docx", saveOptions);
            
        
```

## خاتمة

في هذا البرنامج التعليمي ، استكشفنا وظيفة الاحتفاظ بأحرف التحكم القديمة عند حفظ مستند باستخدام Aspose.Words for .NET. لقد تعلمنا كيفية الحفاظ على تلك الأحرف الخاصة التي قد تكون مهمة لتنسيق المستند أو عرضه بشكل صحيح.

 يعد الاحتفاظ بأحرف التحكم القديمة مفيدًا بشكل خاص عند العمل مع المستندات التي تستخدم ميزات قديمة أو محددة ، مثل أحرف التحكم الخاصة. من خلال تمكين`KeepLegacyControlChars`الخيار عند حفظ المستند ، فإنك تضمن الحفاظ على هذه الأحرف.

يوفر Aspose.Words for .NET مجموعة من خيارات النسخ الاحتياطي المرنة والقوية لتلبية احتياجات معالجة المستندات الخاصة بك. باستخدام الخيارات المناسبة ، يمكنك تخصيص عملية النسخ الاحتياطي للحفاظ على الخصائص المحددة لمستنداتك.

لا تتردد في دمج هذه الوظيفة في مشاريع Aspose.Words for .NET لضمان تكامل أحرف التحكم القديمة والحفاظ عليها في مستنداتك.