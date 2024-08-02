---
title: تصدير إلى تخفيض السعر مع محاذاة محتوى الجدول
linktitle: تصدير إلى تخفيض السعر مع محاذاة محتوى الجدول
second_title: Aspose.Words واجهة برمجة تطبيقات معالجة المستندات
description: تعرف على كيفية تصدير مستندات Word إلى Markdown مع جداول محاذية باستخدام Aspose.Words for .NET. اتبع دليلنا خطوة بخطوة للحصول على جداول Markdown المثالية.
type: docs
weight: 10
url: /ar/net/programming-with-markdownsaveoptions/export-into-markdown-with-table-content-alignment/
---
## مقدمة

مرحبًا يا من هناك! هل تساءلت يومًا عن كيفية تصدير مستند Word الخاص بك إلى تنسيق Markdown مع جداول محاذاة تمامًا؟ سواء كنت مطورًا يعمل على التوثيق أو مجرد شخص يحب Markdown، فهذا الدليل مناسب لك. سنتعمق في التفاصيل الجوهرية لاستخدام Aspose.Words for .NET لتحقيق ذلك. هل أنت مستعد لتحويل جداول Word الخاصة بك إلى جداول Markdown محاذاة بدقة؟ هيا بنا نبدأ!

## المتطلبات الأساسية

قبل أن نتعمق في التعليمات البرمجية، هناك بعض الأشياء التي ستحتاج إلى توفرها:

1.  Aspose.Words لمكتبة .NET: تأكد من أن لديك مكتبة Aspose.Words لـ .NET. يمكنك تنزيله من[صفحة الإصدارات Aspose](https://releases.aspose.com/words/net/).
2. بيئة التطوير: قم بإعداد بيئة التطوير الخاصة بك. يعد Visual Studio خيارًا شائعًا لتطوير .NET.
3. المعرفة الأساسية بـ C#: يعد فهم C# أمرًا ضروريًا لأننا سنكتب التعليمات البرمجية بهذه اللغة.
4. نموذج مستند Word: احصل على مستند Word يمكنك استخدامه للاختبار.

## استيراد مساحات الأسماء

قبل أن نبدأ بالبرمجة، فلنستورد مساحات الأسماء الضرورية. سيتيح لنا ذلك الوصول إلى فئات Aspose.Words والأساليب التي سنستخدمها.

```csharp
using Aspose.Words;
using Aspose.Words.Saving;
```

## الخطوة 1: تهيئة المستند و DocumentBuilder

أول الأشياء أولاً، نحتاج إلى إنشاء مستند Word جديد وتهيئة ملف`DocumentBuilder` كائن لبدء بناء وثيقتنا.

```csharp
// المسار إلى دليل المستندات.
string dataDir = "YOUR DOCUMENT DIRECTORY";

// إنشاء مستند جديد.
Document doc = new Document();

// تهيئة DocumentBuilder.
DocumentBuilder builder = new DocumentBuilder(doc);
```

## الخطوة 2: إدراج الخلايا ومحاذاة المحتوى

بعد ذلك، سنقوم بإدراج بعض الخلايا في وثيقتنا وضبط محاذاتها. يعد هذا أمرًا بالغ الأهمية لضمان احتفاظ تصدير Markdown بالمحاذاة الصحيحة.

```csharp
// أدخل خلية وقم بتعيين المحاذاة إلى اليمين.
builder.InsertCell();
builder.ParagraphFormat.Alignment = ParagraphAlignment.Right;
builder.Write("Cell1");

// أدخل خلية أخرى وقم بتعيين المحاذاة إلى المركز.
builder.InsertCell();
builder.ParagraphFormat.Alignment = ParagraphAlignment.Center;
builder.Write("Cell2");
```

## الخطوة 3: تعيين محاذاة محتوى الجدول لتصدير Markdown

 الآن، حان الوقت لتكوين`MarkdownSaveOptions` للتحكم في محاذاة محتوى الجدول في ملف Markdown المُصدَّر. سنقوم بحفظ المستند بإعدادات محاذاة مختلفة لنرى كيف يعمل.

```csharp
// قم بإنشاء كائن MarkdownSaveOptions.
MarkdownSaveOptions saveOptions = new MarkdownSaveOptions
{
    TableContentAlignment = TableContentAlignment.Left
};

// احفظ المستند بمحاذاة لليسار.
doc.Save(dataDir + "LeftTableContentAlignment.md", saveOptions);

// تغيير المحاذاة إلى اليمين وحفظها.
saveOptions.TableContentAlignment = TableContentAlignment.Right;
doc.Save(dataDir + "RightTableContentAlignment.md", saveOptions);

// تغيير المحاذاة إلى المركز وحفظها.
saveOptions.TableContentAlignment = TableContentAlignment.Center;
doc.Save(dataDir + "CenterTableContentAlignment.md", saveOptions);
```

## الخطوة 4: استخدم محاذاة محتوى الجدول تلقائيًا

 ال`Auto`يأخذ خيار المحاذاة المحاذاة من الفقرة الأولى في عمود الجدول المقابل. يمكن أن يكون هذا مفيدًا عندما يكون لديك تحالفات مختلطة في جدول واحد.

```csharp
// اضبط المحاذاة على تلقائي.
saveOptions.TableContentAlignment = TableContentAlignment.Auto;

// حفظ المستند مع المحاذاة التلقائية.
doc.Save(dataDir + "AutoTableContentAlignment.md", saveOptions);
```

## خاتمة

وهناك لديك! يعد تصدير مستندات Word إلى Markdown مع جداول محاذية باستخدام Aspose.Words for .NET أمرًا سهلاً بمجرد أن تعرف كيفية القيام بذلك. تسهل هذه المكتبة القوية التحكم في تنسيق جداولك ومواءمتها، مما يضمن ظهور مستندات Markdown بالطريقة التي تريدها تمامًا. ترميز سعيد!

## الأسئلة الشائعة

### ما هو Aspose.Words لـ .NET؟
Aspose.Words for .NET هي مكتبة قوية تمكن المطورين من إنشاء مستندات Word وتعديلها وتحويلها وتصديرها برمجيًا.

### هل يمكنني تعيين محاذاة مختلفة لأعمدة مختلفة في نفس الجدول؟
 نعم باستخدام`Auto` خيار المحاذاة، يمكنك الحصول على محاذاة مختلفة بناءً على الفقرة الأولى في كل عمود.

### هل أحتاج إلى ترخيص لاستخدام Aspose.Words لـ .NET؟
 نعم، يتطلب Aspose.Words for .NET ترخيصًا للحصول على الوظائف الكاملة. يمكنك الحصول على[ترخيص مؤقت](https://purchase.aspose.com/temporary-license/) للتقييم.

### هل من الممكن تصدير عناصر المستند الأخرى إلى Markdown باستخدام Aspose.Words؟
نعم، يدعم Aspose.Words تصدير عناصر متنوعة مثل العناوين والقوائم والصور إلى تنسيق Markdown.

### أين يمكنني الحصول على الدعم إذا واجهت مشاكل؟
 يمكنك الحصول على الدعم من[منتدى دعم Aspose.Words](https://forum.aspose.com/c/words/8).
