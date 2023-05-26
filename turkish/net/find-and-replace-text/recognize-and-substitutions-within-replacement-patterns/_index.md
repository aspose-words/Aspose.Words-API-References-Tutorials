---
title: التعرف والبدائل ضمن أنماط الاستبدال
linktitle: التعرف والبدائل ضمن أنماط الاستبدال
second_title: Aspose.Words لمراجع .NET API
description: تعرف على كيفية استخدام أنماط الاستبدال مع عمليات التعرف والاستبدال في Aspose.Words for .NET لمعالجة مستندات Word.
type: docs
weight: 10
url: /tr/net/find-and-replace-text/recognize-and-substitutions-within-replacement-patterns/
---

في هذه المقالة ، سوف نستكشف الكود المصدري C # أعلاه لفهم كيفية استخدام وظيفة التعرف والبدائل ضمن أنماط الاستبدال في Aspose.Words مكتبة .NET. تساعد هذه الميزة في التعرف على أنماط البحث المعقدة وإجراء عمليات الاستبدال بناءً على المجموعات التي تم التقاطها أثناء معالجة المستند.

## المتطلبات الأساسية

- المعرفة الأساسية للغة C #.
- بيئة تطوير .NET مع تثبيت مكتبة Aspose.Words.

## الخطوة الأولى: إنشاء مستند جديد

 قبل أن نبدأ في استخدام التطابقات والاستبدالات في أنماط الاستبدال ، نحتاج إلى إنشاء مستند جديد باستخدام Aspose.Words for .NET. يمكن القيام بذلك عن طريق إنشاء مثيل لملف`Document` هدف:

```csharp
Document doc = new Document();
```

## الخطوة 2: أدخل النص في المستند

 بمجرد أن نحصل على مستند ، يمكننا إدراج نص باستخدام ملف`DocumentBuilder`هدف. في مثالنا ، نستخدم الامتداد`Write` طريقة لإدخال عبارة "جيسون يعطي بول بعض المال." :

```csharp
DocumentBuilder builder = new DocumentBuilder(doc);
builder.Write("Jason gives money to Paul.");
```

## الخطوة 3: الاعترافات والبدائل في أنماط الاستبدال

 الآن سوف نستخدم ملف`Range.Replace` وظيفة لإجراء بحث عن نص واستبداله باستخدام تعبير عادي للتعرف على أنماط معينة. في مثالنا ، نستخدم التعبير النمطي`([A-z]+) gives money to ([A-z]+)` للتعرف على الجمل التي يعطي فيها شخص ما المال لشخص آخر. نحن نستخدم نمط الاستبدال`$2 takes money from $1` لإجراء الاستبدال عن طريق عكس الأدوار. استخدام`$1` و`$2` يشير إلى المجموعات التي تم التقاطها بواسطة التعبير العادي:

```csharp
Regex regex = new Regex(@"([A-z]+) gives money to ([A-z]+)");

FindReplaceOptions options = new FindReplaceOptions { UseSubstitutions = true };

doc.Range.Replace(regex, @"$2 takes money from $1", options);
```

### مثال على شفرة المصدر للتعرف على البدائل ضمن أنماط الاستبدال باستخدام Aspose.Words for .NET

فيما يلي المثال الكامل لشفرة المصدر لتوضيح استخدام التطابقات والاستبدالات في أنماط الاستبدال باستخدام Aspose.Words for .NET:

```csharp

	Document doc = new Document();
	DocumentBuilder builder = new DocumentBuilder(doc);

	builder.Write("Jason give money to Paul.");

	Regex regex = new Regex(@"([A-z]+) give money to ([A-z]+)");

	FindReplaceOptions options = new FindReplaceOptions { UseSubstitutions = true };

	doc.Range.Replace(regex, @"$2 take money from $1", options);

```

## خاتمة

في هذه المقالة ، استكشفنا الكود المصدري C # لفهم كيفية استخدام ميزة التعرف والاستبدال ضمن أنماط الاستبدال في Aspose.Words for .NET. لقد اتبعنا دليلًا تفصيليًا لإنشاء مستند وإدراج نص وإجراء بحث واستبدال باستخدام التعبيرات العادية وأنماط الاستبدال استنادًا إلى المجموعات الملتقطة ومعالجة المستند.
