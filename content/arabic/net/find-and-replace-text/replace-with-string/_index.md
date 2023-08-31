---
title: استبدل بسلسلة
linktitle: استبدل بسلسلة
second_title: واجهة برمجة تطبيقات معالجة المستندات Aspose.Words
description: تعرف على كيفية استبدال النص بسلسلة في مستند Word بـ Aspose.Words for .NET.
type: docs
weight: 10
url: /ar/net/find-and-replace-text/replace-with-string/
---
في هذه المقالة ، سوف نستكشف الكود المصدري C # أعلاه لفهم كيفية استخدام وظيفة "استبدال السلسلة" في مكتبة Aspose.Words for .NET. تتيح لك هذه الميزة إجراء استبدال النص بناءً على سلسلة أحرف معينة في مستند Word.

## المتطلبات الأساسية

- المعرفة الأساسية للغة C #.
- بيئة تطوير .NET مع تثبيت مكتبة Aspose.Words.

## الخطوة الأولى: إنشاء مستند جديد

 قبل أن نبدأ في استخدام استبدال السلسلة ، نحتاج إلى إنشاء مستند جديد باستخدام Aspose.Words for .NET. يمكن القيام بذلك عن طريق إنشاء مثيل لملف`Document` هدف:

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document doc = new Document();
```

## الخطوة 2: أدخل النص في المستند

 بمجرد أن نحصل على مستند ، يمكننا إدراج نص باستخدام ملف`DocumentBuilder` هدف. في مثالنا ، نستخدم الامتداد`Writeln` طريقة ادخال عبارة "sad crazy bad":

```csharp
DocumentBuilder builder = new DocumentBuilder(doc);
builder.Writeln("sad mad bad");
```

## الخطوة 3: استبدل بسلسلة

 نحن نستخدم ال`Range.Replace`طريقة لاستبدال النص بسلسلة. في مثالنا ، نستبدل كل تكرارات كلمة "sad" بكلمة "bad" باستخدام الامتداد`FindReplaceOptions` الخيار مع`FindReplaceDirection.Forward` اتجاه البحث:

```csharp
doc.Range.Replace("sad", "bad", new FindReplaceOptions(FindReplaceDirection.Forward));
```

## الخطوة 4: حفظ المستند المحرر

 أخيرًا ، نحفظ المستند المعدل في دليل محدد باستخدام امتداد`Save` طريقة:

```csharp
doc.Save(dataDir + "FindAndReplace.ReplaceWithString.docx");
```

### مثال على شفرة المصدر لـ Replace With String باستخدام Aspose.Words for .NET

فيما يلي نموذج التعليمات البرمجية المصدر الكامل لتوضيح استخدام الاستبدال بسلسلة أحرف بـ Aspose.Words for .NET:

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

في هذه المقالة ، استكشفنا الكود المصدري C # لفهم كيفية استخدام وظيفة Replace With String في Aspose.Words for .NET. لقد اتبعنا دليلًا تفصيليًا لإنشاء مستند وإدراج نص واستبداله بسلسلة وحفظ المستند المعدل.

### التعليمات

#### س: ما هي وظيفة "استبدال بسلسلة" في Aspose.Words لـ .NET؟

ج: تسمح لك وظيفة "Replace With String" في Aspose.Words for .NET بإجراء استبدال النص بناءً على سلسلة أحرف معينة في مستند Word. يمكّنك من العثور على تكرارات سلسلة معينة واستبدالها بسلسلة أخرى محددة.

#### س: كيف يمكنني إنشاء مستند جديد باستخدام Aspose.Words for .NET؟

 ج: لإنشاء مستند جديد باستخدام Aspose.Words for .NET ، يمكنك إنشاء نسخة من ملف`Document` هدف. فيما يلي مثال على كود C # لإنشاء مستند جديد:

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document doc = new Document();
```

#### س: كيف يمكنني إدراج نص في مستند باستخدام Aspose.Words for .NET؟

 ج: بمجرد الحصول على مستند ، يمكنك إدراج نص باستخدام ملف`DocumentBuilder` هدف. في Aspose.Words for .NET ، يمكنك استخدام طرق مختلفة لـ`DocumentBuilder` فئة لإدراج نص في مواقع مختلفة. على سبيل المثال ، يمكنك استخدام ملف`Writeln` طريقة لإدراج نص في سطر جديد. هذا مثال:

```csharp
DocumentBuilder builder = new DocumentBuilder(doc);
builder.Writeln("sad mad bad");
```

#### س: كيف يمكنني إجراء استبدال النص بسلسلة في Aspose.Words for .NET؟

 ج: لإجراء استبدال النص بسلسلة في Aspose.Words for .NET ، يمكنك استخدام`Range.Replace` الطريقة وتحديد السلسلة المراد استبدالها والسلسلة المراد استبدالها بها. تؤدي هذه الطريقة مطابقة نصية بسيطة وتحل محل جميع تكرارات السلسلة المحددة. هذا مثال:

```csharp
doc.Range.Replace("sad", "bad", new FindReplaceOptions(FindReplaceDirection.Forward));
```

#### س: هل يمكنني إجراء استبدال نص حساس لحالة الأحرف بوظيفة "استبدال بسلسلة" في Aspose.Words for .NET؟

ج: نعم ، بشكل افتراضي ، تكون وظيفة "استبدال بسلسلة" في Aspose.Words for .NET حساسة لحالة الأحرف. هذا يعني أنه لن يستبدل سوى النص الذي يتطابق تمامًا مع السلسلة المحددة من حيث الحالة. إذا كنت تريد إجراء استبدال غير حساس لحالة الأحرف ، فيمكنك تعديل النص الذي سيتم استبداله وسلسلة الاستبدال لتكون الحالة نفسها ، أو يمكنك استخدام تقنيات أخرى مثل التعبيرات العادية.

#### س: هل يمكنني استبدال تكرارات متعددة لسلسلة في مستند باستخدام وظيفة "استبدال بسلسلة" في Aspose.Words for .NET؟

 ج: نعم ، يمكنك استبدال تكرارات متعددة لسلسلة في مستند باستخدام وظيفة "استبدال بسلسلة" في Aspose.Words for .NET. ال`Range.Replace` سيحل الأسلوب محل جميع تكرارات السلسلة المحددة في محتوى المستند.

#### س: هل هناك أي قيود أو اعتبارات عند استخدام وظيفة "استبدال بسلسلة" في Aspose.Words for .NET؟

ج: عند استخدام وظيفة "Replace With String" في Aspose.Words for .NET ، من المهم أن تكون على دراية بالسياق والتأكد من تطبيق الاستبدال في المكان المقصود فقط. تأكد من أن سلسلة البحث لا تظهر في الأماكن غير المرغوب فيها ، مثل الكلمات الأخرى أو كجزء من تنسيق خاص. بالإضافة إلى ذلك ، ضع في اعتبارك الآثار المترتبة على الأداء عند معالجة الكلمات بمستندات كبيرة أو عمليات استبدال متكررة.

#### س: هل يمكنني استبدال السلاسل بأطوال مختلفة باستخدام وظيفة "استبدال السلسلة" في Aspose.Words for .NET؟

ج: نعم ، يمكنك استبدال السلاسل بأطوال مختلفة باستخدام وظيفة "استبدال السلسلة" في Aspose.Words for .NET. يمكن أن تكون سلسلة الاستبدال بأي طول ، وستحل محل التطابق التام لسلسلة البحث. سيتم ضبط المستند وفقًا لذلك لملاءمة طول السلسلة الجديدة.