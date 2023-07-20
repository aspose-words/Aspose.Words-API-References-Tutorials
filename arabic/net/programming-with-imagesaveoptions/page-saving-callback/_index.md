---
title: استدعاء حفظ الصفحة
linktitle: استدعاء حفظ الصفحة
second_title: واجهة برمجة تطبيقات معالجة المستندات Aspose.Words
description: تعرف على كيفية تخصيص حفظ صفحات المستند للصور باستخدام Aspose.Words for .NET.
type: docs
weight: 10
url: /ar/net/programming-with-imagesaveoptions/page-saving-callback/
---

في هذا البرنامج التعليمي ، سوف نستكشف الكود المصدري C # المقدم لاستخدام إعادة اتصال حفظ الصفحة مع خيارات حفظ الصور Aspose.Words لـ .NET. تتيح لك هذه الميزة تنفيذ إجراءات مخصصة عند حفظ كل صفحة من المستند كصورة.

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
ImageSaveOptions imageSaveOptions = new ImageSaveOptions(SaveFormat.Png)
{
     PageSet = new PageSet(new PageRange(0, doc.PageCount - 1)),
     PageSavingCallback = new HandlePageSavingCallback()
};
```

 في هذه الخطوة ، نقوم بتكوين خيارات حفظ الصورة عن طريق إنشاء ملف`ImageSaveOptions` هدف. نحدد تنسيق النسخ الاحتياطي المطلوب ، هنا "Png" لتنسيق PNG. نحن نستخدم`PageSet` لتحديد نطاق الصفحات المراد حفظها ، هنا من الصفحة الأولى إلى الصفحة الأخيرة من المستند (`doc.PageCount - 1`). وضعنا أيضا`PageSavingCallback` إلى مثيل`HandlePageSavingCallback`، وهي فئة مخصصة للتعامل مع الصفحة حفظ رد الاتصال.

## الخطوة 4: تنفيذ رد اتصال حفظ الصفحة

```csharp
public class HandlePageSavingCallback : IPageSavingCallback
{
     public void PageSaving(PageSavingArgs args)
     {
         // تنفيذ الإجراءات المخصصة الخاصة بك هنا
         // يمكنك الوصول إلى معلومات الصفحة من خلال خاصية "args.PageIndex"
         // يمكنك أيضًا تغيير خيارات الحفظ لكل صفحة على حدة
     }
}
```

 في هذه الخطوة ، نقوم بتنفيذ`HandlePageSavingCallback` الطبقة التي تنفذ`IPageSavingCallback` واجهه المستخدم. يمكنك تخصيص هذه الفئة عن طريق إضافة إجراءات معينة في ملف`PageSaving` طريقة. يمكنك الوصول إلى معلومات الصفحة من خلال`args.PageIndex` ممتلكات`PageSavingArgs` تم تمرير الكائن كوسيطة.

## الخطوة 5: حفظ الصفحات كصور

```csharp
doc.Save(dataDir + "WorkingWithImageSaveOptions.PageSavingCallback.png", imageSaveOptions);
```

 في هذه الخطوة الأخيرة ، نقوم بحفظ كل صفحة من المستند كصورة باستخدام ملف`Save` الطريقة وتمرير المسار إلى ملف الإخراج بامتداد`.png` التمديد ، جنبًا إلى جنب مع خيارات الحفظ المحددة.

يمكنك الآن تشغيل التعليمات البرمجية المصدر لتنفيذ إجراءات مخصصة عند حفظ كل صفحة من المستند كصورة. سيتم حفظ الملف الناتج في الدليل المحدد باسم "WorkingWithImageSaveOptions.PageSavingCallback.png".

### عينة من التعليمات البرمجية المصدر لـ Page Saving Callback باستخدام Aspose.Words for .NET


```csharp 
//المسار إلى دليل المستند الخاص بك
string dataDir = "YOUR DOCUMENT DIRECTORY"; 


Document doc = new Document(dataDir + "Rendering.docx");

ImageSaveOptions imageSaveOptions = new ImageSaveOptions(SaveFormat.Png)
{
	PageSet = new PageSet(new PageRange(0, doc.PageCount - 1)),
	PageSavingCallback = new HandlePageSavingCallback()
};

doc.Save(dataDir + "WorkingWithImageSaveOptions.PageSavingCallback.png", imageSaveOptions);
        
```

## خاتمة

في هذا البرنامج التعليمي ، استكشفنا صفحة حفظ وظيفة رد الاتصال باستخدام خيارات حفظ الصور Aspose.Words لـ .NET. لقد تعلمنا كيفية تنفيذ الإجراءات المخصصة عند حفظ كل صفحة من المستند كصورة.

هذه الميزة مفيدة عندما تريد إجراء عمليات محددة على كل صفحة عند التحويل إلى الصور. يمكنك الوصول إلى معلومات الصفحة واستخدامها لتخصيص خيارات النسخ الاحتياطي أو إجراء معالجة أخرى خاصة بالصفحة.

تقدم Aspose.Words for .NET مجموعة واسعة من الميزات المتقدمة لمعالجة المستندات وإنشائها. يعد تذكير حفظ الصفحة واحدًا من العديد من الأدوات القوية التي يوفرها لك لتخصيص عملية حفظ الصفحات في الصور.