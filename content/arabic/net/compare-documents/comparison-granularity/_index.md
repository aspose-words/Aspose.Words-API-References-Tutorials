---
title: دقة المقارنة في مستند Word
linktitle: دقة المقارنة في مستند Word
second_title: Aspose.Words واجهة برمجة تطبيقات معالجة المستندات
description: تعرف على ميزة مقارنة التفاصيل في مستند Word في Aspose.Words لـ .NET والتي تسمح بمقارنة المستندات حرفًا بحرف، والإبلاغ عن التغييرات التي تم إجراؤها.
type: docs
weight: 10
url: /ar/net/compare-documents/comparison-granularity/
---
فيما يلي دليل خطوة بخطوة لشرح التعليمات البرمجية المصدر لـ C# أدناه، والتي تستخدم ميزة مقارنة التفاصيل في مستند Word في Aspose.Words for .NET.

## الخطوة 1: المقدمة

تتيح لك ميزة مقارنة التفاصيل في Aspose.Words for .NET مقارنة المستندات على مستوى الأحرف. وهذا يعني أنه ستتم مقارنة كل شخصية وسيتم الإبلاغ عن التغييرات وفقًا لذلك.

## الخطوة الثانية: تهيئة البيئة

قبل أن تبدأ، تحتاج إلى إعداد بيئة التطوير الخاصة بك للعمل مع Aspose.Words لـ .NET. تأكد من تثبيت مكتبة Aspose.Words ولديك مشروع C# مناسب لتضمين الكود فيه.

## الخطوة 3: إضافة التجميعات المطلوبة

لاستخدام ميزة مقارنة التفاصيل في Aspose.Words لـ .NET، يتعين عليك إضافة التجميعات الضرورية إلى مشروعك. تأكد من أن لديك المراجع المناسبة لـ Aspose.Words في مشروعك.

```csharp
using Aspose.Words;
using Aspose.Words.DocumentBuilder;
```

## الخطوة 4: إنشاء المستندات

في هذه الخطوة، سنقوم بإنشاء مستندين باستخدام فئة DocumentBuilder. سيتم استخدام هذه الوثائق للمقارنة.

```csharp
// إنشاء المستند أ.
DocumentBuilder builderA = new DocumentBuilder(new Document());
builderA.Writeln("This is a simple A word.");

// إنشاء مستند ب.
DocumentBuilder builderB = new DocumentBuilder(new Document());
builderB.Writeln("This is simple B words.");
```

## الخطوة 5: تكوين خيارات المقارنة

في هذه الخطوة، سنقوم بتكوين خيارات المقارنة لتحديد دقة المقارنة. هنا سوف نستخدم التفاصيل على مستوى الشخصية.

```csharp
CompareOptions compareOptions = new CompareOptions { Granularity = Granularity.CharLevel };
```

## الخطوة 6: مقارنة المستندات

الآن دعونا نقارن المستندات باستخدام طريقة المقارنة لفئة المستند. سيتم حفظ التغييرات في المستند أ.

```csharp
builderA.Document.Compare(builderB.Document, "author", DateTime.Now, compareOptions);
```

 ال`Compare`تقوم الطريقة بمقارنة المستند أ مع المستند ب وحفظ التغييرات في المستند أ. يمكنك تحديد اسم المؤلف وتاريخ المقارنة كمرجع.

## خاتمة

في هذه المقالة، قمنا باستكشاف ميزة مقارنة التفاصيل في Aspose.Words لـ .NET. تتيح لك هذه الميزة مقارنة المستندات على مستوى الشخصية والإبلاغ عن التغييرات. يمكنك استخدام هذه المعرفة لإجراء مقارنات تفصيلية للمستندات في مشاريعك.

### نموذج التعليمات البرمجية المصدر لتفاصيل المقارنة باستخدام Aspose.Words لـ .NET

```csharp
            
DocumentBuilder builderA = new DocumentBuilder(new Document());
DocumentBuilder builderB = new DocumentBuilder(new Document());

builderA.Writeln("This is A simple word");
builderB.Writeln("This is B simple words");

CompareOptions compareOptions = new CompareOptions { Granularity = Granularity.CharLevel };

builderA.Document.Compare(builderB.Document, "author", DateTime.Now, compareOptions);            
        
```

## خاتمة

في هذا البرنامج التعليمي، اكتشفنا ميزة تفاصيل المقارنة في Aspose.Words لـ .NET. تتيح لك هذه الميزة تحديد مستوى التفاصيل عند مقارنة المستندات. من خلال اختيار مستويات تفصيلية مختلفة، يمكنك إجراء مقارنات تفصيلية على مستوى الحرف أو الكلمة أو الكتلة، وفقًا لمتطلباتك المحددة. يوفر Aspose.Words for .NET إمكانية مرنة وقوية لمقارنة المستندات، مما يجعل من السهل تحديد الاختلافات في المستندات بمستويات مختلفة من التفاصيل.

### الأسئلة الشائعة

#### س: ما هو الغرض من استخدام تفاصيل المقارنة في Aspose.Words لـ .NET؟

ج: دقة المقارنة في Aspose.Words لـ .NET تسمح لك بتحديد مستوى التفاصيل عند مقارنة المستندات. باستخدام هذه الميزة، يمكنك مقارنة المستندات على مستويات مختلفة، مثل مستوى الأحرف أو مستوى الكلمات أو حتى مستوى الكتلة. يوفر كل مستوى من التفاصيل مستوى مختلفًا من التفاصيل في نتائج المقارنة.

#### س: كيف يمكنني استخدام تفاصيل المقارنة في Aspose.Words لـ .NET؟

ج: لاستخدام دقة المقارنة في Aspose.Words لـ .NET، اتبع الخطوات التالية:
1. قم بإعداد بيئة التطوير الخاصة بك باستخدام مكتبة Aspose.Words.
2. قم بإضافة التجميعات الضرورية إلى مشروعك عن طريق الرجوع إلى Aspose.Words.
3.  قم بإنشاء المستندات التي تريد مقارنتها باستخدام`DocumentBuilder` فصل.
4.  قم بتكوين خيارات المقارنة عن طريق إنشاء ملف`CompareOptions` الكائن وتعيين`Granularity` الخاصية إلى المستوى المطلوب (على سبيل المثال،`Granularity.CharLevel` للمقارنة على مستوى الشخصية).
5.  استخدم`Compare`الطريقة على مستند واحد، وتمرير المستند الآخر و`CompareOptions` الكائن كمعلمات. ستقوم هذه الطريقة بمقارنة المستندات بناءً على التفاصيل المحددة وحفظ التغييرات في المستند الأول.

#### س: ما هي المستويات المتوفرة لدقة المقارنة في Aspose.Words لـ .NET؟

ج: يوفر Aspose.Words لـ .NET ثلاثة مستويات من دقة المقارنة:
- `Granularity.CharLevel`: يقارن المستندات على مستوى الأحرف.
- `Granularity.WordLevel`: يقارن المستندات على مستوى الكلمة.
- `Granularity.BlockLevel`: يقارن المستندات على مستوى الكتلة.

#### س: كيف يمكنني تفسير نتائج المقارنة بدقة على مستوى الشخصية؟

ج: من خلال الدقة على مستوى الأحرف، يتم تحليل كل حرف في المستندات المقارنة بحثًا عن الاختلافات. ستظهر نتائج المقارنة التغييرات على مستوى الحرف الفردي، بما في ذلك الإضافات والحذف والتعديلات.