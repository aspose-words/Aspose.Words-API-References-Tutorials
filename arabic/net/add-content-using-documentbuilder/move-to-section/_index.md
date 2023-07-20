---
title: الانتقال إلى قسم في مستند Word
linktitle: الانتقال إلى قسم في مستند Word
second_title: واجهة برمجة تطبيقات معالجة المستندات Aspose.Words
description: دليل خطوة بخطوة لاستخدام ميزة Move To Section في مستند Word في Aspose.Words for .NET يتعامل مع الأقسام والفقرات في مستندات Word.
type: docs
weight: 10
url: /ar/net/add-content-using-documentbuilder/move-to-section/
---
في هذا المثال ، سنرشدك إلى كيفية استخدام ميزة Move To Section في مستند Word في Aspose.Words for .NET خطوة بخطوة باستخدام كود المصدر C # المقدم. تتيح لك هذه الميزة التنقل والتعامل مع الأقسام المختلفة داخل مستند Word. اتبع الخطوات أدناه لدمج هذه الوظيفة في تطبيقك.

## الخطوة 1: قم بإنشاء مستند جديد وإضافة قسم

أولاً ، نحتاج إلى إنشاء مستند جديد وإضافة قسم إليه. استخدم الكود التالي لإنجاز هذه الخطوة:

```csharp
Document doc = new Document();
doc.AppendChild(new Section(doc));
```

ينشئ هذا الرمز مستندًا فارغًا جديدًا ويضيف قسمًا إلى هذا المستند.

## الخطوة 2: انقل DocumentBuilder إلى القسم الثاني وأضف نصًا

بعد ذلك ، نحتاج إلى نقل DocumentBuilder إلى القسم الثاني من المستند وإضافة بعض النص هناك. استخدم الكود التالي لإجراء هذه الخطوة:

```csharp
DocumentBuilder builder = new DocumentBuilder(doc);
builder. MoveToSection(1);
builder.Writeln("Text added to the 2nd section.");
```

ينشئ هذا الرمز DocumentBuilder من المستند الموجود ، ثم ينقل المؤشر من DocumentBuilder إلى القسم الثاني من المستند. أخيرًا ، يضيف النص المحدد إلى هذا القسم.

## الخطوة 3: تحميل مستند بالفقرات الموجودة

إذا كنت تريد العمل مع مستند موجود يحتوي على فقرات ، فيمكنك تحميل هذا المستند باستخدام الكود التالي:

```csharp
doc = new Document(MyDir + "Paragraphs.docx");
ParagraphCollection paragraphs = doc.FirstSection.Body.Paragraphs;
Assert.AreEqual(22, paragraphs.Count);
```

يقوم هذا الرمز بتحميل المستند المحدد (استبدل "MyDir +" Paragraphs.docx"" بالمسار الفعلي إلى المستند الخاص بك) والوصول إلى مجموعة الفقرات من القسم الأول من المستند. الخط`Assert.AreEqual(22, paragraphs.Count);` يتحقق من أن المستند يحتوي على 22 فقرة.

## الخطوة 4: إنشاء DocumentBuilder لمستند

يمكنك إنشاء مؤشر DocumentBuilder على فقرة معينة باستخدام المؤشرات الموضعية.

```csharp
builder = new DocumentBuilder(doc);
Assert.AreEqual(0, paragraphs.IndexOf(builder.CurrentParagraph));
```

## الخطوة 5: حرك المؤشر إلى فقرة معينة


يمكنك تحريك مؤشر DocumentBuilder إلى فقرة معينة باستخدام المؤشرات الموضعية. هيريس كيفية القيام بذلك:

```csharp
builder. MoveToParagraph(2, 10);
Assert.AreEqual(2, paragraphs.IndexOf(builder.CurrentParagraph));
builder.Writeln("This is a new third paragraph.");
Assert.AreEqual(3, paragraphs.IndexOf(builder.CurrentParagraph));
```

يقوم هذا الرمز بنقل مؤشر DocumentBuilder إلى الفقرة الثالثة من القسم الثاني (الفقرة في الفهرس 2) وإلى الموضع 10. ثم يضيف فقرة جديدة مع بعض النص ويتحقق من وضع المؤشر بشكل جيد على هذه الفقرة الجديدة.

### مثال على شفرة المصدر لـ Move To Move To Section باستخدام Aspose.Words for .NET

```csharp
Document doc = new Document();
doc.AppendChild(new Section(doc));

// انقل DocumentBuilder إلى القسم الثاني وأضف نصًا.
DocumentBuilder builder = new DocumentBuilder(doc);
builder.MoveToSection(1);
builder.Writeln("Text added to the 2nd section.");

// إنشاء وثيقة مع فقرات.
doc = new Document(MyDir + "Paragraphs.docx");
ParagraphCollection paragraphs = doc.FirstSection.Body.Paragraphs;
Assert.AreEqual(22, paragraphs.Count);

// عندما نقوم بإنشاء DocumentBuilder لمستند ، يكون المؤشر في بداية المستند افتراضيًا ،
// وسيتم إضافة أي محتوى مضاف بواسطة DocumentBuilder إلى المستند.
builder = new DocumentBuilder(doc);
Assert.AreEqual(0, paragraphs.IndexOf(builder.CurrentParagraph));

//يمكنك تحريك المؤشر إلى أي موضع في الفقرة.
builder.MoveToParagraph(2, 10);
Assert.AreEqual(2, paragraphs.IndexOf(builder.CurrentParagraph));
builder.Writeln("This is a new third paragraph. ");
Assert.AreEqual(3, paragraphs.IndexOf(builder.CurrentParagraph));
```

هذا كل شئ ! لقد فهمت الآن كيفية استخدام وظيفة الانتقال إلى قسم Aspose.Words for .NET باستخدام كود المصدر المقدم. يمكنك الآن دمج هذه الوظيفة في التطبيق الخاص بك ومعالجة أقسام وفقرات مستندات Word بشكل ديناميكي.

## خاتمة

في هذا المثال ، استكشفنا ميزة Move To Section في Aspose.Words for .NET. لقد تعلمنا كيفية إنشاء مستند جديد وإضافة أقسام إليه واستخدام فئة DocumentBuilder للتنقل إلى أقسام وفقرات محددة داخل مستند Word. توفر هذه الميزة للمطورين أدوات قوية للتعامل مع محتوى وهيكل مستندات Word برمجيًا باستخدام Aspose.Words for .NET.

### الأسئلة الشائعة للانتقال إلى قسم في مستند Word

#### س: ما هو الغرض من ميزة "الانتقال إلى القسم" في Aspose.Words for .NET؟

ج: تسمح ميزة Move To Section في Aspose.Words for .NET للمطورين بالانتقال إلى الأقسام المختلفة ومعالجتها داخل مستند Word برمجيًا. يوفر القدرة على إدراج المحتوى أو تعديله أو حذفه في أقسام معينة من المستند.

#### س: كيف يمكنني نقل DocumentBuilder إلى قسم معين في مستند Word؟

ج: لنقل DocumentBuilder إلى قسم معين في مستند Word ، يمكنك استخدام طريقة MoveToSection لفئة DocumentBuilder. تأخذ هذه الطريقة فهرس القسم الهدف كمعامل وتضع المؤشر في بداية هذا القسم.

#### س: هل يمكنني إضافة أو تعديل المحتوى بعد الانتقال إلى قسم معين باستخدام ميزة النقل إلى القسم؟

ج: نعم ، بمجرد وضع DocumentBuilder في القسم المطلوب باستخدام MoveToSection ، يمكنك استخدام طرق مختلفة لفئة DocumentBuilder ، مثل Writeln أو Write أو InsertHtml ، لإضافة محتوى ذلك القسم أو تعديله.

#### س: كيف يمكنني العمل مع فقرات موجودة في مستند باستخدام ميزة "نقل إلى قسم"؟

ج: يمكنك تحميل مستند موجود يحتوي على فقرات باستخدام مُنشئ المستند ثم الوصول إلى مجموعة الفقرات من القسم المطلوب باستخدام خاصية FirstSection.Body.Paragraphs.

#### س: هل يمكنني نقل مؤشر DocumentBuilder إلى فقرة معينة داخل قسم باستخدام ميزة Move To Section؟

ج: نعم ، يمكنك تحريك مؤشر DocumentBuilder إلى فقرة معينة داخل قسم باستخدام طريقة MoveToParagraph. تأخذ هذه الطريقة مؤشرات الفقرة الهدف وموضع الحرف (الإزاحة) داخل الفقرة كمعلمات.