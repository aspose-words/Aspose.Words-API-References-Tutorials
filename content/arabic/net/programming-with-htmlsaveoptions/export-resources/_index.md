---
title: تصدير الموارد
linktitle: تصدير الموارد
second_title: Aspose.Words واجهة برمجة تطبيقات معالجة المستندات
description: تعرف على كيفية تصدير الموارد مثل CSS والخطوط مع حفظ مستندات Word بتنسيق HTML باستخدام Aspose.Words for .NET. اتبع دليلنا خطوة بخطوة.
type: docs
weight: 10
url: /ar/net/programming-with-htmlsaveoptions/export-resources/
---
## مقدمة

مرحبًا بك، أيها الزميل المتحمس للتكنولوجيا! إذا وجدت نفسك بحاجة إلى تحويل مستندات Word إلى HTML، فأنت في المكان الصحيح. اليوم، نحن نتعمق في عالم Aspose.Words for .NET الرائع. تجعل هذه المكتبة القوية من السهل العمل مع مستندات Word برمجيًا. في هذا البرنامج التعليمي، سنتعرف على خطوات تصدير الموارد، مثل الخطوط وCSS، عند حفظ مستند Word بتنسيق HTML باستخدام Aspose.Words لـ .NET. استعدوا لرحلة ممتعة وغنية بالمعلومات!

## المتطلبات الأساسية

قبل أن نتعمق في الكود، دعنا نتأكد من حصولك على كل ما تحتاجه للبدء. فيما يلي قائمة مرجعية سريعة:

1.  Visual Studio: تأكد من تثبيت Visual Studio على جهازك. يمكنك تنزيله من[موقع فيجوال ستوديو](https://visualstudio.microsoft.com/).
2.  Aspose.Words لـ .NET: ستحتاج إلى مكتبة Aspose.Words لـ .NET. إذا لم تكن قد حصلت عليه بعد، احصل على نسخة تجريبية مجانية من[إصدارات Aspose](https://releases.aspose.com/words/net/) أو شرائه من[متجر أسبوز](https://purchase.aspose.com/buy).
3. المعرفة الأساسية بـ C#: الفهم الأساسي لـ C# سيساعدك على متابعة أمثلة التعليمات البرمجية.

حصلت على كل ذلك؟ عظيم! دعنا ننتقل إلى استيراد مساحات الأسماء الضرورية.

## استيراد مساحات الأسماء

لاستخدام Aspose.Words لـ .NET، يتعين عليك تضمين مساحات الأسماء ذات الصلة في مشروعك. إليك كيفية القيام بذلك:

```csharp
using Aspose.Words;
using Aspose.Words.Saving;
```

تعد مساحات الأسماء هذه ضرورية للوصول إلى فئات Aspose.Words والأساليب التي سنستخدمها في برنامجنا التعليمي.

دعونا نحلل عملية تصدير الموارد عند حفظ مستند Word بتنسيق HTML. سنأخذ الأمر خطوة بخطوة، لذلك من السهل متابعته.

## الخطوة 1: قم بإعداد دليل المستندات الخاص بك

أول الأشياء أولاً، عليك تحديد المسار إلى دليل المستندات الخاص بك. هذا هو المكان الذي يوجد فيه مستند Word الخاص بك والمكان الذي سيتم فيه حفظ ملف HTML.

```csharp
// المسار إلى دليل المستندات.
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

 يستبدل`"YOUR DOCUMENT DIRECTORY"` مع المسار الفعلي إلى الدليل الخاص بك.

## الخطوة 2: قم بتحميل مستند Word

 بعد ذلك، لنقم بتحميل مستند Word الذي تريد تحويله إلى HTML. في هذا البرنامج التعليمي، سنستخدم مستندًا اسمه`Rendering.docx`.

```csharp
Document doc = new Document(dataDir + "Rendering.docx");
```

يقوم سطر التعليمات البرمجية هذا بتحميل المستند من الدليل المحدد.

## الخطوة 3: تكوين خيارات حفظ HTML

لتصدير الموارد مثل CSS والخطوط، تحتاج إلى تكوين ملف`HtmlSaveOptions`. تعتبر هذه الخطوة ضرورية لضمان أن مخرجات HTML الخاصة بك جيدة التنظيم وتتضمن الموارد اللازمة.

```csharp
HtmlSaveOptions saveOptions = new HtmlSaveOptions
{
    CssStyleSheetType = CssStyleSheetType.External,
    ExportFontResources = true,
    ResourceFolder = dataDir + "Resources",
    ResourceFolderAlias = "http://example.com/resources"
};
```

دعنا نحلل ما يفعله كل خيار:
- `CssStyleSheetType = CssStyleSheetType.External`: يحدد هذا الخيار ضرورة حفظ أنماط CSS في ورقة أنماط خارجية.
- `ExportFontResources = true`: يتيح ذلك تصدير موارد الخطوط.
- `ResourceFolder = dataDir + "Resources"`: يحدد المجلد المحلي حيث سيتم حفظ الموارد (مثل الخطوط وملفات CSS).
- `ResourceFolderAlias = "http://example.com/resources"`: يعين اسمًا مستعارًا لمجلد المورد، والذي سيتم استخدامه في ملف HTML.

## الخطوة 4: احفظ المستند بتنسيق HTML

بعد تكوين خيارات الحفظ، فإن الخطوة الأخيرة هي حفظ المستند كملف HTML. إليك كيفية القيام بذلك:

```csharp
doc.Save(dataDir + "WorkingWithHtmlSaveOptions.ExportResources.html", saveOptions);
```

يقوم سطر التعليمات البرمجية هذا بحفظ المستند بتنسيق HTML، بالإضافة إلى الموارد المصدرة.

## خاتمة

وهناك لديك! لقد نجحت في تصدير الموارد أثناء حفظ مستند Word بتنسيق HTML باستخدام Aspose.Words لـ .NET. باستخدام هذه المكتبة القوية، يصبح التعامل مع مستندات Word برمجيًا أمرًا في غاية السهولة. سواء كنت تعمل على تطبيق ويب أو تحتاج فقط إلى تحويل المستندات للاستخدام دون الاتصال بالإنترنت، فإن Aspose.Words هو الحل الأمثل لك.

## الأسئلة الشائعة

### هل يمكنني تصدير الصور مع الخطوط وCSS؟
 نعم يمكنك! يدعم Aspose.Words for .NET تصدير الصور أيضًا. فقط تأكد من تكوين`HtmlSaveOptions` وفقاً لذلك.

### هل هناك طريقة لتضمين CSS بدلاً من استخدام ورقة أنماط خارجية؟
 قطعاً. يمكنك ضبط`CssStyleSheetType` ل`CssStyleSheetType.Embedded` إذا كنت تفضل الأنماط المضمنة.

### كيف يمكنني تخصيص اسم ملف HTML الناتج؟
 يمكنك تحديد أي اسم ملف تريده في ملف`doc.Save` طريقة. على سبيل المثال،`doc.Save(dataDir + "CustomFileName.html", saveOptions);`.

### هل يدعم Aspose.Words التنسيقات الأخرى إلى جانب HTML؟
 نعم، فهو يدعم العديد من التنسيقات بما في ذلك PDF وDOCX وTXT والمزيد. تفحص ال[توثيق](https://reference.aspose.com/words/net/) للحصول على قائمة كاملة.

### أين يمكنني الحصول على المزيد من الدعم والموارد؟
لمزيد من المساعدة، قم بزيارة[منتدى دعم Aspose.Words](https://forum.aspose.com/c/words/8) . يمكنك أيضًا العثور على وثائق وأمثلة مفصلة على الموقع[موقع أسبوز](https://reference.aspose.com/words/net/).