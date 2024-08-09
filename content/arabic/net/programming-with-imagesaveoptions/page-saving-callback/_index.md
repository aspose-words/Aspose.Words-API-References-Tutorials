---
title: رد الاتصال بحفظ الصفحة
linktitle: رد الاتصال بحفظ الصفحة
second_title: Aspose.Words واجهة برمجة تطبيقات معالجة المستندات
description: تعلم كيفية حفظ كل صفحة من مستند Word كصورة PNG منفصلة باستخدام Aspose.Words لـ .NET من خلال دليلنا التفصيلي خطوة بخطوة.
type: docs
weight: 10
url: /ar/net/programming-with-imagesaveoptions/page-saving-callback/
---
## مقدمة

مرحبًا يا من هناك! هل شعرت يومًا بالحاجة إلى حفظ كل صفحة من مستند Word كصور منفصلة؟ ربما تريد تقسيم تقرير كبير إلى عناصر مرئية سهلة الفهم، أو ربما تحتاج إلى إنشاء صور مصغرة للمعاينة. مهما كان السبب، فإن استخدام Aspose.Words for .NET يجعل هذه المهمة سهلة للغاية. في هذا الدليل، سنرشدك خلال عملية إعداد رد اتصال لحفظ الصفحة لحفظ كل صفحة من المستند كصورة PNG فردية. دعونا نتعمق في الأمر!

## المتطلبات الأساسية

قبل أن نبدأ، تأكد من أن لديك ما يلي:

1.  Aspose.Words for .NET: إذا لم تكن قد قمت بذلك بالفعل، فقم بتنزيله وتثبيته من[هنا](https://releases.aspose.com/words/net/).
2. Visual Studio: يجب أن يعمل أي إصدار، لكنني سأستخدم Visual Studio 2019 لهذا الدليل.
3. المعرفة الأساسية بـ C#: ستحتاج إلى فهم أساسي لـ C# للمتابعة.

## استيراد مساحات الأسماء

أولاً، نحتاج إلى استيراد مساحات الأسماء الضرورية. يساعدنا هذا في الوصول إلى الفئات والأساليب المطلوبة دون كتابة مساحة الاسم الكاملة في كل مرة.

```csharp
using System;
using Aspose.Words;
using Aspose.Words.Saving;
```

## الخطوة 1: قم بإعداد دليل المستندات الخاص بك

حسنًا، لنبدأ بتحديد المسار إلى دليل المستندات الخاص بك. هذا هو المكان الذي يوجد فيه مستند Word الذي تم إدخاله والمكان الذي سيتم فيه حفظ الصور الناتجة.

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## الخطوة 2: قم بتحميل المستند الخاص بك

بعد ذلك، سنقوم بتحميل المستند الذي تريد معالجته. تأكد من وجود المستند ("Rendering.docx") في الدليل المحدد.

```csharp
Document doc = new Document(dataDir + "Rendering.docx");
```

## الخطوة 3: تكوين خيارات حفظ الصورة

نحن بحاجة إلى تكوين الخيارات لحفظ الصور. في هذه الحالة، نقوم بحفظ الصفحات كملفات PNG.

```csharp
ImageSaveOptions imageSaveOptions = new ImageSaveOptions(SaveFormat.Png)
{
    PageSet = new PageSet(new PageRange(0, doc.PageCount - 1)),
    PageSavingCallback = new HandlePageSavingCallback()
};
```

 هنا،`PageSet` يحدد نطاق الصفحات المراد حفظها، و`PageSavingCallback` يشير إلى فئة رد الاتصال المخصصة لدينا.

## الخطوة 4: تنفيذ رد الاتصال بحفظ الصفحة

الآن، دعونا ننفذ فئة رد الاتصال التي تتعامل مع كيفية حفظ كل صفحة.

```csharp
private class HandlePageSavingCallback : IPageSavingCallback
{
    public void PageSaving(PageSavingArgs args)
    {
        args.PageFileName = string.Format(dataDir + "Page_{0}.png", args.PageIndex);
    }
}
```

 تنفذ هذه الفئة`IPageSavingCallback` واجهة، وداخل`PageSaving` الطريقة، نحدد نمط التسمية لكل صفحة محفوظة.

## الخطوة 5: احفظ المستند كصور

وأخيرًا، نقوم بحفظ المستند باستخدام الخيارات التي تم تكوينها.

```csharp
doc.Save(dataDir + "WorkingWithImageSaveOptions.PageSavingCallback.png", imageSaveOptions);
```

## خاتمة

وهنا لديك! لقد قمت بنجاح بإعداد رد اتصال لحفظ الصفحة لحفظ كل صفحة من مستند Word كصورة PNG منفصلة باستخدام Aspose.Words for .NET. تعتبر هذه التقنية مفيدة بشكل لا يصدق لمختلف التطبيقات، بدءًا من إنشاء معاينات الصفحة وحتى إنشاء صور فردية للصفحات للتقارير. 

ترميز سعيد!

## الأسئلة الشائعة

### هل يمكنني حفظ الصفحات بتنسيقات أخرى غير PNG؟  
 نعم، يمكنك حفظ الصفحات بتنسيقات مختلفة مثل JPEG، وBMP، وTIFF عن طريق تغيير ملف`SaveFormat` في`ImageSaveOptions`.

### ماذا لو كنت أرغب في حفظ صفحات محددة فقط؟  
 يمكنك تحديد الصفحات التي تريد حفظها عن طريق ضبط`PageSet` المعلمة في`ImageSaveOptions`.

### هل من الممكن تخصيص جودة الصورة؟  
 قطعاً! يمكنك تعيين خصائص مثل`ImageSaveOptions.JpegQuality` للتحكم في جودة الصور الناتجة.

### كيف يمكنني التعامل مع المستندات الكبيرة بكفاءة؟  
بالنسبة للمستندات الكبيرة، فكر في معالجة الصفحات على دفعات لإدارة استخدام الذاكرة بشكل فعال.

### أين يمكنني العثور على مزيد من المعلومات حول Aspose.Words for .NET؟  
 تحقق من[الوثائق](https://reference.aspose.com/words/net/) للحصول على أدلة وأمثلة شاملة.