---
title: دقة المقارنة
linktitle: دقة المقارنة
second_title: Aspose.Words لمراجع .NET API
description: تعرف على ميزة مقارنة التفاصيل في Aspose.Words for .NET التي تسمح بمقارنة المستندات حرفًا بحرف ، والإبلاغ عن التغييرات التي تم إجراؤها.
type: docs
weight: 10
url: /ru/net/compare-documents/comparison-granularity/
---
فيما يلي دليل تفصيلي خطوة بخطوة لشرح الكود المصدري C # أدناه ، والذي يستخدم ميزة مقارنة التفاصيل في Aspose.Words for .NET.

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
