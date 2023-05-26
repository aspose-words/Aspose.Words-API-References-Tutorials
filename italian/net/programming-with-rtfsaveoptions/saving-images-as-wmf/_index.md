---
title: حفظ الصور بتنسيق Wmf
linktitle: حفظ الصور بتنسيق Wmf
second_title: Aspose.Words لمراجع .NET API
description: تعرف على كيفية حفظ الصور بتنسيق WMF عند التحويل إلى RTF باستخدام Aspose.Words for .NET.
type: docs
weight: 10
url: /it/net/programming-with-rtfsaveoptions/saving-images-as-wmf/
---

في هذا البرنامج التعليمي ، سوف نستكشف كود المصدر C # المقدم لميزة "حفظ الصور كـ WMF مع خيارات حفظ RTF" مع Aspose.Words for .NET. تتيح لك هذه الميزة حفظ صور المستند بتنسيق Windows Metafile (WMF) عند التحويل إلى تنسيق RTF.

## الخطوة الأولى: تهيئة البيئة

قبل أن تبدأ ، تأكد من إعداد بيئة التطوير الخاصة بك باستخدام Aspose.Words for .NET. تأكد من أنك أضفت المراجع الضرورية واستوردت مساحات الأسماء المناسبة.

## الخطوة الثانية: تحميل المستند

```csharp
// المسار إلى دليل المستندات الخاص بك
string dataDir = "YOUR DOCUMENTS DIRECTORY";

Document doc = new Document(dataDir + "Document.docx");
```

 في هذه الخطوة ، نقوم بتحميل المستند باستخدام ملف`Document` الطريقة وتمرير المسار إلى ملف DOCX للتحميل.

## الخطوة 3: تكوين خيارات النسخ الاحتياطي

```csharp
RtfSaveOptions saveOptions = new RtfSaveOptions { SaveImagesAsWmf = true };
```

في هذه الخطوة ، نقوم بتكوين خيارات النسخ الاحتياطي لـ RTF. نخلق ملف`RtfSaveOptions` كائن وتعيين`SaveImagesAsWmf` ملكية ل`true`. هذا يخبر Aspose.Words بحفظ صور الوثيقة بصيغة WMF عند التحويل إلى RTF.

## الخطوة 4: حفظ المستند

```csharp
doc.Save(dataDir + "WorkingWithRtfSaveOptions.SavingImagesAsWmf.rtf", saveOptions);
```

 في هذه الخطوة الأخيرة ، نقوم بحفظ المستند الناتج بتنسيق RTF باستخدام ملف`Save` الطريقة وتمرير المسار إلى ملف الإخراج ، جنبًا إلى جنب مع خيارات الحفظ المحددة.

يمكنك الآن تشغيل التعليمات البرمجية المصدر لحفظ صور المستند بتنسيق WMF أثناء التحويل إلى تنسيق RTF. سيتم حفظ المستند الناتج في الدليل المحدد باسم "WorkingWithRtfSaveOptions.SavingImagesAsWmf.rtf".

### عينة من التعليمات البرمجية المصدر لوظيفة حفظ صور WMF باستخدام خيارات حفظ RTF باستخدام Aspose.Words for .NET ".

```csharp

            
string dataDir = "YOUR DOCUMENT DIRECTORY";

Document doc = new Document(dataDir + "Document.docx");

RtfSaveOptions saveOptions = new RtfSaveOptions { SaveImagesAsWmf = true };

doc.Save(dataDir + "WorkingWithRtfSaveOptions.SavingImagesAsWmf.rtf", saveOptions);
            
        
```
## خاتمة

في هذا البرنامج التعليمي ، اكتشفنا وظيفة حفظ الصور بتنسيق WMF مع خيارات حفظ RTF في Aspose.Words for .NET. تعلمنا كيفية حفظ الصور من مستند بتنسيق WMF عند التحويل إلى تنسيق RTF.

هذه الميزة مفيدة عندما تريد الحفاظ على جودة ودقة الصور في مستندات RTF الخاصة بك. من خلال حفظ الصور بتنسيق WMF ، يمكنك التأكد من بقاء مظهرها وحدتها كما هي.

يوفر Aspose.Words for .NET العديد من الميزات المتقدمة لمعالجة المستندات وإنشائها. يعد حفظ الصور بتنسيق WMF أثناء التحويل إلى تنسيق RTF أحد الأدوات القوية العديدة التي يوفرها لك.