---
title: تعيين مجلد الصور
linktitle: تعيين مجلد الصور
second_title: Aspose.Words واجهة برمجة تطبيقات معالجة المستندات
description: قم بتحويل مستندات Word إلى Markdown مع محاذاة الجدول المناسبة باستخدام Aspose.Words لـ .NET. اتبع دليلنا التفصيلي للحصول على نتائج مثالية.
type: docs
weight: 10
url: /ar/net/programming-with-markdownsaveoptions/set-images-folder/
---
## مقدمة

هل سبق لك أن أردت تصدير مستند Word الخاص بك إلى تنسيق Markdown مع التأكد من محاذاة الجداول والمحتوى بشكل مثالي؟ Aspose.Words for .NET هو الحل الأمثل لهذه المهمة. في هذه المقالة، سنرشدك خلال عملية إعداد Aspose.Words، وإعداد مستندك، وتصديره إلى Markdown مع محاذاة محتوى الجدول بشكل صحيح. سنقوم بتفصيل كل خطوة لتسهيل متابعتها وفهمها. لذلك، دعونا نتعمق ونحول مستندات Word الخاصة بك إلى ملفات Markdown متناسقة بشكل جميل!

## المتطلبات الأساسية

قبل أن نبدأ، تأكد من أن لديك ما يلي:

-  Aspose.Words لـ .NET: يمكنك تنزيله[هنا](https://releases.aspose.com/words/net/).
-  ترخيص صالح: احصل على نسخة تجريبية مجانية[هنا](https://releases.aspose.com/) أو ترخيص مؤقت[هنا](https://purchase.aspose.com/temporary-license/).
- Visual Studio: أو أي بيئة تطوير متكاملة أخرى تدعم تطوير .NET.
- المعرفة الأساسية بـ C#: فهم لغة البرمجة C#.

## استيراد مساحات الأسماء

للبدء، ستحتاج إلى استيراد مساحات الأسماء الضرورية في مشروع C# الخاص بك. ستسمح لك مساحات الأسماء هذه بالوصول إلى وظيفة Aspose.Words.

```csharp
using Aspose.Words;
using Aspose.Words.Saving;
using System.IO;
```

## الخطوة 1: قم بإعداد مشروعك

أول الأشياء أولاً، قم بإعداد مشروع .NET الخاص بك في IDE الخاص بك. قم بإنشاء تطبيق وحدة تحكم جديد وقم بإضافة مرجع إلى Aspose.Words لـ .NET.

### 1.1 إنشاء مشروع جديد

افتح Visual Studio وقم بإنشاء مشروع تطبيق وحدة تحكم جديد. أطلق عليه اسم "MarkdownExporter" أو شيء مشابه.

### 1.2 إضافة مرجع Aspose.Words

 لإضافة Aspose.Words إلى مشروعك، يمكنك إما تنزيل ملف DLL من ملف[موقع أسبوز](https://releases.aspose.com/words/net/) وإضافته يدويًا، أو استخدم NuGet Package Manager:

```bash
Install-Package Aspose.Words
```

## الخطوة 2: اكتب الكود المراد تصديره كـ Markdown

الآن، دعنا نكتب الكود لقراءة مستند Word وحفظه كملف Markdown مع محاذاة الجدول المناسبة.

### 2.1 تحديد المسار إلى المستند الخاص بك

قم بتعيين المسار إلى مستند Word الخاص بك والمجلد الذي تريد حفظ الصور فيه.

```csharp
string dataDir = "YOUR_DOCUMENT_DIRECTORY";
```

### 2.2 قم بتحميل المستند

قم بتحميل مستند Word الخاص بك باستخدام Aspose.Words.

```csharp
Document doc = new Document(dataDir + "Image bullet points.docx");
```

### 2.3 تكوين خيارات حفظ تخفيض السعر

 تكوين`MarkdownSaveOptions` لتحديد المكان الذي يجب تخزين الصور فيه.

```csharp
MarkdownSaveOptions saveOptions = new MarkdownSaveOptions
{
    ImagesFolder = dataDir + "Images"
};
```

### 2.4 احفظ المستند باسم Markdown

 إستخدم`MemoryStream` لحفظ المستند بتنسيق Markdown.

```csharp
using (MemoryStream stream = new MemoryStream())
{
    doc.Save(stream, saveOptions);
}
```

## خاتمة

يعد تصدير مستند Word إلى Markdown مع محاذاة محتوى الجدول باستخدام Aspose.Words لـ .NET أمراً مباشرًا عند اتباع هذه الخطوات. باستخدام بضعة أسطر من التعليمات البرمجية، يمكنك أتمتة عملية التحويل والتأكد من تنسيق المحتوى الخاص بك بشكل جيد. الآن، يمكنك بسهولة مشاركة مستنداتك بتنسيق Markdown، مع العلم أنها ستبدو رائعة وتحافظ على بنيتها.

## الأسئلة الشائعة

### هل يمكنني استخدام Aspose.Words لـ .NET مع لغات البرمجة الأخرى؟

نعم، يمكن استخدام Aspose.Words for .NET مع أي لغة متوافقة مع .NET مثل VB.NET، وF#، والمزيد.

### كيف يمكنني الحصول على ترخيص مؤقت لـ Aspose.Words؟

 يمكنك الحصول على ترخيص مؤقت[هنا](https://purchase.aspose.com/temporary-license/).

### ما أنواع المستندات التي يمكنني تحويلها إلى Markdown؟

يمكنك تحويل مستندات Word المختلفة بما في ذلك .doc و.docx و.rtf والمزيد.

### هل هناك أي قيود في الإصدار التجريبي من Aspose.Words؟

تحتوي النسخة التجريبية على بعض القيود مثل العلامات المائية في ملفات الإخراج. يمكنك الحصول على نسخة تجريبية مجانية[هنا](https://releases.aspose.com/).

### أين يمكنني العثور على المزيد من الأمثلة والوثائق الخاصة بـ Aspose.Words؟

 يمكنك العثور على وثائق وأمثلة مفصلة على[موقع أسبوز](https://reference.aspose.com/words/net/).
