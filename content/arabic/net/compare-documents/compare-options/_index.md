---
title: قارن الخيارات في مستند Word
linktitle: قارن الخيارات في مستند Word
second_title: واجهة برمجة تطبيقات معالجة المستندات Aspose.Words
description: دليل خطوة بخطوة لشرح كود مصدر C # لخيارات المقارنة في ميزة مستند Word باستخدام Aspose.Words for .NET.
type: docs
weight: 10
url: /ar/net/compare-documents/compare-options/
---
في هذا البرنامج التعليمي ، سنشرح كيفية استخدام ميزة المقارنة في مستند Word مع Aspose.Words for .NET. اتبع الخطوات أدناه لفهم شفرة المصدر وتطبيق التغييرات.

## الخطوة 1: مقارنة المستندات بالخيارات المخصصة

 للبدء ، قم بتحميل وثيقتين للمقارنة. في هذا المثال ، سوف نستخدم الامتداد`Clone()` طريقة لإنشاء نسخة من المستند الأصلي. إليك الطريقة:

```csharp
Document docA = new Document(MyDir + "Document.docx");
Document docB = docA.Clone();
```

## الخطوة 2: تكوين خيارات المقارنة

 سنقوم الآن بتكوين خيارات المقارنة من خلال إنشاء ملف`CompareOptions` الكائن وتعيين الخصائص المختلفة حسب الحاجة. إليك الطريقة:

```csharp
CompareOptions options = new CompareOptions
{
IgnoreFormatting = true,
IgnoreHeadersAndFooters = true,
IgnoreCaseChanges = true,
IgnoreTables = true,
IgnoreFields = true,
IgnoreComments = true,
IgnoreTextboxes=true,
IgnoreFootnotes=true
};
```

## الخطوة 3: مقارنة المستندات بالخيارات المخصصة

 سنستخدم الآن ملف`Compare()` طريقة تمرير الخيارات المخصصة لمقارنة الوثيقتين. ستحدد هذه الطريقة التغييرات في المستند الأصلي. إليك الطريقة:

```csharp
// قارن المستندات بالخيارات المخصصة
docA.Compare(docB, "user", DateTime.Now, options);

// تحقق مما إذا كانت المستندات متساوية
Console.WriteLine(docA.Revisions.Count == 0 ? "Documents are equal": "Documents are not equal");
```

### مثال على كود المصدر لمقارنة الخيارات باستخدام Aspose.Words for .NET

فيما يلي رمز المصدر الكامل لميزة مقارنة الخيارات مع Aspose.Words for .NET:

```csharp

	Document docA = new Document(MyDir + "Document.docx");
	Document docB = docA.Clone();

	CompareOptions options = new CompareOptions
	{
		IgnoreFormatting = true,
		IgnoreHeadersAndFooters = true,
		IgnoreCaseChanges = true,
		IgnoreTables = true,
		IgnoreFields = true,
		IgnoreComments = true,
		IgnoreTextboxes = true,
		IgnoreFootnotes = true
	};

	docA.Compare(docB, "user", DateTime.Now, options);

	Console.WriteLine(docA.Revisions.Count == 0 ? "Documents are equal" : "Documents are not equal");

```

باستخدام هذا الرمز ، يمكنك مقارنة مستندين باستخدام خيارات مخصصة لتجاهل عناصر محددة عند المقارنة مع Aspose.Words for .NET.

## خاتمة

في هذا البرنامج التعليمي ، تعلمنا كيفية استخدام خيارات المقارنة في Aspose.Words for .NET لتخصيص عملية المقارنة عند مقارنة مستندين. من خلال تحديد خيارات مختلفة ، يمكنك تجاهل عناصر محددة وجعل عملية المقارنة أكثر مرونة. تتيح لك هذه الميزة إمكانية التحكم بشكل أكبر في عملية المقارنة ، وتكييفها وفقًا لمتطلباتك الخاصة. يوفر Aspose.Words for .NET إمكانات قوية لمقارنة المستندات ، مما يجعل من السهل تحديد الاختلافات بين المستندات مع تجاهل بعض العناصر حسب الحاجة.

### التعليمات

#### س: ما هو الغرض من استخدام خيارات المقارنة في Aspose.Words for .NET؟

ج: تتيح لك مقارنة الخيارات في Aspose.Words for .NET تخصيص عملية المقارنة عند مقارنة مستندين. باستخدام هذه الخيارات ، يمكنك تحديد العناصر التي يجب تجاهلها أثناء المقارنة ، مثل تغييرات التنسيق والرؤوس والتذييلات والجداول والحقول والتعليقات ومربعات النص والحواشي السفلية.

#### س: كيف يمكنني استخدام خيارات المقارنة في Aspose.Words for .NET؟

ج: لاستخدام خيارات المقارنة في Aspose.Words for .NET ، اتبع الخطوات التالية:
1. قم بتحميل المستندين اللذين تريد مقارنتهما في كائنات مستند منفصلة.
2.  استخدم ال`Clone()` طريقة لإنشاء نسخة من المستند الأصلي.
3.  إنشاء`CompareOptions` الكائن وتعيين خصائصه لتخصيص عملية المقارنة. يمكنك تحديد العناصر التي يجب تجاهلها أثناء المقارنة.
4.  استخدم ال`Compare()` الطريقة على أحد المستندات وتمرير المستند الآخر و`CompareOptions` الكائن كمعلمات. ستقوم هذه الطريقة بمقارنة المستندات بناءً على الخيارات المحددة وتمييز التغييرات في المستند الأصلي.
5.  افحص ال`Revisions` ملكية المستند الأصلي. إذا كان العدد صفرًا ، فهذا يعني أن المستندات متطابقة ، مع مراعاة الخيارات المحددة.

#### س: ما هي الخيارات الشائعة المتوفرة في CompareOptions؟

ج: تشمل الخيارات الشائعة المتوفرة في CompareOptions ما يلي:
- `IgnoreFormatting`: يتجاهل التغييرات في التنسيق.
- `IgnoreHeadersAndFooters`: يتجاهل التغييرات في الرؤوس والتذييلات.
- `IgnoreCaseChanges`: يتجاهل تغييرات حالة الأحرف (أحرف كبيرة / صغيرة).
- `IgnoreTables`: يتجاهل التغييرات في الجداول.
- `IgnoreFields`: يتجاهل التغييرات في المجالات.
- `IgnoreComments`: يتجاهل التغييرات في التعليقات.
- `IgnoreTextboxes`يتجاهل التغييرات في مربعات النص.
- `IgnoreFootnotes`: يتجاهل التغييرات في الحواشي.

#### س: هل يمكنني استخدام خيارات مخصصة لعناصر محددة أثناء مقارنة المستندات؟

 ج: نعم ، يمكنك استخدام خيارات مخصصة لعناصر محددة أثناء مقارنة المستندات. من خلال تحديد خصائص ملف`CompareOptions` وفقًا لذلك ، يمكنك اختيار العناصر التي يجب تجاهلها والعناصر التي يجب مراعاتها أثناء المقارنة.