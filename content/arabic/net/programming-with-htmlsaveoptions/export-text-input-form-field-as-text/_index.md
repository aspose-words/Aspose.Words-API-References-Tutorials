---
title: تصدير حقل نموذج إدخال النص كنص
linktitle: تصدير حقل نموذج إدخال النص كنص
second_title: Aspose.Words واجهة برمجة تطبيقات معالجة المستندات
description: تعرف على كيفية تصدير حقول نموذج إدخال النص كنص عادي باستخدام Aspose.Words لـ .NET باستخدام هذا الدليل الشامل خطوة بخطوة.
type: docs
weight: 10
url: /ar/net/programming-with-htmlsaveoptions/export-text-input-form-field-as-text/
---
## مقدمة

إذن، هل تغوص في عالم Aspose.Words لـ .NET؟ اختيار رائع! إذا كنت تتطلع إلى معرفة كيفية تصدير حقل نموذج إدخال النص كنص، فأنت في المكان الصحيح. سواء كنت بدأت للتو أو تصقل مهاراتك، سيرشدك هذا الدليل إلى كل ما تحتاج إلى معرفته. دعونا نبدأ، أليس كذلك؟

## المتطلبات الأساسية

قبل أن نتعمق في التفاصيل الجوهرية، دعونا نتأكد من أن لديك كل ما تحتاجه للمتابعة بسلاسة:

-  Aspose.Words for .NET: قم بتنزيل أحدث إصدار وتثبيته من[هنا](https://releases.aspose.com/words/net/).
- IDE: Visual Studio أو أي بيئة تطوير C#.
- المعرفة الأساسية لـ C#: فهم بناء جملة C# الأساسي ومفاهيم البرمجة الموجهة للكائنات.
- المستند: نموذج مستند Word (`Rendering.docx`) مع حقول نموذج إدخال النص.

## استيراد مساحات الأسماء

أول الأشياء أولاً، تحتاج إلى استيراد مساحات الأسماء الضرورية. إنها بمثابة اللبنات الأساسية التي تجعل كل شيء يعمل بسلاسة.

```csharp
using System;
using System.IO;
using Aspose.Words;
using Aspose.Words.Saving;
```

حسنًا، الآن بعد أن أصبحت مساحات الأسماء لدينا جاهزة، فلننتقل إلى الإجراء!

## الخطوة 1: إعداد المشروع

قبل أن ندخل في الكود، دعونا نتأكد من إعداد مشروعنا بشكل صحيح.

## إنشاء المشروع

1. افتح Visual Studio: ابدأ بفتح Visual Studio أو بيئة تطوير C# المفضلة لديك.
2.  إنشاء مشروع جديد: انتقل إلى`File > New > Project` . يختار`Console App (.NET Core)` أو أي نوع آخر من المشاريع ذات الصلة.
3.  قم بتسمية مشروعك: امنح مشروعك اسمًا ذا معنى، مثل`AsposeWordsExportExample`.

## إضافة Aspose.Words

1.  إدارة حزم NuGet: انقر بزر الماوس الأيمن على مشروعك في Solution Explorer وحدد`Manage NuGet Packages`.
2.  البحث عن Aspose.Words: في NuGet Package Manager، ابحث عن`Aspose.Words`.
3.  تثبيت Aspose.Words: انقر على`Install` لإضافة مكتبة Aspose.Words إلى مشروعك.

## الخطوة 2: قم بتحميل مستند Word

الآن بعد أن تم إعداد مشروعنا، فلنقم بتحميل مستند Word الذي يحتوي على حقول نموذج إدخال النص.

1. تحديد دليل المستندات: حدد المسار إلى الدليل الذي تم تخزين المستند فيه.
2.  قم بتحميل المستند: استخدم`Document` فئة لتحميل مستند Word الخاص بك.

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document doc = new Document(dataDir + "Rendering.docx");
```

## الخطوة 3: إعداد دليل التصدير

قبل أن نقوم بالتصدير، دعونا نتأكد من أن دليل التصدير الخاص بنا جاهز. هذا هو المكان الذي سيتم فيه حفظ ملف HTML والصور.

1. تحديد دليل التصدير: حدد المسار الذي سيتم حفظ الملفات المصدرة فيه.
2. فحص الدليل وتنظيفه: تأكد من وجود الدليل وأنه فارغ.

```csharp
string imagesDir = Path.Combine(dataDir, "Images");

if (Directory.Exists(imagesDir))
    Directory.Delete(imagesDir, true);

Directory.CreateDirectory(imagesDir);
```

## الخطوة 4: تكوين خيارات الحفظ

هنا يحدث السحر. نحن بحاجة إلى إعداد خيارات الحفظ لدينا لتصدير حقل نموذج إدخال النص كنص عادي.

1.  إنشاء خيارات الحفظ: تهيئة ملف جديد`HtmlSaveOptions` هدف.
2.  ضبط خيار تصدير النص: قم بتكوين`ExportTextInputFormFieldAsText`الملكية ل`true`.
3. تعيين مجلد الصور: حدد المجلد الذي سيتم حفظ الصور فيه.

```csharp
HtmlSaveOptions saveOptions = new HtmlSaveOptions(SaveFormat.Html)
{
    ExportTextInputFormFieldAsText = true,
    ImagesFolder = imagesDir
};
```

## الخطوة 5: احفظ المستند بتنسيق HTML

أخيرًا، دعونا نحفظ مستند Word كملف HTML باستخدام خيارات الحفظ التي تم تكوينها.

1. تحديد مسار الإخراج: حدد المسار الذي سيتم حفظ ملف HTML فيه.
2.  احفظ المستند: استخدم`Save` طريقة`Document`فئة لتصدير المستند.

```csharp
doc.Save(dataDir + "ExportedDocument.html", saveOptions);
```

## خاتمة

وهنا لديك! لقد نجحت في تصدير حقل نموذج إدخال نص كنص عادي باستخدام Aspose.Words لـ .NET. كان من المفترض أن يمنحك هذا الدليل نهجًا واضحًا وتدريجيًا لتحقيق هذه المهمة. تذكر أن الممارسة تؤدي إلى الإتقان، لذا استمر في تجربة الخيارات والإعدادات المختلفة لمعرفة ما يمكنك فعله باستخدام Aspose.Words.

## الأسئلة الشائعة

### هل يمكنني تصدير أنواع أخرى من حقول النموذج باستخدام نفس الطريقة؟

 نعم، يمكنك تصدير أنواع أخرى من حقول النموذج عن طريق تكوين خصائص مختلفة للملف`HtmlSaveOptions` فصل.

### ماذا لو كانت وثيقتي تحتوي على صور؟

 سيتم حفظ الصور في مجلد الصور المحدد. تأكد من ضبط`ImagesFolder` الممتلكات في`HtmlSaveOptions`.

### هل أحتاج إلى ترخيص لـ Aspose.Words؟

 نعم، يمكنك الحصول على نسخة تجريبية مجانية[هنا](https://releases.aspose.com/) أو شراء ترخيص[هنا](https://purchase.aspose.com/buy).

### هل يمكنني تخصيص HTML الذي تم تصديره؟

 قطعاً! يوفر Aspose.Words خيارات متنوعة لتخصيص مخرجات HTML. الرجوع إلى[الوثائق](https://reference.aspose.com/words/net/) لمزيد من التفاصيل.

### هل Aspose.Words متوافق مع .NET Core؟

نعم، Aspose.Words متوافق مع .NET Core و.NET Framework ومنصات .NET الأخرى.
