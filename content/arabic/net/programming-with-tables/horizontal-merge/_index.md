---
title: دمج أفقي
linktitle: دمج أفقي
second_title: Aspose.Words واجهة برمجة تطبيقات معالجة المستندات
description: تعرف على كيفية دمج الخلايا أفقيًا في مستند Word باستخدام Aspose.Words لـ .NET من خلال هذا البرنامج التعليمي التفصيلي خطوة بخطوة.
type: docs
weight: 10
url: /ar/net/programming-with-tables/horizontal-merge/
---
## مقدمة

مرحبًا يا من هناك! هل أنت مستعد للغوص في عالم Aspose.Words لـ .NET؟ اليوم، سنتناول ميزة مفيدة جدًا: الدمج الأفقي في الجداول. قد يبدو هذا تقنيًا بعض الشيء، لكن لا تقلق، أنا أساندك. بحلول نهاية هذا البرنامج التعليمي، ستكون محترفًا في دمج الخلايا في مستندات Word الخاصة بك برمجيًا. لذا، دعونا نشمر عن سواعدنا ونبدأ!

## المتطلبات الأساسية

قبل أن ننتقل إلى التفاصيل الجوهرية، هناك بعض الأشياء التي ستحتاج إلى توفرها:

1. Aspose.Words for .NET Library: إذا لم تكن قد قمت بذلك بالفعل، فقم بتنزيل Aspose.Words for .NET Library. يمكنك الاستيلاء عليها[هنا](https://releases.aspose.com/words/net/).
2. بيئة التطوير: تأكد من إعداد بيئة تطوير مناسبة، مثل Visual Studio.
3. المعرفة الأساسية بـ C#: الفهم الأساسي لبرمجة C# سيكون مفيدًا.

بمجرد الانتهاء من ترتيب هذه الأمور، ستكون جاهزًا للانطلاق!

## استيراد مساحات الأسماء

قبل الغوص في التعليمات البرمجية، دعونا نتأكد من أننا قمنا باستيراد مساحات الأسماء الضرورية. في مشروع C# الخاص بك، تأكد من تضمين:

```csharp
using Aspose.Words;
using Aspose.Words.Tables;
```

حسنًا، دعنا نقسم عملية دمج خلايا الجدول أفقيًا في مستند Word باستخدام Aspose.Words لـ .NET.

## الخطوة 1: إعداد المستند الخاص بك

 أول الأشياء أولاً، نحتاج إلى إنشاء مستند Word جديد وتهيئة الملف`DocumentBuilder`:

```csharp
// المسار إلى دليل المستندات الخاص بك
string dataDir = "YOUR DOCUMENT DIRECTORY";

Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
```

 يقوم مقتطف الرمز هذا بإعداد مستند جديد وإعداد الملف`DocumentBuilder` للعمل.

## الخطوة 2: إدخال الخلية الأولى

بعد ذلك، نبدأ بإدخال الخلية الأولى ووضع علامة عليها للدمج الأفقي:

```csharp
builder.InsertCell();
builder.CellFormat.HorizontalMerge = CellMerge.First;
builder.Write("Text in merged cells.");
```

 هنا، نقوم بإدراج خلية جديدة وتعيينها`HorizontalMerge`الملكية ل`CellMerge.First`، للإشارة إلى أن هذه الخلية هي بداية تسلسل الخلايا المدمجة.

## الخطوة 3: إدراج الخلية المدمجة

الآن نقوم بإدراج الخلية التي سيتم دمجها مع الخلية السابقة:

```csharp
builder.InsertCell();
builder.CellFormat.HorizontalMerge = CellMerge.Previous;
builder.EndRow();
```

 يتم تعيين هذه الخلية للدمج مع الخلية السابقة باستخدام`CellMerge.Previous` . لاحظ كيف ننهي الصف بـ`builder.EndRow()`.

## الخطوة 4: إدراج الخلايا غير المدمجة

لتوضيح الفرق، دعونا نقوم بإدراج بضع خلايا غير مدمجة:

```csharp
builder.InsertCell();
builder.CellFormat.HorizontalMerge = CellMerge.None;
builder.Write("Text in one cell.");
builder.InsertCell();
builder.Write("Text in another cell.");
builder.EndRow();
```

هنا، نقوم بإدراج خليتين بدون دمج أفقي. يوضح هذا كيفية تصرف الخلايا عندما لا تكون جزءًا من تسلسل مدمج.

## الخطوة 5: الانتهاء من الجدول

وأخيراً ننهي الجدول ونحفظ الوثيقة:

```csharp
builder.EndTable();
doc.Save(dataDir + "WorkingWithTables.HorizontalMerge.docx");
```

يكمل مقتطف الكود هذا الجدول ويحفظ المستند في الدليل المحدد.

## خاتمة

وهنا لديك! لقد أتقنت للتو فن دمج الخلايا أفقيًا في مستند Word باستخدام Aspose.Words for .NET. باتباع هذه الخطوات، يمكنك إنشاء هياكل جدول معقدة بسهولة. استمر في التجربة واستكشاف إمكانيات Aspose.Words لجعل مستنداتك ديناميكية ومرنة حسب حاجتك. ترميز سعيد!

## الأسئلة الشائعة

### ما هو Aspose.Words لـ .NET؟
Aspose.Words for .NET هي مكتبة قوية تتيح للمطورين إنشاء مستندات Word وتحريرها ومعالجتها برمجيًا في تطبيقات .NET.

### هل يمكنني دمج الخلايا عموديًا باستخدام Aspose.Words لـ .NET؟
 نعم، يمكنك أيضًا دمج الخلايا عموديًا باستخدام`CellFormat.VerticalMerge` ملكية.

### هل Aspose.Words لـ .NET مجاني للاستخدام؟
 يقدم Aspose.Words for .NET نسخة تجريبية مجانية، ولكن للحصول على الوظائف الكاملة، ستحتاج إلى شراء ترخيص. يمكنك الحصول على ترخيص مؤقت[هنا](https://purchase.aspose.com/temporary-license/).

### كيف يمكنني معرفة المزيد حول Aspose.Words لـ .NET؟
 يمكنك استكشاف الوثائق التفصيلية[هنا](https://reference.aspose.com/words/net/).

### أين يمكنني الحصول على الدعم لـ Aspose.Words لـ .NET؟
 إذا كانت لديك أية استفسارات أو مشكلات، يمكنك زيارة منتدى دعم Aspose[هنا](https://forum.aspose.com/c/words/8).