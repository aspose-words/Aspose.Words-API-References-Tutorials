---
title: استبدال بسلسلة
linktitle: استبدال بسلسلة
second_title: Aspose.Words واجهة برمجة تطبيقات معالجة المستندات
description: تعرف على كيفية استبدال النص بسلسلة في مستند Word باستخدام Aspose.Words لـ .NET.
type: docs
weight: 10
url: /ar/net/find-and-replace-text/replace-with-string/
---
في هذه المقالة، سنستكشف التعليمات البرمجية المصدر لـ C# أعلاه لفهم كيفية استخدام وظيفة Replace With String في مكتبة Aspose.Words for .NET. تتيح لك هذه الميزة إجراء استبدال النص بناءً على سلسلة أحرف معينة في مستند Word.

## المتطلبات الأساسية

- المعرفة الأساسية بلغة C#.
- بيئة تطوير .NET مع تثبيت مكتبة Aspose.Words.

## الخطوة 1: إنشاء مستند جديد

 قبل أن نبدأ في استخدام استبدال السلسلة، نحتاج إلى إنشاء مستند جديد باستخدام Aspose.Words لـ .NET. يمكن القيام بذلك عن طريق إنشاء مثيل لـ`Document` هدف:

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document doc = new Document();
```

## الخطوة 2: أدخل النص في المستند

 بمجرد حصولنا على مستند، يمكننا إدراج نص باستخدام ملف`DocumentBuilder` هدف. في مثالنا، نستخدم`Writeln` طريقة إدخال عبارة "حزين مجنون سيء":

```csharp
DocumentBuilder builder = new DocumentBuilder(doc);
builder.Writeln("sad mad bad");
```

## الخطوة 3: استبدل بسلسلة

 نحن نستخدم ال`Range.Replace`طريقة استبدال النص بسلسلة. في مثالنا، نستبدل كل تكرارات كلمة "sad" بكلمة "bad" باستخدام`FindReplaceOptions` الخيار مع`FindReplaceDirection.Forward` اتجاه البحث:

```csharp
doc.Range.Replace("sad", "bad", new FindReplaceOptions(FindReplaceDirection.Forward));
```

## الخطوة 4: حفظ المستند المحرر

وأخيرًا، نقوم بحفظ المستند المعدل في دليل محدد باستخدام الملف`Save` طريقة:

```csharp
doc.Save(dataDir + "FindAndReplace.ReplaceWithString.docx");
```

### مثال على التعليمات البرمجية المصدر لـ Replace With String باستخدام Aspose.Words لـ .NET

فيما يلي نموذج التعليمات البرمجية المصدر الكامل لتوضيح استخدام الاستبدال بسلسلة أحرف باستخدام Aspose.Words لـ .NET:

```csharp

	// المسار إلى دليل المستندات.
	string dataDir = "YOUR DOCUMENT DIRECTORY";
	Document doc = new Document();
	DocumentBuilder builder = new DocumentBuilder(doc);
	
	builder.Writeln("sad mad bad");

	doc.Range.Replace("sad", "bad", new FindReplaceOptions(FindReplaceDirection.Forward));

	doc.Save(dataDir + "FindAndReplace.ReplaceWithString.docx");
  
```

## خاتمة

في هذه المقالة، قمنا باستكشاف التعليمات البرمجية المصدر لـ C# لفهم كيفية استخدام وظيفة Replace With String في Aspose.Words لـ .NET. لقد اتبعنا دليلاً خطوة بخطوة لإنشاء مستند وإدراج نص واستبداله بسلسلة وحفظ المستند المعدل.

### الأسئلة الشائعة

#### س: ما هي وظيفة "الاستبدال بسلسلة" في Aspose.Words لـ .NET؟

ج: تتيح لك وظيفة "استبدال بسلسلة" في Aspose.Words لـ .NET إجراء استبدال النص بناءً على سلسلة أحرف معينة في مستند Word. يمكّنك من العثور على تكرارات سلسلة معينة واستبدالها بسلسلة محددة أخرى.

#### س: كيف يمكنني إنشاء مستند جديد باستخدام Aspose.Words لـ .NET؟

 ج: لإنشاء مستند جديد باستخدام Aspose.Words لـ .NET، يمكنك إنشاء مثيل`Document` هدف. فيما يلي مثال على كود C# لإنشاء مستند جديد:

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document doc = new Document();
```

#### س: كيف يمكنني إدراج نص في مستند باستخدام Aspose.Words for .NET؟

 ج: بمجرد حصولك على مستند، يمكنك إدراج نص باستخدام ملف`DocumentBuilder` هدف. في Aspose.Words for .NET، يمكنك استخدام طرق مختلفة لـ`DocumentBuilder` فئة لإدراج النص في مواقع مختلفة. على سبيل المثال، يمكنك استخدام`Writeln` طريقة إدراج نص في سطر جديد هنا مثال:

```csharp
DocumentBuilder builder = new DocumentBuilder(doc);
builder.Writeln("sad mad bad");
```

#### س: كيف يمكنني إجراء استبدال النص بسلسلة في Aspose.Words لـ .NET؟

 ج: لإجراء استبدال النص بسلسلة في Aspose.Words لـ .NET، يمكنك استخدام`Range.Replace` الطريقة وحدد السلسلة التي سيتم استبدالها والسلسلة التي سيتم استبدالها بها. تقوم هذه الطريقة بإجراء مطابقة نصية بسيطة واستبدال كافة تكرارات السلسلة المحددة. هنا مثال:

```csharp
doc.Range.Replace("sad", "bad", new FindReplaceOptions(FindReplaceDirection.Forward));
```

#### س: هل يمكنني إجراء استبدال نص حساس لحالة الأحرف باستخدام وظيفة "استبدال بسلسلة" في Aspose.Words لـ .NET؟

ج: نعم، بشكل افتراضي، تكون وظيفة "استبدال بسلسلة" في Aspose.Words لـ .NET حساسة لحالة الأحرف. وهذا يعني أنه سيستبدل فقط النص الذي يتطابق تمامًا مع السلسلة المحددة من حيث الحالة. إذا كنت تريد إجراء استبدال غير حساس لحالة الأحرف، فيمكنك تعديل النص المراد استبداله وسلسلة الاستبدال بحيث تحتوي على نفس حالة الأحرف، أو يمكنك استخدام تقنيات أخرى مثل التعبيرات العادية.

#### س: هل يمكنني استبدال تكرارات متعددة لسلسلة في مستند باستخدام وظيفة "استبدال بسلسلة" في Aspose.Words لـ .NET؟

 ج: نعم، يمكنك استبدال تكرارات متعددة لسلسلة في مستند باستخدام وظيفة "استبدال بسلسلة" في Aspose.Words لـ .NET. ال`Range.Replace` ستستبدل الطريقة جميع تكرارات السلسلة المحددة في محتوى المستند.

#### س: هل هناك أي قيود أو اعتبارات عند استخدام وظيفة "استبدال بسلسلة" في Aspose.Words لـ .NET؟

ج: عند استخدام وظيفة "Replace With String" في Aspose.Words لـ .NET، من المهم أن تكون على دراية بالسياق وتتأكد من تطبيق الاستبدال فقط في المكان المقصود. تأكد من عدم ظهور سلسلة البحث في أماكن غير مرغوب فيها، مثل الكلمات الأخرى أو كجزء من تنسيق خاص. بالإضافة إلى ذلك، ضع في اعتبارك الآثار المترتبة على الأداء عند معالجة الكلمات باستخدام مستندات كبيرة أو عمليات استبدال متكررة.

#### س: هل يمكنني استبدال سلاسل ذات أطوال مختلفة باستخدام وظيفة "استبدال بسلسلة" في Aspose.Words لـ .NET؟

ج: نعم، يمكنك استبدال سلاسل ذات أطوال مختلفة باستخدام وظيفة "Replace With String" في Aspose.Words لـ .NET. يمكن أن تكون سلسلة الاستبدال بأي طول، وسوف تحل محل المطابقة التامة لسلسلة البحث. سيتم ضبط المستند وفقًا لذلك لاستيعاب طول السلسلة الجديد.