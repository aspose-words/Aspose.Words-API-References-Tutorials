---
title: دقة المقارنة في مستند Word
linktitle: دقة المقارنة في مستند Word
second_title: واجهة برمجة تطبيقات معالجة المستندات Aspose.Words
description: تعرف على ميزة مقارنة الدقة في مستند Word في Aspose.Words for .NET التي تتيح مقارنة المستندات حرفًا بحرف ، مع إجراء تغييرات في إعداد التقارير.
type: docs
weight: 10
url: /ar/net/compare-documents/comparison-granularity/
---
فيما يلي دليل تفصيلي خطوة بخطوة لشرح الكود المصدري C # أدناه ، والذي يستخدم ميزة مقارنة التفاصيل في مستند Word في Aspose.Words for .NET.

## الخطوة 1: مقدمة

تتيح لك ميزة مقارنة التفاصيل في Aspose.Words for .NET مقارنة المستندات على مستوى الأحرف. هذا يعني أنه سيتم مقارنة كل حرف وسيتم الإبلاغ عن التغييرات وفقًا لذلك.

## الخطوة الثانية: تهيئة البيئة

قبل أن تبدأ ، تحتاج إلى إعداد بيئة التطوير الخاصة بك للعمل مع Aspose.Words for .NET. تأكد من تثبيت مكتبة Aspose.Words وأن لديك مشروع C # مناسب لتضمين الكود.

## الخطوة 3: إضافة التجميعات المطلوبة

لاستخدام ميزة مقارنة التفاصيل في Aspose.Words for .NET ، تحتاج إلى إضافة التجميعات الضرورية إلى مشروعك. تأكد من أن لديك المراجع المناسبة لـ Aspose. Words في مشروعك.

```csharp
using Aspose.Words;
using Aspose.Words.DocumentBuilder;
```

## الخطوة 4: إنشاء المستندات

في هذه الخطوة ، سننشئ وثيقتين باستخدام فئة DocumentBuilder. سيتم استخدام هذه الوثائق للمقارنة.

```csharp
// قم بإنشاء مستند أ.
DocumentBuilder builderA = new DocumentBuilder(new Document());
builderA.Writeln("This is a simple A word.");

// إنشاء مستند B.
DocumentBuilder builderB = new DocumentBuilder(new Document());
builderB.Writeln("This is simple B words.");
```

## الخطوة 5: تكوين خيارات المقارنة

في هذه الخطوة ، سنقوم بتكوين خيارات المقارنة لتحديد دقة المقارنة. هنا سوف نستخدم دقة على مستوى الحرف.

```csharp
CompareOptions compareOptions = new CompareOptions { Granularity = Granularity.CharLevel };
```

## الخطوة 6: مقارنة المستندات

دعنا الآن نقارن المستندات باستخدام طريقة المقارنة لفئة المستند. سيتم حفظ التغييرات في المستند أ.

```csharp
builderA.Document.Compare(builderB.Document, "author", DateTime.Now, compareOptions);
```

 ال`Compare` يقارن الأسلوب المستند A بالمستند B ويحفظ التغييرات في المستند A. يمكنك تحديد اسم المؤلف وتاريخ المقارنة كمرجع.

## خاتمة

في هذه المقالة ، استكشفنا ميزة مقارنة التفاصيل في Aspose.Words for .NET. تتيح لك هذه الميزة مقارنة المستندات على مستوى الأحرف وتقرير التغييرات. يمكنك استخدام هذه المعرفة لإجراء مقارنات تفصيلية بين المستندات في مشاريعك.

### نموذج لشفرة مصدر للمقارنة باستخدام Aspose.Words for .NET

```csharp
            
DocumentBuilder builderA = new DocumentBuilder(new Document());
DocumentBuilder builderB = new DocumentBuilder(new Document());

builderA.Writeln("This is A simple word");
builderB.Writeln("This is B simple words");

CompareOptions compareOptions = new CompareOptions { Granularity = Granularity.CharLevel };

builderA.Document.Compare(builderB.Document, "author", DateTime.Now, compareOptions);            
        
```

## خاتمة

في هذا البرنامج التعليمي ، استكشفنا ميزة مقارنة الدقة في Aspose.Words for .NET. تتيح لك هذه الميزة تحديد مستوى التفاصيل عند مقارنة المستندات. باختيار مستويات دقة مختلفة ، يمكنك إجراء مقارنات تفصيلية على مستوى الحرف أو الكلمة أو الكتلة ، وفقًا لمتطلباتك الخاصة. يوفر Aspose.Words for .NET قدرة مرنة وقوية لمقارنة المستندات ، مما يجعل من السهل تحديد الاختلافات في المستندات بمستويات متفاوتة من التفصيل.

### التعليمات

#### س: ما هو الغرض من استخدام دقة المقارنة في Aspose.Words for .NET؟

ج: دقة المقارنة في Aspose.Words for .NET تسمح لك بتحديد مستوى التفاصيل عند مقارنة المستندات. باستخدام هذه الميزة ، يمكنك مقارنة المستندات على مستويات مختلفة ، مثل مستوى الحرف أو مستوى الكلمة أو حتى مستوى الكتلة. يوفر كل مستوى من مستويات الدقة مستوى مختلفًا من التفاصيل في نتائج المقارنة.

#### س: كيف يمكنني استخدام دقة المقارنة في Aspose.Words لـ .NET؟

ج: لاستخدام دقة المقارنة في Aspose.Words لـ .NET ، اتبع الخطوات التالية:
1. قم بإعداد بيئة التطوير الخاصة بك باستخدام مكتبة Aspose.Words.
2. أضف التجميعات اللازمة إلى مشروعك بالرجوع إلى Aspose.Words.
3.  قم بإنشاء المستندات التي تريد مقارنتها باستخدام`DocumentBuilder` فصل.
4.  قم بتكوين خيارات المقارنة عن طريق إنشاء ملف`CompareOptions` الكائن ووضع`Granularity` إلى المستوى المطلوب (على سبيل المثال ،`Granularity.CharLevel` للمقارنة على مستوى الشخصية).
5.  استخدم ال`Compare` على مستند واحد ، ويمرر المستند الآخر و`CompareOptions` الكائن كمعلمات. ستعمل هذه الطريقة على مقارنة المستندات بناءً على الدقة المحددة وحفظ التغييرات في المستند الأول.

#### س: ما المستويات المتاحة من دقة المقارنة في Aspose.Words لـ .NET؟

ج: يوفر Aspose.Words for .NET ثلاثة مستويات من دقة المقارنة:
- `Granularity.CharLevel`: يقارن المستندات على مستوى الحرف.
- `Granularity.WordLevel`: يقارن المستندات على مستوى الكلمة.
- `Granularity.BlockLevel`: يقارن المستندات على مستوى الكتلة.

#### س: كيف يمكنني تفسير نتائج المقارنة بدقة على مستوى الأحرف؟

ج: مع الدقة على مستوى الأحرف ، يتم تحليل كل حرف في المستندات المقارنة بحثًا عن الاختلافات. ستظهر نتائج المقارنة التغييرات على مستوى الشخصية الفردية ، بما في ذلك الإضافات والحذف والتعديلات.