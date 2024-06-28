---
title: رد الاتصال بحفظ الصفحة
linktitle: رد الاتصال بحفظ الصفحة
second_title: Aspose.Words واجهة برمجة تطبيقات معالجة المستندات
description: تعرف على كيفية تخصيص حفظ صفحات المستندات إلى صور باستخدام Aspose.Words لـ .NET.
type: docs
weight: 10
url: /ar/net/programming-with-imagesaveoptions/page-saving-callback/
---

في هذا البرنامج التعليمي، سوف نستكشف التعليمات البرمجية المصدر لـ C# المتوفرة لاستخدام رد الاتصال بحفظ الصفحة مع خيارات حفظ الصور Aspose.Words لـ .NET. تتيح لك هذه الميزة تنفيذ إجراءات مخصصة عند حفظ كل صفحة من المستند كصورة.

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
ImageSaveOptions imageSaveOptions = new ImageSaveOptions(SaveFormat.Png)
{
     PageSet = new PageSet(new PageRange(0, doc.PageCount - 1)),
     PageSavingCallback = new HandlePageSavingCallback()
};
```

 في هذه الخطوة، نقوم بتكوين خيارات حفظ الصورة عن طريق إنشاء ملف جديد`ImageSaveOptions` هدف. نحدد تنسيق النسخ الاحتياطي المطلوب، هنا "Png" لتنسيق PNG. نحن نستخدم`PageSet` لتحديد نطاق الصفحات المراد حفظها، هنا من الصفحة الأولى إلى الصفحة الأخيرة من المستند (`doc.PageCount - 1`). نحن أيضا نضع`PageSavingCallback` إلى مثال`HandlePageSavingCallback`، وهي فئة مخصصة للتعامل مع رد الاتصال بحفظ الصفحة.

## الخطوة 4: تنفيذ رد الاتصال بحفظ الصفحة

```csharp
public class HandlePageSavingCallback : IPageSavingCallback
{
     public void PageSaving(PageSavingArgs args)
     {
         // قم بتنفيذ الإجراءات المخصصة الخاصة بك هنا
         // يمكنك الوصول إلى معلومات الصفحة من خلال خاصية "args.PageIndex".
         // يمكنك أيضًا تغيير خيارات الحفظ لكل صفحة على حدة.
     }
}
```

 في هذه الخطوة نقوم بتنفيذ`HandlePageSavingCallback` الطبقة التي تنفذ`IPageSavingCallback` واجهه المستخدم. يمكنك تخصيص هذه الفئة عن طريق إضافة إجراءاتك المحددة في ملف`PageSaving` طريقة. يمكنك الوصول إلى معلومات الصفحة من خلال`args.PageIndex` ملكية`PageSavingArgs` تم تمرير الكائن كوسيطة.

## الخطوة 5: حفظ الصفحات كصور

```csharp
doc.Save(dataDir + "WorkingWithImageSaveOptions.PageSavingCallback.png", imageSaveOptions);
```

 في هذه الخطوة الأخيرة، نقوم بحفظ كل صفحة من المستند كصورة باستخدام ملف`Save` الطريقة وتمرير المسار إلى ملف الإخراج باستخدام الملف`.png` الملحق، بالإضافة إلى خيارات الحفظ المحددة.

يمكنك الآن تشغيل التعليمات البرمجية المصدر لتنفيذ إجراءات مخصصة عند حفظ كل صفحة من المستند كصورة. سيتم حفظ الملف الناتج في الدليل المحدد بالاسم "WorkingWithImageSaveOptions.PageSavingCallback.png".

### نموذج التعليمات البرمجية المصدر لرد الاتصال بحفظ الصفحة باستخدام Aspose.Words لـ .NET


```csharp 
// المسار إلى دليل المستندات الخاص بك
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

في هذا البرنامج التعليمي، استكشفنا وظيفة رد الاتصال لحفظ الصفحة باستخدام خيارات حفظ الصور Aspose.Words لـ .NET. لقد تعلمنا كيفية تنفيذ إجراءات مخصصة عند حفظ كل صفحة من المستند كصورة.

تكون هذه الميزة مفيدة عندما تريد إجراء عمليات محددة على كل صفحة عند التحويل إلى صور. يمكنك الوصول إلى معلومات الصفحة واستخدامها لتخصيص خيارات النسخ الاحتياطي أو إجراء معالجة أخرى خاصة بالصفحة.

يقدم Aspose.Words for .NET نطاقًا واسعًا من الميزات المتقدمة لمعالجة المستندات وإنشائها. يعد Save Page Reminder واحدًا من العديد من الأدوات القوية التي توفر لك تخصيص عملية حفظ الصفحات على الصور.